---
title: "Kombiner binære filer i Power BI Desktop"
description: "Kombiner nemt binære datakilder i Power BI Desktop"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 395562dfecba4657ffa906494f81532febb6a11f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="combine-binaries-in-power-bi-desktop"></a>Kombiner binære filer i Power BI Desktop
En effektiv måde at importere data på i **Power BI Desktop** er at kombinere flere filer, som har det samme skema, til en enkelt logisk tabel. I versionen af **Power BI Desktop** fra november 2016 (og efterfølgende versioner) er denne praktiske og populære metode blevet nemmere og mere omfattende, som beskrevet i denne artikel.

For at komme i gang med at kombinere binære filer fra samme mappe skal du vælge **Hent data > Filer > Mappe**.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-binaries-behavior"></a>Tidligere funktionsmåde for kombination af binære filer
Før versionen af **Power BI Desktop** fra november 2016 kunne du kombinere visse filtyper via transformeringen ved at **kombinere binære filer**, men der var begrænsninger:

* Transformeringer blev ikke taget i betragtning for hver enkelt fil, før filerne blev komprimeret til en enkelt tabel. Du var derfor ofte nødt til at kombinere filer og derefter filtrere *headerværdierne* ud ved at filtrere rækker som en del af redigeringsprocessen.
* Transformeringen ved at **kombinere binære filer** fungerede kun for *tekst*- eller *CSV*-filer og kunne ikke anvendes på andre understøttede filformater f.eks. Excel-projektmapper, JSON-filer og andre.

Kunder har anmodet om en mere intuitiv håndtering af transformeringen ved at **kombinere binære filer**, så transformeringen er blevet forbedret.

## <a name="current-combine-binaries-behavior"></a>Tidligere funktionsmåde for kombination af binære filer
**Power BI Desktop** håndterer nu de **kombinerede binære filer** mere effektivt. Du starter ved at vælge **Kombiner binære** enten på båndet **Hjem** i **forespørgselseditoren** eller fra selve kolonnen.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

Transformeringen ved at **kombinere binære filer** fungerer nu på følgende måde:

* Transformeringen ved at **kombinere binære filer** analyserer de enkelte inputfiler og bestemmer det rette filformat, der skal bruges, f.eks. en fil af typen *tekst* eller *Excel-projektmappe* eller *JSON*.
* Transformeringen giver dig mulighed for at vælge et bestemt objekt fra den første fil, f.eks. en *Excel-projektmappe*, der skal trækkes ud.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* De **kombinerede binære filer** gør derefter automatisk følgende:
  
  * Opretter et eksempel på en forespørgsel, der udfører alle nødvendige udtrækningstrin i en enkelt fil.
  * Opretter en *funktionsforespørgsel*, der angiver parametre for filen/det binære input i *eksempelforespørgslen*. Exempelforespørgslen og funktionsforespørgslen er kædet sammen, så ændringer i eksempelforespørgslen afspejles i funktionsforespørgslen.
  * Anvender *funktionsforespørgslen* på den oprindelige forespørgsel med binære inputfiler (f.eks. forespørgslen *Mappe*), så den anvender funktionsforespørgslen for binære inputfiler på de enkelte rækker og derefter udvider det resulterende dataudtræk som kolonner på øverste niveau.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

Med den nye funktionsmåde for **kombinerede binære filer** kan du nemt kombinere alle binære filer i en bestemt mappe, hvis de har samme filtype og struktur (dvs. de samme kolonner).

Derudover kan du nemt kan anvende yderligere transformerings- eller udtrækstrin ved at ændre den automatisk oprettede *eksempelforespørgsel* uden at skulle bekymre dig om at ændre eller oprette yderligere trin til *funktionsforespørgslen*. Ændringer i *eksempelforespørgslen* oprettes automatisk i den tilknyttede *funktionsforespørgsel*.

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til CSV-filer i Power BI Desktop](desktop-connect-csv.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

