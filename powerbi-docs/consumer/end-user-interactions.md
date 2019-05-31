---
title: Forstå, hvordan visualiseringer interagerer i en rapport
description: Dokumentation til Power BI-slutbrugere, der forklarer, hvordan visualiseringer interagerer på en rapportside.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7148a52d7c7475fbe685f83b1e1cc325521460db
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413146"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Sådan krydsfiltrerer visualiseringer hinanden i en Power BI-rapport
En af de fantastiske funktioner i Power BI er den måde, som alle visualiseringer på rapportside er forbundet på. Hvis du vælger et datapunkt i en af visualiseringerne, ændres alle andre visualiseringer med disse data på siden på baggrund af dette valg. 

![video af interaktion mellem visualiseringer](media/end-user-interactions/interactions.gif)

Som standard, hvis du vælger et datapunkt i én visualisering på en rapportside vil tværgående filtrering, tværgående fremhævning, og analysere de andre visualiseringer på siden. 

Dette kan være nyttigt at identificere hvordan én værdi i dine data, der bidrager til en anden. F.eks, at vælge redigering segmentet i kransediagram, fremhæves bidraget fra dette segment til hver kolonne i de enheder i alt efter måned diagrammet, og det har filtreret kurvediagrammet til højre.

![Billede af visuelle elementer interaktion](media/end-user-interactions/power-bi-interactions.png)

Se [Om filtrering og fremhævning](../power-bi-reports-filters-and-highlighting.md). 

Lige præcis hvordan visualiseringerne på en side interagerer på, angives af *designeren* af rapporten. Designere har mulighed for at slå interaktion mellem visualiseringer til og fra og ændre standardfunktionsmåden for tværgående filtrering, tværgående fremhævning og analysering. 
  
> [!NOTE]
> Begreberne *tværgående filter* og *tværgående fremhævning* bruges til at skelne mellem den funktionsmåde, der er beskrevet her, og hvad der sker, når du bruger ruden **Filtre** til at filtrere og fremhæve visualiseringer.  

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- Hvis rapporten indeholder en visualisering, der understøtter [detailudledning](../power-bi-visualization-drill-down.md), som standard foretager detailudledning i én visualisering har ingen indvirkning på de andre visualiseringer på rapportsiden.     
- Hvis du bruger visualA til at interagere med visualB, anvendes filtre på visualiseringsniveau fra visualA til visualB.

## <a name="next-steps"></a>Næste trin
[Sådan bruger du rapportfiltre](../power-bi-how-to-report-filter.md)
