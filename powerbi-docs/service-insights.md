---
title: Generér automatisk dataindsigt med Power BI
description: Find ud af, hvordan du kan få indsigt i datasæt og dashboardfelter.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 5f571cabcc413947713cd232863b3ecad910436d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "73872234"
---
# <a name="generate-data-insights-automatically-with-power-bi"></a>Generér automatisk dataindsigt med Power BI
Har du et nyt datasæt, og er du ikke helt sikker på, hvor du skal starte?  Har du brug for hurtigt at oprette et dashboard?  Vil du hurtigt søge efter indsigter, som du måske gik glip af?

Kør Quick Insights for at oprette interessante interaktive visualiseringer, der er baseret på dine data. Quick Insights kan køres på et helt datasæt (hurtig indsigt) eller på et bestemt dashboardfelt (områdebaseret indsigt). Du kan endda køre indsigter på en indsigt!

> [!NOTE]
> Insights fungerer ikke med DirectQuery. Det fungerer kun med data, der er uploadet til Power BI.
> 

Funktionen Quick Insights er baseret på et voksende [sæt avancerede analytiske algoritmer](service-insight-types.md), der er udviklet sammen med Microsoft Research, som vi vil fortsætte med at bruge for at gøre det muligt for flere personer at finde indsigter i deres data på nye og intuitive måder.

## <a name="run-quick-insights-on-a-dataset"></a>Kør Quick Insights på et datasæt
Se Amanda køre Quick Insights på et datasæt, åbne en indsigt i Fokustilstand, fastgøre en af disse indsigter som et felt på sit dashboard og derefter få indsigter for et dashboardfelt.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Nu er det din tur. Udforsk Insights ved hjælp af [Eksempel på analyse af leverandørkvalitet](sample-supplier-quality.md).

1. På fanen **Datasæt** skal du vælge **Flere indstillinger** (...) og derefter vælge **Få hurtig indsigt**.
   
    ![Fanen Datasæt](media/service-insights/power-bi-ellipses.png)
   
    ![Menuen med tre prikker](media/service-insights/power-bi-tab.png)
2. Power BI bruger [forskellige algoritmer](service-insight-types.md) til at søge efter tendenser i dit datasæt.
   
    ![Søger efter dialogboksen Indsigt](media/service-insights/pbi_autoinsightssearching.png)
3. Dine indsigter er klar på få sekunder.  Vælg **Vis indsigt** for at vise visualiseringer.
   
    ![Meddelelse om fuldførelse](media/service-insights/pbi_autoinsightsuccess.png)
   
    > [!NOTE]
    > Nogle datasæt kan ikke generere indsigt, da dataene ikke er statistisk vigtige.  Hvis du vil vide mere, kan du se [Optimer dine data til indsigt](service-insights-optimize.md).
    > 
    
4. Visualiseringerne vises på et særligt **Hurtig indsigt**-lærred med op til 32 separate indsigtskort. Hvert kort har et diagram eller en graf samt en kort beskrivelse.
   
    ![Lærred med Hurtig indsigt](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Interager med indsigtskortene

1. Hold markøren over et kort, og vælg ikonet med tegnestiften for at føje visualiseringen til et dashboard.

2. Hold over et kort, vælg **Flere indstillinger** (...), og vælg derefter **Vis indsigt**. 

    Skærmbilledet Indsigt åbnes i fokustilstand.
   
    ![Indsigt i fokustilstand](media/service-insights/power-bi-insight-focus.png)
3. I fokustilstand kan du:
   
   * Filtrér visualiseringerne. Hvis ruden **Filtre** ikke allerede er åben, skal du udvide den ved at vælge pilen i højre side af vinduet.

       ![Menuen Filtre i Indsigt udvidet](media/service-insights/power-bi-insights-filter-new.png)
   * Fastgør indsigtskortet til et dashboard ved at vælge **Fastgør visuelt element**.
   * Kør indsigt på selve kortet, der ofte kaldes for *Områdebaseret indsigt*. Øverst til højre skal du vælge ikonet med elpæren ![Få indblik-ikon](media/service-insights/power-bi-bulb-icon.png) eller **Få indblik**.
     
       ![Få indsigt-ikon](media/service-insights/pbi-autoinsights-tile.png)
     
     Indsigterne vises til venstre, og nye kort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.
     
       ![Indsigt i indsigt](media/service-insights/power-bi-insights-on-insights-new.png)
4. Vælg **Afslut Fokustilstand** øverst til venstre, hvis du vil vende tilbage til det oprindelige indsigtslærred.

## <a name="run-insights-on-a-dashboard-tile"></a>Kør indsigt på et dashboardfelt
I stedet for at søge efter indsigt i et helt datasæt kan du begrænse din søgning og foretage en områdebaseret indsigt for de data, der er brugt til at oprette et enkelt dashboardfelt. 

1. Åbn et dashboard.
2. Peg på et felt. vælg **Flere indstillinger** (...), og vælg derefter **Vis indsigt**. Feltet åbnes i [Fokustilstand](service-focus-mode.md) med indsigtskortene vist langs højre.    
   
    ![Fokustilstand](media/service-insights/pbi-insights-tile.png)    
3. Er der en indsigt, der vækker din interesse? Vælg indsigtskortet for at udforske mere. Den valgte indsigt vises til venstre, og nye indsigtskort, som udelukkende er baseret på dataene i den enkelte indsigt, vises til højre.    
4. Fortsæt med udforske dine data, og når du finder en interessant indsigt, kan du fastgøre den til dit dashboard ved at vælge **Fastgør din visual** fra øverste højre hjørne.

## <a name="next-steps"></a>De næste trin
- Hvis du ejer et datasæt, [kan du optimere det til Hurtig indsigt](service-insights-optimize.md).
- Få mere at vide om de [tilgængelige typer Hurtig indsigt](service-insight-types.md).

Har du flere spørgsmål? [Prøv Power BI-community'et](https://community.powerbi.com/).

