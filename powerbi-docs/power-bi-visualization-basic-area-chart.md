---
title: "Basisområdediagram (selvstudium)"
description: "Selvstudium: Basisområdediagram."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 42e068b11c22c32f1a6736a6ca8f9020594fb40a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="basic-area-chart-tutorial"></a>Basisområdediagram (selvstudium)
Basisområdediagrammet (lagdelt områdediagram) er baseret på kurvediagrammet. Området mellem akse og kurve er udfyldt med farver for at angive mængde. 

Områdediagrammer fremhæver omfanget af ændringer over tid og kan bruges til at fremhæve den samlede værdi på tværs af en udvikling. Data, som repræsenterer indtjening over tid, kan f.eks. afbildes i et områdediagram for at fremhæve den samlede indtjening.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Brugsscenarier for et områdediagram
Basisområdediagrammer er et godt valg:

* Når du vil se og sammenligne mængdeudviklingen på tværs af tidsperioder. 
* Når du har enkelte perioder, der repræsenterer et sæt, som kan tælles fysisk.

## <a name="create-a-basic-area-chart"></a>Opret et basisområdediagram
Hvis du selv vil følge med og udføre trinnene i dette selvstudium, skal du logge på Power BI og vælge **Hent data \> Eksempler > \>Eksempel på detailhandelsanalyse**. 

1. Vælg feltet **Butikker i alt** fra dashboardet "Eksempel på detailhandelsanalyse" for at åbne rapporten "Eksempel på detailhandelsanalyse".
2. Vælg **Rediger rapport** for at åbne rapporten i Redigeringsvisning.
3. Tilføj en ny rapportside.
4. Opret et områdediagram, der viser dette års salg og sidste års salg pr. måned.
   
   a.  I ruden **Felter** skal du vælge **Salg \> Sidste års salg** og **Dette års salg > Værdi**.
   
   b.  Konvertér diagrammet til et basisområdediagram.    
   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Vælg **Tid \> Måned** for at føje det til **Akse**.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Hvis du vil vise diagrammet pr. måned, skal du vælge ellipsemenuen (øverst til højre i visualiseringen) og vælge **Sortér efter måned**.

## <a name="highlighting-and-cross-filtering"></a>Fremhævning og krydsfiltrering
Du kan få mere at vide om brug af ruden Filtre under [Føj et filter til en rapport](power-bi-report-add-filter.md).

Hvis du vil markere et område, skal du klikke i området eller langs den øverste linje.  Basisområdediagrammer krydsfiltrerer ikke de andre visualiseringer på rapportsiden. Områdediagrammer kan dog krydsfiltreres af andre visualiseringer på rapportsiden.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Basisområdediagrammer er ikke velegnede til sammenligning af værdier på grund af blokeringer på de lagdelte områder. Der bruges gennemsigtighed i Power BI til at angive overlapning af områder. Det virker dog bedst, hvis der kun er to eller tre forskellige områder. Hvis du vil sammenligne en udvikling med mere end tre mål, kan du prøve at bruge kurvediagrammer. Hvis du vil sammenligne en mængde med mere end tre mål, kan du prøve at bruge træstrukturdiagrammer.

## <a name="next-steps"></a>Næste trin
[Rapporter i Power BI](service-reports.md)  
[Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)  
[Power BI – grundlæggende begreber](service-basic-concepts.md)  
Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

