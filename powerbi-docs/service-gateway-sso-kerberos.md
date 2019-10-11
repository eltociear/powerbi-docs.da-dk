---
title: Konfigurer SSO – Kerberos
description: Konfigurer din gateway med Kerberos for at aktivere SSO fra Power BI til datakilder i det lokale miljø
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 0fb52262790c6c1935d8152f043f726a9471817d
ms.sourcegitcommit: 9bf3cdcf5d8b8dd12aa1339b8910fcbc40f4cbe4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/05/2019
ms.locfileid: "71968988"
---
# <a name="configure-kerberos-based-sso-from-power-bi-service-to-on-premises-data-sources"></a>Konfigurer Kerberos-baseret SSO fra Power BI-tjenesten til datakilder i det lokale miljø

Brug [Begrænset Kerberos-delegering](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) for at muliggøre en problemfri SSO-forbindelse. Aktivering af SSO gør det nemt for Power BI-rapporter og -dashboards at opdatere data fra kilder i det lokale miljø, samtidig med at de tilladelser på brugerniveau, der er konfigureret for disse kilder, overholdes.

Der skal være konfigureret flere elementer, hvis begrænset Kerberos-delegering skal fungere korrekt, herunder _tjenestens hovednavn_ (SPN) og delegeringsindstillinger i tjenestekonti.

### <a name="prerequisite-1-install-and-configure-the-microsoft-on-premises-data-gateway"></a>Forudsætning 1: Installér og konfigurer Microsoft-datagatewayen i det lokale miljø

Datagatewayen i det lokale miljø understøtter en direkte opgradering samt _overtagelse af indstillinger_ for eksisterende gateways.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>Forudsætning 2: Kør gatewayens Windows-tjeneste som en domænekonto.

I en standardinstallation kører gatewayen som en tjenestekonto på en lokal computer (specifikt _NT-tjeneste\PBIEgwService_) som vist på følgende billede:

![Skærmbillede af tjenestekonto](media/service-gateway-sso-kerberos/service-account.png)

Hvis du vil aktivere begrænset Kerberos-delegering, skal gatewayen køre som en domænekonto, medmindre din instans af Azure Active Directory (Azure AD) allerede er synkroniseret med din lokale instans af Active Directory (ved hjælp af Azure AD DirSync/Connect). Hvis du vil skifte til en domænekonto, skal du se [Skift gatewaytjenestekonto](/data-integration/gateway/service-gateway-service-account).

> [!NOTE]
> Hvis Azure AD Connect er konfigureret, og brugerkonti er synkroniserede, behøver gatewaytjenesten ikke at udføre lokale Azure AD-opslag på kørselstidspunktet. I stedet kan du blot bruge den lokale tjeneste-SID for gatewaytjenesten til at fuldføre al påkrævet konfiguration i Azure Active Directory. De konfigurationstrin for begrænset Kerberos-delegering, der er beskrevet i denne artikel, er de samme konfigurationstrin som dem, der benyttes i Azure Active Directory-konteksten. De anvendes ganske enkelt på gatewayens computerobjekt (identificeret af det lokale tjeneste-SID) i Azure AD i stedet for domænekontoen.

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>Forudsætning 3: Du skal have rettigheder som domæneadministrator til at konfigurere indstillinger for SPN'er (SetSPN) og Kerberos-begrænset delegering

Det anbefales ikke, at en domæneadministrator midlertidigt eller permanent giver andre rettigheder til at konfigurere SPN'er og Kerberos-delegering uden at kræve, at den pågældende person har rettigheder som domæneadministrator. I følgende afsnit beskrives de anbefalede konfigurationstrin mere detaljeret.

## <a name="configure-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Konfigurer begrænset Kerberos-delegering for gatewayen og datakilden

Som domæneadministrator kan du konfigurere et SPN og delegeringsindstillinger for domænekontoen (hvis det er relevant) for gatewaytjenesten.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>Konfigurer et SPN til gatewaytjenestekontoen

Først skal du undersøge, om der allerede er oprettet et SPN for den domænekonto, der bruges som gatewaytjenestenkonto:

1. Start **Active Directory-brugere og -computere** som domæneadministrator.

2. Højreklik på domænet, vælg **Find**, og angiv navnet på gatewaytjenestekontoen.

3. Højreklik i søgeresultaterne på gatewaytjenestekontoen, og vælg **Egenskaber**.

4. Hvis fanen **Delegering** vises i dialogboksen **Egenskaber**, var der allerede oprettet et SPN, og du kan gå videre til [Forberedelse af ressourcebaseret eller begrænset Kerberos-standarddelegering](#decide-on-resource-based-or-standard-kerberos-constrained-delegation).

    Hvis fanen **Delegering** ikke er synlig i dialogboksen **Egenskaber**, kan du manuelt oprette et SPN for den pågældende konto for at aktivere fanen. Brug det [setspn-værktøj](https://technet.microsoft.com/library/cc731241.aspx), der følger med Windows. Du skal have rettigheder som domæneadministrator for at oprette et SPN.

    Forestil dig f.eks., at gatewaytjenestekontoen er **Contoso\GatewaySvc**, og at navnet på computeren, hvor gatewaytjenesten kører, kaldes **MyGatewayMachine**. Hvis du vil angive SPN'et for gatewaytjenestekontoen, skal du køre følgende kommando:

    ![Billede af angivet kommando for SPN](media/service-gateway-sso-kerberos/set-spn.png)

    Du kan også angive SPN'et ved hjælp af MMC-snap-in'en Active Directory-brugere og -computere (Microsoft Management Console).

### <a name="decide-on-resource-based-or-standard-kerberos-constrained-delegation"></a>Forberedelse af ressourcebaseret eller begrænset Kerberos-standarddelegering

Indstillinger for delegering kan være konfigureret for _enten_ ressourcebaseret begrænset Kerberos-delegering eller begrænset Kerberos-standarddelegering. Brug ressourcebaseret delegering, hvis din datakilde tilhører et andet domæne end din gateway, men vær opmærksom på, at denne tilgang kræver Windows Server 2012 eller nyere. Se [oversigtssiden for begrænset Kerberos-delegering](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) for at få flere oplysninger om forskellene mellem de to fremgangsmåder for delegering.

 Når du har besluttet dig for, hvilken tilgang du vil bruge, skal du _enten_ fortsætte med afsnittet [Konfigurer gatewaytjenestekontoen for begrænset Kerberos-standarddelegering](#configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation) _eller_ [Konfigurer gatewaytjenestekontoen for ressourcebaseret begrænset Kerberos-delegering](#configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation). Undlad at fuldføre begge underafsnit.

## <a name="configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation"></a>Konfigurer gatewaytjenestekontoen for begrænset Kerberos-standarddelegering

> [!NOTE]
> Gennemfør trinnene i dette afsnit, hvis du vil aktivere begrænset Kerberos-standarddelegering. Hvis du vil aktivere ressourcebaseret begrænset Kerberos-delegering, skal du fuldføre trinnene i underafsnittet [Konfigurer gatewaytjenestekontoen for ressourcebaseret begrænset Kerberos-delegering](#configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation).

Nu angiver vi delegeringsindstillingerne for gatewaytjenestekontoen. Der er mange værktøjer, som kan bruges til at udføre disse trin. Her bruger vi Active Directory-brugere og -computere, der er et MMC-snap-in (Microsoft Management Console), som du kan bruge til at administrere og publicere oplysninger i mappen. Det findes som standard i domænecontrollere, men du kan også aktivere det via konfiguration af Windows-funktioner på andre computere.

Vi skal konfigurere begrænset Kerberos-delegering med protokoloverførsel. Med begrænset delegering skal du være eksplicit med, hvilke tjenester du vil tillade, at gatewayen præsenterer delegerede legitimationsoplysninger for. Det er f.eks. kun SQL Server- eller SAP HANA-serveren, der accepterer delegeringskald fra gatewaytjenestekontoen.

I dette afsnit forudsættes det, at du allerede har konfigureret SPN'er for de underliggende datakilder (f.eks. SQL Server, SAP HANA, SAP BW, Teradata og Spark). Du kan få mere at vide om, hvordan du konfigurerer disse datakildeserveres SPN'er i den tekniske dokumentation til den respektive databaseserver. Du kan også se under overskriften *Hvilken SPN kræver dit program?* i blogindlægget [Min tjekliste til Kerberos](https://techcommunity.microsoft.com/t5/SQL-Server-Support/My-Kerberos-Checklist-8230/ba-p/316160).

I følgende trin antager vi, at vi har et lokalt miljø med to computere i det samme domæne: en gatewaycomputer og en databaseserver, der kører SQL Server, og som allerede er blevet konfigureret til Kerberos-baseret SSO. Trinnene kan benyttes for en af de andre understøttede datakilder, så længe datakilden allerede er konfigureret til Kerberos-baseret enkeltlogon. Af hensyn til dette eksempel antager vi også, at vi har følgende indstillinger og navne:

* Active Directory-domæne (Netbios): **Contoso**
* Gatewaymaskinens navn: **MyGatewayMachine**
* Gatewaytjenestekonto: **Contoso\GatewaySvc**
* Navn på computer med SQL Server-datakilde: **TestSQLServer**
* SQL Server-datakildens tjenestekonto: **Contoso\SQLService**

Her kan du se, hvordan du konfigurerer delegeringsindstillingerne:

1. Åbn **Active Directory-brugere og -computere** med rettigheder som domæneadministrator.

2. Højreklik på gatewaytjenestekontoen (**Contoso\GatewaySvc**), og vælg **Egenskaber**.

3. Vælg fanen **Delegering**.

4. Vælg **Hav kun tillid til denne computer i forbindelse med delegering til de angivne tjenester** > **Brug en vilkårlig godkendelsesprotokol**.

5. Under **Tjenester, som denne konto kan give delegerede legitimationsoplysninger** skal du vælge **Tilføj**.

6. I den nye dialogboks skal du vælge **Brugere eller computere**.

7. Angiv tjenestekontoen for datakilden; en SQL Server-datakilde kan f.eks. have en tjenestekonto som **Contoso\SQLService**. Der skal allerede være angivet et korrekt SPN for datakilden på denne konto. Når kontoen er tilføjet, skal du vælge **OK**.

8. Vælg det hovednavn for tjenesten (SPN), du har oprettet for databaseserveren. I dette eksempel begynder SPN med **MSSQLSvc**. Hvis du har tilføjet både det fulde domænenavn (FQDN) og NetBIOS- SPN til din databasetjeneste, vælges begge dele. Du kan muligvis kun se ét.

9. Vælg **OK**. Du bør nu kunne se SPN'et på listen over tjenester, som gatewaytjenestekontoen kan give uddelegerede legitimationsoplysninger til.

    ![Skærmbillede af dialogboksen Egenskaber for gatewayconnector](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

Nu skal du gå til [Tildel gatewaytjenestekontoen rettigheder til lokale politikker på gatewaymaskinen](#grant-the-gateway-service-account-local-policy-rights-on-the-gateway-machine) for at fortsætte med konfigurationsprocessen.

## <a name="configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation"></a>Konfigurer gatewaytjenestekontoen for ressourcebaseret begrænset Kerberos-delegering

> [!NOTE]
> Gennemfør trinnene i dette afsnit, hvis du vil aktivere ressourcebaseret begrænset Kerberos-delegering. Hvis du vil aktivere begrænset Kerberos-standarddelegering, skal du fuldføre trinnene i underafsnittet [Konfigurer gatewaytjenestekontoen for begrænset Kerberos-standarddelegering](#configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation).

Brug [ressourcebaseret Kerberos-begrænset delegering](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) til at aktivere enkeltlogon-forbindelse til Windows Server 2012 og nyere versioner, som tillader, at front end- og back end-tjenester er i forskellige domæner. Hvis dette skal fungere, skal domænet for back end-tjenesten have tillid til domænet for front end-tjenesten.

I følgende trin antager vi, at vi har et lokalt miljø med to computere i forskellige domæner: en gatewaycomputer og en databaseserver, der kører SQL Server, og som allerede er blevet konfigureret til Kerberos-baseret SSO. Trinnene kan benyttes for en af de andre understøttede datakilder, så længe datakilden allerede er konfigureret til Kerberos-baseret enkeltlogon. Af hensyn til dette eksempel antager vi også, at vi har følgende indstillinger og navne:

* Active Directory-frontenddomæne (Netbios): **ContosoFrontEnd**
* Active Directory-backenddomæne (Netbios): **ContosoBackEnd**
* Gatewaymaskinens navn: **MyGatewayMachine**
* Gatewaytjenestekonto: **ContosoFrontEnd\GatewaySvc**
* Navn på computer med SQL Server-datakilde: **TestSQLServer**
* SQL Server-datakildens tjenestekonto: **ContosoBackEnd\SQLService**

Med udgangspunkt i disse eksempelnavne og -indstillinger skal du fuldføre følgende konfigurationstrin:

1. På domænecontrolleren for domænet **ContosoFrontEnd** skal du sikre, at der ikke anvendes nogen delegeringsindstillinger for gatewaytjenestekontoen, ved at bruge **Active Directory-bruger og -computere**, som er en MMC-snap-in (Microsoft Management Console).

    ![Egenskaber for gatewayconnector](media/service-gateway-sso-kerberos-resource/gateway-connector-properties.png)

2. Ved hjælp af **Active Directory-brugere og -computere** skal du på domænecontrolleren for domænet **ContosoBackEnd** sørge for, at der ikke er anvendt nogen delegeringsindstillinger for back end-tjenestekontoen.

    ![Egenskaber for SQL-tjenesten](media/service-gateway-sso-kerberos-resource/sql-service-properties.png)

3. Herudover skal du sikre, at attributten **msDS-AllowedToActOnBehalfOfOtherIdentity** for denne konto heller ikke er angivet. Du kan finde denne attribut i **attributeditoren**, som vist på følgende billede:

    ![SQL-tjenesteattributter](media/service-gateway-sso-kerberos-resource/sql-service-attributes.png)

4. Opret en gruppe i **Active Directory-brugere og -computere** på domænecontrolleren for domænet **ContosoBackEnd**. Føj gatewaytjenestekontoen til denne gruppe, som vist på følgende billede. På billedet vises en ny gruppe ved navn _ResourceDelGroup_ og gatewaytjenestekontoen **GatewaySvc**, der er føjet til denne gruppe.

    ![Gruppeegenskaber](media/service-gateway-sso-kerberos-resource/group-properties.png)

5. Åbn en kommandoprompt, og kør følgende kommandoer i domænecontrolleren for domænet **ContosoBackEnd** for at opdatere attributten **msDS-AllowedToActOnBehalfOfOtherIdentity** for back end-tjenestekontoen:

    ```powershell
    $c = Get-ADGroup ResourceDelGroup
    Set-ADUser SQLService -PrincipalsAllowedToDelegateToAccount $c
    ```

6. Du kan bekræfte, at opdateringen afspejles, på fanen "Attributeditor" i egenskaberne for back end-tjenestekontoen i **Active Directory-brugere og -computere.** **msDS-AllowedToActOnBehalfOfOtherIdentity** bør nu være angivet.

## <a name="grant-the-gateway-service-account-local-policy-rights-on-the-gateway-machine"></a>Tildel gatewaytjenestekontoen rettigheder til lokale politikker på gatewaymaskinen

På den computer, der kører gatewaytjenesten (**MyGatewayMachine** i eksemplet), skal du til sidst tildele den lokale politik **Repræsenter en klient efter godkendelse** og **Funger som en del af operativsystemet (SeTcbPrivilege)** til gatewaytjenestekontoen. Du kan udføre og bekræfte denne konfiguration med editoren til lokal gruppepolitik (**gpedit**).

1. Kør: *gpedit.msc* på gatewaycomputeren.

2. Gå til **Lokal computerpolitik** &gt; **Computerkonfiguration** &gt; **Windows-indstillinger** &gt; **Sikkerhedsindstillinger** &gt; **Lokale politikker** &gt; **Tildeling af brugerrettigheder**.

    ![Skærmbillede af mappestrukturen Lokal computerpolitik](media/service-gateway-sso-kerberos/user-rights-assignment.png)

3. Under **Tildeling af brugerrettigheder** på listen over politikker skal du vælge **Repræsenter en klient efter godkendelse**.

    ![Skærmbillede af politikken Repræsenter en klient](media/service-gateway-sso-kerberos/impersonate-client.png)

    Højreklik, og åbn **Egenskaber**. Se listen over konti. Den skal omfatte gatewaytjenestekontoen (**Contoso\GatewaySvc** eller **ContosoFrontEnd\GatewaySvc**, afhængigt af typen af begrænset delegering).

4. Under **Tildeling af brugerrettigheder** på listen over politikker skal du vælge **Optræd som en del af operativsystemet (SeTcbPrivilege)** . Kontrollér, at gatewaytjenestekontoen også er medtaget på listen over konti.

5. Genstart processen for tjenesten med **datagatewayen i det lokale miljø**.

### <a name="set-user-mapping-configuration-parameters-on-the-gateway-machine-if-required"></a>Angiv konfigurationsparametre for brugertilknytning på gatewaycomputeren, hvis det er relevant

Hvis du ikke har konfigureret Azure AD Connect, skal du følge disse trin for at knytte en bruger af Power BI-tjenesten til en Azure AD-bruger. Hver Active Directory-bruger, der tilknyttes på denne måde, skal have SSO-tilladelser til din datakilde. Du kan få flere oplysninger i denne [Guy in a Cube-video](https://www.youtube.com/watch?v=NG05PG9aiRw).

1. Åbn den primære konfigurationsfil til gatewayen, `Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`. Denne fil er som standard gemt i C:\Programfiler\datagateway i det lokale miljø.

1. Angiv **ADUserNameLookupProperty** til en Active Directory-attribut, der ikke er i brug. Vi antager, at `msDS-cloudExtensionAttribute1` bruges i de efterfølgende trin, selvom denne attribut kun er tilgængelig i Windows Server 2012 og nyere. Angiv **ADUserNameReplacementProperty** til `SAMAccountName`. Gem konfigurationsfilen.

1. På fanen **Tjenester** i Jobliste skal du højreklikke på gatewaytjenesten og vælge **Genstart**.

    ![Skærmbillede af fanen Tjenester i Jobliste](media/service-gateway-sso-kerberos/restart-gateway.png)

1. For hver bruger af Power BI-tjenesten, du vil aktivere Kerberos-SSO for, skal du angive egenskaben `msDS-cloudExtensionAttribute1` for en lokal Active Directory-bruger (med SSO-tilladelse til din datakilde) til det fulde brugernavn (dvs. UPN) for brugeren af Power BI-tjenesten. Hvis du f.eks. logger på Power BI-tjenesten som `test@contoso.com`, og du vil knytte denne bruger til en lokal Active Directory-bruger med SSO-tilladelser, f.eks. `test@LOCALDOMAIN.COM`, skal du angive `test@LOCALDOMAIN.COM`s attribut `msDS-cloudExtensionAttribute1` til `test@contoso.com`.

    Du kan angive egenskaben `msDS-cloudExtensionAttribute1` ved hjælp af MMC-snap-in'en Active Directory-brugere og -computere (Microsoft Management Console):
    
    1. Start Active Directory-brugere og -computere som domæneadministrator.
    
    1. Højreklik på domænet, vælg Find, og skriv kontonavnet på den lokale Active Directory-bruger, som du vil tilknytte.
    
    1. Vælg fanen **Attributeditor**.
    
        Find egenskaben `msDS-cloudExtensionAttribute1`, og dobbeltklik på den. Angiv værdien til brugerens fulde brugernavn (dvs. UPN), som du bruger til at logge på Power BI-tjenesten.
    
    1. Vælg **OK**.
    
        ![Skærmbillede af dialogboksen Editor til strengattribut](media/service-gateway-sso-kerberos/edit-attribute.png)
    
    1. Vælg **Anvend**. Kontrollér, at den korrekte værdi er blevet angivet i kolonnen **Værdi**.

## <a name="complete-data-source-specific-configuration-steps"></a>Udfør datakildespecifikke konfigurationstrin

SAP HANA og SAP BW har ekstra datakildespecifikke konfigurationskrav og -forudsætninger, der skal opfyldes, før du kan oprette en SSO-forbindelse gennem gatewayen til disse datakilder. Du kan finde flere oplysninger på [konfigurationssiden til SAP HANA](service-gateway-sso-kerberos-sap-hana.md) og [konfigurationssiden til SAP BW – CommonCryptoLib (sapcrypto.dll)](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md). Det er også muligt at [konfigurere SAP BW til brug sammen medgx64krb5 SNC-biblioteket](service-gateway-sso-kerberos-sap-bw-gx64krb.md), men dette bibliotek anbefales ikke af Microsoft, da det ikke længere understøttes af SAP. Du bør bruge CommonCryptoLib _eller_ gx64krb5 som dit SNC-bibliotek. Du må ikke gennemføre konfigurationstrinnene for begge biblioteker.

> [!NOTE]
> Andre SNC-biblioteker kan også fungere for BW SSO, men de understøttes ikke officielt af Microsoft.

## <a name="run-a-power-bi-report"></a>Kør Power BI-rapport

Når alle konfigurationstrin er fuldført, kan du bruge siden **Administrer gateway** i Power BI til at konfigurere den datakilde, du vil bruge for SSO. Hvis du har flere gateways, skal du sørge for at vælge den gateway, du har konfigureret til Kerberos SSO. Under **Avancerede indstillinger** skal du derefter sørge for, at afkrydsningsfeltet **Brug SSO via Kerberos til DirectQuery-forespørgsler** er markeret.

![Skærmbillede af Avancerede indstillinger](media/service-gateway-sso-kerberos/advanced-settings.png)

 Publicer en **DirectQuery-baseret** rapport fra Power BI Desktop. Denne rapport skal bruge data, der er tilgængelige for den bruger, som er tilknyttet den Azure Active Directory-bruger (AAD), der logger på Power BI-tjenesten. Du skal bruge DirectQuery i stedet for at importere på grund af den måde, opdatering fungerer på. Når du opdaterer importbaserede rapporter, bruger gatewayen de legitimationsoplysninger, du angav i felterne **Brugernavn** og **Adgangskode**, da du oprettede datakilden. Det vil sige, at Kerberos SSO **ikke** bruges. Når du publicerer, skal du desuden sørge for at vælge den gateway, du har konfigureret til SSO, hvis du har flere gateways. I Power BI-tjenesten kan du nu opdatere rapporten eller oprette en ny rapport, der er baseret på det publicerede datasæt.

Denne konfiguration fungerer i de fleste tilfælde. Med Kerberos kan der dog være forskellige konfigurationer afhængigt af dit miljø. Hvis rapporten stadig ikke indlæses, skal du kontakte domæneadministratoren for at få problemet undersøgt yderligere. Hvis din datakilde er SAP BW, kan du også se afsnittet om fejlfinding for de datakildespecifikke konfigurationssider for [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md#troubleshooting) og [gx64krb5/gsskrb5](service-gateway-sso-kerberos-sap-bw-gx64krb.md#troubleshooting), afhængigt af hvilket SNC-bibliotek du har valgt.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om **datagateway i det lokale miljø** og **DirectQuery** i følgende ressourcer:

* [Hvad er en datagateway i det lokale miljø?](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
