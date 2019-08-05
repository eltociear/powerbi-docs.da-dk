---
title: Hent flere data
description: Aktivér segmenteret hentning af store datasæt for Power BI-visualiseringer
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bc8ff673927fd66bf44164e4e9950c279b98c6c1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425062"
---
# <a name="fetch-more-data-from-power-bi"></a>Hent flere data fra Power BI

API'en til indlæsning af flere data tilsidesætter den faste grænse på 30.000 datapunkter. Så får du dataene i dele. Størrelsen af delene kan konfigureres for at forbedre ydeevnen i henhold til brugscasen.  

## <a name="enable-segmented-fetch-of-large-datasets"></a>Aktivér segmenteret hentning af store datasæt

I segmenteringstilstanden `dataview` skal du definere et "vindue" for dataReductionAlgorithm i visualiseringens `capabilities.json` for den påkrævede dataViewMapping.
`count` fastsætter størrelsen af vinduet, hvilket begrænser antallet af nye datarækker, der kan føjes til `dataview` ved hver opdatering.

Skal føjes til capabilities.json

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

## <a name="usage-in-the-custom-visual"></a>Brug i den brugerdefinerede visualisering

Du kan se om indikationsdataene findes ved at tjekke om `dataView.metadata.segment` findes:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Det er også muligt at kontrollere, om det er den første eller en efterfølgende opdatering ved at tjekke `options.operationKind`.

`VisualDataChangeOperationKind.Create` betyder det første segment, og `VisualDataChangeOperationKind.Append` betyder efterfølgende segmenter.

Se kodestykket nedenfor for at se et eksempel på implementering:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subesquent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

Metoden `fetchMoreData` kan også aktiveres fra en hændelsesmanager i brugergrænsefladen

```typescript
btn_click(){
{
    // check if more data is expected for the current dataview
    if (dataView.metadata.segment) {
        //request for more data if available, as resopnce Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example when the 100 MB limit has been reached
        }
    }
}
```

Power BI kalder metoden `update` for visualiseringen med et nyt datasegment som et svar på at kalde metoden `this.host.fetchMoreData`.

> [!NOTE]
> Power BI begrænser for øjeblikket det samlede antal hentede data til **100 MB** for at undgå begrænsninger i klientens hukommelse. Du kan registrere, at denne grænse nås, når fetchMoreData() returnerer "false".*
