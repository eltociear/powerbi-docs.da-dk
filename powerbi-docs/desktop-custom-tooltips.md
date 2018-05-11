---
title: Tilpasning af værktøjstips i Power BI Desktop
description: Opret brugerdefinerede værktøjstip for visualiseringer ved hjælp af træk og slip
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 6783987bb0afaea4131012425d91aacb2decb5cf
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Tilpasning af værktøjstips i Power BI Desktop
Værktøjstips er en elegant måde at angive flere oplysninger om kontekst og detaljer om datapunkter på i en visualisering. På følgende billede vises et værktøjstip, der er anvendt på et diagram i Power BI Desktop.

![](media/desktop-custom-tooltips/custom-tooltips_1.png)

Når der oprettes en visualisering, viser standardværktøjstippet datapunktets værdi og kategori. Tilpasning af oplysningerne i værktøjstips kan i mange tilfælde være meget nyttigt og give yderligere kontekst og oplysninger til brugere, der får vist visualiseringen. Med brugerdefinerede værktøjstips kan du angive yderligere datapunkter, der vises som en del af værktøjstippet.

## <a name="how-to-customize-tooltips"></a>Sådan tilpasser du værktøjstips
Du opretter et brugerdefineret værktøjstip på følgende måde: I brønden **Felter** i ruden **Visualiseringer** skal du blot trække et felt til den bucket, der hedder **Værktøjstips**, som vist på følgende billede. På følgende billede er fire felter blevet placeret i den bucket, der hedder **Værktøjstips**.

![](media/desktop-custom-tooltips/custom-tooltips_2.png)

Når du har føjet værktøjstips til brønden Felt, vises værdierne for disse felter i værktøjstippet, når du holder over et datapunkt i visualiseringen.

![](media/desktop-custom-tooltips/custom-tooltips_3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Tilpasning af værktøjstips med sammenlægning eller Hurtig beregning
Du kan tilpasse et værktøjstip yderligere ved at vælge en sammenlægningsfunktion eller en *Hurtig beregning*. Det gør du ved at vælge pilen ved siden af feltet i den bucket, der hedder **Værktøjstips**, og vælge mellem de tilgængelige indstillinger.

![](media/desktop-custom-tooltips/custom-tooltips_4.png)

Der er mange forskellige måder at tilpasse **Værktøjstips** på ved hjælp af et hvilket som helst felt i dit datasæt, så du hurtigt kan vise oplysninger og levere indsigt til dine brugere, som får vist dine dashboards eller rapporter.

