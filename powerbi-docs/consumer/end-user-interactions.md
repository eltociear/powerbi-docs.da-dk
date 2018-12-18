---
title: Forstå, hvordan visualiseringer interagerer i en rapport
description: Dokumentation til Power BI-slutbrugere, der forklarer, hvordan visualiseringer interagerer på en rapportside.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 406f1f6428d5ce26401720220eaffe32314a9bbd
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280414"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Sådan krydsfiltrerer visualiseringer hinanden i en Power BI-rapport
En af de fantastiske funktioner i Power BI er den måde, som alle visualiseringer på rapportside er forbundet på. Hvis du vælger et datapunkt i en af visualiseringerne, ændres alle andre visualiseringer med disse data på siden på baggrund af dette valg. 

![video af interaktion mellem visualiseringer](media/end-user-interactions/interactions.gif)

Som standard kan visualiseringer på en rapportside bruges til tværgående filtrering, tværgående fremhævning og analysering af de andre visualiseringer på siden. Hvis du f.eks. vælger en delstat på en kortvisualisering, fremhæves søjlediagrammet måske, og kurvediagrammet filtreres, så der kun vises data, som gælder for denne ene delstat.

Se [Om filtrering og fremhævning](../power-bi-reports-filters-and-highlighting.md). Og hvis du har en visualisering, der understøtter [detailudledning](../power-bi-visualization-drill-down.md) som standard, har det ingen indvirkning på andre visualiseringer på rapportsiden, at du foretager detailudledning i én visualisering. 

Lige præcis hvordan visualiseringerne på en side interagerer på, angives af *designeren* af rapporten. Designere har mulighed for at slå interaktion mellem visualiseringer til og fra og ændre standardfunktionsmåden for tværgående filtrering, tværgående fremhævning og analysering.
  
> [!NOTE]
> Begreberne *tværgående filter* og *tværgående fremhævning* bruges til at skelne mellem den funktionsmåde, der er beskrevet her, og hvad der sker, når du bruger ruden **Filtre** til at filtrere og fremhæve visualiseringer.  

### <a name="next-steps"></a>Næste trin
[Sådan bruger du rapportfiltre](../power-bi-how-to-report-filter.md)
