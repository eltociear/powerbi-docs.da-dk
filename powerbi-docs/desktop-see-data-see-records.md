---
title: Vis data og poster i visualiseringer i Power BI Desktop
description: Brug funktionerne Vis data og Vis poster i Power BI Desktop til at analysere oplysninger
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/09/2017
ms.author: davidi
ms.openlocfilehash: c43ec48d1bd34a5df2578c6cc117dd3e3bbdb64f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Brug Vis data og Vis poster i visualiseringer i Power BI Desktop
I **Power BI Desktop** kan du analysere alle visualiseringers detaljer og få vist en tekstrepræsentation af dataene eller enkelte dataelementer for en valgt visualisering. Disse funktioner kaldes nogle gange for *klikfrekvens*, *detaljeadgang* eller *detaljeadgang til oplysninger*.

Du kan bruge **Vis poster** til at få vist de underliggende rækker for ét valgt dataelement fra en visualisering eller bruge **Vis data** til at få vist en tekstversion af de værdier, der bruges i visualiseringen. Der er nogle begrænsninger ved brug af **Vis data** og **Vis poster**, hvilket beskrives i slutningen af denne artikel.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Brug af Vis data i Power BI Desktop
Knappen **Vis data** er placeret på fanen **Data/analyse** under sektionen **Værktøjer til visualiseringer** på båndet.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

Du kan også **få vist data** ved at højreklikke på en visualisering og derefter vælge **Vis data** i den menu, der vises.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> Du skal holde over et datapunkt i visualiseringen, før højrekliksmenuen er tilgængelig.
> 
> 

Når du vælger **Vis data**, fokuserer **Power BI Desktop** på den visualisering og de data, du har valgt, og dedikerer plads på canvasset til at vise denne visualisering og tekstrepræsentationen af dataene. Visualiseringen vises på den øverste halvdel af lærredet, og dataene vises på den nederste halvdel, som vist på følgende billede. Dette er den *vandrette* visning.

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

Du kan også skifte til en *lodret visning* (eller tilbage til *vandret visning*) ved at vælge ikonet i øverste højre hjørne.

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

Hvis du vil vende tilbage til rapporten, skal du vælge **< Tilbage til rapport** i øverste venstre hjørne på canvasset.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Brug af Vis poster i Power BI Desktop
Du kan også fokuserer på ét dataelement i en visualisering og analysere de underliggende data. Når en visualisering vælges, er der to måder at bruge **Vis poster** på: Du kan aktivere til/fra-knappen **Vis poster** på båndet **Data/analyse** og derefter klikke på et dataelement, eller du kan højreklikke på et dataelement og vælge **Vis poster** i den menu, der vises.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> Hvis den valgte visualisering ikke understøtter **Vis poster**, er knappen nedtonet på båndet.
> 
> 

Når du har valgt **Vis poster**, fokuserer **Power BI Desktop** på dette enkelte dataelement og dedikerer canvasområdet til at vise dataene for dette element, som vist på følgende billede.

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

Hvis du vil vende tilbage til rapporten, skal du vælge knappen **Tilbage til rapport** i øverste venstre hjørne på canvasset.

## <a name="limitations"></a>Begrænsninger
Der er nogle få begrænsninger, som skal overvejes, når **Vis data** eller **Vis poster** bruges:

* Det er kun følgende visualiseringstyper, der understøttes:
  * **Søjle**
  * **Kolonne**
  * **Kort**
  * **Trækort**
  * **Kartogram**
  * **Cirkel**
  * **Krans**
  * **Tragtformet**
* Du kan ikke bruge **Vis poster**, når der benyttes en beregnet måling i visualiseringen
* Du kan ikke bruge **Vis poster**, når du har forbindelse til en live flerdimensionel model

## <a name="next-steps"></a>Næste trin
**Power BI Desktop** indeholder mange forskellige funktioner til formatering af rapporter og dataadministration. I følgende ressourcer kan du se nogle eksempler:

* [Brug gruppering og gruppering i beholder i Power BI Desktop](desktop-grouping-and-binning.md)
* [Brug gitterlinjer, fastgørelse til gitter, z-rækkefølge, justering og fordeling i Power BI Desktop-rapporter](desktop-gridlines-snap-to-grid.md)

