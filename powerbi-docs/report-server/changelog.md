---
title: Ændringslog for Power BI-rapportserver
description: Denne ændringslog er for Power BI-rapportserver, og den viser nye elementer sammen med fejlrettelser til hvert frigivet build.
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 03/31/2018
ms.author: jtarquino
ms.openlocfilehash: ec97676fc043f9d8bd014465cc1fd2c0ffcca423
ms.sourcegitcommit: 52278d8e0c23ae5eaf46b10a6a2f1fb071a0f1cc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2018
ms.locfileid: "40257190"
---
# <a name="changelog-for-power-bi-report-server"></a>Ændringslog for Power BI-rapportserver

Denne ændringslog er for Power BI-rapportserver, og den viser nye elementer sammen med fejlrettelser til hvert frigivet build.

Hvis du vil have detaljerede oplysninger om nye funktioner, skal du se [Nyheder i Power BI-rapportserver](whats-new.md). 

## <a name="august-2018"></a>August 2018
- **Power BI-rapportserver**
    - *Version 1.3.6801.38816 (build 15.0.2.540), frigivet: 15. august 2018*
        - Funktioner
            - SAP HANA SSO Direct Query understøttes nu med Kerberos for Power BI-rapporter
            - Brugerdefineret Visual API udgivet sammen med frigivelsen, version 1.13.0
            - Brugerdefinerede visualiseringer går tilbage til en tidligere version, der er kompatibel med den aktuelle version af server-API'et (hvis tilgængeligt)

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.61.5192.64 (august 2018), frigivet: 15. august 2018*
        - Indeholder ændringer, der kræves for at oprette forbindelse til Power BI-rapportserver (august 2018)         
        
## <a name="march-2018"></a>Marts 2018
- **Power BI-rapportserver**
    - *Version 1.2.6690.34729 (Build 15.0.2.402), udgivet: 27. april 2018*
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
    - *Version 1.1.6582.41691 (Build 14.0.600.442), udgivet: 10. januar 2018*
        - Sikkerhedsopdateringer
        - Fejlrettelser
            - Rettelse til Model.GetParameters, der returnerer 400
            - Rettelse til angivelsen af delte datasæt til eksisterende sideinddelte rapporter (RDL)
            - Rettelse til ExecutionNotFoundException, når du eksporterer en rapport med forskellige parameterværdier til PDF-fil

    - *Version 1.1.6551.5155 (Build 14.0.600.438) udgivet: 11. december 2017*
        - Fejlrettelser
            - Der kunne ikke gemmes data efter opdatering til bestemte Power BI Desktop-rapporter.

    - *Version 1.1.6530.30789 (Build 14.0.600.437), udgivet: 17. november 2017*
        - Fejlrettelser
            - Rettelse til grundlæggende godkendelsesscenarier 
            - Rettelse af ugedage, som ikke kunne vælges på siden med tidsplan for abonnementer, planer for opdatering af cache og snapshots af historik på portalen
            - For sideinddelte rapporter (RDL) er der foretaget en rettelse i tilfælde af udtryk i et tekstfelt med egenskaben .KanStrækkes indstillet til falsk, som medfører, at værdier ikke viser farver, og at skrifttyperne ikke er rigtige
            - For Power BI-rapporter (PBIX) er der foretaget en rettelse for at løse et problem, hvor der vises et tomt visuelt element, når der føjes forklaringer til et kurvediagram

    - *Version 1.1.6514.9163 (Build 14.0.600.434), udgivet: 1. november 2017*
        - Fejlrettelser
            - Rettelse af problemer med pålideligheden ved upload af PBIX-rapporter på mere end 500 MB
            - Rettelse af problem med indlæsning af data i PBIX-rapporter på mere end 1 GB

    - *Version 1.1.6513.3500 (Build 14.0.600.433), udgivet: 31. oktober 2017*
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
    - *Version: 2.51.4885.3981 (oktober 2017), udgivet: 10. april 2018*
        - Sikkerhedsopdateringer

    - *Version: 2.51.4885.2501 (oktober 2017), udgivet: 10. januar 2018*
        - Sikkerhedsopdateringer

    - *Version: 2.51.4885.1423 (oktober 2017), udgivet: 17. november 2017*
        - Fejlrettelser
            - Rettelse af 32-bit Power BI Desktop, som ikke kunne køre på x86-operativsystemer
            - For Power BI-rapporter (PBIX): rettelse til visning af x-aksens gitterlinjer
            - Andre mindre fejlrettelser

    - *Version: 2.51.4885.1041 (oktober 2017), udgivet: 31. oktober 2017*
        - Funktioner
            - Indeholder ændringer, der kræves for at oprette forbindelse med Power BI-rapportserver (oktober 2017)

## <a name="june-2017"></a>Juni 2017

- **Power BI-rapportserver**
    - *Build 14.0.600.309, udgivet: 10. januar 2018*
        - Sikkerhedsopdateringer

    - *Build 14.0.600.305, udgivet: 19. september 2017*  
        - Fejlrettelser
            - Opdatering til den seneste [Bing Maps Web Control](https://msdn.microsoft.com/library/mt712542.aspx)

    - *Build 14.0.600.301, udgivet: 11. juli 2017*
        - Fejlrettelser
            - Koden `{{UserId}}` fortolkes som de gemte legitimationsoplysninger i stedet for den bruger, der kører rapporten i Power BI-rapporter
            - Nogle billeder gengives ikke i rapporter i Power BI-rapportserver
            - Det var ikke muligt at ændre navnet på en Power BI-rapport i Power BI-rapportserver
            - Der kunne ikke indlæses brugerdefinerede visuelle elementer i Power BI-mobilappen (det kræver geninstallation af mobilappen for at rydde op i det lokale cachelager)

    - *Build 14.0.600.271, udgivet: 12. juni 2017*
        - Første udgivelse af Power BI-rapportserver

- **Power BI Desktop (optimeret til Power BI-rapportserver)**
    - *Version: 2.47.4766.4901 (juni 2017), udgivet 10. januar 2018*
        - Sikkerhedsopdateringer

## <a name="next-steps"></a>Næste trin

[Hvad er Power BI-rapportserveren?](get-started.md)
[Administratoroversigt](admin-handbook-overview.md)  
[Installer Power BI-rapportserver](install-report-server.md)  
[Installér Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
