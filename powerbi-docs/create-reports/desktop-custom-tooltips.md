---
title: Tilpasser værktøjstips i Power BI Desktop
description: Opret brugerdefinerede værktøjstip for visualiseringer ved hjælp af træk og slip
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: a21bccb78df5ba84d3e9a7dc07d9d392c74c0153
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85231939"
---
# <a name="customize-tooltips-in-power-bi-desktop"></a>Tilpas værktøjstip i Power BI Desktop

Værktøjstips er en elegant måde at angive flere oplysninger om kontekst og detaljer om datapunkter på i en visualisering. På følgende billede vises et værktøjstip, der er anvendt på et diagram i Power BI Desktop.

![Standardværktøjstip](media/desktop-custom-tooltips/custom-tooltips-1.png)

Når der oprettes en visualisering, viser standardværktøjstippet datapunktets værdi og kategori. Der er mange tilfælde, hvor tilpasning af oplysningerne i værktøjstippet er nyttigt. Tilpasning af værktøjstip giver yderligere kontekst og oplysninger til brugere, der får vist det visuelle element. Med brugerdefinerede værktøjstips kan du angive yderligere datapunkter, der vises som en del af værktøjstippet.

## <a name="how-to-customize-tooltips"></a>Sådan tilpasser du værktøjstips

Du opretter et brugerdefineret værktøjstip på følgende måde: I området **Felter** i ruden **Visualiseringer** skal du trække et felt til den krukke, der hedder **Værktøjstip**, som vist på følgende billede. På det følgende billede er tre felter blevet placeret i feltet **Værktøjstip**.

![Tilføj felter til værktøjstip](media/desktop-custom-tooltips/custom-tooltips-2.png)

Når du har føjet værktøjstip til feltet **Værktøjstip**, vises værdierne for disse felter i værktøjstippet, når du peger med musen på et datapunkt i visualiseringen.

![Brugerdefineret værktøjstip](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-measures"></a>Tilpasning af værktøjstip med sammenlægning eller hurtig beregning

Du kan tilpasse et værktøjstip yderligere ved at vælge en sammenlægningsfunktion eller en *hurtigmåling*. Vælg pilen ud for feltet i krukken **Værktøjstip**. Vælg derefter blandt de tilgængelige indstillinger.

![Værktøjstip med hurtigmåling](media/desktop-custom-tooltips/custom-tooltips-4.png)

Der er mange måder at tilpasse værktøjstip på ved hjælp af et hvilket som helst felt i dit datasæt, så du hurtigt kan vise oplysninger og levere indsigt til dine brugere, som får vist dine dashboards eller rapporter.
