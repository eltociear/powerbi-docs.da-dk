---
title: Basisområdediagram
description: Basisområdediagram.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 02d81a4ebb92ec199887109c7f2d9afcb6449eda
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54276117"
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
 - Power BI-tjenesten
 - Eksempel på analyse af detailhandel

Log på Power BI for at følge fremgangsmåden, og vælg **Hent Data \>Eksempler \> Eksempel på detailhandelsanalyse > Opret forbindelse**, og vælg **Gå til dashboard**. 

## <a name="create-a-basic-area-chart"></a>Opret et basisområdediagram
 

1. Vælg feltet **Butikker i alt** fra dashboardet "Eksempel på detailhandelsanalyse" for at åbne rapporten "Eksempel på detailhandelsanalyse".
2. Vælg **Rediger rapport** for at åbne rapporten i redigeringsvisning.
3. Tilføj en ny rapport ved at vælge det gule plusikon (+) nederst i rapporten.
4. Opret et områdediagram, der viser dette års salg og sidste års salg pr. måned.
   
   a. I ruden FELTER skal du vælge **Salg \> Sidste års salg** og **Dette års salg > Værdi**.

   ![](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  Konvertér diagrammet til et grundlæggende områdediagram ved at vælge ikonet Områdediagram i ruden Visualiseringer.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Vælg **Tid \> Måned** for at føje det til **Akse**.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Hvis du vil vise diagrammet pr. måned, skal du vælge ellipsemenuen (øverst til højre i visualiseringen) og vælge **Sortér efter måned**. Hvis du vil ændre sorteringsrækkefølgen, skal du vælge ellipsen igen og vælge enten **Sortér stigende** eller **Sortér faldende**.

## <a name="highlighting-and-cross-filtering"></a>Fremhævning og krydsfiltrering
Du kan få mere at vide om brug af ruden Filters under [Føj et filter til en rapport](../power-bi-report-add-filter.md).

For at fremhæve et bestemt område i diagrammet skal du markere dette område eller dets øverste kant.  Hvis der er andre visualiseringer på samme side, vil den i modsætning til andre visualiseringstyper ikke krydsfiltrere med de andre visualiseringer på rapportsiden, når et grundlæggende område markeres. Områdediagrammer kan dog krydsfiltreres af andre visualiseringer på rapportsiden. 

1. Prøv det selv ved at vælge dit områdediagram og kopiere det til en anden rapportside (Ctrl + C og Ctrl + V).
2. Vælg det ene af de nedtonede områder og derefter det andet nedtonede område. Bemærk, at det ikke påvirker de øvrige visualiseringer på siden.

    ![Dette års salg valgt i områdediagram](media/power-bi-visualization-basic-area-chart/power-bi-select-area.png)

3. Nu skal du vælge et element på en af de andre visualiseringer på siden, f.eks. en søjle i et søjlediagram eller en måned i et kurvediagram. Læg mærke til, hvordan det påvirker områdediagrammet – det bliver filtreret.  

    ![Det liggende søjlediagram FT Oglethorpe valgt](media/power-bi-visualization-basic-area-chart/power-bi-filter.png) 

Hvis du vil vide mere, kan du se [Visuelle interaktioner i rapporter](../service-reports-visual-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding   
* [Gør rapporten tilgængelig for personer med handicap](../desktop-accessibility.md)
* Basisområdediagrammer er ikke velegnede til sammenligning af værdier på grund af blokeringer på de lagdelte områder. Der bruges gennemsigtighed i Power BI til at angive overlapning af områder. Det virker dog bedst, hvis der kun er to eller tre forskellige områder. Hvis du vil sammenligne en udvikling med mere end tre mål, kan du prøve at bruge kurvediagrammer. Hvis du vil sammenligne en mængde med mere end tre mål, kan du prøve at bruge træstrukturdiagrammer.

## <a name="next-step"></a>Næste trin
[Rapporter i Power BI](power-bi-visualization-card.md)  

