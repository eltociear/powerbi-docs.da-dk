---
title: Fejlfinding af, hvordan man udvikler en brugerdefineret visualisering i Power BI
description: I denne artikel beskrives nogle almindelige problemer, som kan opstå under udviklingen eller oprettelsen af en brugerdefineret visualisering i Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: troubleshooting
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: bfdca7f5652106271ba46f0cffd2759b7b4595eb
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485616"
---
# <a name="troubleshoot-power-bi-visuals"></a>Fejlfind visualiseringer i Power BI

## <a name="debug"></a>Fejlfind

**Pbivi-kommando blev ikke fundet (eller tilsvarende fejl)**

Når du kører `pbiviz` i terminalens kommandolinje, bør du få vist hjælpeskærmen. Hvis det ikke er tilfældet, er den ikke installeret korrekt. Sørg for, at du har mindst 4.0-versionen af NodeJS installeret.

**Hvis du ikke kan finde visualiseringen til fejlfinding på fanen Visualiseringer**

Visual for fejlfinding ligner et prompt-ikon på fanen **Visualiseringer**.

![Valg af visualisering](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Hvis du ikke kan se det, skal du sørge for, at det er aktiveret i Power BI-indstillingerne.

> [!NOTE]
> Visual for fejlfinding findes kun i Power BI-tjenesten og ikke i Power BI Desktop eller mobilappen. Det pakkede visual fungerer stadig overalt.

**Det var ikke muligt at kontakte serveren med dit visual**

Kør visualiseringsserveren med kommandoen `pbiviz start` i terminalens kommandoline fra roden afvisualiseringsprojektet. Hvis serveren ikke kører, er det sandsynligt, at SSL-certifikaterne ikke er installeret korrekt.

Du er meget velkommen til at kontakte supportteamet for Power BI-visuals (pbicvsupport@microsoft.com), hvis du har spørgsmål, kommentarer eller problemer.

## <a name="next-steps"></a>De næste trin

Du kan finde flere oplysninger under [Ofte stillede spørgsmål om Power BI-visualiseringer](power-bi-custom-visuals-faq.md#organizational-power-bi-visuals).