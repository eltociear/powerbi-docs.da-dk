---
title: Avanceret redigeringstilstand
description: Power BI-visualiseringer med avancerede kontrolelementer i brugergrænsefladen
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 625105aed773bce5cf70932f092faf60ea001c2c
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425545"
---
# <a name="advanced-edit-mode"></a>Avanceret redigeringstilstand

Visualiseringer, der kræver avancerede kontrolelementer i brugergrænsefladen, kan deklarere understøttelse af Avanceret redigeringstilstand.
Hvis den understøttes, vises knappen `Edit` i visualiseringens menu i redigeringstilstand for rapporten.
Når der klikkes på knappen `Edit`, angives EditMode til `Advanced`.
Visualiseringen kan bruge EditMode-flaget til at bestemme, hvilke kontrolelementer i brugergrænsefladen der skal vises.

Som standard understøtter visualiseringen ikke Avanceret redigeringstilstand.
Hvis der kræves en anden funktionsmåde, skal den angives eksplicit i visualiseringens `capabilities.json`-fil ved at angive egenskaben `advancedEditModeSupport`.

De mulige værdier er:

- 0 – NotSupported

- 1 – SupportedNoAction

- 2 – SupportedInFocus

## <a name="entering-advanced-edit-mode"></a>Åbning af Avanceret redigeringstilstand

Knappen `Edit` er synlig, hvis:

 1 – egenskaben `advancedEditModeSupport` under capabilities.json er angivet til enten `SupportedNoAction` eller `SupportedInFocus`.

 2 – visualiseringen vises i redigeringstilstand for rapporten.

Hvis egenskaben `advancedEditModeSupport` mangler under capabilities.json eller er angivet til `NotSupported`, forsvinder knappen "Rediger".

![Åbning af redigeringstilstand](./media/edit-mode.png)

Når brugeren klikker på `Edit`, modtager visualiseringen kaldet update(), hvor EditMode er angivet til `Advanced`.
I henhold til værdierne, der er angivet under egenskaberne, sker følgende handlinger:

* `SupportedNoAction` – Der kræves ingen yderligere handling af værten.
* `SupportedInFocus` – Værten fremviser visualiseringen i fokustilstand.

## <a name="exiting-advanced-edit-mode"></a>Afslutning af Avanceret redigeringstilstand

Knappen `Back to report` er synlig, hvis:

1 – egenskaben `advancedEditModeSupport` under capabilities.json er angivet til `SupportedInFocus`.
