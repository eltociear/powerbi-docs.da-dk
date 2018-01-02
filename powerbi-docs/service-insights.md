---
title: "Få Hurtig indsigt i Power BI"
description: "Dokumentation til at køre og arbejde med Hurtig indsigt med Power BI-tjenesten."
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
ms.date: 09/01/2017
ms.author: mihart
ms.openlocfilehash: 8b069f29737992817d20396007864cc8c005ca99
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="quick-insights-with-power-bi"></a>Hurtig indsigt med Power BI
Har du et nyt datasæt, og er du ikke helt sikker på, hvor du skal starte?  Har du brug for hurtigt at oprette et dashboard?  Vil du hurtigt søge efter indsigter, som du måske gik glip af?

Kør Hurtig indsigt for at oprette interessante interaktive visualiseringer, der er baseret på dine data. Hurtig indsigt kan køres på et helt datasæt (Hurtig indsigt) eller på et bestemt dashboardfelt (Områdebaseret indsigt). Du kan endda køre Hurtig indsigt på en indsigt!

> **Bemærk!** Hurtig indsigt fungerer ikke med DirectQuery. Det fungerer kun med data, der er uploadet til Power BI.
> 
> 

Funktionen Hurtig indsigt er baseret på et voksende [sæt avancerede analytiske algoritmer](service-insight-types.md), der er udviklet sammen med Microsoft Research, som vi vil fortsætte med at bruge for at gøre det muligt for flere personer at finde indsigter i deres data på nye og intuitive måder.

## <a name="run-quick-insights-on-a-dataset"></a>Kør Hurtig indsigt på et datasæt
Se Amanda køre Hurtig indsigt på et datasæt, åbne en indsigt i Fokustilstand, fastgøre en af disse Hurtige indsigter som et felt på sit dashboard og derefter få Hurtig indsigt i et visuelt element.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Nu er det din tur. Udforsk Hurtig indsigt ved hjælp af [Supplier Quality Analysis Sample](sample-supplier-quality.md).

1. Vælg ellipsen (...) fra fanen **Datasæt**, og vælg **Få indsigt**.
   
    ![](media/service-insights/power-bi-ellipses.png)
   
    ![](media/service-insights/power-bi-tab.png)
2. Power BI bruger [forskellige algoritmer](service-insight-types.md) til at søge efter tendenser i dit datasæt.
   
    ![](media/service-insights/pbi_autoinsightssearching.png)
3. Dine indsigter er klar på få sekunder.  Vælg **Vis indsigter** for at vise visualiseringer.
   
    ![](media/service-insights/pbi_autoinsightsuccess.png)
   
   > **Bemærk!** Nogle datasæt kan ikke generere Hurtig indsigt, da dataene ikke er statistisk vigtige.  Hvis du vil vide mere, kan du se [Optimer dine data til Hurtig indsigt](service-insights-optimize.md).
   > 
   > 
4. Visualiseringerne vises på et særligt **Hurtig indsigt**-lærred med op til 32 separate indsigtskort. Hvert kort har et diagram eller en graf samt en kort beskrivelse.
   
    ![](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-quick-insight-cards"></a>Interager med Hurtig indsigt-kortene
  ![](media/service-insights/pbi_hover.png)

1. Hold markøren over et kort, og vælg ikonet med tegnestiften for at føje visualiseringen til et dashboard.
2. Hold markøren over et kort, og vælg ikonet Fokustilstand for at få vist kortet i fuldskærmsvisning.
   
    ![](media/service-insights/power-bi-insight-focus.png)
3. I fokustilstand kan du:
   
   * [filtrere](service-interact-with-a-report-in-reading-view.md) visualiseringerne.  For at få vist filtrene skal du øverst til højre vælge pilen til at udvide ruden Filtre.
     
        ![](media/service-insights/power-bi-insights-filter-new.png)
   * Fastgør indsigtskortet til et dashboard ved at vælge ikonet ![](media/service-insights/power-bi-pin-icon.png) med tegnestiften eller **Fastgør visuelt element**.
   * Du kan køre Hurtig indsigt på selve kortet. Dette kaldes **Områdebaseret Hurtig indsigt**. Øverst til højre skal du vælge ikonet med elpæren ![](media/service-insights/power-bi-bulb-icon.png) eller **Få indsigt**.
     
       ![](media/service-insights/pbi-autoinsights-tile.png)
     
     Hurtig indsigt vises til venstre, og nye kort, som udelukkende er baseret på dataene i den enkelte Hurtig indsigt, vises til højre.
     
       ![](media/service-insights/power-bi-insights-on-insights-new.png)
4. Vælg **Afslut Fokustilstand** øverst til venstre, hvis du vil vende tilbage til det oprindelige Hurtig indsigt-lærred.

## <a name="run-quick-insights-on-a-dashboard-tile"></a>Kør Hurtig indsigt på et dashboardfelt
I stedet for at søge efter indsigter i et helt datasæt kan du begrænse din søgning til de data, der er brugt til at oprette et enkelt dashboardfelt. Dette kaldes **Områdebaseret Hurtig indsigt**.

1. Åbn et dashboard.
2. Vælg et felt, og [åbn feltet i Fokuseringstilstand](service-focus-mode.md).
3. Vælg **Få indsigt** øverst til højre.
   
    ![](media/service-insights/pbi-autoinsights-tile.png)
4. Power BI viser indsigtskortene langs højre side af feltet.
   
    ![](media/service-insights/pbi-insights-tile.png)
5. Er der en indsigt, der vækker din interesse? Vælg indsigtskortet for at udforske mere. Den valgte Hurtige indsigt vises til venstre, og nye indsigtskort, som udelukkende er baseret på dataene i den enkelte Hurtige indsigt, vises til højre.
6. Fortsæt med udforske dine data, og når du finder en interessant Hurtig indsigt, kan du fastgøre dens visuelle element til dit dashboard ved at vælge **Fastgør visuelt element** fra det øverste højre hjørne. Du kan også sende feedback for at give datasættets ejer besked, om en bestemt Hurtig indsigt var nyttig eller ej.
   
    ![](media/service-insights/useful.png)

## <a name="next-steps"></a>Næste trin
Hvis du ejer et datasæt, [kan du optimere det til Quick Insights](service-insights-optimize.md)

Få mere at vide om de [tilgængelige typer Hurtig indsigt](service-insight-types.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

