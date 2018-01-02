---
title: "Ændringslog for Power BI-rapportserver"
description: "Denne ændringslog er for Power BI-rapportserver, og den viser nye elementer sammen med fejlrettelser til hvert frigivet build."
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: maggies
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/17/2017
ms.author: jaimeta
ms.openlocfilehash: e56976943e58aba8c9ef36c576a16ab5eba4c796
ms.sourcegitcommit: 7d4ad2ba92a932d7cc6637348e0774be6623559e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/18/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Ændringslog for Power BI-rapportserver

Denne ændringslog er for Power BI-rapportserver, og den viser nye elementer sammen med fejlrettelser til hvert frigivet build.

Hvis du vil have detaljerede oplysninger om nye funktioner, skal du se [Nyheder i Power BI-rapportserver](whats-new.md).

## <a name="october-2017"></a>Oktober 2017

- **Power BI-rapportserver**
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
    - *Build 14.0.600.305, udgivet: 19. september 2017*  
        - Fejlrettelser
            - Opdatering til den seneste [Bing Maps Web Control](https://msdn.microsoft.com/library/mt712542.aspx)

    - *Build 14.0.600.301, udgivet: 11. juli 2017*
        - Fejlrettelser
            - Koden {{UserId}} fortolkes som de gemte legitimationsoplysninger i stedet for den bruger, der kører rapporten i Power BI-rapporter
            - Nogle billeder gengives ikke i rapporter i Power BI-rapportserver
            - Det var ikke muligt at ændre navnet på en Power BI-rapport i Power BI-rapportserver
            - Der kunne ikke indlæses brugerdefinerede visuelle elementer i Power BI-mobilappen (det kræver geninstallation af mobilappen for at rydde op i det lokale cachelager)

    - *Build 14.0.600.271, udgivet: 12. juni 2017*
        - Første udgivelse af Power BI-rapportserver

## <a name="next-steps"></a>Næste trin

[Brugerhåndbog](user-handbook-overview.md)  
[Administratorhåndbog](admin-handbook-overview.md)  
[Hurtig introduktion: Installér Power BI-rapportserver](quickstart-install-report-server.md)  
[Installér Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)