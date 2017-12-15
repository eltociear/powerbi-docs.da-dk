---
title: "Forstå sikkerhed på rækkeniveau med Power BI Desktop"
description: "Sådan konfigurerer du sikkerhed på rækkeniveau for importerede datasæt og DirectQuery i Power BI Desktop."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: asaxton
ms.openlocfilehash: e6b6efb976de8df6064f2eb1156237d1a1250807
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Sikkerhed på rækkeniveau med Power BI Desktop
Sikkerhed på rækkeniveau med Power BI Desktop kan bruges til at begrænse adgang til datakilder for bestemte brugere. Filtre begrænser data på rækkeniveau. Du kan definere filtre i roller.

Du kan nu konfigurere sikkerhed på rækkeniveau for datamodeller, der er importeret til Power BI, med Power BI Desktop. Du kan også konfigurere sikkerhed på rækkeniveau for datasæt, der anvender DirectQuery, f.eks SQL Server. Tidligere kunne du kun implementere sikkerhed på rækkeniveau i Analysis Services-modeller i det lokale miljø uden for Power BI. I forbindelse med direkte forbindelser i Analysis Services kan du konfigurere sikkerhed på rækkeniveau for modellen i det lokale miljø. Sikkerhedsindstillingen vises ikke for datasæt med direkte forbindelse.

> [!IMPORTANT]
> Hvis du har defineret roller/regler i Power BI-tjenesten, skal du genskabe disse roller i Power BI Desktop og publicere rapporten i tjenesten.
> 
> 

Få mere at vide om indstillinger for [Sikkerhed på rækkeniveau i Power BI-tjenesten](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Næste trin
[Sikkerhed på rækkeniveau med Power BI-tjenesten](service-admin-rls.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

