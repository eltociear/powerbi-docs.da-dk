---
title: Brug Kerberos til SSO (enkeltlogon) i forbindelse med datakilder i det lokale miljø
description: Konfigurer din gateway med Kerberos for at aktivere SSO fra Power BI til datakilder i det lokale miljø
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: e2183596a66526ced7cfa4a298420972b63a87ca
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226244"
---
# <a name="use-kerberos-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Brug Kerberos til SSO (enkeltlogon) fra Power BI til datakilder i det lokale miljø

Brug [Begrænset Kerberos-delegering](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) for at muliggøre en problemfri forbindelse med enkeltlogon (SSO). Aktivering af SSO gør det nemt for Power BI-rapporter og -dashboards at opdatere data fra kilder i det lokale miljø.

## <a name="supported-data-sources"></a>Understøttede datakilder

Vi understøtter i øjeblikket følgende datakilder:

* SQL Server
* SAP HANA
* SAP BW
* Teradata
* Spark
* Impala

Vi understøtter også SAP HANA med [SAML (Security Assertion Markup Language)](service-gateway-sso-saml.md).

### <a name="sap-hana"></a>SAP HANA

Hvis du vil aktivere SSO til SAP HANA, skal du først følge disse trin:

* Kontrollér, at SAP HANA-serveren kører den påkrævede minimumversion, hvilket afhænger af niveauet af din SAP HANA-serverplatform:
  * [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* Installér SAP's seneste HANA ODBC-driver på gatewaycomputeren.  Minimumversionen er HANA ODBC version 2.00.020.00 fra august 2017.

Du kan finde flere oplysninger om konfiguration af SSO til SAP HANA ved hjælp af Kerberos under [Enkeltlogon ved hjælp af Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) i Sikkerhedsvejledning til SAP HANA. Se også linket på den side – især SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory.

## <a name="prepare-for-kerberos-constrained-delegation"></a>Forberedelse til begrænset Kerberos-delegering

Du skal konfigurere flere elementer, hvis begrænset Kerberos-delegering skal fungere korrekt, herunder *tjenestens hovednavn* (SPN – Service Principal Name) og delegeringsindstillinger for tjenestekonti.

### <a name="prerequisite-1-install-and-configure-the-microsoft-on-premises-data-gateway"></a>Forudsætning 1: Installér og konfigurer Microsoft-datagatewayen i det lokale miljø

Denne version af datagatewayen i det lokale miljø understøtter en lokal opgradering samt indstillingsovertagelse af eksisterende gateways.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>Forudsætning 2: Kør gatewayens Windows-tjeneste som en domænekonto.

I en standardinstallation kører gatewayen som en tjenestekonto på en lokal computer (specifikt *NT Service\PBIEgwService*).

![Skærmbillede af tjenestekonto](media/service-gateway-sso-kerberos/service-account.png)

Hvis du vil aktivere begrænset Kerberos-delegering, skal gatewayen køre som en domænekonto, medmindre din instans af Azure Active Directory (Azure AD) allerede er synkroniseret med din lokale instans af Active Directory (ved hjælp af Azure AD DirSync/Connect). Hvis du vil skifte til en domænekonto, skal du se [Skift gatewayen til en domænekonto](#switching-the-gateway-to-a-domain-account) senere i denne artikel.

> [!NOTE]
> Hvis Azure AD Connect er konfigureret, og brugerkonti er synkroniseret, behøver gatewaytjenesten ikke at udføre lokale Azure AD-opslag på kørselstidspunktet. Du kan bruge det lokale tjeneste-SID (i stedet for at kræve en domænekonto) til gatewaytjenesten. De konfigurationstrin for begrænset Kerberos-delegering, der er beskrevet i denne artikel, er de samme som til den konfiguration. De anvendes simpelthen på gatewayens computerobjekt i Azure AD i stedet for domænekontoen.

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>Forudsætning 3: Du skal have rettigheder som domæneadministrator til at konfigurere indstillinger for SPN'er (SetSPN) og begrænset Kerberos-delegering

Det anbefales ikke, at en domæneadministrator midlertidigt eller permanent giver andre rettigheder til at konfigurere SPN'er og Kerberos-delegering uden at kræve rettigheder som domæneadministrator. I følgende afsnit beskrives de anbefalede konfigurationstrin mere detaljeret.

## <a name="configure-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Konfigurer begrænset Kerberos-delegering for gatewayen og datakilden

Som domæneadministrator kan du konfigurere et SPN og delegeringsindstillinger for domænekontoen for gatewaytjenesten.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>Konfigurer et SPN til gatewaytjenestekontoen

Først skal du undersøge, om der allerede er oprettet et SPN for den domænekonto, der bruges som gatewaytjenestenkonto:

1. Åbn **Active Directory-brugere og -computere** som domæneadministrator.

2. Højreklik på domænet, vælg **Find**, og angiv navnet på gatewaytjenestekontoen.

3. Højreklik på gatewaytjenestekontoen i søgeresultaterne, og vælg **Egenskaber**.

4. Hvis fanen **Delegering** er synlig i dialogboksen **Egenskaber**, er der allerede oprettet et SPN. Du kan gå videre til at konfigurere delegeringsindstillingerne.

    Hvis fanen **Delegering** ikke er synlig i dialogboksen **Egenskaber**, kan du manuelt oprette et SPN for den pågældende konto. Så tilføjes fanen **Delegering**. Brug det [setspn-værktøj](https://technet.microsoft.com/library/cc731241.aspx), der følger med Windows. Du skal have rettigheder som domæneadministrator for at oprette et SPN.

    Forestil dig f.eks., at gatewaytjenestekontoen er "PBIEgwTest\GatewaySvc", og at navnet på computeren, hvor gatewaytjenesten kører, kaldes **Computer1**. Kør følgende kommando for at angive SPN'et for gatewaytjenestekontoen for computeren i dette eksempel:

    ![Billede af angivet kommando for SPN](media/service-gateway-sso-kerberos/set-spn.png)

    Når dette trin er fuldført, kan vi gå videre til at konfigurere delegeringsindstillinger.

### <a name="configure-delegation-settings-on-the-gateway-service-account"></a>Konfigurer delegeringsindstillinger på gatewaytjenestekontoen

Det andet konfigurationskrav er delegeringsindstillinger på gatewaytjenestekontoen . Der er mange værktøjer, som kan bruges til at udføre disse trin. Her bruger vi Active Directory-brugere og -computere, der er et MMC-snap-in (Microsoft Management Console), som du kan bruge til at administrere og publicere oplysninger i mappen. Det er tilgængeligt på domænecontrollere som standard. Du kan også aktivere det via konfiguration af Windows-funktioner på andre computere.

Vi skal konfigurere begrænset Kerberos-delegering med protokoloverførsel. Med begrænset delegering skal du være eksplicit med, hvilke tjenester du vil uddelegere til. Det er f.eks. kun SQL Server- eller SAP HANA-serveren, der accepterer delegeringskald fra gatewaytjenestekontoen.

I dette afsnit forudsættes det, at du allerede har konfigureret SPN'er for de underliggende datakilder (f.eks. SQL Server, SAP HANA, Teradata og Spark). Du kan få mere at vide om, hvordan du konfigurerer disse datakildeserveres SPN'er i den tekniske dokumentation til den respektive databaseserver. Du kan også se blogindlægget [Hvilket SPN kræver din app?](https://blogs.msdn.microsoft.com/psssql/2010/06/23/my-kerberos-checklist/)

I følgende trin antager vi, at vi har et lokalt miljø med to computere: en gatewaycomputer og en databaseserver, der kører SQL Server. Af hensyn til dette eksempel antager vi også, at vi har følgende indstillinger og navne:

* Navn på gatewaycomputer: **PBIEgwTestGW**
* Gatewaytjenestekonto: **PBIEgwTest\GatewaySvc** (kontoens visningsnavn: Gateway Connector)
* Navn på computer med SQL Server-datakilde: **PBIEgwTestSQL**
* SQL Server-datakildens tjenestekonto: **PBIEgwTest\SQLService**

Her kan du se, hvordan du konfigurerer delegeringsindstillingerne:

1. Åbn **Active Directory-brugere og -computere** med rettigheder som domæneadministrator.

2. Højreklik på gatewaytjenestekontoen (**PBIEgwTest\GatewaySvc**), og vælg **Egenskaber**.

3. Vælg fanen **Delegering**.

4. Vælg **Hav kun tillid til denne computer i forbindelse med delegering til de angivne tjenester** > **Brug en vilkårlig godkendelsesprotokol**.

6. Under **Tjenester, som denne konto kan give delegerede legitimationsoplysninger** skal du vælge **Tilføj**.

7. I den nye dialogboks skal du vælge **Brugere eller computere**.

8. Angiv tjenestekontoen for SQL Server-datakilden (**PBIEgwTest\SQLService**), og vælg **OK**.

9. Vælg det hovednavn for tjenesten (SPN), du har oprettet for databaseserveren. I dette eksempel begynder SPN med **MSSQLSvc**. Hvis du har tilføjet både det fulde domænenavn (FQDN) og NetBIOS- SPN til din databasetjeneste, vælges begge dele. Du kan muligvis kun se ét.

10. Vælg **OK**. Du bør nu kunne se SPN'et på listen.

    Du kan også vælge **Udvidet**, hvis du vil have vist både FQDN og NetBIOS-SPN. Dialogboksen ligner følgende dialogboks, hvis du valgte **Udvidet**. Vælg **OK**.

    ![Skærmbillede af dialogboksen Egenskaber for gatewayconnector](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

På den computer, der kører gatewaytjenesten (**PBIEgwTestGW** i eksemplet), skal du til sidst tildele gatewaytjenestekontoen den lokale politik **Repræsenter en klient efter godkendelse**. Du kan udføre og bekræfte dette med Editor til lokal gruppepolitik (**gpedit**).

1. Kør: *gpedit.msc* på gatewaycomputeren.

1. Gå til **Lokal computerpolitik** > **Computerkonfiguration** > **Windows-indstillinger** > **Sikkerhedsindstillinger** > **Lokale politikker** > **Tildeling af brugerrettigheder**.

    ![Skærmbillede af mappestrukturen Lokal computerpolitik](media/service-gateway-sso-kerberos/user-rights-assignment.png)

1. Under **Tildeling af brugerrettigheder** på listen over politikker skal du vælge **Repræsenter en klient efter godkendelse**.

    ![Skærmbillede af politikken Repræsenter en klient](media/service-gateway-sso-kerberos/impersonate-client.png)

    Højreklik, og åbn **Egenskaber**. Se listen over konti. Den skal omfatte gatewaytjenestekontoen (**PBIEgwTest\GatewaySvc**).

1. Under **Tildeling af brugerrettigheder** på listen over politikker skal du vælge **Optræd som en del af operativsystemet (SeTcbPrivilege)**. Kontrollér, at gatewaytjenestekontoen også er medtaget på listen over konti.

1. Genstart processen for tjenesten med **datagatewayen i det lokale miljø**.

Hvis du bruger SAP HANA, anbefaler vi at følge disse ekstra trin, som kan generere en mindre forbedring af ydeevnen.

1. Find og åbn denne konfigurationsfil i installationsmappen for gatewayen: *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

1. Find egenskaben *FullDomainResolutionEnabled*, og rediger dens værdi til *True*.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

## <a name="run-a-power-bi-report"></a>Kør Power BI-rapport

Når alle konfigurationstrin er fuldført, kan du bruge siden **Administrer gateway** i Power BI til at konfigurere datakilden. Derefter kan du under **Avancerede indstillinger** aktivere SSO og publicere rapporter og datasæt med binding til den pågældende datakilde.

![Skærmbillede af Avancerede indstillinger](media/service-gateway-sso-kerberos/advanced-settings.png)

Denne konfiguration fungerer i de fleste tilfælde. Med Kerberos kan der dog være forskellige konfigurationer afhængigt af dit miljø. Hvis rapporten stadig ikke indlæses, skal du kontakte domæneadministratoren for at få problemet undersøgt yderligere.

## <a name="switch-the-gateway-to-a-domain-account"></a>Skift gatewayen til en domænekonto

Hvis det er nødvendigt, kan du skifte gatewayen fra en lokal tjenestekonto til en, der kører som domænekonto, ved hjælp af brugergrænsefladen i **Datagateway i det lokale miljø**. Sådan gør du:

1. Åbn konfigurationsværktøjet til **Datagateway i det lokale miljø**.

   ![Skærmbillede af indstilling til at starte gatewayskrivebordsprogrammet](media/service-gateway-sso-kerberos/gateway-desktop-app.png)

2. Vælg knappen**Log på** på hovedsiden, og log på med din Power BI-konto.

3. Når logon er fuldført, kan du vælge fanen **Tjenesteindstillinger**.

4. Vælg **Skift konto** for at starte den guidede gennemgang.

   ![Skærmbillede af skrivebordsprogrammet Datagateway i det lokale miljø med indstillingen Skift konto fremhævet](media/service-gateway-sso-kerberos/change-account.png)

## <a name="configure-sap-bw-for-sso"></a>Konfigurer SAP BW til SSO

Nu hvor du forstår, hvordan Kerberos fungerer sammen med en gateway, kan du konfigurere SSO til SAP Business Warehouse (SAP BW). I følgende trin forudsættes det, at du allerede har [forberedt til begrænset Kerberos-delegering](#preparing-for-kerberos-constrained-delegation), som beskrevet tidligere i denne artikel.

Denne vejledning er et forsøg på at være så omfattende som muligt. Hvis du allerede har fuldført nogle af disse trin, kan du springe dem over. Du har måske allerede oprettet en tjenestebruger for din SAP BW-server og knyttet et SPN til den, eller du har måske allerede installeret biblioteket `gsskrb5`.

### <a name="set-up-gsskrb5-on-client-machines-and-the-sap-bw-server"></a>Konfigurer gsskrb5 på klientcomputere og SAP BW-serveren

> [!NOTE]
> `gsskrb5` understøttes ikke længere aktivt af SAP. Du kan finde flere oplysninger under [SAP Note 352295](https://launchpad.support.sap.com/#/notes/352295). Bemærk også, at `gsskrb5` ikke tillader SSO-forbindelser fra datagatewayen til SAP BW-meddelelsesservere. Det er kun forbindelser til SAP BW-programservere, der er mulige.

`gsskrb5` skal bruges af både klienten og serveren, før en SSO-forbindelse via gatewayen kan fuldføres. Common Crypto-biblioteket (sapcrypto) understøttes ikke i øjeblikket.

1. Download `gsskrb5` - `gx64krb5` fra [SAP Note 2115486](https://launchpad.support.sap.com/) (SAP s-bruger er påkrævet). Sørg for, at du mindst har version 1.0.11.x af gsskrb5.dll og gx64krb5.dll.

1. Placer biblioteket et sted på gatewaycomputeren, der er tilgængeligt for din gatewayinstans (og også for den grafiske brugergrænseflade i SAP, hvis du vil teste SSO-forbindelsen ved hjælp af SAP Logon).

1. Placer en ekstra kopi på SAP BW-servercomputeren et sted, der er tilgængelig for SAP BW-serveren.

1. På klient- og servercomputerne skal du sætte variablerne `SNC\_LIB` og `SNC\_LIB\_64` for miljøet til at pege på placeringerne af henholdsvis gsskrb5.dll og gx64krb5.dll.

### <a name="create-a-sap-bw-service-user-and-enable-snc-communication"></a>Opret en SAP BW-tjenestebruger, og aktivér SNC-kommunikation

Ud over den konfiguration af gatewayen, du allerede har foretaget, er der et par yderligere trin, som kræves specifikt for SAP BW. Afsnittet [Konfigurer delegeringsindstillinger på gatewaytjenestekontoen](#configure-delegation-settings-on-the-gateway-service-account) i dokumentationen forudsætter, at du allerede har konfigureret SPN'er for de underliggende datakilder. Sådan fuldføres konfigurationen af gatewayen for SAP BW:

1. På en Active Directory-domænecontrollerserver skal du oprette en tjenestebruger (indledningsvist blot en almindelig Active Directory-bruger) for din SAP BW-programserver i dit Active Directory-miljø. Derefter skal du tildele et SPN til den.

    SAP anbefaler, at du starter SPN med `SAP/`, men det bør også være muligt at bruge andre præfikser, f.eks. `HTTP/`. Du bestemmer, hvad der kommer efter `SAP/`. Du kan f.eks. bruge tjenestebrugerens brugernavn for SAP BW-serveren. Hvis du f.eks. opretter `BWServiceUser@\<DOMAIN\>` som din tjenestebruger, kan du bruge SPN `SAP/BWServiceUser`. En måde at angive SPN-tilknytningen på er ved at benytte kommandoen setspn. Hvis du f.eks. vil angive SPN'et for den tjenestebruger, vi lige har oprettet, skal du køre følgende kommando fra et cmd-vindue på en domænecontrollercomputer: `setspn -s SAP/ BWServiceUser DOMAIN\ BWServiceUser`. Du kan finde flere oplysninger i dokumentationen til SAP BW.

1. Giv tjenestebrugeren adgang til SAP BW-programserveren:

    1. På SAP BW-servercomputeren skal du føje tjenestebrugeren til gruppen Lokal administrator for din SAP BW-server. Åbn programmet Computeradministration, og dobbeltklik på gruppen Lokal administrator for din server.

        ![Skærmbillede af programmet Computeradministration](media/service-gateway-sso-kerberos/computer-management.png)

    1. Dobbeltklik på gruppen Lokal administrator, og vælg derefter **Tilføj** for at føje tjenestebrugeren til gruppen. Vælg **Kontrollér navne** for at sikre, at du har angivet navnet korrekt. Vælg **OK**.

1. Angiv tjenestebrugeren for SAP BW-serveren som den bruger, der starter SAP BW-servertjenesten på SAP BW-servercomputeren.

    1. Åbn **Kør**, og angiv "Services.msc". Kig efter den tjeneste, der svarer til instansen af din SAP BW-programserver. Højreklik på den, og vælg **Egenskaber**.

        ![Skærmbillede af Tjenester med Egenskaber fremhævet](media/service-gateway-sso-kerberos/server-properties.png)

    1. Skift til fanen **Log på**, og skift brugeren til din SAP BW-tjenestebruger. Angiv brugerens adgangskode, og vælg **OK**.

1. Log på din server i SAP Logon, og angiv følgende profilparametre ved hjælp af RZ10-transaktionen:

    1. Angiv profilparameteren snc/identity/as til p:\<den SAP BW-tjenestebruger, du har oprettet\>, f.eks. p:BWServiceUser@MYDOMAIN.COM. Bemærk det p:, der står foran tjenestebrugerens UPN. Det er ikke p:CN=, ligesom når Common Crypto-biblioteket bruges som SNC-bibliotek.

    1. Angiv profilparameteren snc/gssapi\_lib til \<path til gsskrb5.dll/gx64krb5.dll på servercomputeren (det bibliotek, du bruger, afhænger af OS-bittæthed)\>. Husk at placere biblioteket et sted, som SAP BW-programserveren har adgang til.

    1. Du skal også angive følgende profilparametre og ændre værdierne efter behov, så de passer til dine behov. Bemærk, at de sidste fem indstillinger gør det muligt for klienter at oprette forbindelse til SAP BW-serveren ved hjælp af SAP Logon, uden at SNC er konfigureret.

        | **Indstilling** | **Værdi** |
        | --- | --- |
        | snc/data\_protection/max | 3 |
        | snc/data\_protection/min | 1 |
        | snc/data\_protection/use | 9 |
        | snc/accept\_insecure\_cpic | 1 |
        | snc/accept\_insecure\_gui | 1 |
        | snc/accept\_insecure\_r3int\_rfc | 1 |
        | snc/accept\_insecure\_rfc | 1 |
        | snc/permit\_insecure\_start | 1 |

    1. Angiv egenskaben snc/enable til 1.

1. Når du har angivet disse profilparametre, skal du åbne SAP-administrationskonsollen på servercomputeren og genstarte SAP BW-instansen. Hvis serveren ikke vil starte, skal du kontrollere, at du har angivet profilparametrene korrekt. Du kan få flere oplysninger om profilparameterindstillinger i [SAP-dokumentationen](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm). Hvis du støder på problemer, kan du også se vores fejlfindingsoplysninger senere i dette afsnit.

### <a name="map-a-sap-bw-user-to-an-active-directory-user"></a>Knyt en SAP BW-bruger til en Active Directory-bruger

Knyt en Active Directory-bruger til en bruger af SAP BW-programserveren, og test SSO-forbindelsen i SAP Logon.

1. Log på din SAP BW-server ved hjælp af SAP Logon. Kør transaktionen SU01.

1. Under **Bruger** skal du angive den SAP BW-bruger, du vil aktivere SSO-forbindelser for (på forrige skærmbillede angiver vi tilladelser for BIUSER). Vælg ikonet **Rediger** (billedet af en pen) øverst til venstre i vinduet SAP Logon.

    ![Skærmbillede af skærmen til vedligeholdelse af SAP BW-bruger](media/service-gateway-sso-kerberos/user-maintenance.png)

1. Vælg fanen **SNC**. Angiv p:\<din Active Directory-bruger\>@\<dit domæne\> i tekstfeltet SNC-navn. Bemærk det obligatoriske p:, der skal være foran Active Directory-brugerens UPN. Den Active Directory-bruger, du angiver, skal tilhøre den person eller organisation, som du vil aktivere SSO-adgang til SAP BW-programserveren for. Hvis du f.eks. vil aktivere SSO-adgang for brugeren [testuser@TESTDOMAIN.COM](mailto:testuser@TESTDOMAIN.COM), skal du angive p:testuser@TESTDOMAIN.COM.

    ![Skærmbillede af skærmen til vedligeholdelse af SAP BW-brugere](media/service-gateway-sso-kerberos/maintain-users.png)

1. Vælg ikonet **Gem** (billedet af en diskette) øverst til venstre på skærmen.

### <a name="test-sign-in-by-using-sso"></a>Test logon vha. SSO

Bekræft, at du kan logge på serveren. Brug SAP Logon via SSO som den Active Directory-bruger, du lige har aktiveret SSO-adgang for.

1. Log på en computer, hvor SAP Logon er installeret, som den Active Directory-bruger, du lige har aktiveret SSO-adgang for. Start SAP Logon, og opret en ny forbindelse.

1. På skærmen **Opret ny systempost** skal du vælge **Brugerangivet system** > **Næste**.

    ![Skærmbillede af skærmen Opret ny systempost](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Udfyld de relevante oplysninger på den næste skærm, herunder programserver, instansnummer og system-id. Vælg **Udfør**.

1. Højreklik på den nye forbindelse, og vælg **Egenskaber**. Vælg fanen **Netværk**. I tekstfeltet **SNC-navn** skal du angive p:\<SAP BW-tjenestebrugerens UPN\>, f.eks. p:BWServiceUser@MYDOMAIN.COM. Vælg derefter **OK**.

    ![Skærmbillede af skærmen Egenskaber for systempost](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Dobbeltklik på den forbindelse, du lige har oprettet, for at forsøge at oprette en SSO-forbindelse til SAP BW-serveren. Hvis denne forbindelse lykkes, kan du fortsætte til næste trin. Ellers skal du gennemse de tidligere trin i dette dokument for at sikre, at de er blevet afsluttet korrekt, eller gennemse afsnittet med fejlfinding nedenfor. Bemærk! Hvis du ikke kan oprette forbindelse til SAP BW-serveren via SSO i denne kontekst, så kan du ikke oprette forbindelse til SAP BW-serveren ved hjælp af SSO i gatewaykonteksten.

### <a name="troubleshoot-installation-and-connections"></a>Fejlfinding i forbindelse med installation og forbindelser

Hvis du støder på problemer, skal du følge disse trin for at foretage fejlfinding af installationen af gsskrb5 og SSO-forbindelser fra SAP Logon.

- Det kan være nyttigt at få vist serverlogge (…work\dev\_w0 på servercomputeren) i forbindelse med fejlfinding af evt. fejl, du måtte støde på under fuldførelse af trinnene til konfiguration af gsskrb5. Dette er især tilfældet, hvis SAP BW-serveren ikke starter, efter profilparametrene er blevet ændret.

- Hvis du ikke kan starte SAP BW-tjenesten på grund af en logonfejl, har du muligvis angivet en forkert adgangskode ved angivelsen af "start som" bruger i SAP BW. Bekræft adgangskoden ved at logge på en computer i dit Active Directory-miljø som SAP BW-tjenestebrugeren.

- Hvis du får vist fejl om legitimationsoplysninger til SQL, der forhindrer serveren i at starte, skal du kontrollere, at du har givet tjenestebrugeren adgang til SAP BW-databasen.

- Du får muligvis vist følgende meddelelse: "(GSS-API) Den angivne destination er ukendt eller kan ikke nås". Det betyder normalt, at du har angivet det forkerte SNC-navn. Sørg for kun at bruge "p:" og ikke "p:CN=" eller andet i klientprogrammet ud over tjenestebrugerens UPN.

- Du får muligvis vist følgende meddelelse: "(GSS-API) Der blev angivet et ugyldigt navn". Sørg for, at "p:" er i værdien for serverens profilparameter for SNC-identitet.

- Du får muligvis vist følgende meddelelse: "(SNC fejl) Det angivne modul blev ikke fundet". Dette skyldes som regel, at `gsskrb5.dll/gx64krb5.dll` er blevet placeret et sted, hvor der kræves rettigheder som administrator for at få adgang.

### <a name="add-registry-entries-to-the-gateway-machine"></a>Føj registreringsdatabaseposter til gatewaycomputeren

Føj påkrævede poster i registreringsdatabasen til registreringsdatabasen for den computer, som gatewayen er installeret på. Her er de kommandoer, der skal køres:

1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

### <a name="set-configuration-parameters-on-the-gateway-machine"></a>Angiv konfigurationsparametre på gatewaycomputeren

Der er to muligheder for at angive parameterkonfiguration, afhængigt af om Azure AD Connect er konfigureret, så brugerne kan logge på Power BI-tjenesten som Azure AD-brugere.

Hvis du har konfigureret Azure AD Connect, skal du følge disse trin.

1. Åbn den primære konfigurationsfil til gatewayen, `Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`. Denne fil er som standard gemt i C:\Programfiler\datagateway i det lokale miljø.

1. Kontrollér, at egenskaben **FullDomainResolutionEnabled** er angivet til **Sand**, og at **SapHanaSsoRemoveDomainEnabled** er angivet til **Falsk**.

1. Gem konfigurationsfilen.

1. På fanen **Tjenester** i Jobliste skal du højreklikke på gatewaytjenesten og vælge **Genstart**.

    ![Skærmbillede af fanen Tjenester i Jobliste](media/service-gateway-sso-kerberos/restart-gateway.png)

Hvis du ikke har konfigureret Azure AD Connect, skal du følge disse trin for hver enkelt bruger af Power BI-tjenesten, som du vil knytte til en Azure AD-bruger. Disse trin linker manuelt en bruger af Power BI-tjenesten til en Active Directory-bruger med tilladelse til at logge på SAP BW.

1. Åbn den primære konfigurationsfil til gatewayen, `Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`. Denne fil er som standard gemt i C:\Programfiler\datagateway i det lokale miljø.

1. Angiv **ADUserNameLookupProperty** til `msDS-cloudExtensionAttribute1` og **ADUserNameReplacementProperty** til `SAMAccountName`. Gem konfigurationsfilen.

1. På fanen **Tjenester** i Jobliste skal du højreklikke på gatewaytjenesten og vælge **Genstart**.

    ![Skærmbillede af fanen Tjenester i Jobliste](media/service-gateway-sso-kerberos/restart-gateway.png)

1. Angiv egenskaben `msDS-cloudExtensionAttribute1` for Active Directory-brugeren. Dette er den bruger, du knyttede til en SAP BW-bruger. Angiv egenskaben til den bruger af Power BI-tjenesten, som du vil aktivere Kerberos SSO for. En måde at angive egenskaben `msDS-cloudExtensionAttribute1` på er ved at bruge MMC-snap-in'et Active Directory-brugere og -computere. Du kan også bruge andre metoder.

    1. Log på en domænecontrollermaskine som en administratorbruger.

    1. Åbn mappen **Brugere** i snap-in-vinduet, og dobbeltklik på den Active Directory-bruger, du har knyttet til en SAP BW-bruger.

    1. Vælg fanen **Attributeditor**.

        Hvis du ikke kan se denne fane, skal du søge efter vejledning i, hvordan du aktiverer den, eller bruge en anden metode til at angive egenskaben. Vælg én af attributterne og derefter M-nøglen for at gå til de Active Directory-egenskaber, der starter med bogstavet m. Find egenskaben `msDS-cloudExtensionAttribute1`, og dobbeltklik på den. Angiv værdien til det brugernavn, du bruger til at logge på Power BI-tjenesten, i formularen YourUser@YourDomain.

    1. Vælg **OK**.

        ![Skærmbillede af dialogboksen Editor til strengattribut](media/service-gateway-sso-kerberos/edit-attribute.png)

    1. Vælg **Anvend**. Kontrollér, at den korrekte værdi er blevet angivet i kolonnen **Værdi**.

### <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service"></a>Føj en ny datakilde for SAP BW-programserveren til Power BI-tjenesten

Føj SAP BW-datakilden til din gateway ved at følge instruktionerne tidligere i denne artikel om [kørsel af en rapport](#running-a-power-bi-report).

1. I vinduet til konfiguration af datakilde skal du angive programserverens **værtsnavn**, **systemnummer** og **klient-id**, på samme måde som du ville, når du logger på din SAP BW-server fra Power BI Desktop. Som **Godkendelsesmetode** skal du vælge **Windows**.

1. I feltet **SNC-partnernavn** skal du angive p: \<det SPN, du knyttede til din SAP BW-tjenestebruger\>. Hvis SPN f.eks. er SAP/BWServiceUser@MYDOMAIN.COM, skal du angive p:SAP/BWServiceUser@MYDOMAIN.COM i feltet **SNC-partnernavn**.

1. For SNC-biblioteket skal du vælge **SNC\_LIB** eller **SNC\_LIB\_64**.

1. **Brugernavn** og **Adgangskode** skal være brugernavnet og adgangskoden for en Active Directory-bruger med tilladelse til at logge på SAP BW-serveren med SSO. Disse skal med andre ord tilhøre en Active Directory-bruger, der er blevet knyttet til en SAP BW-bruger via SU01-transaktionen. Disse legitimationsoplysninger bruges kun, hvis feltet **Brug SSO via Kerberos til DirectQuery-forespørgsler** ikke er markeret.

1. Markér feltet **Brug SSO via Kerberos til DirectQuery-forespørgsler**, og vælg **Anvend**. Hvis testen af forbindelsen ikke fuldføres, skal du kontrollere, at de forrige trin til installation og konfiguration blev udført korrekt.

    Gatewayen anvender altid de angivne legitimationsoplysninger til at etablere en testforbindelse til serveren og foretage planlagte opdateringer af importbaserede rapporter. Gatewayen forsøger kun at oprette en SSO-forbindelse, hvis **Brug SSO via Kerberos til DirectQuery-forespørgsler** er markeret, og brugeren får adgang til en direkte forespørgselsbaseret rapport eller et forespørgselsbaseret datasæt.

### <a name="test-your-setup"></a>Test din installation

Du tester din konfiguration ved at publicere en DirectQuery-rapport fra Power BI Desktop til Power BI-tjenesten. Kontrollér, at du er logget på Power BI-tjenesten som enten en Azure AD-bruger eller en bruger, du har knyttet til egenskaben `msDS-cloudExtensionAttribute1` for en Azure AD-bruger. Hvis konfigurationen er fuldført, burde du kunne oprette en rapport på baggrund af det publicerede datasæt i Power BI-tjenesten. Du burde også kunne hente data via visualiseringer i rapporten.

### <a name="troubleshoot-gateway-connectivity-issues"></a>Fejlfinding af problemer med gatewayforbindelse

1. Se loggene til gatewayen. Åbn programmet til konfiguration af gatewayen, og vælg **Diagnosticering** > **Eksportér logge**. De nyeste fejl vises nederst i de logfiler, du undersøger.

    ![Skærmbillede af programmet Datagateway i det lokale miljø med Diagnosticering fremhævet](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. Slå SAP BW-sporing til, og gennemse de genererede logfiler. Der findes flere forskellige typer SAP BW-sporing. Du kan få flere oplysninger i dokumentationen til SAP.

## <a name="errors-from-an-insufficient-kerberos-configuration"></a>Fejl fra en utilstrækkelig Kerberos-konfiguration

Hvis den underliggende databaseserver og gateway ikke er konfigureret korrekt til begrænset Kerberos-delegering, kan du få vist følgende fejlmeddelelse om problemer med at indlæse data:

![Skærmbillede af fejlmeddelelse](media/service-gateway-sso-kerberos/load-data-error.png)

De tekniske detaljer, der er knyttet til fejlmeddelelsen (DM_GWPipeline_Gateway_ServerUnreachable), kan se ud på følgende måde:

![Skærmbillede af de tekniske detaljer af fejlmeddelelse](media/service-gateway-sso-kerberos/server-unreachable.png)

Resultatet er, at gatewayen ikke kan repræsentere den oprindelige bruger korrekt, og det lykkedes ikke at oprette forbindelse til databasen.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om **datagatewayen i det lokale miljø** og **DirectQuery** i følgende ressourcer:

* [Datagateway i det lokale miljø](service-gateway-onprem.md)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
