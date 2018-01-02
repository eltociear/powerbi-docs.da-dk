---
title: Brug af beregnede tabeller i Power BI Desktop
description: Beregnede tabeller i Power BI Desktop
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: bdfbf79f2b261e9246cb406d9ed9c8ebefc1440e
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>Brug af beregnede tabeller i Power BI Desktop
Med beregnede tabeller kan du føje en ny tabel til modellen. Men i stedet for at forespørge efter og indlæse værdier i din nye tabels kolonner fra en datakilde kan du oprette en DAX-formel (Data Analysis Expressions), der definerer værdierne i tabellen. I Power BI Desktop oprettes der beregnede kolonner ved hjælp af funktionen Ny tabel i Rapportvisning eller Datavisning.

I de fleste tilfælde importerer du data til din model fra en ekstern datakilde. Beregnede tabeller giver dog visse fordele. Beregnede tabeller er generelt bedst til mellemliggende beregninger og data, der skal gemmes som en del af modellen, i stedet for løbende beregninger eller beregninger, der er en del af en forespørgsel.

I modsætning til tabeller, der er oprettet som en del af en forespørgsel, baseres beregnede tabeller, der er oprettet i Rapportvisning eller Datavisning, på data, du allerede har indlæst i modellen. Det kan f.eks. være, at du vil forene eller sammenføje to tabeller på tværs.

Beregnede tabeller kan have relationer til andre tabeller på samme måde som normale tabeller. Kolonnerne i den beregnede tabel indeholder datatyper og formatering og kan tilhøre en datakategori. Du kan navngive kolonnerne, som du vil, og føje dem til en rapportvisualisering på samme måde som alle andre felter. Beregnede tabeller beregnes igen, hvis nogen af de tabeller, der hentes data fra, opdateres.

Beregnede kolonner beregner resultater ved hjælp af DAX ([Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx)), der et formelsprog, som er udviklet til at arbejde sammen med relationsdata som i Power BI Desktop. DAX indeholder et bibliotek med mere end 200 funktioner, operatorer og konstruktioner, hvilket giver stor fleksibilitet, når du opretter formler til beregning af resultater for stort set alle dataanalyser.

## <a name="lets-look-at-an-example"></a>Lad os se på et eksempel
Jeff, der er projektleder hos Contoso, har en tabel med medarbejdere i nordvest og en anden tabel med medarbejdere i sydvest. Jeff vil gerne lægge de to tabeller sammen til en enkelt tabel.

**NorthwestEmployees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**SoutwestEmployees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Det er meget let at forene disse to tabeller med en beregnet tabel. Jeff kan oprette en beregnet tabel i enten Rapportvisning eller Datavisning, men det er dog lidt lettere at gøre det i Datavisning, da han kan se sin nye beregnede tabel med det samme.

I **Datavisning** på fanen **Udformning** klikker Jeff på **Ny tabel**. Der vises en formellinjen.

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

Jeff angiver derefter følgende formel:

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

Der oprettes en ny tabel med navnet Western Region Employees.

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

Jeffs nye tabel Western Region Employees vises på samme måde som en hvilken som helst anden tabel på listen Felter. Han kan oprette relationer til andre tabeller, tilføje beregnede kolonner og målinger samt føje en eller flere felter til rapporter på samme måde som en hvilken som helst anden tabel.

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Funktioner i forbindelse med beregnede tabeller
Beregnede tabeller kan defineres af et DAX-udtryk, der returnerer en tabel, herunder en enkelt reference til en anden tabel. Eksempel:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

Du kan bruge beregnede tabeller med DAX for at løse mange analyseproblemer. Vi har kun givet en hurtig introduktion til beregnede tabeller her. Når du begynder at arbejde med beregnede tabeller, er her nogle af de mest almindelige DAX-tabelfunktioner, som måske kan være nyttige:

&lt;TABLE&gt; DISTINCT VALUES CROSSJOIN UNION NATURALINNERJOIN NATURALLEFTOUTERJOIN INTERSECT CALENDAR CALENDARAUTO

Du kan se disse og andre DAX-funktioner, der returnerer en tabel, under [Reference til DAX-funktioner](https://msdn.microsoft.com/ee634396.aspx).

