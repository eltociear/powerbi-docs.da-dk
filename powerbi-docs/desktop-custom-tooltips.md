---
title: Tilpasning af værktøjstips i Power BI Desktop
description: Opret brugerdefinerede værktøjstip for visualiseringer ved hjælp af træk og slip
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: efbae4250b7b3cab18892cf519bfac5da3a88e1b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73868659"
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Tilpasning af værktøjstips i Power BI Desktop
Værktøjstips er en elegant måde at angive flere oplysninger om kontekst og detaljer om datapunkter på i en visualisering. På følgende billede vises et værktøjstip, der er anvendt på et diagram i Power BI Desktop.

![Standardværktøjstip](media/desktop-custom-tooltips/custom-tooltips-1.png)

Når der oprettes en visualisering, viser standardværktøjstippet datapunktets værdi og kategori. Der er mange tilfælde, hvor tilpasning af oplysningerne i værktøjstip er nyttigt og give yderligere kontekst og oplysninger til brugere, der får vist visualiseringen. Med brugerdefinerede værktøjstips kan du angive yderligere datapunkter, der vises som en del af værktøjstippet.

## <a name="how-to-customize-tooltips"></a>Sådan tilpasser du værktøjstips
Du opretter et brugerdefineret værktøjstip på følgende måde: I brønden **Felter** i ruden **Visualiseringer** skal du trække et felt til den bucket, der hedder **Værktøjstips**, som vist på følgende billede. I det følgende billede er to felter blevet placeret i feltet **Værktøjstip**.

![Tilføj felter til værktøjstip](media/desktop-custom-tooltips/custom-tooltips-2.png)

Når du har føjet værktøjstip til feltet, vises værdierne for disse felter i værktøjstippet, når du peger med musen på et datapunkt i visualiseringen.

![Brugerdefineret værktøjstip](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Tilpasning af værktøjstips med sammenlægning eller Hurtig beregning
Du kan tilpasse et værktøjstip yderligere ved at vælge en sammenlægningsfunktion eller en *Hurtig beregning*. Det gør du ved at vælge pilen ved siden af feltet i den bucket, der hedder **Værktøjstips**, og vælge mellem de tilgængelige indstillinger.

![Værktøjstip med Hurtig beregning](media/desktop-custom-tooltips/custom-tooltips-4.png)

Der er mange måder at tilpasse **Værktøjstips** på ved hjælp af et hvilket som helst felt i dit datasæt, så du hurtigt kan vise oplysninger og levere indsigt til dine brugere, som får vist dine dashboards eller rapporter.

