---
title: Opret forbindelse til Azure Mobile Engagement med Power BI
description: Azure Mobile Engagement til Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 85b43579785983da2ddc3ac2e302396d1a282792
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-mobile-engagement-with-power-bi"></a>Opret forbindelse til Azure Mobile Engagement med Power BI
Med Power BI Azure Mobile Engagement-indholdspakken kan du hurtigt få indsigt i dine appdata.

Opret forbindelse til [Azure Mobile Engagement-indholdspakken](https://app.powerbi.com/groups/me/getdata/services/azme) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-azure-mobile/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
    ![](media/service-connect-to-azure-mobile/services.png)
3. Vælg **Azure Mobile Engagement** \> **Hent**.
   
    ![](media/service-connect-to-azure-mobile/azme.png) 
4. Angiv gruppen af apps og appnavnet. Disse oplysninger finder du i din Azure Mobile Engagement-konto.
   
    ![](media/service-connect-to-azure-mobile/parameters.png) 
5. Som godkendelsesmetode skal du angive din nøgle og klikke på Log på.
   
    ![](media/service-connect-to-azure-mobile/creds.png)
6. Efter import af data i Power BI får du vist et nyt dashboard og datasæt samt en ny rapport i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*, som forsvinder, når du har valgt:
   
    ![](media/service-connect-to-azure-mobile/dashboard.png)

 **Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="next-steps"></a>Næste trin
[Kom i gang i Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

