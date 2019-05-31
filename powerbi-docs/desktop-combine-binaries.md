---
title: Kombiner filer (binære) i Power BI Desktop
description: Kombiner nemt datakilder med filer (binære) i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: f43bb105f7e17ce453e96c6eff875349efd45cb2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65239625"
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Kombiner filer (binære) i Power BI Desktop
En effektiv måde at importere data på i **Power BI Desktop** er at kombinere flere filer, som har det samme skema, til en enkelt logisk tabel. I versionen af **Power BI Desktop** fra november 2016 (og efterfølgende versioner) er denne praktiske og populære metode blevet nemmere og mere omfattende, som beskrevet i denne artikel.

For at komme i gang med at kombinere filer fra samme mappe skal du vælge **Hent data > Filer > Mappe**.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-files-binaries-behavior"></a>Tidligere funktionsmåde for kombination af filer (binære)
Før versionen af **Power BI Desktop** fra november 2016 blev denne funktionalitet kaldt for **Kombiner binære**, og du kunne kombinere bestemte filtyper med transformationen **Kombiner binære**, men der var nogle begrænsninger:

* Transformeringer blev ikke taget i betragtning for hver enkelt fil, før filerne blev komprimeret til en enkelt tabel. Du var derfor ofte nødt til at kombinere filer og derefter filtrere *headerværdierne* ud ved at filtrere rækker som en del af redigeringsprocessen.
* Transformeringen ved at **kombinere binære filer** fungerede kun for *tekst*- eller *CSV*-filer og kunne ikke anvendes på andre understøttede filformater f.eks. Excel-projektmapper, JSON-filer og andre.

Kunder har anmodet om en mere intuitiv håndtering af handlingen **Kombiner binære**, så transformationen er blevet forbedret og omdøbt til **Kombiner filer**.

## <a name="current-combine-files-behavior"></a>Nuværende funktionsmåde for kombination af filer
**Power BI Desktop** håndterer nu **Kombiner filer (binære)** mere effektivt. Du starter ved at vælge **Kombiner filer** enten på båndet **Hjem** i **Forespørgselseditor** eller fra selve kolonnen.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

Transformationen **Kombiner filer** fungerer nu på følgende måde:

* Transformationen **Kombiner filer** analyserer de enkelte inputfiler og bestemmer det rette filformat, der skal bruges, f.eks. en fil af typen *tekst* eller *Excel-projektmappe* eller *JSON*.
* Transformeringen giver dig mulighed for at vælge et bestemt objekt fra den første fil, f.eks. en *Excel-projektmappe*, der skal trækkes ud.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* **Kombiner filer** udfører derefter automatisk følgende forespørgsler:
  
  * Opretter et eksempel på en forespørgsel, der udfører alle nødvendige udtrækningstrin i en enkelt fil.
  * Opretter en *funktionsforespørgsel*, der angiver parametre for filen/det binære input i *eksempelforespørgslen*. Exempelforespørgslen og funktionsforespørgslen er kædet sammen, så ændringer i eksempelforespørgslen afspejles i funktionsforespørgslen.
  * Anvender *funktionsforespørgslen* på den oprindelige forespørgsel med binære inputfiler (f.eks. forespørgslen *Mappe*), så den anvender funktionsforespørgslen for binære inputfiler på de enkelte rækker og derefter udvider det resulterende dataudtræk som kolonner på øverste niveau.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

Med den nye funktionsmåde for **Kombiner filer** kan du nemt kombinere alle filer i en bestemt mappe, så længe de har samme filtype og struktur (f.eks. de samme kolonner).

Derudover kan du nemt kan anvende yderligere transformations- eller udtrækningstrin ved at ændre den automatisk oprettede *eksempelforespørgsel* uden at skulle bekymre dig om at ændre eller oprette yderligere trin til *funktionsforespørgslen*. Ændringer i *eksempelforespørgslen* oprettes automatisk i den tilknyttede *funktionsforespørgsel*.

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til CSV-filer i Power BI Desktop](desktop-connect-csv.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

