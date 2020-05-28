---
title: Angiv rapportvisninger af sideinddelte rapporter – Power BI
description: I denne artikel får du mere at vide om de forskellige tilgængelige rapportvisninger af sideinddelte rapporter i Power BI-tjenesten.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: ''
ms.topic: conceptual
ms.date: 05/14/2020
ms.openlocfilehash: 3816cfe4e1b61b9445e16d7c322c5ba19aa2bc3d
ms.sourcegitcommit: 21b06e49056c2f69a363d3a19337374baa84c83f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/15/2020
ms.locfileid: "83407926"
---
# <a name="set-report-views-for-paginated-reports-in-the-power-bi-service"></a>Angiv rapportvisninger af sideinddelte rapporter i Power BI-tjenesten

Når du gengiver en sideinddelt rapport i Power BI-tjenesten, er standardvisningen HTML-baseret og interaktiv. En anden rapportvisning af faste sideformater, f.eks. PDF, er den nye indstilling Sidevisning.

**Interaktiv standardvisning**

![Standardvisning](media/page-view/power-bi-paginated-default-view.png)

**Sidevisning**

![Sidevisning](media/page-view/power-bi-paginated-page-view.png)

I Sidevisning ser den gengivne rapport anderledes ud end standardvisningen. Nogle egenskaber og begreber i sideinddelte rapporter gælder kun for faste sider. Visningen svarer til, når rapporten udskrives eller eksporteres. Du kan stadig ændre nogle elementer, f.eks. parameterværdier, men der er ikke andre interaktive funktioner såsom sortering og redigering af kolonner.

Sidevisning understøtter alle de funktioner, som browserens PDF-fremviser understøtter, f.eks. Zoom ind, Zoom ud og Tilpas til siden.

## <a name="switch-to-page-view"></a>Skift til Sidevisning

Når du åbner en sideinddelt rapport, gengives den som standard i interaktiv visning. Hvis rapporten indeholder parametre, skal du vælge parametre og derefter få vist rapporten.

1. Vælg **Vis** på værktøjslinjen > **Sidevisning**.

    ![Skift til Sidevisning](media/page-view/power-bi-paginated-page-view-dropdown.png)

2. Du kan ændre indstillingerne for sidevisning ved at vælge **Sideindstillinger** i menuen **Vis** på værktøjslinjen. 

    ![Vælg Sideindstillinger](media/page-view/power-bi-paginated-page-settings-dropdown.png)
    
    I dialogboksen **Sideindstillinger** findes indstillinger til angivelse af **Sidestørrelse** og **Retning** for Sidevisning. Når du har anvendt sideindstillinger, gælder de samme indstillinger, når du senere udskriver siden.
   
    ![Dialogboksen Sideindstillinger](media/page-view/power-bi-paginated-page-settings-dialog.png)

3. Hvis du vil skifte tilbage til den interaktive visning, skal du vælge **Standard** på rullelisten **Vis**.

## <a name="browser-support"></a>Browserunderstøttelse

Sidevisning understøttes i browserne Google Chrome og Microsoft Edge. Sørg for, at visning af PDF'er i browseren er aktiveret. Det er standardindstillingen for disse browsere.

Sidevisning understøttes ikke i Internet Explorer og Safari, så indstillingen er deaktiveret. Det understøttes heller ikke i browsere på mobilenheder eller i de oprindelige Power BI-mobilapps.  


## <a name="next-steps"></a>Næste trin

- [Publicer en sideinddelt rapport i Power BI-tjenesten](../consumer/paginated-reports-view-power-bi-service.md)
- [Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)
