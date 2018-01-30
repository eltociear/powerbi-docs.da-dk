---
title: Certificerede brugerdefinerede Power BI-visualiseringer
description: Krav og proces til afsendelse af en brugerdefineret visualisering til certificering. Og en liste over allerede certificerede brugerdefinerede visualiseringer.
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
ms.openlocfilehash: 90449f79da8aed3d992b9ac8bf83ac2ac4c0f83c
ms.sourcegitcommit: 2ae323fbed440c75847dc55fb3e21e9c744cfba0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/23/2018
---
# <a name="getting-a-custom-visual-certified"></a>Sådan får du en brugerdefineret visualisering *certificeret*
## <a name="what-is-meant-by-certified"></a>Hvad menes der med *certificeret*?
En *certificeret visualisering* er en visualisering, der opfylder et sæt af kodekrav, og som har bestået strenge sikkerhedstests.  Når en brugerdefineret visualisering er blevet certificeret, kan den [eksporteres til PowerPoint](service-publish-to-powerpoint.md) og vises i modtagne mails, når en bruger [abonnerer på rapportsider](service-report-subscribe.md). Den kan selvfølgelig også bruges som [brugerdefinerede visuelle standardelementer](power-bi-custom-visuals.md), føjes til Power BI-tjenesten og Power BI Desktop-rapporter og vises i Power BI-mobil og integreret.

Er du webudvikler og interesseret i at oprette dine egne visualiseringer og føje dem til [Microsoft AppSource](https://appsource.microsoft.com)? Du kan få mere at vide om, hvordan du gør, under [Introduktion til Udviklerværktøj](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Certificeringskrav
* Godkendt af Microsoft AppSource    
* Den brugerdefinerede visualisering er skrevet med Versioned API 1.2 eller nyere    
* Der er et kodelager tilgængeligt til gennemsyn (f.eks. Visual code, der er tilgængeligt for os via GitHub)    
* Anvender kun OSS-komponenter, der kan gennemses offentligt    
* Har ikke adgang til eksterne tjenester eller ressourcer    

> **TIP**! Det anbefales, at du bruger EsLint med det sikkerhedsregelsæt, der anvendes som standard, til at forudvalidere koden før indsendelse.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Processen for indsendelse af en brugerdefineret visualisering til certificering
Sådan indsender du en brugerdefineret visualisering til certificering:

1. Send en mail til Support for brugerdefinerede Power BI-visualiseringer (pbicvsupport@microsoft.com). Du skal inkludere følgende oplysninger i mailen:    
   
   * Titel: Anmodning om certificering af visualisering    
   * Link til GitHub-lageret, der hoster visualiseringens kildekode    
   * Overhold kravene (se ovenfor)    
   * Bestå gennemgangen af koden og sikkerheden    
2. Microsofts team for brugerdefinerede visualiseringer giver dig besked, når din brugerdefinerede visualisering er certificeret og føjet til listen over certificerede visualiseringer (nedenfor) eller afvises med en rapport over de problemer, der skal løses. Det er udviklerens ansvar at vedligeholde en åben kommunikationslinje med Microsoft og opdatere deres godkendte visualiseringer efter behov.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Fjernelse af certificerede brugerdefinerede Power BI-visualiseringer
Microsoft kan, efter eget skøn, fjerne en visualisering fra listen over godkendte visualiseringer.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Liste over brugerdefinerede visualiseringer, der er blevet certificeret
| Link til AppSource | Link til video |
| --- | --- |
| [Tilknytningsregler](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Aster-feltdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar (Beyondsoft-kalender)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Butterflydiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Video](https://youtu.be/So5xKMSpVJI) |
| [Kasse med hale](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Murstensdiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | |
| [Boblediagram fra Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340?src=office) | |
| [Punkttegnsdiagram](https://store.office.com/app.aspx?assetid=WA104380755) |[Video1](https://youtu.be/AOlsFYkfkcw)   [Video2](https://youtu.be/AQvd2FhRyCI) |
| [Punkttegnsdiagram fra OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Video](https://youtu.be/mtvUNl9bMjA) |
| [Kalender fra Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [Lysestange fra OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | |
| [Firkantudsnitsværktøj](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Video](https://youtu.be/iYOkJ1APueY) |
| [Akkorddiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Cirkulær måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Cylindrisk måler](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Skivemåler](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Kransdiagram (ringdiagram) af MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Video](https://youtu.be/pDToHDFHnq8) |
| [Dot Plot fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381101) | |
| [Punktvisning af OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Video](https://youtu.be/4lskRgcpFJY) |
| [Dot Plot fra Microsoft](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760?src=office) | |
| [Analysekransdiagram af ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Detaljeret kartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045?src=office) | |
| [Detaljeret fladekort](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044?src=office) | |
| [Analysesøjlediagram fra ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881?src=office) | |
| [Analysesøjlediagram for tidsbaserede data fra ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | |
| [Analyseskransdiagram fra ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dobbelt-KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Video](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Forbedret punktdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | |
| [Enlighten-akvarie](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| [Enlighten-boblestak](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380868) | |
| [Enlighten-udsnitsværktøj](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960?tab=Overview) | |
| [Enlighten-stakblanding](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten-vaffeldiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Enlighten-verdens flag](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380923) | |
| [Prognose-TBATS](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326?src=office) | |
| [Tragt med kilde]() | || [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Video](https://youtu.be/qJ7s_KrGiUU) |
| [Hierarkidiagram fra Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333?src=office) | |
| [Histogram](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Vandret tragt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Video](https://youtu.be/SudZei68PPo) |
| [Billedtidslinje](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [Infographic Designer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898?src=office) | |
| [KPI-indikator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [KPI-ticker fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | |
| [LineDot-diagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766?src=office) | |
| [Lineær måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Mekko-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Video](https://youtu.be/90FLCKpgicA)|
| [Afspilningsakse (dynamisk udsnitsværktøj)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power-KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Video](https://youtu.be/IvfIP3E6-1Q) |
| [Impulsdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | |
| [Radardiagram](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Ringdiagram (kransdiagram) af MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Video](https://youtu.be/pDToHDFHnq8)|
| [Roterende diagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007?src=office) |  |
| [Sankey-diagram](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Video](https://youtu.be/WWP9wVUHGaA) |
| [Rulning](https://store.office.com/scroller-WA104381018.aspx) |[Video](https://youtu.be/uhRFQF2cGSY) |
| [Smartfilter af SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline af OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Video](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Heatmaptabel](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Omdrejningstæller](https://store.office.com/tachometer-WA104380937.aspx?) |[Video](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Tekstombryder](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Termometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Video](https://youtu.be/SPX9mgrAdBc)|
| [Tidsserieopdeling](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Tidslinjeudsnitsværktøj](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tornadodiagram](https://store.office.com/tornado-chart-WA104380768.aspx) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Ultimate-variansdiagram af Klaus Birringer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140?src=office) | |
| [Ultimate-vandfald gratis](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | |
| [VitaraCharts - MicroChart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381165) | |
| [Vaffeldiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Video](https://youtu.be/1vRqYUsm3Vk) |
| [Ordcloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Video](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Næste trin
[Introduktion til udviklerværktøjerne til brugerdefinerede visualiseringer (prøveversion)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Microsofts brugerdefinerede afspilningsliste for visualiseringer på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualiseringer i Power BI](power-bi-report-visualizations.md)  
[Brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals.md)  
[Publicer brugerdefinerede visualiseringer i Microsoft AppSource](developer/office-store.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

