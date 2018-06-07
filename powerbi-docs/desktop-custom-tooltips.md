---
title: Tilpasning af værktøjstips i Power BI Desktop
description: Opret brugerdefinerede værktøjstip for visualiseringer ved hjælp af træk og slip
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5dfd22f8b45253ece4ed8f699adec9abcaa1a8ed
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721150"
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Tilpasning af værktøjstips i Power BI Desktop
Værktøjstips er en elegant måde at angive flere oplysninger om kontekst og detaljer om datapunkter på i en visualisering. På følgende billede vises et værktøjstip, der er anvendt på et diagram i Power BI Desktop.

![Standardværktøjstip](media/desktop-custom-tooltips/custom-tooltips-1.png)

Når der oprettes en visualisering, viser standardværktøjstippet datapunktets værdi og kategori. Tilpasning af oplysningerne i værktøjstips kan i mange tilfælde være meget nyttigt og give yderligere kontekst og oplysninger til brugere, der får vist visualiseringen. Med brugerdefinerede værktøjstips kan du angive yderligere datapunkter, der vises som en del af værktøjstippet.

## <a name="how-to-customize-tooltips"></a>Sådan tilpasser du værktøjstips
Du opretter et brugerdefineret værktøjstip på følgende måde: I brønden **Felter** i ruden **Visualiseringer** skal du blot trække et felt til den bucket, der hedder **Værktøjstips**, som vist på følgende billede. I det følgende billede er to felter blevet placeret i feltet **Værktøjstip**.

![Tilføj felter til værktøjstip](media/desktop-custom-tooltips/custom-tooltips-2.png)

Når du har føjet værktøjstip til feltet, vises værdierne for disse felter i værktøjstippet, når du peger med musen på et datapunkt i visualiseringen.

![Brugerdefineret værktøjstip](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Tilpasning af værktøjstips med sammenlægning eller Hurtig beregning
Du kan tilpasse et værktøjstip yderligere ved at vælge en sammenlægningsfunktion eller en *Hurtig beregning*. Det gør du ved at vælge pilen ved siden af feltet i den bucket, der hedder **Værktøjstips**, og vælge mellem de tilgængelige indstillinger.

![Værktøjstip med Hurtig beregning](media/desktop-custom-tooltips/custom-tooltips-4.png)

Der er mange forskellige måder at tilpasse **Værktøjstips** på ved hjælp af et hvilket som helst felt i dit datasæt, så du hurtigt kan vise oplysninger og levere indsigt til dine brugere, som får vist dine dashboards eller rapporter.

