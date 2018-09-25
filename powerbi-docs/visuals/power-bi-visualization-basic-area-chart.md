---
title: Basisområdediagram
description: Basisområdediagram.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ddf08edf7494cd8b918a93d41b384b4e89376d95
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/21/2018
ms.locfileid: "46543336"
---
# <a name="basic-area-chart"></a>Basisområdediagram
Basisområdediagrammet (lagdelt områdediagram) er baseret på kurvediagrammet. Området mellem akse og kurve er udfyldt med farver for at angive mængde. 

Områdediagrammer fremhæver omfanget af ændringer over tid og kan bruges til at fremhæve den samlede værdi på tværs af en udvikling. Data, som repræsenterer indtjening over tid, kan f.eks. afbildes i et områdediagram for at fremhæve den samlede indtjening.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Brugsscenarier for et områdediagram
Basisområdediagrammer er et godt valg:

* Når du vil se og sammenligne mængdeudviklingen på tværs af tidsperioder. 
* Når du har enkelte perioder, der repræsenterer et sæt, som kan tælles fysisk.

### <a name="prerequisites"></a>Forudsætninger
 - Power BI-tjeneste
 - Eksempel på analyse af detailhandel

Log på Power BI for at følge fremgangsmåden, og vælg **Hent Data \>Eksempler \> Eksempel på detailhandelsanalyse > Opret forbindelse**, og vælg **Gå til dashboard**. 

## <a name="create-a-basic-area-chart"></a>Opret et basisområdediagram
 

1. Vælg feltet **Butikker i alt** fra dashboardet "Eksempel på detailhandelsanalyse" for at åbne rapporten "Eksempel på detailhandelsanalyse".
2. Vælg **Rediger rapport** for at åbne rapporten i redigeringsvisning.
3. Tilføj en ny rapport ved at vælge det gule plusikon (+) nederst i rapporten.
4. Opret et områdediagram, der viser dette års salg og sidste års salg pr. måned.
   
   a. I ruden FELTER skal du vælge **Salg \> Sidste års salg** og **Dette års salg > Værdi**.

   ![](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  Konvertér diagrammet til en grundlæggende områdediagram ved at vælge ikonet Områdediagram i ruden VISUALISERINGER.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Vælg **Tid \> Måned** for at føje det til **Akse**.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Hvis du vil vise diagrammet pr. måned, skal du vælge ellipsemenuen (øverst til højre i visualiseringen) og vælge **Sortér efter måned**.

## <a name="highlighting-and-cross-filtering"></a>Fremhævning og krydsfiltrering
Du kan få mere at vide om brug af ruden FILTRE under [Føj et filter til en rapport](../power-bi-report-add-filter.md).

For at fremhæve et bestemt område i diagrammet skal du markere dette område eller dets øverste kant.  Hvis der er andre visualiseringer på samme side, vil den i modsætning til andre visualiseringstyper ikke krydsfiltrere med de andre visualiseringer på rapportsiden, når et grundlæggende område markeres. Områdediagrammer kan dog krydsfiltreres af andre visualiseringer på rapportsiden. Hvis du vil vide mere, kan du se [Visuelle interaktioner i rapporter](../consumer/end-user-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding   
* [Gør rapporten tilgængelig for personer med handicap](../desktop-accessibility.md)
* Basisområdediagrammer er ikke velegnede til sammenligning af værdier på grund af blokeringer på de lagdelte områder. Der bruges gennemsigtighed i Power BI til at angive overlapning af områder. Det virker dog bedst, hvis der kun er to eller tre forskellige områder. Hvis du vil sammenligne en udvikling med mere end tre mål, kan du prøve at bruge kurvediagrammer. Hvis du vil sammenligne en mængde med mere end tre mål, kan du prøve at bruge træstrukturdiagrammer.

## <a name="next-steps"></a>Næste trin
[Rapporter i Power BI](../consumer/end-user-reports.md)  
[Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)  
[Power BI – grundlæggende begreber](../consumer/end-user-basic-concepts.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

