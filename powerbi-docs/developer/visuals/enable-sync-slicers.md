---
title: Tilføj funktionen Synkroniser udsnitsværktøjer i Power BI-visualiseringer
description: I denne artikel beskrives det, hvordan du føjer funktionen Synkroniser udsnitsværktøjer til visualiseringer i Power BI.
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 4d7b73a5d06f34fd197464d4444d0e19d6c1c026
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237200"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Synkroniser udsnitsværktøjer i visualiseringer i Power BI

For at understøtte funktionen [Synkroniser udsnitsværktøjer](https://docs.microsoft.com/power-bi/desktop-slicers) skal dit brugerdefinerede visuelle udsnit bruge API-version 1.13 eller nyere.

Derudover skal du aktivere indstillingen i filen *capabilities.json* som vist i følgende kode:

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

Når du har opdateret filen *capabilities.json*, kan du få vist ruden med indstillinger for **Synkroniser udsnitsværktøjer**, når du vælger det brugerdefinerede visuelle udsnit.

> [!NOTE]
> Funktionen Synkroniser udsnitsværktøjer understøtter ikke mere end ét felt. Hvis udsnittet har mere end ét felt (**kategori** eller **måling**), er funktionen deaktiveret.

![Ruden "Synkroniser udsnit"](./media/sync-slicers-panel.png)

I ruden **Synkroniser udsnit** kan du se, at synligheden af og filtreringen med dit udsnit muligvis er anvendt på flere rapportsider.
