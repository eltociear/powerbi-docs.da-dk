---
title: "Interager med en rapport i Læsevisning i Power BI"
description: "Interager med en rapport i Læsevisning i Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/15/2017
ms.author: mihart
ms.openlocfilehash: 54de712e0743801b3e8c565ca997bbc56e254c69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Interager med en rapport i Læsevisning i Power BI
## <a name="reading-view"></a>Læsevisning
Læsevisning er ikke så interaktiv som [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md), men tilstanden giver dig stadigvæk mange indstillinger til udforskning af dine data. Dette kan være praktisk ved visning af rapporter [delt med dig](service-share-dashboards.md), der kun kan åbnes i Læsevisning.

Læsevisning er en sjov og sikker måde at både lege med og lære dine data at kende. I Læsevisning kan du lave tværgående fremhævning og tværgående filtrering af visuelle elementer på en side.  Du skal blot fremhæve eller vælge en værdi i ét visuelt element, og straks kan du se dens indvirkning på de andre visuelle elementer. Brug Filterruden til at tilføje og redigere filtre på en rapportside og ændre den måde, hvorpå værdier sorteres i en visualisering. De filtreringer og fremhævninger, du foretager, gemmes ikke sammen med rapporten.

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>Foretag tværgående fremhævning af de relaterede visualiseringer på en side
De visuelle effekter på en enkelt rapportside er alle indbyrdes "forbundet".  Det betyder, at hvis du vælger én eller flere værdier i en visualisering, ændres andre visualiseringer, der bruger den samme værdi, på baggrund af denne markering.

![](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> Hold CTRL-tasten nede for at vælge mere end ét element i en visualisering.
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>Peg på visuelle elementer for at få vist detaljer
![](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>Sortering af dataene i en visualisering
Vælg ellipserne (...) for at åbne **Sortér efter**. Vælg rullepilen for at markere, hvilket felt der skal sorteres efter, eller vælg AZ-ikonet for at skifte mellem stigende og faldende. 

![](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>Interager med filtre
Hvis rapportens forfatter har tilføjet filtre til en side i en rapport, kan du interagere med dem i Læsevisning. De ændringer, du foretager, bliver ikke gemt sammen med rapporten.

1. Vælg Filterikonet i øverste højre hjørne.
   
   ![](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. Du får vist alle de filtre, der er anvendt til det visuelle element, som du har valgt (Filtre på visualiseringsniveau), på tværs af hele rapportsiden (Filtre på sideniveau) og på tværs af hele rapporten (Filtre på rapporteringsniveau).
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. Peg på et filter, og udvid det ved at vælge pil ned.
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. Foretag ændringer af filtrene, og se, hvordan de visuelle elementer påvirkes.  
   
   * I dette eksempel har vi et Filter på sideniveau for **Kæde**. Skift til **Fashions Direct** i stedet for **Lindseys** ved at fjerne markeringen fra en og føje den til en anden.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * Eller fjern filtrering helt på **Kæde** ved at vælge viskelæderikonet ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) eller ved at vælge begge kædebutikker.
   * Vælg **Område**-filtret på sideniveau, og skift til **Avanceret filtrering**. Filtrer for kun at få vist områder, der starter med **FD** og ikke indeholder tallet 4.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

Du kan finde flere oplysninger i [Føj et filter til en rapport](power-bi-report-add-filter.md) og [Om filtre og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md).

## <a name="zoom-in-on-individual-visuals"></a>Zoom ind på individuelle visuelle elementer
Peg på en visuel gengivelse, og vælg ikonet **Fokuseringstilstand**![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg). Når du får vist en visualisering i fokuseringstilstand, udvides den, så den fylder hele rapportlærredet som vist nedenfor.

![](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

Vælg ikonet for **Fuld skærm** i den øverste menulinje for at få vist den samme visualisering uden forstyrrende menulinjer  ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png)  .

![](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

Du kan få mere at vide under [Fokuseringstilstand til rapporter](service-focus-mode.md) og [Fuldskærmstilstand til rapporter](service-fullscreen-mode.md)

## <a name="adjust-the-display-dimensions"></a>Tilpas visningsdimensionerne
Rapporter vises på mange forskellige enheder med forskellig skærmstørrelse og størrelsesforhold.  Standardgengivelsen er måske ikke lige det, du ønsker at se på din enhed.  Hvis du vil justere, skal du markere **Visning** og vælge:

* Tilpas til siden: Skaler indholdet, så det passer bedst til siden
* Tilpas til siden: Skaler indholdet, så det passer bedst til siden
* Faktisk størrelse: Vis indholdet i fuld størrelse  

![](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  I Læsevisning er den visningsindstilling du vælger midlertidig – den gemmes ikke, når du lukker rapporten.

  Hvis du vil vide mere, kan du se [Selvstudium: Ændring af visningsindstillingerne i en rapport](power-bi-change-report-display-settings.md).

## <a name="next-steps"></a>Næste trin
[Rapporter i Power BI](service-reports.md)

[Åbn Redigeringsvisning](service-reading-view-and-editing-view.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

