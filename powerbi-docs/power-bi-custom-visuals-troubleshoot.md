---
title: Fejlfinding af, hvordan man udvikler en brugerdefineret visualisering i Power BI
description: I denne artikel beskrives nogle almindelige problemer, som kan opstå under udviklingen eller oprettelsen af en brugerdefineret visualisering i Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: troubleshooting
ms.date: 11/06/2018
ms.openlocfilehash: d1897c010cb275e1f44077ca00e6448e5ee05ab2
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874522"
---
# <a name="troubleshoot-power-bi-power-bi-visuals"></a>Foretag fejlfinding af visualiseringer i Power BI

## <a name="debug"></a>Fejlfinding

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

Du er meget velkommen til at kontakte supportteamet til Power BI-visualiseringer: *pbicvsupport@microsoft.com*  , hvis du har spørgsmål, kommentarer eller problemer.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger under [Ofte stillede spørgsmål om Power BI-visualiseringer](power-bi-custom-visuals-faq.md#organizational-visuals).