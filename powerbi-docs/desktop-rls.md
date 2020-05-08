---
title: Begræns dataadgang med sikkerhed på rækkeniveau (RLS) for Power BI Desktop
description: Sådan konfigurerer du sikkerhed på rækkeniveau for importerede datasæt og DirectQuery i Power BI Desktop.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 7a9aa0ca62ae4f1008d4cf47caa909841f9ec495
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "77464355"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Begræns dataadgang med sikkerhed på rækkeniveau (RLS) for Power BI Desktop

Du kan nu bruge sikkerhed på rækkeniveau med Power BI Desktop til at begrænse adgang til datakilder for bestemte brugere. Filtre begrænser data på rækkeniveau. Du kan definere filtre i roller.

Du kan nu konfigurere sikkerhed på rækkeniveau for datamodeller, der er importeret til Power BI, med Power BI Desktop. Du kan også konfigurere sikkerhed på rækkeniveau for datasæt, der anvender [DirectQuery](desktop-use-directquery.md), f.eks. SQL Server. Tidligere kunne du kun implementere sikkerhed på rækkeniveau i Analysis Services-modeller i det lokale miljø uden for Power BI. I forbindelse med liveforbindelser i Analysis Services kan du konfigurere sikkerhed på rækkeniveau for modellen i det lokale miljø. Sikkerhedsindstillingen vises ikke for datasæt med direkte forbindelse.

> [!IMPORTANT]
> Hvis du har defineret roller og regler i Power BI-tjenesten, skal du genskabe disse roller i Power BI Desktop og publicere rapporten i tjenesten. Få mere at vide om indstillinger for [Sikkerhed på rækkeniveau i Power BI-tjenesten](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>De næste trin

[Sikkerhed på rækkeniveau med Power BI-tjenesten](service-admin-rls.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/).