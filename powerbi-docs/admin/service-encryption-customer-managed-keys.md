---
title: Brug kundeadministrerede nøgler i Power BI
description: Få mere at vide om, hvordan du bruger kundeadministrerede nøgler i Power BI.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 08/12/2020
LocalizationGroup: Premium
ms.openlocfilehash: 8d13cc7a24486fada7f8d428ba52abeaa49d2518
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160922"
---
# <a name="use-customer-managed-keys-in-power-bi"></a>Brug kundeadministrerede nøgler i Power BI

Power BI krypterer inaktive og igangværende data. Power BI bruger som standard Microsoft-administrerede nøgler til kryptering af dine data. Organisationer kan vælge at bruge deres egne nøgler til kryptering af inaktivt brugerindhold i hele Power BI, fra rapportbilleder til importerede datasæt i Premium-kapaciteter. 

## <a name="why-use-customer-managed-keys"></a>Derfor skal du bruge kundeadministrerede nøgler
Med Power BI CMK (Customer Managed Keys) kan organisationer overholde gældende krav til kryptering af inaktive data hos deres udbyder af cloudtjenester (i dette tilfælde Microsoft). CMK gør det muligt for organisationer at kryptere deres Power BI-brugerindhold med en nøgle, de leverer og administrerer. Hvis du tilbagekalder en kundeadministreret nøgle, bliver brugerindhold i Power BI ulæseligt for alle i løbet af en time, herunder Microsoft. Sammenlignet med BYOK-tilbuddet dækker CMK også brugerindhold uden for Power BI Premium-kapaciteter, det håndhæver strengere politikker for cachelagring og aktiverer som standard BYOK på alle kapaciteter. 
 
## <a name="how-to-use-customer-managed-keys"></a>Sådan bruger du kundeadministrerede nøgler
Hvis du vil tilmelde dig kundeadministrerede Power BI-nøgler, skal din organisation opfylde størrelseskravene. Din organisations globale administrator skal indsende en supportanmodning til Microsoft, eller administratoren kan kontakte den Microsoft-kundeansvarlige i din organisation for at få mere at vide om processen.  


## <a name="next-steps"></a>Næste trin

Følgende links indeholder oplysninger, der kan være nyttige i forbindelse med kundeadministrerede nøgler:

* [Medbring dine egne krypteringsnøgler til Power BI](service-encryption-byok.md)
* [Konfigurer understøttelse af Multi-Geo til Power BI Premium](service-admin-premium-multi-geo.md)
* [Sådan fungerer kapaciteter](service-premium-what-is.md#how-capacities-function)
* [Trinvis opdatering](service-premium-incremental-refresh.md)
