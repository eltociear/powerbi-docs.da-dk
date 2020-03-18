---
title: Avanceret redigeringstilstand i Power BI-visualiseringer
description: I denne artikel beskrives det, hvordan du angiver avancerede kontrolelementer til brugergrænsefladen i Power BI-visualiseringer.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 97242883fe90c8f5e115818a24e4bb1c49f69b77
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380546"
---
# <a name="advanced-edit-mode-in-power-bi-visuals"></a>Avanceret redigeringstilstand i Power BI-visualiseringer

Hvis du har brug for avancerede kontrolelementer til brugergrænsefladen i din Power BI-visualisering, kan du benytte dig af avanceret redigeringstilstand. Når du er i redigeringstilstand for en rapport, vælger du knappen **Rediger** for at indstille redigeringstilstanden til **Avanceret**. En visualisering kan bruge flaget `EditMode` til at bestemme, om dette kontrolelement skal vises.

Som standard understøtter visualiseringen ikke avanceret redigeringstilstand. Hvis der kræves en anden funktionsmåde, kan du angive dette eksplicit i visualiseringens *capabilities.json*-fil ved at angive egenskaben `advancedEditModeSupport`.

De mulige værdier er:

- `0` - NotSupported

- `1` - SupportedNoAction

- `2` - SupportedInFocus

## <a name="enter-advanced-edit-mode"></a>Start avanceret redigeringstilstand

Knappen **Rediger** vises, hvis:

* Egenskaben `advancedEditModeSupport` i filen *capabilities.json* er indstillet til enten `SupportedNoAction` eller `SupportedInFocus`.

* Visualiseringen vises i redigeringstilstand for rapporten.

Hvis egenskaben `advancedEditModeSupport` mangler i filen *capabilities.json* eller er angivet til `NotSupported`, forsvinder knappen **Rediger**.

![Åbning af redigeringstilstand](media/advanced-edit-mode/edit-mode.png)

Når du vælger **Rediger**, får det visuelle element et opdateringskald(), hvor EditMode er angivet til `Advanced`. Afhængigt af den værdi, der er angivet i filen *capabilities.json*, udføres følgende handlinger:

* `SupportedNoAction`: Der kræves ingen yderligere handling af værten.
* `SupportedInFocus`: Værten fremviser visualiseringen i fokustilstand.

## <a name="exit-advanced-edit-mode"></a>Afslut avanceret redigeringstilstand

Knappen **Tilbage til rapport** vises, hvis:

* Egenskaben `advancedEditModeSupport` i filen *capabilities.json* er indstillet til `SupportedInFocus`.
