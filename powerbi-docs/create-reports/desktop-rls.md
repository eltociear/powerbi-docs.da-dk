---
title: Begræns dataadgang med sikkerhed på rækkeniveau (RLS) for Power BI Desktop
description: Sådan konfigurerer du sikkerhed på rækkeniveau for importerede datasæt og DirectQuery i Power BI Desktop.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 9036967c826dee83847c3bc3d4a903bbe749b2ce
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238636"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Begræns dataadgang med sikkerhed på rækkeniveau (RLS) for Power BI Desktop

Du kan nu bruge sikkerhed på rækkeniveau med Power BI Desktop til at begrænse adgang til datakilder for bestemte brugere. Filtre begrænser data på rækkeniveau. Du kan definere filtre i roller.

Du kan nu konfigurere sikkerhed på rækkeniveau for datamodeller, der er importeret til Power BI, med Power BI Desktop. Du kan også konfigurere sikkerhed på rækkeniveau for datasæt, der anvender [DirectQuery](../connect-data/desktop-use-directquery.md), f.eks. SQL Server. Tidligere kunne du kun implementere sikkerhed på rækkeniveau i Analysis Services-modeller i det lokale miljø uden for Power BI. I forbindelse med liveforbindelser i Analysis Services kan du konfigurere sikkerhed på rækkeniveau for modellen i det lokale miljø. Sikkerhedsindstillingen vises ikke for datasæt med direkte forbindelse.

> [!IMPORTANT]
> Hvis du har defineret roller og regler i Power BI-tjenesten, skal du genskabe disse roller i Power BI Desktop og publicere rapporten i tjenesten. Få mere at vide om indstillinger for [Sikkerhed på rækkeniveau i Power BI-tjenesten](../admin/service-admin-rls.md).

[!INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-limitations.md)]

[!INCLUDE [include-short-name](../includes/rls-faq.md)]

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger, der er relateret til denne artikel, i følgende ressourcer:

- [Sikkerhed på rækkeniveau (RLS) med Power BI](../admin/service-admin-rls.md)
- [Sikkerhed på rækkeniveau (RLS) i Power BI Desktop](../guidance/rls-guidance.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
- Forslag? [Få ideer til at forbedre Power BI](https://ideas.powerbi.com/)
