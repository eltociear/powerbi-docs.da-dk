---
title: Brug af beregnede tabeller i Power BI Desktop
description: Beregnede tabeller i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: c72387d40ddf4b193481a37dbcb40695668eab66
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "75837353"
---
# <a name="create-calculated-tables-in-power-bi-desktop"></a>Opret beregnede tabeller i Power BI Desktop
I de fleste tilfælde opretter du tabeller ved at importere data til din model fra en ekstern datakilde. Men med *beregnede tabeller* kan du tilføje nye tabeller, der er baseret på data, du allerede har indlæst i modellen. I stedet for at forespørge efter og indlæse værdier i din nye tabels kolonner fra en datakilde kan du oprette en [DAX-formel (Data Analysis Expressions)](/dax/index), der definerer værdierne i tabellen.

DAX er et formelsprog, der bruges til at arbejde med relationsdata, som i Power BI Desktop. DAX inkluderer et bibliotek med mere end 200 funktioner, operatorer og konstruktioner, hvilket giver stor fleksibilitet, når du opretter formler til beregning af resultater for stort set alle dataanalyser. Beregnede tabeller er bedst til mellemliggende beregninger og data, der skal gemmes som en del af modellen, i stedet for løbende beregninger eller som forespørgselsresultater. Det kan f.eks. være, at du vil *forene* eller *sammenføje* to eksisterende tabeller på tværs.

Beregnede tabeller kan have relationer til andre tabeller på samme måde som andre Power BI Desktop-tabeller. Beregnede tabelkolonner indeholder datatyper og formatering og kan tilhøre en datakategori. Du kan navngive kolonnerne, som du vil, og føje dem til rapportvisualiseringer på samme måde som alle andre felter. Beregnede tabeller beregnes igen, hvis en eller flere af de tabeller, de henter data fra, opdateres.

## <a name="create-a-calculated-table"></a>Opret en beregnet tabel

Du opretter beregnede tabeller ved hjælp af funktionen **Ny tabel** i Rapportvisning eller Datavisning i Power BI Desktop.

Forestil dig f.eks., at du er personalechef, der har en tabel med **Northwest Employees** og en anden tabel med **Southwest Employees**. Du vil kombinere de to tabeller i en enkelt tabel, der kaldes **Western Region Employees**.

**Northwest Employees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**Southwest Employees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

I Rapportvisning eller Datavisning i Power BI Desktop skal du i gruppen **Beregninger** under fanen **Udformning** vælge **Ny tabel**. Det er lidt nemmere at gøre i Datavisning, da du straks kan se den nye beregnede tabel.

 ![Ny tabel i Datavisning](media/desktop-calculated-tables/calctables_formulabarempty.png)

Indtast følgende formel på formellinjen:

```dax
Western Region Employees = UNION('Northwest Employees', 'Southwest Employees')
```

Der oprettes en ny tabel med navnet **Western Region Employees**, og den vises på samme måde som en hvilken som helst anden tabel på ruden **Felter**. Du kan oprette relationer til andre tabeller, tilføje målinger og beregnede kolonner samt føje felterne til rapporter på samme måde som en hvilken som helst anden tabel.

 ![Ny beregnet tabel](media/desktop-calculated-tables/calctables_westregionempl.png)

 ![Ny tabel i ruden Felter](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Funktioner i forbindelse med beregnede tabeller

Du kan definere en beregnet tabel af et DAX-udtryk, der returnerer en tabel, herunder en enkelt reference til en anden tabel. Eksempel:

```dax
New Western Region Employees = 'Western Region Employees'
```

I denne artikel får du kun en hurtig introduktion til beregnede tabeller. Du kan bruge beregnede tabeller med DAX for at løse mange analyseproblemer. Her er nogle af de mest almindelige DAX-tabelfunktioner, som du kan bruge:

* DISTINCT
* VÆRDIER
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

Du kan se disse og andre DAX-funktioner, der returnerer en tabel, under [Reference til DAX-funktioner](/dax/dax-function-reference).

