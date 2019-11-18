---
title: Ændringslog for Power BI-rapportserver
description: Denne ændringslog er for Power BI-rapportserver, og den viser nye elementer sammen med fejlrettelser til hvert frigivet build.
ms.author: jaimeta
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/25/2019
ms.openlocfilehash: 0a4aaa5d9fcb3d5dab6cce0b0c8dd6034581aedb
ms.sourcegitcommit: 17f45a81b0dcbf9e3f1fb2a551584170baecd320
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/25/2019
ms.locfileid: "72922550"
---
# <a name="change-log-for-power-bi-report-server"></a>Ændringslog for Power BI-rapportserver

Denne ændringslog er for Power BI-rapportserver, og den viser nye elementer sammen med fejlrettelser til hvert frigivet build.

Hvis du vil have detaljerede oplysninger om nye funktioner, skal du se [Nyheder i Power BI-rapportserver](whats-new.md). 

## <a name="september-2019"></a>September 2019
- **Power BI-rapportserver**
    - *Version: 1.6.7236.4246 (build 15.0.1102.646), udgivet: 25. oktober 2019*
        - Sikkerhedsopdateringer
        - Fejlrettelser
            - Rettelse til et problem, hvor .NET Framework 4.7 ikke er installeret.
            - Rettelse til sideinddelte rapporter for Teradata med parametre for flere værdier med fejl 110083.
            - Rettelse til URLRoot-værdien, som ikke fungerer, hvis der er flere bindinger af URL-adresser for webtjenesten, og en af dem er http://+80/reportserver.
          - Rettelse til sideinddelte rapporter med parametre for flere værdier, der vises uden for rapportområdet.
          
    - *Version: 1.6.7221.30698 (Build 15.0.1102.620), udgivet: 9. oktober 2019*
        - Fejlrettelser
            - Rettelse til den brugerdefinerede visualisering Tekstfilter.
            - Rettelse af ydeevnen for rullelisteudsnitsværktøjer.
            - Rettelse til Strip PII fra telemetri.
          - Rettelse af URL-adresser, så der ikke skelnes mellem store og små bogstaver.
          
    - *Version 1.6.7206.38019 (build 15.0.1102.597), udgivet: 26. september 2019*
        - Sikkerhedsopdateringer
        - Fejlrettelser
           - Sideinddelte rapporter
             - Rettelse af tilgængelighedsproblemer, der opstod under brug af Internet Explorer og Microsoft Edge.
             - Rettelse af problemer med SAP HANA, mens forbindelsen testes.
             - Rettelse af problemer, der blev fundet under levering af en liste over mailadresser.
             - Rettelse til Power BI-rapporter, der bruger en DirectQuery-datakilde og integreret godkendelse.
             - Rettelse til sideinddelte rapporter, der skal gengives med filterparametre, når et snapshot er aktiveret.
             - Rettelse til dobbelt udførelse af gemte procedurer under udførelse af en rapport.
             - Rettelse til standardtjenestekontoen, der tildeles SQL Server-logontilladelser, når den brugerdefinerede tjenestekonto er konfigureret til at køre Power BI-rapportserver.
             - Rettelse til adgang til modeller, mens der opdateres i en japansk tidszone.
             - Rettelse til forældede modeller, når en ny version af rapporten uploades under en opdatering.
             - Rettelse til parameterværdier, der indeholder "&"-tegnet.
         - Programmering
             - Opdateret web-API: /PowerBIReports({Id})/DataSources (PATCH), som tillader opdatering af forbindelsesstrenge.
         
- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.73.5586.1501 (september 2019), udgivet: 25. oktober 2019*
        - Fejlrettelser
            - Rettelse til telemetri.
            
    - *Version: 2.73.5586.1241 (september 2019), udgivet: 9. oktober 2019*
        - Fejlrettelser
            - Rettelse til den brugerdefinerede visualisering Tekstfilter.
            - Rettelse af ydeevnen for rullelisteudsnitsværktøjer.
            - Rettelse til Strip PII fra telemetri.
            
    - *Version: 2.73.5586.821 (september 2019), udgivet: 26. september 2019* (nyt build og ny version)
        - Indeholder ændringer, der kræves for at oprette forbindelse til Power BI-rapportserver (september 2019)

    
## <a name="may-2019"></a>Maj 2019

- **Power BI-rapportserver**          
    - *Version 1.5.7074.36177 (build 15.0.1102.371), udgivet: 21. maj 2019*
        - Fejlrettelser
            - Sideinddelte rapporter
                - Rettelse, så integrering af skrifttyper i PDF altid aktiveres.
                - Rettelse for at angive cookies, der sendes via https som sikre
                - Rettelse af problemer med pop op-vinduer på grund af scriptfejl
                - Rettelse af visningsproblemer med mobilappen på Android-telefoner
                - Rettelse af tidsnavigator i mobilrapporten, så det korrekte ugenummer vises, uanset hvornår regnskabsåret begynder
                - Den konfigurerbare egenskab "RestrictedResourceMimeTypeForUpload" blev tilføjet, så administratorer kan angive forbudte MIME-typer
         - Funktioner
            - Understøttelse af visualiseringer, der er tillid til, er føjet til PBIRS

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.69.5467.1801 (maj 2019), udgivet: 21. maj 2019*
        - Fejlrettelser
            - Rettelse for at undgå gentagen angivelse af legitimationsoplysninger under upload af PBIX til PBIRS
            - Rettelser til åbning af dokumenter med # i filnavnet
            - Nemmere link i forbindelse med at navigere tilbage er føjet til vinduet Valg i PBIRS
            - Rettelse til tilstanden Høj kontrast i PBIRS, så knappen Tilbage vises, vis visuelle advarselsmeddelelser.
            - Rettelser af brugergrænsefladen for ruden Valg, skalering af lærred.

    - *Version: 2.69.5467.5201 (maj 2019), udgivet: Juli 30, 2019*
        - Fejlrettelser
            - Rettelse af forkert telemetri-logføring

## <a name="january-2019"></a>Januar 2019

- **Power BI-rapportserver**          
    - *Version 1.4.7024.16477 (build 15.0.1102.299), udgivet: 28. marts 2019*
        - Fejlrettelser
            - Power BI-rapporter
                - Rettelse af en fejl i grundlæggende legitimationsoplysninger, når en direkte forespørgsel bruges i forbindelse med SAP Hana og SAP BW
                - Rettelse af en fejl i forbindelse med dataopdatering af OData-feed, hvor der står "Filen eller assemblyen "Microsoft.OData.Core.NetFX35.V7" kunne ikke indlæses"

- **Power BI-rapportserver**            
    - *Version 1.4.6969.7395 (Build 15.0.1102.235), udgivet: 30. januar 2019*
        - Fejlrettelser
            - Power BI-rapporter
                - Rettelse af problem med grundlæggende legitimationsoplysninger, når du bruger en direkte forespørgsel
                - Rettelse af tovejsrelationer med anvendte sikkerhedsfiltre på rækkeniveau
                - Rettelse af forældede data efter modelopdatering i et udskaleringsmiljø
                - Rettelse af dobbelt rullepanel for tabel/matrix i Firefox 63+
                - Rettelse af +/-ikonstørrelse i Internet Explorer
            - Sideinddelte rapporter
                - Rettelse af problem med opdatering af brugen af en delt datakilde i en rapport

    - *Version 1.4.6960.38798 (Build 15.0.1102.222), udgivet: 22. januar, 2019*
        - Funktioner
            - Power BI-rapporter 
                - Understøttelse af sikkerhed på rækkeniveau
                - Udvid og skjul i matrixrækkeoverskrifter
                - Kopiér og indsæt mellem .pbix-filer
                - Smarte justeringshjælpelinjer
                - Understøttelse af SAP BW 2.0 Connector
            - Administratorer
                - Mulighed for at begrænse udvidelser til ressourcer, der kan uploades til rapportserveren
                - Mulighed for at begrænse understøttede linkskemaer
            - Programmering
                - Ny Web-API: /PowerBIReports({Id})/DataModelRoles (GET)
                - Ny Web-API: /PowerBIReports({Id})/DataModelRoleAssignments (GET & PUT)
                - Du kan få flere detaljer i [REST API til Power BI-rapportserver](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)
        - Fejlrettelser
            - Sikkerhedsrisiko ved HTML-indskydelse
            - Eksport til PDF-fil viser ikke Euro-symbolet
            - Lagring af en adgangskode med flere datakilder i Power BI-rapporter gør adgangskoder, der ikke er blevet ændret, ugyldige
            - Problemer med visning af visuelle elementer i Power BI-mobilappen

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.65.5313.1562 (januar 2019), udgivet: 30. januar 2019*
        - Genvej og fastgjorte ikoner bevares efter fjernelse af Power BI-rapportserver
        - Rettelse af fastgørelse af Power BI-rapportserver til startmenuen, som medfører sort tekst på et sort ikon

    - *Version: 2.65.5313.1421 (januar 2019), udgivet: Januar 22, 2019* (nyt build og ny version)
        - Indeholder ændringer, der er påkrævet for at oprette forbindelse til Power BI-rapportserver (januar 2019) 
    - *Version: 2.65.5313.5141 (januar 2019), udgivet: Juli 31, 2019* (nyt build og ny version)
        - Fejlrettelser
            - Rettelse af forkert telemetri-logføring

## <a name="august-2018"></a>August 2018

- **Power BI-rapportserver**
    - *Version 1.3.6816.37243 (Build 15.0.2.557), udgivet: 30. august, 2018*
        - Fejlrettelser
            - Der er løst et problem, der opstod, når serveren blev opgraderet fra tidligere versioner af PBI Report Server, hvor en omdirigering af en binding ikke blev opdateret, så kunderne så dette:      
            *`
            Failed to load expression host assembly. Details: Could not load file or assembly 'Microsoft.ReportingServices.ProcessingObjectModel, Version=2018.7.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040) (rsErrorLoadingExprHostAssembly)
             `*
             
            - Fejl i gennemsigtighed af datamærkat er nu løst.
            
    - *Version 1.3.6801.38816 (Build 15.0.2.540), udgivet: 15. august, 2018*
        - Funktioner
            - SAP HANA SSO Direct Query understøttes nu med Kerberos for Power BI-rapporter
            - Brugerdefineret Visual API udgivet sammen med frigivelsen, version 1.13.0
            - Brugerdefinerede visualiseringer går tilbage til en tidligere version, der er kompatibel med den aktuelle version af server-API'et (hvis tilgængeligt)

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.61.5192.641 (august 2018), udgivet: 15. august, 2018*
        - Indeholder ændringer, der kræves for at oprette forbindelse til Power BI-rapportserver (august 2018)         
    - *Version: 2.61.5192.7701 (august 2018), udgivet: 8. august 2019* (nyt build og ny version)
        - Fejlrettelser
            - Rettelse af forkert telemetri-logføring
            
## <a name="march-2018"></a>Marts 2018

- **Power BI-rapportserver**
    - *Version 1.2.6690.34729 (Build 15.0.2.402), udgivet: 27. april, 2018*
        - Fejlrettelser
            - Aktivér overførsel af SQL Server Reporting Services 2017-kataloger
            - Power BI-rapporter (PBIX)
                - Rapporter kan opdateres, når en server konfigureres til at anvende brugerdefineret godkendelse
                - Hvis du ændrer egenskaberne for en rapport, nulstilles legitimationsoplysningerne for datakilden ikke
            - Sideinddelte rapporter (RDL)
                - Brug af `Lookup()` eller afledte funktioner som `LookupSet()` og `MultiLookup()` i RDL-udtryk resulterer ikke længere i `#Error`
                - Sammenkædede rapporter respekterer sidestørrelsen for destinationsrapporten under udskrivning
                - Der kan oprettes abonnementer for sammenkædede rapporter, der bruger overlappende parametre
                - Standarder for parametre med flere værdier kan ændres, når du bruger IE11
                - Leveringsindstillingerne for datadrevet abonnement kan redigeres
                - Abonnementer kan ses og redigeres under kørsel af abonnementet
                - Hvis der angives legitimationsoplysninger for datakilden, fjernes udtryksbaserede forbindelsesstrenge ikke
            - KPI'er
                - Tendenslinjer opdateres, når data opdateres
            - Generelle forbedringer af stabilitet

    - *Version 1.2.6660.39920 (Build 15.0.2.389), udgivet: 28. marts 2018*
        - Fejlrettelser
            - Til Power BI-rapporter (PBIX): Programrettelse af Eksport data, der ikke virker i forbindelse med Power BI-visualiseringer
            - Til Power BI-rapporter (PBIX): Programrettelse af URL-filtre, der ikke virker
            - Til sideinddelte rapporter (RDL): Programrettelse af billeder, der ikke vises korrekt i IE 11 efter opgraderingen til udgaven af Power BI-rapportserver fra marts

    - *Version 1.2.6648.38132 (Build 15.0.2.378), udgivet: 19. marts 2018*
        - Sikkerhedsopdateringer
        - Forbedringer af Hjælp til handicappede
        - Fejlrettelser
            - Rettelse af et problem med parametersynlighed for sideinddelte rapporter (RDL) ved genindlæsning efter en redigering af rapportegenskaber
            - Rettelse af et problem på webportalen, hvor cookien for glidende udløb ignoreres ved godkendelse af brugerdefinerede formularer
            - Rettelse af et problem, hvor der oprettes forskellige rækkehøjder ved eksport til Word, hvis rækkeindholdet er tomt
            - Rettelse af et problem for sideinddelte rapporter (RDL), hvor en udtryksbaseret forbindelsesstreng slettes, når datakildens legitimationsoplysninger ændres
            - Rettelse af et problem, så det nu er muligt at anvende KPI'er med tekstværdier
            - Rettelse af et problem for sideinddelte rapporter (RDL), så det nu er muligt at føje et nyt datasæt til en eksisterende sideinddelt rapport (RDL)
            - Rettelse af andre problemer med stabilitet og brugervenlighed

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - Version: 2.56.5023.1043 (marts 2018), udgivet: 19. marts 2018
        - Indeholder ændringer, der kræves for at oprette forbindelse med Power BI-rapportserver (marts 2018)

## <a name="october-2017"></a>Oktober 2017

- **Power BI-rapportserver**
    - *Version 1.1.6582.41691 (Build 14.0.600.442), udgivet: 10. januar, 2018*
        - Sikkerhedsopdateringer
        - Fejlrettelser
            - Rettelse til Model.GetParameters, der returnerer 400
            - Rettelse til angivelsen af delte datasæt til eksisterende sideinddelte rapporter (RDL)
            - Rettelse til ExecutionNotFoundException, når du eksporterer en rapport med forskellige parameterværdier til PDF-fil

    - *Version 1.1.6551.5155 (Build 14.0.600.438), udgivet: 11. december, 2017*
        - Fejlrettelser
            - Der kunne ikke gemmes data efter opdatering til bestemte Power BI Desktop-rapporter.

    - *Version 1.1.6530.30789 (Build 14.0.600.437), udgivet: 17. november, 2017*
        - Fejlrettelser
            - Rettelse til grundlæggende godkendelsesscenarier 
            - Rettelse af ugedage, som ikke kunne vælges på siden med tidsplan for abonnementer, planer for opdatering af cache og snapshots af historik på portalen
            - For sideinddelte rapporter (RDL) er der foretaget en rettelse i tilfælde af udtryk i et tekstfelt med egenskaben .KanStrækkes indstillet til falsk, som medfører, at værdier ikke viser farver, og at skrifttyperne ikke er rigtige
            - For Power BI-rapporter (PBIX) er der foretaget en rettelse for at løse et problem, hvor der vises et tomt visuelt element, når der føjes forklaringer til et kurvediagram

    - *Version 1.1.6514.9163 (Build 14.0.600.434), udgivet: 1. november, 2017*
        - Fejlrettelser
            - Rettelse af problemer med pålideligheden ved upload af PBIX-rapporter på mere end 500 MB
            - Rettelse af problem med indlæsning af data i PBIX-rapporter på mere end 1 GB

    - *Version 1.1.6513.3500 (Build 14.0.600.433), udgivet: 31. oktober, 2017*
        - Funktioner
            - Integreret understøttelse af datamodel
            - Visning af Excel-projektmapper (med Office Online Server-integration aktiveret)
            - Planlagt dataopdatering (PBIX)
            - Understøttelse af direkte forespørgsler
            - Understøttelse af store filer (op til 2 GB)
            - Offentlig REST-API
            - Understøttelse af delte datasæt i Power BI Desktop (via oData)
            - Understøttelse af URL-parameter til PBIX-filer
            - Forbedringer af Hjælp til handicappede

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.51.4885.3981 (oktober 2017), udgivet: 10. april, 2018*
        - Sikkerhedsopdateringer

    - *Version: 2.51.4885.2501 (oktober 2017), udgivet: 10. januar, 2018*
        - Sikkerhedsopdateringer

    - *Version: 2.51.4885.1423 (oktober 2017), udgivet: 17. november, 2017*
        - Fejlrettelser
            - Rettelse af 32-bit Power BI Desktop, som ikke kunne køre på x86-operativsystemer
            - For Power BI-rapporter (PBIX): rettelse til visning af x-aksens gitterlinjer
            - Andre mindre fejlrettelser

    - *Version: 2.51.4885.1041 (oktober 2017), udgivet: 31. oktober, 2017*
        - Funktioner
            - Indeholder ændringer, der kræves for at oprette forbindelse med Power BI-rapportserver (oktober 2017)

## <a name="june-2017"></a>Juni 2017

- **Power BI-rapportserver**
    - *Build 14.0.600.309, udgivet: 10. januar, 2018*
        - Sikkerhedsopdateringer

    - *Build 14.0.600.305, udgivet: 19. september, 2017*  
        - Fejlrettelser
            - Opdatering til den seneste [Bing Maps Web Control](https://msdn.microsoft.com/library/mt712542.aspx)

    - *Build 14.0.600.301, udgivet: 11. juli, 2017*
        - Fejlrettelser
            - Koden `{{UserId}}` fortolkes som de gemte legitimationsoplysninger i stedet for den bruger, der kører rapporten i Power BI-rapporter
            - Nogle billeder gengives ikke i rapporter i Power BI-rapportserver
            - Det var ikke muligt at ændre navnet på en Power BI-rapport i Power BI-rapportserver
            - Der kunne ikke indlæses brugerdefinerede visuelle elementer i Power BI-mobilappen (det kræver geninstallation af mobilappen for at rydde op i det lokale cachelager)

    - *Build 14.0.600.271,udgivet: 12. juni, 2017*
        - Første udgivelse af Power BI-rapportserver

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.47.4766.4901 (juni 2017), udgivet: 10. januar, 2018*
        - Sikkerhedsopdateringer

## <a name="next-steps"></a>Næste trin

[Hvad er Power BI-rapportserveren?](get-started.md)
[Administratoroversigt](admin-handbook-overview.md)  
[Installer Power BI-rapportserver](install-report-server.md)  
[Download Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
