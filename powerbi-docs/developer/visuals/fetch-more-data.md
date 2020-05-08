---
title: Hent flere data fra Power BI
description: I denne artikel gennemgås det, hvordan segmenteret hentning af store datasæt for Power BI-visualiseringer aktiveres.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 6c79673e9d4b7edc95bdfe0373bb8a47d9fe587b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380680"
---
# <a name="fetch-more-data-from-power-bi"></a>Hent flere data fra Power BI

I denne artikel beskrives det, hvordan du indlæser flere data for at overskride den faste grænse for et datapunkt på 30 KB. Denne fremgangsmåde omfatter data i segmenter. Hvis du vil forbedre ydeevnen, kan du konfigurere segmentstørrelsen, så den passer til din use case.  

## <a name="enable-a-segmented-fetch-of-large-datasets"></a>Aktivér en segmenteret hentning af store datasæt

I segmenteringstilstanden `dataview` skal du definere et vindue for dataReductionAlgorithm i visualiseringens *capabilities.json*-fil for den påkrævede dataViewMapping. `count` fastsætter størrelsen af vinduet, hvilket begrænser antallet af nye datarækker, der kan føjes til `dataview` ved hver opdatering.

Tilføj følgende kode i filen *capabilities.json*:

```typescript
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "window": {
                        "count": 100
                    }
                }
            }
    }
]
```

Nye segmenter føjes til den eksisterende `dataview` og leveres til visualiseringen som et `update`-kald.

## <a name="usage-in-the-power-bi-visual"></a>Brug i visualiseringer i Power BI

Du kan se, om dataene findes, ved at kontrollere forekomsten af `dataView.metadata.segment`:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Du kan også se, om det er den første eller en efterfølgende opdatering, ved at kontrollere `options.operationKind`. I følgende kode refererer `VisualDataChangeOperationKind.Create` til det første segment, mens `VisualDataChangeOperationKind.Append` refererer til efterfølgende segmenter.

Se følgende kodestykke for at se et eksempel på implementering:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subsequent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

Du kan også aktivere metoden `fetchMoreData` fra en hændelsesmanager for brugergrænsefladen som vist her:

```typescript
btn_click(){
{
    // check if more data is expected for the current data view
    if (dataView.metadata.segment) {
        //request for more data if available; as a response, Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

Som svar på kald af metoden `this.host.fetchMoreData` kalder Power BI metoden `update` for det visuelle element med et nyt datasegment.

> [!NOTE]
> Power BI begrænser i øjeblikket det samlede antal hentede data til 100 MB for at undgå begrænsninger af klientens hukommelse. Du kan se, at grænsen er nået, når fetchMoreData() returnerer `false`.
