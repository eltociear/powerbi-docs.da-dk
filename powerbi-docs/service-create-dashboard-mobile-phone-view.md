---
title: Opret en visning af et Power BI-dashboard til mobiltelefoner
description: Lær at oprette en tilpasset visning af et dashboard i Power BI-tjenesten, der er specialdesignet til visning på mobiltelefoner.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 4d237a308e059ce712872860031f122de9d6795c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238415"
---
# <a name="create-a-view-of-a-power-bi-dashboard-optimized-for-mobile-phones"></a>Opret en visning af et Power BI-dashboard optimeret til mobiltelefoner
Når du får vist dashboards i Power BI-mobilappen på en telefon, vil du opdage, at dashboardfelterne er placeret et ad gangen efter hinanden, alle med den samme størrelse. Du kan i Power BI-tjenesten oprette en tilpasset visning af et dashboard, som du ejer, specifikt til telefoner.

Når du vender telefonen om på siden, ser du dashboardet, som det er arrangeret i tjenesten, ikke som du designede det til telefonen.

> [!NOTE]
> Når du redigerer telefonvisningen, kan alle, der ser dashboardet på en telefon, i realtid se de ændringer, du foretager. Hvis du eksempelvis frigør alle felter i dashboardets telefonvisning, har dashboardet på telefonen pludseligt ingen felter. 
> 
> 

## <a name="create-a-phone-view-of-a-dashboard"></a>Opret en telefonvisning af et dashboard
1. Åbn et dashboard i Power BI-tjenesten.
2. Vælg pilen ud for **Webvisning** i øverste højre hjørne > vælg **Telefonvisning**.

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-dashboard.png)

    Hvis du ikke er ejeren af dashboardet, kan du ikke se denne indstilling.

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-canvas.png)

    Visningen til redigering af telefonens dashboard åbnes. Her kan du frigøre, tilpasse størrelsen på og omarrangere felter, så de passer til telefonvisningen. Webversionen af dashboardet ændres ikke.


1. Vælg et felt for at trække, tilpasse eller frigøre det. Du kan se, at de andre felter flyttes væk, når du trækker et felt.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-unpin-tile-phone-dashboard.png)
   
    De frigjorte felter flyttes til ruden Frigjorte felter, hvor de bliver, medmindre du tilføjer dem igen.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-post-edit.png)
2. Hvis du skifter mening, skal du vælge **Nulstil felter**, og de vender tilbage til den tidligere størrelse og rækkefølge.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-reset-tiles.png)
   
    Størrelsen og formen på felterne på en telefon ændres kun en lille smule, hvis du kun åbner visningen til telefonredigering i Power BI-tjenesten. Så hvis dashboardet skal vende tilbage til den nøjagtige tilstand, før du åbnede det i visningen til telefonredigering, skal du vælge **Nulstil felter**.
3. Når du er tilfreds med telefonens dashboardlayout, skal du vælge pilen ud for **Telefonvisning** i øverste højre hjørne > vælge **Webvisning**.
   
    Power BI gemmer telefonlayoutet automatisk.

## <a name="next-steps"></a>Næste trin
* [Opret rapporter, der er optimeret til Power BI-telefonapps](desktop-create-phone-report.md)
* [Opret dynamiske visualiseringer, der er optimeret til alle størrelser](desktop-create-responsive-visuals.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

