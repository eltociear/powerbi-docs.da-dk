---
title: Kør og få vist indsigt på dashboardfelter
description: Find ud af, hvordan du som Power BI-slutbruger kan få indsigt i dine dashboardfelter.
author: mihart
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 06/22/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 111b2b5fe0ae4b341816becdb4baf0b96e057cdd
ms.sourcegitcommit: caf60154a092f88617eb177bc34fb784f2365962
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/25/2020
ms.locfileid: "85354495"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Få vist dataindsigt på dashboardfelter med Power BI

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

Hvert enkelt [visualiseringsfelt](end-user-tiles.md) på dashboardet er en indgang til at udforske data. Når du vælger et felt, åbnes en rapport, eller [Spørgsmål og svar åbnes](end-user-q-and-a.md), hvor du kan filtrere, sortere og fordybe dig i datasættet bag rapporten. Når du kører indsigt, udfører Power BI denne udforskning af data for dig.

![tilstand for ellipsemenuen](./media/end-user-insights/power-bi-insight.png)

Kør indsigt for at generere interessante interaktive visualiseringer på baggrund af dine data. Indsigt kan køres på et bestemt dashboardfelt, og du kan tilmed køre indsigt for en indsigt.

Funktionen Quick Insights er baseret på et voksende [sæt avancerede analytiske algoritmer](end-user-insight-types.md), der er udviklet sammen med Microsoft Research, som vi vil fortsætte med at bruge for at gøre det muligt for flere personer at finde indsigter i deres data på nye og intuitive måder.

## <a name="run-insights-on-a-dashboard-tile"></a>Kør indsigt på et dashboardfelt
Når du kører indsigt på et dashboardfelt, søger Power BI kun i de data, der bruges til at oprette dette enkelte dashboardfelt. 

1. [Åbn et dashboard](end-user-dashboards.md).
2. Peg på et felt. vælg **Flere indstillinger** (...), og vælg **Vis indsigt**. 

    ![tilstand for ellipsemenuen](./media/end-user-insights/power-bi-hovers.png)


3. Feltet åbnes i [Fokustilstand](end-user-focus.md) med indsigtskortene vist langs højre.    
   
    ![Fokustilstand](./media/end-user-insights/power-bi-insights-tile.png)    
4. Er der en indsigt, der vækker din interesse? Vælg indsigtskortet for at udforske mere. Den valgte indsigt vises til venstre, og nye indsigtskort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.    

 ## <a name="interact-with-the-insight-cards"></a>Interager med indsigtskortene
Når du har åbnet en indsigt, kan du fortsætte med at udforske.

   * Filtrer visualiseringen på lærredet.  Du kan få vist filtrene ved at vælge pilen i det øverste højre hjørne for at udvide ruden Filtre.

      ![indsigt og menuen Filtre udvidet](./media/end-user-insights/power-bi-filters.png)
   
   * Kør indsigt på selve indsigtskortet. Dette kaldes ofte **relateret indsigt**. Vælg et indsigtskort for at aktivere det. Det vises på dit rapportlærred.
   
      ![indsigt og menuen Filtre udvidet](./media/end-user-insights/power-bi-insight-card.png)
   
   * I øverste højre hjørne skal du vælge ikonet med elpæren ![ikonet Få indsigt](./media/end-user-insights/power-bi-bulb-icon.png) eller **Få indsigt**. Indsigterne vises til venstre, og nye kort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.
     
     ![menulinje, der viser ikonet Få indblik](./media/end-user-insights/power-bi-related.png)
     
Vælg **Afslut Fokustilstand** i øverste venstre hjørne for at vende tilbage til din rapport.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- **Vis indsigter** fungerer ikke med alle typer af dashboardfelter. Det er f.eks. ikke tilgængeligt for brugerdefinerede Power BI-visuals.<!--[Power BI visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Næste trin

Kør indsigt på visualiseringer i rapporter [ved hjælp af funktionen Analysér](end-user-analyze-visuals.md)    
Få mere at vide om de [tilgængelige typer Hurtig indsigt](end-user-insight-types.md)

