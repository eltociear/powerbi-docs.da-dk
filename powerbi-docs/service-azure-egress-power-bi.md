---
title: Udgående data i Power BI og Azure
description: Forstå gebyrer for udgående data i Azure og Power BI, afhængigt af lejerplacering og Power BI Premium
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 17175e1accb5013b960c5e1a71ae036b3dda72f3
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73855578"
---
# <a name="power-bi-and-azure-egress"></a>Udgående data i Power BI og Azure

Når du bruger Power BI sammen med Azure-datakilder, kan du undgå gebyrer for udgående data i Azure ved at sørge for, at din Power BI-lejer er i samme område som dine Azure-datakilder.

Når din Power BI-lejer er installeret i det samme Azure-område, som du installerer dine datakilder i, skal du ikke betale gebyrer for udgående data for planlagte opdateringer og DirectQuery-interaktioner. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Sådan afgør du, hvor din Power BI-lejer er placeret

Du kan finde ud af, hvor din Power BI-lejer er placeret, i artiklen [Hvor findes min Power BI-lejer](service-admin-where-is-my-tenant-located.md).

For Power BI Premium Multi-Geo-kunder forholder det sig sådan, at hvis din Power BI-lejer ikke er i den optimale placering for nogle af dine Azure-baserede datakilder, kan du installere Power BI Premium Multi-Geo i det ønskede Azure-område og få fordel af at have din Power BI-lejer og Azure-datakilder i det samme Azure-område.

## <a name="next-steps"></a>Næste trin

Du kan få flere oplysninger om Power BI Premium eller Multi-Geo i følgende ressourcer:

* [Hvad er Microsoft Power BI Premium?](service-premium-what-is.md)
* [Sådan køber du Power BI Premium](service-admin-premium-purchase.md)
* [Multi-Geo-understøttelse af Power BI Premium (prøveversion)](service-admin-premium-multi-geo.md)
* [Hvor findes min Power BI-lejer?](service-admin-where-is-my-tenant-located.md)
* [Ofte stillede spørgsmål til Power BI Premium](service-premium-faq.md)


