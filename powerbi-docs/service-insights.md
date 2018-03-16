---
title: "Generér automatisk dataindsigt med Power BI"
description: "Find ud af, hvordan du kan få indsigt i datasæt og dashboardfelter."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: et_MLSL2sA8
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 5623667cd1a39b05795d162055ad0d3351d127bc
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/09/2018
---
# <a name="automatically-generate-data-insights-with-power-bi"></a>Generér automatisk dataindsigt med Power BI
Har du et nyt datasæt, og er du ikke helt sikker på, hvor du skal starte?  Har du brug for hurtigt at oprette et dashboard?  Vil du hurtigt søge efter indsigter, som du måske gik glip af?

Kør Quick Insights for at oprette interessante interaktive visualiseringer, der er baseret på dine data. Quick Insights kan køres på et helt datasæt (hurtig indsigt) eller på et bestemt dashboardfelt (områdebaseret indsigt). Du kan endda køre indsigter på en indsigt!

> **Bemærk!** Insights fungerer ikke med DirectQuery. Det fungerer kun med data, der er uploadet til Power BI.
> 
> 

Funktionen Quick Insights er baseret på et voksende [sæt avancerede analytiske algoritmer](service-insight-types.md), der er udviklet sammen med Microsoft Research, som vi vil fortsætte med at bruge for at gøre det muligt for flere personer at finde indsigter i deres data på nye og intuitive måder.

## <a name="run-quick-insights-on-a-dataset"></a>Kør Quick Insights på et datasæt
Se Amanda køre Quick Insights på et datasæt, åbne en indsigt i Fokustilstand, fastgøre en af disse indsigter som et felt på sit dashboard og derefter få indsigter for et dashboardfelt.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Nu er det din tur. Udforsk Quick Insights ved hjælp af [Eksempel på analyse af leverandørkvalitet](sample-supplier-quality.md).

1. Vælg ellipsen (...) fra fanen **Datasæt**, og vælg **Få indsigt**.
   
    ![Fanen Datasæt](media/service-insights/power-bi-ellipses.png)
   
    ![ellipsemenu](media/service-insights/power-bi-tab.png)
2. Power BI bruger [forskellige algoritmer](service-insight-types.md) til at søge efter tendenser i dit datasæt.
   
    ![Søger efter dialogboksen Indsigt](media/service-insights/pbi_autoinsightssearching.png)
3. Dine indsigter er klar på få sekunder.  Vælg **Vis indsigt** for at vise visualiseringer.
   
    ![meddelelse om fuldførelse](media/service-insights/pbi_autoinsightsuccess.png)
   
   > **Bemærk!**: Nogle datasæt kan ikke generere indsigt, da dataene ikke er statistisk vigtige.  Hvis du vil vide mere, kan du se [Optimer dine data til indsigt](service-insights-optimize.md).
   > 
   > 
1. Visualiseringerne vises på et særligt **Hurtig indsigt**-lærred med op til 32 separate indsigtskort. Hvert kort har et diagram eller en graf samt en kort beskrivelse.
   
    ![Lærred med Hurtig indsigt](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Interager med indsigtskortene
  ![tegnestiftikon](media/service-insights/pbi_hover.png)

1. Hold markøren over et kort, og vælg ikonet med tegnestiften for at føje visualiseringen til et dashboard.
2. Peg på et kort, vælg ellipsen (...), og vælg **Vis indsigt**. Dette åbner indsigt i fuld skærm.
   
    ![Fuld skærm med indsigt](media/service-insights/power-bi-insight-focus.png)
3. I fokustilstand kan du:
   
   * Filtrér visualiseringerne.  For at få vist filtrene skal du øverst til højre vælge pilen til at udvide ruden Filtre.
        ![Indsigt og menuen Filtre er udvidet](media/service-insights/power-bi-insights-filter-new.png)
   * Fastgør indsigtskortet til et dashboard ved at vælge ikonet Fastgør ![tegnestiftikon](media/service-insights/power-bi-pin-icon.png) eller **Fastgør visualisering**.
   * Kør indsigt på selve kortet. Dette kaldes ofte **Områdebaseret indsigt**. Øverst til højre skal du vælge ikonet med elpæren ![Få indblik-ikon](media/service-insights/power-bi-bulb-icon.png) eller **Få indblik**.
     
       ![menulinje, der viser ikonet Få indblik](media/service-insights/pbi-autoinsights-tile.png)
     
     Indsigterne vises til venstre, og nye kort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.
     
       ![indblik i indblik](media/service-insights/power-bi-insights-on-insights-new.png)
4. Vælg **Afslut Fokustilstand** øverst til venstre, hvis du vil vende tilbage til det oprindelige indsigtslærred.

## <a name="run-insights-on-a-dashboard-tile"></a>Kør indsigt på et dashboardfelt
I stedet for at søge efter indsigter i et helt datasæt kan du begrænse din søgning til de data, der er brugt til at oprette et enkelt dashboardfelt. Også dette kaldes ofte **Områdebaseret indsigt**.

1. Åbn et dashboard.
2. Peg på et felt. vælg ellipsen (...), og vælg **Vis indsigt**. Feltet åbnes i [Fokustilstand](service-focus-mode.md) med indsigtskortene vist langs højre.    
   
    ![Fokustilstand](media/service-insights/pbi-insights-tile.png)    
4. Er der en indsigt, der vækker din interesse? Vælg indsigtskortet for at udforske mere. Den valgte indsigt vises til venstre, og nye indsigtskort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.    
6. Fortsæt med udforske dine data, og når du finder en interessant indsigt, kan du fastgøre den til dit dashboard ved at vælge **Fastgør din visual** fra øverste højre hjørne.

## <a name="next-steps"></a>Næste trin
Hvis du ejer et datasæt, [kan du optimere det til Quick Insights](service-insights-optimize.md)

Få mere at vide om de [tilgængelige typer Hurtig indsigt](service-insight-types.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

