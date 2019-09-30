---
title: Forstå, hvordan visualiseringer interagerer i en rapport
description: Dokumentation til Power BI-slutbrugere, der forklarer, hvordan visualiseringer interagerer på en rapportside.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: b95df5c32d9058e4480d7af5e226a971ba581144
ms.sourcegitcommit: 02042995df12cc4e4b97eb8a369e62364eb5af36
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256290"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Sådan krydsfiltrerer visualiseringer hinanden i en Power BI-rapport
En af de fantastiske funktioner i Power BI er den måde, som alle visualiseringer på rapportside er forbundet på. Hvis du vælger et datapunkt i en af visualiseringerne, ændres alle andre visualiseringer med disse data på siden på baggrund af dette valg. 

![video af interaktion mellem visualiseringer](media/end-user-interactions/interactions.gif)

Hvis du vælger et datapunkt i én visualisering på en rapportside, udføres der som standard tværgående filtrering, tværgående fremhævning og analyse af de andre visualiseringer på siden. 

Det kan være nyttigt for at identificere, hvordan en værdi i dine data bidrager til en anden. Hvis du f.eks. vælger segmentet Redigering i kransediagrammet, fremhæves bidraget fra dette segment for de enkelte kolonner i diagrammet Antal enheder i alt efter måned, og kurvediagrammet til højre er filtreret.

![billede af interaktion mellem visualiseringer](media/end-user-interactions/power-bi-interactions.png)

Se [Om filtrering og fremhævning](../power-bi-reports-filters-and-highlighting.md). 

Lige præcis hvordan visualiseringerne på en side interagerer på, angives af *designeren* af rapporten. Designere har mulighed for at slå interaktion mellem visualiseringer til og fra og ændre standardfunktionsmåden for tværgående filtrering, tværgående fremhævning og analysering. 
  
> [!NOTE]
> Begreberne *tværgående filter* og *tværgående fremhævning* bruges til at skelne mellem den funktionsmåde, der er beskrevet her, og hvad der sker, når du bruger ruden **Filtre** til at filtrere og fremhæve visualiseringer.  

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- Hvis din rapport har en visualisering, der understøtter [detailudledning](../power-bi-visualization-drill-down.md), har det som standard ingen indvirkning på andre visualiseringer på rapportsiden, hvis du foretager detailudledning i én visualisering.     
- Hvis du bruger visual A til at interagere med visual B, anvendes der filtre på visualiseringsniveau fra visual A på visual B.

## <a name="next-steps"></a>Næste trin
[Sådan bruger du rapportfiltre](../power-bi-how-to-report-filter.md)
