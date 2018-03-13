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
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: cc50e4e8830aca3951da6004b8ada3913aff28ed
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/28/2018
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
| [Aster-diagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft-kalender](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [Butterflydiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Kasse med hale-diagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [Kasse med hale-diagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [Murstensdiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Boblediagram fra Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [Punkttegnsdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [Punkttegnsdiagram fra OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Kalender fra Tallan](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [Lysestange fra OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [Kort med tilstand fra OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [Firkantudsnitsværktøj](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [Korde](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [Cirkulær måler fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Klyngekort](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [Clustering](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380861) | |
| [Clustering med udenforliggende værdier](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380889) | |
| [Korrelationsdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380814) | |
| [Cylindrisk måler fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Beslutningstrædiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380817) | |
| [Skivemåler](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [Prikdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [Punktvisning af OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Detaljeret kartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [Detaljeret fladekort](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [Søjlediagram med detailudledning](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Søjlediagram med detailudledning for tidsbaserede data](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Kransediagram med detailudledning](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dobbelt-KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [Forbedret punktdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlighten-akvarie](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [Enlighten-udsnitsværktøj](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Enlighten-stakblanding](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten-vaffeldiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Force-styret graf](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [Prognose-TBATS](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326) | |
| [Prognose med ARIMA](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380888) | |
| [Tragtformet diagram med kilde fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [Ganttdiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Globus med datalinjer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [Hierarkidiagram fra Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Histogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [Histogram med punkter fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [Horisontalt tragtformet diagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [Billede fra CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Billedgitter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Infographic Designer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [KPI-diagram fra Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [KPI-indikator](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [KPI-ticker fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [Lineær måler fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [LineDot-diagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Mekko-diagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [Afspilningsakse (dynamisk udsnitsværktøj)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power-KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power-KPI-matrix](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Kvadrantdiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Radardiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [Cirkeldiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [Roterende diagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey-diagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Rulning](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [Smartfilter fra OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline af OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Sløjfediagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380860) | |
| [Stream-graf](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [Heatmaptabel](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Omdrejningstæller](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Tekstfilter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [Tekstombrydning fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Termometer](https://appsource.microsoft.com/en-us/product/office/WA104379807) | |
| [Diagram med tidsserieopdeling](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [Diagram med tidsserieprognose](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380816) | |
| [Tidslinjeudsnitsværktøj](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tornadodiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Handelsdiagram fra MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimativt afvigelsesdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ultimativt vandfaldsdiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [Liste over brugere fra CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Vaffeldiagram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Ordcloud](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>Næste trin
[Introduktion til udviklerværktøjerne til brugerdefinerede visualiseringer (prøveversion)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Microsofts brugerdefinerede afspilningsliste for visualiseringer på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualiseringer i Power BI](power-bi-report-visualizations.md)  
[Brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals.md)  
[Publicer brugerdefinerede visualiseringer i Microsoft AppSource](developer/office-store.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

