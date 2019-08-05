---
title: Aktivér Synkroniser udsnit
description: Sådan tilføjer du funktionen Synkroniser udsnit for Power BI-visualiseringer
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9966475e8bcaccad2090451b47ef09ef0a9af125
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425016"
---
# <a name="sync-slicers"></a>Synkroniser udsnit

Din brugerdefinerede visualisering skal bruge API 1.13 eller nyere for at understøtte [Synkroniser udsnit](https://docs.microsoft.com/power-bi/desktop-slicers).

Derudover er det nødvendigt at aktivere indstillingen i `capabilities.json` (se eksemplet nedenfor).

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

Når du har foretaget ændringer i `capabilities.json`, kan du se panelet med indstillinger for Synkroniser udsnit, når du klikker på den brugerdefinerede visualisering med udsnit.

> [!NOTE]
> Hvis der er mere end ét felt i udsnittet (kategori eller måling), deaktiveres funktionen, for Synkroniser udsnit understøtter ikke flere felter.

![Panelet Synkroniser udsnit](./media/sync-slicers-panel.png)

På panelet kan du se, at synligheden af og filtreringen med dit udsnit muligvis er anvendt på flere rapportsider.
