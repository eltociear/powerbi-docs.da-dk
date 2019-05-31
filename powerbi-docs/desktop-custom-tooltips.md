---
title: Tilpasning af værktøjstips i Power BI Desktop
description: Opret brugerdefinerede værktøjstip for visualiseringer ved hjælp af træk og slip
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d5259ba22287a8a2ade3107e4320c39713dcb45e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65239760"
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Tilpasning af værktøjstips i Power BI Desktop
Værktøjstips er en elegant måde at angive flere oplysninger om kontekst og detaljer om datapunkter på i en visualisering. På følgende billede vises et værktøjstip, der er anvendt på et diagram i Power BI Desktop.

![Standardværktøjstip](media/desktop-custom-tooltips/custom-tooltips-1.png)

Når der oprettes en visualisering, viser standardværktøjstippet datapunktets værdi og kategori. Der er mange forekomster, når tilpasning af oplysningerne i værktøjstips kan er nyttige, og kan give yderligere kontekst og oplysninger til brugere, der får vist Visualiseringen. Med brugerdefinerede værktøjstips kan du angive yderligere datapunkter, der vises som en del af værktøjstippet.

## <a name="how-to-customize-tooltips"></a>Sådan tilpasser du værktøjstips
Til at oprette et brugerdefineret værktøjstip i den **felter** i den **visualiseringer** ruden trække et felt til den **værktøjstip** bucket, som vist på følgende billede. I det følgende billede er to felter blevet placeret i feltet **Værktøjstip**.

![Tilføj felter til værktøjstip](media/desktop-custom-tooltips/custom-tooltips-2.png)

Når du har føjet værktøjstip til feltet, vises værdierne for disse felter i værktøjstippet, når du peger med musen på et datapunkt i visualiseringen.

![Brugerdefineret værktøjstip](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Tilpasning af værktøjstips med sammenlægning eller Hurtig beregning
Du kan tilpasse et værktøjstip yderligere ved at vælge en sammenlægningsfunktion eller en *Hurtig beregning*. Det gør du ved at vælge pilen ved siden af feltet i den bucket, der hedder **Værktøjstips**, og vælge mellem de tilgængelige indstillinger.

![Værktøjstip med Hurtig beregning](media/desktop-custom-tooltips/custom-tooltips-4.png)

Der er mange måder at tilpasse **værktøjstip**, ved hjælp af en hvilken som helst felt i dit datasæt, at udtrykke en hurtig oplysninger og indsigt, så brugerne får vist dine dashboards eller rapporter.

