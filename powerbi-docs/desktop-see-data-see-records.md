---
title: Vis data og poster i visualiseringer i Power BI Desktop
description: Brug funktionerne Vis data og Vis poster i Power BI Desktop til at analysere oplysninger
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 667b6eac288d3be35eac619b669498b6d7381dc3
ms.sourcegitcommit: 2aa83bd53faad6fb02eb059188ae623e26503b2a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/29/2019
ms.locfileid: "73019258"
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Brug Vis data og Vis poster i visualiseringer i Power BI Desktop
I **Power BI Desktop** kan du analysere alle visualiseringers detaljer og få vist en tekstrepræsentation af de underliggende data eller enkelte dataposter for den valgte visual. Disse funktioner kaldes nogle gange for *klikfrekvens*, *detaljeadgang* eller *detaljeadgang til oplysninger*.

Du kan bruge **Vis data** til at få vist en tekstversion af de værdier, der bruges af den valgte visualisering, eller bruge **Vis poster** til at få vist alle dataene for en valgt post eller et valgt datapunkt. 

![Vis data og Vis poster](media/desktop-see-data-see-records/see-data-record.png)

>[!IMPORTANT]
>**Vis Data** og **Vis poster** understøtter kun følgende visualiseringstyper:
>  - Liggende søjlediagram
>  - Søjlediagram
>  - Kransediagram
>  - Kartogram
>  - Tragt
>  - Kort
>  - Cirkeldiagram
>  - Træstruktur

## <a name="use-see-data-in-power-bi-desktop"></a>Brug af Vis data i Power BI Desktop

**Vis Data** viser de data, der ligger under en visualisering. **Vis data** er placeret på fanen **Data/Analysér** i sektionen **Visual Tools** på båndet, når en visualisering vælges.

![Vis data på båndet](media/desktop-see-data-see-records/see-data1.png)

Du kan også se dataene ved at højreklikke på en visualisering og derefter vælge **Vis Data** i den menu, der vises, eller ved at vælge **Flere indstillinger** (...) i øverste højre hjørne af en visualisering og derefter vælge **Vis Data**.

![Vis Data, højreklik](media/desktop-see-data-see-records/see-data2.png)&nbsp;&nbsp;![Vis Data, flere indstillinger](media/desktop-see-data-see-records/see-data3.png)

> [!NOTE]
> Du skal pege på et datapunkt i den pågældende visual, før højrekliksmenuen er tilgængelig.

Når du vælger **Vis data** eller **Få vist Data**, vises den pågældende visual og tekstrepræsentationen af dataene på canvasset i Power BI Desktop. I den *vandrette visning* vises den pågældende visual på den øverste halvdel af canvasset, og dataene vises på den nederste halvdel. 

![vandret visning](media/desktop-see-data-see-records/see-data4a.png)

Du kan skifte mellem den vandrette visning og en *lodret visning* ved at vælge ikonet i øverste højre hjørne på canvasset.

![Skift til lodret visning](media/desktop-see-data-see-records/see-data4.png)

Du vender tilbage til rapporten ved at vælge **< Tilbage til rapport** i øverste venstre hjørne på canvasset.

![Tilbage til rapport](media/desktop-see-data-see-records/see-data5.png)

## <a name="use-see-records-in-power-bi-desktop"></a>Brug af Vis poster i Power BI Desktop

Du kan også fokusere på ét dataelement i en visualisering og analysere de underliggende data. Du bruger **Vis poster** ved at vælge en visualisering, derefter vælge **Vis poster** på fanen **Data/Analysér** i afsnittet **Visual Tools** på båndet og derefter vælge et datapunkt eller en datarække på visualiseringen. 

![Vis poster på båndet](media/desktop-see-data-see-records/see-record1.png)

> [!NOTE]
> Hvis knappen **Vis poster** på båndet er deaktiveret og nedtonet, betyder det, at den valgte visualisering ikke understøtter **Vis poster**.

Du kan også højreklikke på et dataelement og vælge **Vis poster** i den menu, der vises.

![Vis poster ved at højreklikke](media/desktop-see-data-see-records/see-record2.png)

Når du vælger **Vis poster** for et dataelement, vises alle de data, der er tilknyttet det valgte element, på canvasset i Power BI Desktop. 

![](media/desktop-see-data-see-records/see-record3.png)

Du vender tilbage til rapporten ved at vælge **< Tilbage til rapport** i øverste venstre hjørne på canvasset.

![](media/desktop-see-data-see-records/see-record4.png)

> [!NOTE]
>**Vis poster** har følgende begrænsninger:
> - Du kan ikke ændre dataene i visningen **Vis poster** og gemme dem i rapporten.
> - Du kan ikke bruge **Vis poster**, når der benyttes en beregnet måling i den pågældende visual.
> - Du kan ikke bruge **Vis poster**, når du har forbindelse til en live flerdimensionel model.

## <a name="next-steps"></a>Næste trin
**Power BI Desktop** indeholder mange forskellige funktioner til formatering af rapporter og dataadministration. I følgende ressourcer kan du se nogle eksempler:

* [Brug gruppering og gruppering i beholder i Power BI Desktop](desktop-grouping-and-binning.md)
* [Brug gitterlinjer, fastgørelse til gitter, z-rækkefølge, justering og fordeling i Power BI Desktop-rapporter](desktop-gridlines-snap-to-grid.md)

