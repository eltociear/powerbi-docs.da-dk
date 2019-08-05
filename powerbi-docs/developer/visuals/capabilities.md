---
title: Egenskaber
description: Funktioner og egenskaber for visuelle elementer i Power BI
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f6bb4293a44f98f2f8098fb197c7b406b618d211
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425453"
---
# <a name="power-bi-visual-capabilities"></a>Egenskaber for visuelle elementer i Power BI

Egenskaber indeholder oplysninger til værten om din visualisering. Alle egenskaber i modellen Egenskaber er `optional`

Rodobjekter for visualiseringernes egenskaber er `dataRoles`, `dataViewMappings` osv.

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "advancedEditModeSupport": 0|1|2,
    "sorting": { ... }
}

```

## <a name="define-the-data-fields-your-visual-expects---dataroles"></a>Definer de datafelter, som din visualisering forventer – `dataRoles`

Hvis du vil definere felter, der kan bindes til data, skal du bruge `dataRoles`, der omfatter en matrix med `DataViewRole`-objekter, som definerer alle de egenskaber, der er behov for.

### <a name="properties"></a>Egenskaber

* **name** –det interne navn på dette datafelt (skal være entydigt).
* **kind** – feltets type:
    * `Grouping` – diskrete værdier, der bruges til gruppering af målingsfelter.
    * `Measure` – numeriske dataværdier
    * `GroupingOrMeasure` – kan bruges som enten en gruppering eller en måling.
* **displayName** – det navn, der vises for brugeren i ruden Egenskaber.
* **description** – en kort beskrivelse af feltet (valgfrit).
* **requiredTypes** – den påkrævede datatype for denne datarolle. Alle værdier, der ikke stemmer overens, indstilles til NULL (valgfrit).
* **preferredTypes** – den foretrukne datatype for denne datarolle (valgfrit).

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>Gyldige datatyper i "requiredTypes" og "preferredTypes"

* **bool** – en boolesk værdi
* **Integer** – en heltalsværdi (heltal)
* **numeric** – en numerisk værdi
* **text** – en tekstværdi
* **geography** – geografiske data

### <a name="example"></a>Eksempel

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": "Grouping",
        "requiredTypes": [
            {
                "text": true
            },
            {
                "numeric": true
            },
            {
                "integer": true
            }
        ],
        "preferredTypes": [
            {
                "text": true
            }
        ]
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": "Measure",
        "requiredTypes": [
            {
                "integer": true
            },
            {
                "numeric": true
            }
        ],
        "preferredTypes": [
            {
                "integer": true
            }
        ]
    },
    {
        "displayNameKey": "Visual_Location",
        "name": "Locations",
        "kind": "Measure",
        "displayName": "Locations",
        "requiredTypes": [
            {
                "geography": {
                    "address": true
                }
            },
            {
                "geography": {
                    "city": true
                }
            },
            {
                "geography": {
                    "continent": true
                }
            },
            {
                "geography": {
                    "country": true
                }
            },
            {
                "geography": {
                    "county": true
                }
            },
            {
                "geography": {
                    "place": true
                }
            },
            {
                "geography": {
                    "postalCode": true
                }
            },
            {
                "geography": {
                    "region": true
                }
            },
            {
                "geography": {
                    "stateOrProvince": true
                }
            }
        ]
    }
]
```

Ovenstående dataroller opretter følgende felter

![Visning af datarolle](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped---dataviewmappings"></a>Definer, hvordan du vil have dataene tilknyttet – `dataViewMappings`

En DataViewMapping beskriver, hvordan datarollerne er relateret til hinanden, og giver dig mulighed for at angive betingede krav til dem.

De fleste visualiseringer rummer en enkelt tilknytning, men du kan angive flere dataViewMappings. Hver af de gyldige tilknytninger opretter en DataView. 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[Få mere at vide om DataViewMappings](dataview-mappings.md)

## <a name="define-property-pane-options---objects"></a>Definer indstillinger for egenskabsrude – `objects`

Objekter beskriver de egenskaber, der kan tilpasses, og som er knyttet til den pågældende visualisering.
Hvert objekt kan have flere egenskaber, og hver egenskab har en type tilknyttet.
Typerne refererer til det, som egenskaben vil være. Se nedenfor for at få flere oplysninger om typer.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[Få mere at vide om objekter](objects-properties.md)

## <a name="handle-partial-highlighting---supportshighlight"></a>Håndter delvis fremhævning – `supportsHighlight`

Denne værdi er som standard angivet til falsk, hvilket betyder, at "værdier" filtreres automatisk, når noget på siden vælges, hvilket opdaterer visualiseringen, så den kun viser den valgte værdi. Hvis du vil have vist alle dataene, men kun fremhæve de valgte elementer, skal du angive `supportsHighlight` til sand i capabilities.json.

[Få mere at vide om fremhævning](highlight.md)

## <a name="handle-advanced-edit-mode---advancededitmodesupport"></a>Håndter avanceret redigeringstilstand – `advancedEditModeSupport`

En visualisering kan erklære sin understøttelse af avanceret redigeringstilstand.
En visualisering understøtter ikke som standard avanceret redigeringstilstand, medmindre andet er angivet i capabilities.json.

[Få mere at vide om advancedEditModeSupport](advanced-edit-mode.md)

## <a name="data-sorting-options-for-visual---sorting"></a>Indstillinger for datasortering for visualisering – `sorting`

Sorteringsfunktionsmåden for en visualisering kan defineres via visualiseringens egenskaber.
En visualisering understøtter ikke som standard ændring af sorteringsrækkefølgen, medmindre andet er angivet i capabilities.json.

[Få mere at vide om sortering](sort-options.md)
