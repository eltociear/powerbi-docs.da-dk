---
title: Generér automatisk dataindsigt med Power BI
description: Find ud af, hvordan du kan få indsigt i datasæt og dashboardfelter.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/10/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: f68e962eacf04005d83ec0def10cf8e0e24f6e10
ms.sourcegitcommit: dc8b8a2cf2dcc96ccb46159802ebd9342a7fa840
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/11/2018
ms.locfileid: "49112032"
---
# <a name="automatically-generate-data-insights-with-power-bi"></a>Generér automatisk dataindsigt med Power BI
Hvert enkelt visualiseringsfelt på dashboardet er en indgang til at udforske data. Når du vælger et felt, åbnes en rapport, hvor du kan filtrere, sortere og fordybe dig i datasættet bag rapporten. Når du kører indsigt, udfører Power BI denne udforskning af data for dig.

Kør Quick Insights for at oprette interessante interaktive visualiseringer, der er baseret på dine data. Hurtig indsigt kan køres på et bestemt dashboardfelt, og du kan tilmed køre indsigt på en indsigt.

Funktionen Hurtig indsigt er baseret på et voksende [sæt avancerede analytiske algoritmer](end-user-insight-types.md), der er udviklet sammen med Microsoft Research, som vi vil fortsætte med at bruge for at gøre det muligt for flere personer at finde indsigter i deres data på nye og intuitive måder.

## <a name="run-insights-on-a-dashboard-tile"></a>Kør indsigt på et dashboardfelt
Når du kører indsigt på et dashboardfelt, søger Power BI kun i de data, der bruges til at oprette dette enkelte dashboardfelt. 

1. [Åbn et dashboard](end-user-dashboards.md).
2. Peg på et felt. vælg ellipsen (...), og vælg **Vis indsigt**. 

    ![tilstand for ellipsemenuen](./media/end-user-insights/power-bi-hover.png)


3. Feltet åbnes i [Fokustilstand](end-user-focus.md) med indsigtskortene vist langs højre.    
   
    ![Fokustilstand](./media/end-user-insights/pbi-insights-tile.png)    
4. Er der en indsigt, der vækker din interesse? Vælg indsigtskortet for at udforske mere. Den valgte indsigt vises til venstre, og nye indsigtskort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.    

 ## <a name="interact-with-the-insight-cards"></a>Interager med indsigtskortene
   * Filtrér visualiseringerne.  Du kan få vist filtrene ved at vælge pilen i det øverste højre hjørne for at udvide ruden Filtre.

     ![indsigt og menuen Filtre udvidet](./media/end-user-insights/power-bi-insights-on-insights.png)
   
   * Kør indsigt på selve indsigtskortet. Dette kaldes ofte **relateret indsigt**. I øverste højre hjørne skal du vælge ikonet med elpæren ![ikonet Få indsigt](./media/end-user-insights/power-bi-bulb-icon.png) eller **Få indsigt**.
     
     ![menulinje, der viser ikonet Få indsigt](./media/end-user-insights/power-bi-autoinsights-tile.png)
     
     Indsigterne vises til venstre, og nye kort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.
     
     ![indsigt i indsigt](./media/end-user-insights/power-bi-insights-on-insights-new.png)

Vælg **Afslut Fokustilstand** i øverste venstre hjørne, hvis du vil vende tilbage til det oprindelige indsigtslærred.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- **Vis indsigter** fungerer ikke med DirectQuery. Det fungerer kun med data, der er uploadet til Power BI.
- **Vis indsigter** fungerer ikke med alle typer af dashboardfelter. Det er f.eks. ikke tilgængeligt for brugerdefinerede visualiseringer.<!--[custom visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Næste trin
Få mere at vide om de [tilgængelige typer Hurtig indsigt](end-user-insight-types.md)

