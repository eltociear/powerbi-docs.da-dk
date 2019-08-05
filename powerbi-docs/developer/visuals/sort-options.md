---
title: Sortér
description: Standardfunktionsmåde for sortering i Power BI-visualisering.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f3d913e2bce34850dfae4c9486b2e43c78521a58
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424510"
---
# <a name="sorting-options"></a>Sorteringsindstillinger

`Sorting` angiver standardfunktionsmåden for sortering i visualiseringen.
Egenskaben kræver en af parametrene, der er beskrevet nedenfor:

## <a name="default-sorting"></a>Standardsortering

Indstillingen `default` er den enkleste form. Den muliggør sortering af de data, der præsenteres i afsnittet "DataMappings".
Denne indstilling giver brugeren mulighed for at sortere "DataMappings" og angive sorteringsretningen.

```json
    "sorting": {
        "default": {   }
    }
```

![Sorteringsindstillinger i genvejsmenuen](./media/sorting.png)

## <a name="implicit-sorting"></a>Implicit sortering

`implicit` sorterer med en matrixparameter – `clauses`, der beskriver, hvordan der sorteres efter hver datarolle.
`implicit` betyder, at brugeren af visualiseringen ikke kan ændre sorteringsrækkefølgen.
Der vises ikke sorteringsindstillinger i visualiseringens menu i Power BI. Men Power BI sorterer data i henhold til de angivne indstillinger.

Parametrene `clauses` kan indeholde flere objekter med to parametre:

- `role` – bestemmer `DataMapping` for sortering.

- `direction` – bestemmer sorteringsretningen (1 = stigende, 2 = faldende).

```json
    "sorting": {
        "implicit": {
            "clauses": [
                {
                    "role": "category",
                    "direction": 1
                },
                {
                    "role": "measure",
                    "direction": 2
                }
            ]
        }
    }
```

## <a name="custom-sorting"></a>Brugerdefineret sortering

`custom` betyder, at sorteringen administreres af udvikleren i visualiseringens kode.
