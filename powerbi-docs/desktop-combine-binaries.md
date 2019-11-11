---
title: Kombiner filer (binære) i Power BI Desktop
description: Kombiner nemt datakilder med filer (binære) i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 03a6e044a55613d40a1cf195d6a0ad3b44a9f012
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876562"
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Kombiner filer (binære) i Power BI Desktop
En effektiv måde at importere data på i **Power BI Desktop** er at kombinere flere filer, som har det samme skema, til en enkelt logisk tabel. Denne praktiske og populære tilgang er blevet gjort endnu mere praktisk og mere omfattende, som beskrevet i dette artikel.

For at komme i gang med at kombinere filer fra samme mappe skal du vælge **Hent data > Filer > Mappe**.

![](media/desktop-combine-binaries/combine-binaries_1.png)


## <a name="combine-files-behavior"></a>Funktionsmåden Kombiner filer
Du kan **kombinere filer (binære)** ved at vælge **Kombiner filer** enten via fanen **Hjem** på båndet i **Forespørgselseditor** eller via selve kolonnen.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

Transformationen **Kombiner filer** fungerer på følgende måde:

* Transformationen **Kombiner filer** analyserer de enkelte inputfiler og bestemmer det rette filformat, der skal bruges, f.eks. en fil af typen *tekst* eller *Excel-projektmappe* eller *JSON*.
* Transformeringen giver dig mulighed for at vælge et bestemt objekt fra den første fil, f.eks. en *Excel-projektmappe*, der skal trækkes ud.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* **Kombiner filer** udfører derefter automatisk følgende forespørgsler:
  
  * Opretter et eksempel på en forespørgsel, der udfører alle nødvendige udtrækningstrin i en enkelt fil.
  * Opretter en *funktionsforespørgsel*, der angiver parametre for filen/det binære input i *eksempelforespørgslen*. Exempelforespørgslen og funktionsforespørgslen er kædet sammen, så ændringer i eksempelforespørgslen afspejles i funktionsforespørgslen.
  * Anvender *funktionsforespørgslen* på den oprindelige forespørgsel med binære inputfiler (f.eks. forespørgslen *Mappe*), så den anvender funktionsforespørgslen for binære inputfiler på de enkelte rækker og derefter udvider det resulterende dataudtræk som kolonner på øverste niveau.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

> [!NOTE]
> Omfanget af dit valg i en Excel-projektmappe vil påvirke funktionsmåden for Kombiner binære filer. Du kan f.eks. vælge et bestemt regneark for at kombinere dette regneark eller vælge roden for at kombinere hele filen. Når du vælger en mappe, kombineres de filer, der findes i den pågældende mappe. 


Med funktionsmåden for **Kombiner filer** kan du nemt kombinere alle filer i en bestemt mappe, så længe de har samme filtype og struktur (f.eks. de samme kolonner).

Derudover kan du nemt kan anvende yderligere transformations- eller udtrækningstrin ved at ændre den automatisk oprettede *eksempelforespørgsel* uden at skulle bekymre dig om at ændre eller oprette yderligere trin til *funktionsforespørgslen*. Ændringer i *eksempelforespørgslen* oprettes automatisk i den tilknyttede *funktionsforespørgsel*.

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til CSV-filer i Power BI Desktop](desktop-connect-csv.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

