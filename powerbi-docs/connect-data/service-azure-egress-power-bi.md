---
title: Udgående data i Power BI og Azure
description: Forstå gebyrer for udgående data i Azure og Power BI, afhængigt af lejerplacering og Power BI Premium
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: c93299a2066dd2f15843048742e857495db7242a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85230586"
---
# <a name="power-bi-and-azure-egress"></a>Udgående data i Power BI og Azure

Når du bruger Power BI sammen med Azure-datakilder, kan du undgå gebyrer for udgående data i Azure ved at sørge for, at din Power BI-lejer er i samme område som dine Azure-datakilder.

Når din Power BI-lejer er installeret i det samme Azure-område, som du installerer dine datakilder i, skal du ikke betale gebyrer for udgående data for planlagte opdateringer og DirectQuery-interaktioner. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Sådan afgør du, hvor din Power BI-lejer er placeret

Du kan finde ud af, hvor din Power BI-lejer er placeret, i artiklen [Hvor findes min Power BI-lejer](../admin/service-admin-where-is-my-tenant-located.md).

For Power BI Premium Multi-Geo-kunder forholder det sig sådan, at hvis din Power BI-lejer ikke er i den optimale placering for nogle af dine Azure-baserede datakilder, kan du installere Power BI Premium Multi-Geo i det ønskede Azure-område og få fordel af at have din Power BI-lejer og Azure-datakilder i det samme Azure-område.

## <a name="next-steps"></a>De næste trin

Du kan få flere oplysninger om Power BI Premium eller Multi-Geo i følgende ressourcer:

* [Hvad er Microsoft Power BI Premium?](../admin/service-premium-what-is.md)
* [Sådan køber du Power BI Premium](../admin/service-admin-premium-purchase.md)
* [Multi-Geo-understøttelse af Power BI Premium (prøveversion)](../admin/service-admin-premium-multi-geo.md)
* [Hvor findes min Power BI-lejer?](../admin/service-admin-where-is-my-tenant-located.md)
* [Ofte stillede spørgsmål til Power BI Premium](../admin/service-premium-faq.md)
