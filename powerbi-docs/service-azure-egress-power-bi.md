---
title: Udgående data i Power BI og Azure
description: Forstå gebyrer for udgående data i Azure og Power BI, afhængigt af lejerplacering og Power BI Premium
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 528d31a72d2c78b0a00f853d2df82f3a4eb04eae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295323"
---
# <a name="power-bi-and-azure-egress"></a>Udgående data i Power BI og Azure

Når du bruger Power BI sammen med Azure-datakilder, kan du undgå gebyrer for udgående data i Azure ved at sørge for, at din Power BI-lejer er i samme område som dine Azure-datakilder.

Når din Power BI-lejer er installeret i det samme Azure-område, som du installerer dine datakilder i, skal du ikke betale gebyrer for udgående data for planlagte opdateringer og DirectQuery-interaktioner. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Sådan afgør du, hvor din Power BI-lejer er placeret

Du kan finde ud af, hvor din Power BI-lejer er placeret, i artiklen [Hvor findes min Power BI-lejer](service-admin-where-is-my-tenant-located.md).

For Power BI Premium Multi-Geo-kunder forholder det sig sådan, at hvis din Power BI-lejer ikke er i den optimale placering for nogle af dine Azure-baserede datakilder, kan du installere Power BI Premium Multi-Geo i det ønskede Azure-område og få fordel af at have din Power BI-lejer og Azure-datakilder i det samme Azure-område.

## <a name="next-steps"></a>Næste trin

Du kan få flere oplysninger om Power BI Premium eller Multi-Geo i følgende ressourcer:

* [Hvad er Microsoft Power BI Premium?](service-premium.md)
* [Sådan køber du Power BI Premium](service-admin-premium-purchase.md)
* [Multi-Geo-understøttelse af Power BI Premium (prøveversion)](service-admin-premium-multi-geo.md)
* [Hvor findes min Power BI-lejer?](service-admin-where-is-my-tenant-located.md)
* [Ofte stillede spørgsmål til Power BI Premium](service-premium-faq.md)


