---
title: Tilføj funktionen Synkroniser udsnitsværktøjer i Power BI-visualiseringer
description: I denne artikel beskrives det, hvordan du føjer funktionen Synkroniser udsnitsværktøjer til visualiseringer i Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 055878988a197b80a8e4842a6567966f75af2ce5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880132"
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
