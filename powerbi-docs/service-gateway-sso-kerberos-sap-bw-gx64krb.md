---
title: Brug Kerberos til enkeltlogon (SSO) i forbindelse med SAP BW ved hjælp af gx64krb5
description: Konfigurer din SAP BW-server for at aktivere SSO fra Power BI-tjenesten ved hjælp af gx64krb5
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 5dd31dc4333dc03100370100e16eadab6012c1f0
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106325"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-bw-using-gx64krb5"></a>Brug Kerberos til enkeltlogon (SSO) i forbindelse med SAP BW ved hjælp af gx64krb5

I denne artikel beskrives, hvordan du konfigurerer din SAP BW-server for at aktivere SSO fra Power BI-tjenesten ved hjælp af gx64krb5.

> [!NOTE]
> Du kan fuldføre trinnene i denne artikel foruden trinnene i [Konfigurer SSO i Kerberos](service-gateway-sso-kerberos.md) for at aktivere opdatering af rapporter, der er baseret på SAP BW-programserver, som bruger SSO i Kerberos i Power BI-tjenesten. Microsoft anbefaler dog brug af CommonCryptoLib som dit SNC-bibliotek. SAP byder ikke længere support til gx64krb5, og de trin, der kræves for at konfigurere det til brug med gatewayen, er væsentligt mere komplekse sammenlignet med CommonCryptoLib. I [Konfigurer SAP BW til SSO ved hjælp af CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md) kan du se, hvordan konfigurerer SSO ved hjælp af CommonCryptoLib. Du skal fuldføre konfigurationen af CommonCryptoLib _eller_ gx64krb5. Fuldfør ikke konfigurationstrinnene for begge biblioteker.

### <a name="set-up-gx64krb5gsskrb5-on-gateway-machine-and-the-sap-bw-server"></a>Konfigurer gx64krb5/gsskrb5 på gatewaycomputeren og SAP BW-serveren

> [!NOTE]
> `gx64krb5` og `gsskrb5` understøttes ikke længere af SAP. Du kan finde flere oplysninger under [SAP Note 352295](https://launchpad.support.sap.com/#/notes/352295). Bemærk også, at `gx64krb5` ikke tillader SSO-forbindelser fra datagatewayen til SAP BW-meddelelsesservere. Det er kun forbindelser til SAP BW-programservere, der er mulige. Denne begrænsning med kun programserver findes ikke, hvis du bruger [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md) som SNC-bibliotek. Andre SNC-biblioteker kan også fungere for SSO i BW, men de understøttes ikke officielt af Microsoft.

`gx64krb5` \ `gsskrb5` skal bruges af både klienten og serveren for at fuldføre en SSO-forbindelse via gatewayen, dvs. både klienten og serveren skal bruge det samme SNC-bibliotek.

1. Download `gx64krb5` fra [SAP Note 2115486](https://launchpad.support.sap.com/) (s-bruger af SAP er påkrævet). Sørg for, at du har mindst version 1.0.11.x. Download også `gsskrb5` (32-bit versionen af biblioteket), hvis du vil teste SSO-forbindelsen i SAP GUI, før du forsøger at oprette SSO-forbindelsen via gatewayen (anbefales). 32-bit versionen kræves for at teste med SAP GUI, da SAP GUI kun er tilgængelig i 32-bit.

1. Placer `gx64krb5` et sted på gatewaycomputeren, der er tilgængeligt for tjenestebrugeren af din gateway (og også for SAP GUI, hvis du vil teste SSO-forbindelsen ved hjælp af SAP Logon). Både tjenestebrugeren af gatewayen og brugerne af Active Directory (AD), som tjenestebrugeren repræsenterer, skal have læse- og udførelsestilladelser til .dll. Det anbefales, at du tildeler gruppen Godkendte brugere tilladelser til .dll. Med henblik på test kan du også eksplicit tildele disse tilladelser til både den Tjenestebruger af gatewayen og den bruger af Active Directory, som du bruger til testen.

1. Hvis din BW-server ikke allerede er konfigureret til SSO ved hjælp af gx64krb5/gsskrb5, skal du placere en anden kopi på din SAP BW-computer et sted, der er tilgængeligt for SAP BW-serveren. 

1. Angiv miljøvariablerne `SNC_LIB` eller `SNC_LIB_64` på klient- og servercomputerne. Hvis du bruger gsskrb5, skal du angive variablen `SNC_LIB` til den fulde sti for gsskrb5.dll. Hvis du bruger gx64krb5, skal du angive variablen `SNC_LIB_64` til den fulde sti for gx64krb5.

### <a name="configure-an-sap-bw-service-user-and-enable-snc-communication"></a>Konfigurer en SAP BW-tjenestebruger, og aktivér SNC-kommunikation

Fuldfør dette afsnit, hvis du ikke allerede har konfigureret din SAP BW-server til SNC-kommunikation (f.eks. SSO) ved hjælp af gx64krb5/gsskrb5.

> [!NOTE]
> I dette afsnit antages det, at du allerede har oprettet en tjenestebruger til BW og bundet et egnet SPN til den (f.eks. noget, der starter med `SAP/`).

1. Giv tjenestebrugeren adgang til SAP BW-programserveren:

    1. På SAP BW-servercomputeren skal du føje tjenestebrugeren til gruppen Lokal administrator. Åbn programmet Computeradministration, og dobbeltklik på gruppen Lokal administrator for din server.

        ![Skærmbillede af programmet Computeradministration](media/service-gateway-sso-kerberos/computer-management.png)

    1. Dobbeltklik på gruppen Lokal administrator, og vælg derefter **Tilføj** for at føje tjenestebrugeren til gruppen. Vælg **Kontrollér navne** for at sikre, at du har angivet navnet korrekt. Vælg **OK**.

1. Angiv tjenestebrugeren for SAP BW-serveren som den bruger, der starter SAP BW-servertjenesten på SAP BW-servercomputeren.

    1. Åbn **Kør**, og angiv "Services.msc". Kig efter den tjeneste, der svarer til instansen af din SAP BW-programserver. Højreklik på den, og vælg **Egenskaber**.

        ![Skærmbillede af Tjenester med Egenskaber fremhævet](media/service-gateway-sso-kerberos/server-properties.png)

    1. Skift til fanen **Log på**, og skift brugeren til din SAP BW-tjenestebruger. Angiv brugerens adgangskode, og vælg **OK**.

1. Log på din server i SAP Logon, og angiv følgende profilparametre ved hjælp af RZ10-transaktionen:

    1. Angiv profilparameteren snc/identity/as til p:\<den SAP BW-tjenestebruger, du har oprettet\>, f.eks. p:BWServiceUser@MYDOMAIN.COM. Bemærk det p:, der står foran tjenestebrugerens UPN. Det er ikke p:CN=, ligesom når Common Crypto-biblioteket bruges som SNC-bibliotek.

    1. Angiv profilparameteren snc/gssapi\_lib til \<sti til gsskrb5.dll/gx64krb5.dll på BW-servercomputeren (det bibliotek, du bruger, afhænger af OS-bittæthed)\>. Husk at placere biblioteket et sted, som SAP BW-programserveren har adgang til.

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

Hvis du ikke allerede har gjort det, skal du knytte en Active Directory-bruger til en bruger af SAP BW-programserveren og teste SSO-forbindelsen i SAP Logon.

1. Log på din SAP BW-server ved hjælp af SAP Logon. Kør transaktionen SU01.

1. Under **Bruger** skal du angive den SAP BW-bruger, du vil aktivere SSO-forbindelser for (på forrige skærmbillede angiver vi tilladelser for BIUSER). Vælg ikonet **Rediger** (billedet af en pen) øverst til venstre i vinduet SAP Logon.

    ![Skærmbillede af skærmen til vedligeholdelse af SAP BW-bruger](media/service-gateway-sso-kerberos/user-maintenance.png)

1. Vælg fanen **SNC**. Angiv p:\<din Active Directory-bruger\>@\<dit domæne\> i tekstfeltet SNC-navn. Bemærk det obligatoriske p:, der skal være foran Active Directory-brugerens UPN. Den Active Directory-bruger, du angiver, skal tilhøre den person eller organisation, som du vil aktivere SSO-adgang til SAP BW-programserveren for. Hvis du f.eks. vil aktivere SSO-adgang for brugeren testuser\@TESTDOMAIN.COM, skal du angive p:testuser@TESTDOMAIN.COM.

    ![Skærmbillede af skærmen til vedligeholdelse af SAP BW-brugere](media/service-gateway-sso-kerberos/maintain-users.png)

1. Vælg ikonet **Gem** (billedet af en diskette) øverst til venstre på skærmen.

### <a name="test-sign-in-by-using-sso"></a>Test logon vha. SSO

Kontrollér, at du kan logge på serveren ved hjælp af SAP Logon via SSO som den Active Directory-bruger, du lige har aktiveret SSO-adgang for.

1. Log på en computer, hvor SAP Logon er installeret, som den Active Directory-bruger, du lige har aktiveret SSO-adgang for. Start SAP Logon, og opret en ny forbindelse.

1. På skærmen **Opret ny systempost** skal du vælge **Brugerangivet system** > **Næste**.

    ![Skærmbillede af skærmen Opret ny systempost](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Udfyld de relevante oplysninger på den næste skærm, herunder programserver, instansnummer og system-id. Vælg **Udfør**.

1. Højreklik på den nye forbindelse, og vælg **Egenskaber**. Vælg fanen **Netværk**. I tekstfeltet **SNC-navn** skal du angive p:\<SAP BW-tjenestebrugerens UPN\>, f.eks. p:BWServiceUser@MYDOMAIN.COM. Vælg derefter **OK**.

    ![Skærmbillede af skærmen Egenskaber for systempost](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Dobbeltklik på den forbindelse, du lige har oprettet, for at forsøge at oprette en SSO-forbindelse til SAP BW-serveren. Hvis denne forbindelse lykkes, kan du fortsætte til næste trin. Ellers skal du gennemse de tidligere trin i dette dokument for at sikre, at de er blevet afsluttet korrekt, eller gennemse afsnittet med fejlfinding nedenfor. Bemærk! Hvis du ikke kan oprette forbindelse til SAP BW-serveren via SSO i denne kontekst, så kan du ikke oprette forbindelse til SAP BW-serveren ved hjælp af SSO i gatewaykonteksten.

### <a name="add-registry-entries-to-the-gateway-machine"></a>Føj registreringsdatabaseposter til gatewaycomputeren

Føj krævede registreringsdatabaseposter til registreringsdatabasen på den maskine, som gatewayen er installeret på, samt til maskiner, der er beregnet til at oprette forbindelse fra Power BI Desktop. Her er de kommandoer, der skal køres:

1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

### <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service-or-edit-an-existing-one"></a>Føj en ny datakilde for SAP BW-programserveren til Power BI-tjenesten, eller rediger en eksisterende

1. I vinduet til konfiguration af datakilde skal du angive programserverens **værtsnavn**, **systemnummer** og **klient-id**, på samme måde som du ville, når du logger på din SAP BW-server fra Power BI Desktop.

1. I feltet **SNC-partnernavn** skal du angive p: \<det SPN, du knyttede til din SAP BW-tjenestebruger\>. Hvis SPN f.eks. er SAP/BWServiceUser@MYDOMAIN.COM, skal du angive p:SAP/BWServiceUser@MYDOMAIN.COM i feltet **SNC-partnernavn**.

1. For SNC-biblioteket skal du vælge **SNC_LIB** eller **SNC_LIB_64**. Kontrollér, at SNC_LIB_64 på gatewaycomputeren peger på gx64krb5.dll. Alternativt kan du vælge indstillingen "Brugerdefineret" og angive den fulde sti til gx64krb5.dll (på gatewaycomputeren).

1. Markér feltet **Brug SSO via Kerberos til DirectQuery-forespørgsler**, og vælg **Anvend**. Hvis testen af forbindelsen ikke fuldføres, skal du kontrollere, at de forrige trin til installation og konfiguration blev udført korrekt.

1. [Kør en Power BI-rapport](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>Fejlfinding

### <a name="troubleshoot-gx64krb5gsskrb5-configuration"></a>Foretag fejlfinding af konfigurationen af gx64krb5/gsskrb5

Hvis du støder på problemer, skal du følge disse trin for at foretage fejlfinding af installationen af gx64krb5/gsskrb5 og SSO-forbindelser fra SAP Logon.

* Det kan være nyttigt at få vist serverlogge (…work\dev\_w0 på servercomputeren) i forbindelse med fejlfinding af evt. fejl, du måtte støde på under fuldførelse af trinnene til konfiguration af gx64krb5/gsskrb5. Dette er især tilfældet, hvis SAP BW-serveren ikke starter, efter profilparametrene er blevet ændret.

* Hvis du ikke kan starte SAP BW-tjenesten på grund af en logonfejl, har du muligvis angivet en forkert adgangskode ved angivelsen af "start som" bruger i SAP BW. Bekræft adgangskoden ved at logge på en computer i dit Active Directory-miljø som SAP BW-tjenestebrugeren.

* Hvis du får vist fejl om legitimationsoplysninger til SQL, der forhindrer serveren i at starte, skal du kontrollere, at du har givet tjenestebrugeren adgang til SAP BW-databasen.

* Du får muligvis vist følgende meddelelse: "(GSS-API) Den angivne destination er ukendt eller kan ikke nås". Det betyder normalt, at du har angivet det forkerte SNC-navn. Sørg for kun at bruge "p:" og ikke "p:CN=" eller andet i klientprogrammet ud over tjenestebrugerens UPN.

* Du får muligvis vist følgende meddelelse: "(GSS-API) Der blev angivet et ugyldigt navn". Sørg for, at "p:" er i værdien for serverens profilparameter for SNC-identitet.

* Du får muligvis vist følgende meddelelse: "(SNC fejl) Det angivne modul blev ikke fundet". Dette skyldes som regel, at `gsskrb5.dll/gx64krb5.dll` er blevet placeret et sted, hvor der kræves rettigheder som administrator for at få adgang.

### <a name="troubleshoot-gateway-connectivity-issues"></a>Fejlfinding af problemer med gatewayforbindelse

1. Se loggene til gatewayen. Åbn programmet til konfiguration af gatewayen, og vælg **Diagnosticering** > **Eksportér logge**. De nyeste fejl vises nederst i de logfiler, du undersøger.

    ![Skærmbillede af programmet Datagateway i det lokale miljø med Diagnosticering fremhævet](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. Slå SAP BW-sporing til, og gennemse de genererede logfiler. Der findes flere forskellige typer SAP BW-sporing. Du kan få flere oplysninger i dokumentationen til SAP.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om **datagateway i det lokale miljø** og **DirectQuery** i følgende ressourcer:

* [Hvad er en datagateway i det lokale miljø?](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
