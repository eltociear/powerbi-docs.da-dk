---
title: Brug af beregnede kolonner i Power BI Desktop
description: Beregnede kolonner i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 4178dd37acf12efbe8dd00baed4f6b72ab549841
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2020
ms.locfileid: "75762042"
---
# <a name="create-calculated-columns-in-power-bi-desktop"></a>Opret beregnede kolonner i Power BI Desktop
Med beregnede kolonner kan du føje nye data til en tabel, der allerede findes i din model. Men i stedet for at forespørge efter og indlæse værdier i din nye kolonne fra en datakilde kan du oprette en DAX-formel (Data Analysis Expressions), der definerer værdierne i kolonnen. I Power BI Desktop oprettes der beregnede kolonner ved hjælp af funktionen Ny kolonne i rapportvisningen.

I modsætning til brugerdefinerede kolonner, der oprettes som en del af en forespørgsel ved hjælp af Tilføj brugerdefineret kolonne i forespørgselseditoren, er beregnede kolonner, der oprettes i rapportvisningen eller datavisningen baseret på data, du allerede har indlæst i modellen. Du kan f.eks. vælge at sammenkæde værdier fra to forskellige kolonner i to forskellige men relaterede tabeller, udføre addition eller udtrække understrenge.

Beregnede kolonner, du opretter, vises i felterne på samme måde som alle andre felter, men de har et særligt ikon, der viser, at værdierne er et resultat af en formel. Du kan navngive dine kolonner, som du ønsker det, og føje dem til en rapportvisualisering på samme måde som alle andre felter.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

Beregnede kolonner beregner resultater ved hjælp af [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX), et formelsprog, der er udviklet til at arbejde sammen med relationsdata som i Power BI Desktop. DAX inkluderer et bibliotek med mere end 200 funktioner, operatorer og konstruktioner, hvilket giver stor fleksibilitet, når du opretter formler til beregning af resultater for stort set alle dataanalyser. Du kan få mere at vide om DAX i afsnittet Få mere at vide nederst i denne artikel.

DAX-formler ligner Excel-formler. Faktisk har DAX mange af de samme funktioner som Excel. Men DAX-funktioner er udviklet til at arbejde via data, der opdeles eller filtreres interaktivt i en rapport som i Power BI Desktop. I modsætning til Excel, hvor du kan have en forskellig formel for hver række i en tabel, er det sådan, at når du opretter en DAX-formel for en ny kolonne, beregner den et resultat for alle rækker i tabellen. Kolonneværdier genberegnes efter behov, f.eks. når de underliggende data opdateres, og værdier er ændret.

## <a name="lets-look-at-an-example"></a>Lad os se på et eksempel
Jeff er shipping manager ved Contoso og vil gerne oprette en rapport, der viser antallet af forsendelser til diverse byer. Jeff har tabellen Geographymed separate felter for by og stat. Men Jeff vil gerne have, at rapporten skal vise City, State som en enkelt værdi på samme række. Jeffs Geography-tabel indeholder i øjeblikket ikke det ønskede felt.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

Men med en beregnet kolonne kan Jeff samle, eller sammenkæde, byerne fra kolonnen City med staterne fra kolonnen State.

Jeff højreklikker på tabellen Geography og klikker derefter på Ny kolonne. Derefter indtaster Jeff følgende DAX-formel i formellinjen:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

Denne formel opretter ganske enkelt en ny kolonne, der hedder CityState, og for hver række i tabellen Geography henter den værdier fra kolonnen City, tilføjer et komma og et mellemrum og sammenkæder derefter værdierne fra kolonnen State.

Jeff har nu det ønskede felt.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Jeff kan føje det til sit rapportlærred sammen med antallet af forsendelser. Jeff har nu meget hurtigt og med minimal indsats et felt af typen City, State, som kan føjes til stort set alle visualiseringstyper. Jeff ser, at når der oprettes en kortvisualisering, ved Power BI Desktop allerede, hvordan værdierne for City, State i den nye kolonne skal læses.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>Få mere at vide
Vi har kun givet en hurtig introduktion til beregnede kolonner her. Husk at se [Selvstudium: Opret beregnede kolonner i Power BI Desktop](desktop-tutorial-create-calculated-columns.md), hvor du kan downloade en eksempelfil og få trinvise vejledninger i, hvordan du opretter flere kolonner. 

Du kan få mere at vide om DAX under [Grundlæggende DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Du kan få mere at vide om kolonner, du opretter i forbindelse med en forespørgsel, ved at gå til afsnittet Opret brugerdefinerede kolonner i [Almindelige Query-opgaver i Power BI Desktop](desktop-common-query-tasks.md).  

