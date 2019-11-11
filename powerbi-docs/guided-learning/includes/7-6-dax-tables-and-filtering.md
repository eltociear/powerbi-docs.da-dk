---
ms.openlocfilehash: 5bc0d3bbfb2c2b67b56e6406646f6131a360b97d
ms.sourcegitcommit: a5853ef44ed52e80eabee3757bb6887fa400b75b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799771"
---
Én væsentlig forskel mellem **DAX** og Excel-formelsprog er, at DAX giver dig mulighed at overføre *hele tabeller* mellem udtryk i stedet for, at det er begrænset til en enkelt værdi. Én effektiv effekt er, at DAX gør det muligt at filtrere tabeller i dens udtryk og derefter arbejde med det filtrerede værdisæt.

![](media/7-6-dax-tables-and-filtering/dax-tables-filtering_1.png)

Med DAX kan du oprette helt nye beregnede tabeller og derefter behandle dem som enhver anden tabel, herunder oprette relationer mellem dem og andre tabeller i din datamodel.

## <a name="dax-table-functions"></a>DAX-tabelfunktioner
DAX har en lang række **tabelfunktioner**, herunder følgende:

* FILTER
* ALLE
* VÆRDIER
* DISTINCT
* RELATEDTABLE

Disse funktioner returnerer en hel tabel i stedet for en værdi. Du bruger typisk resultaterne fra en **tabelfunktion** i den videre analyse som en del af et større udtryk i stedet for at bruge den returnerede tabel som en endelig værdi. Det er vigtigt at være opmærksom på, at når du bruger en funktion i tabellen, arver resultaterne relationerne mellem deres kolonner.

Du kan blande tabelfunktioner i udtrykket, så længe hver funktion bruger en tabel og returnerer en tabel. For eksempel skal du overveje følgende DAX-udtryk:

    FILTER (ALL (Table), Condition)

Det udtryk lægger et filter over hele *Tabellen* og ignorerer eventuel aktuelt filterindhold.

Funktionen DISTINCT returnerer de distinkte værdier i en kolonne, der også er synlige i den aktuelle kontekst. Så for at bruge ovenstående eksempel på DAX-udtryk: Hvis du bruger **ALL** i det udtryk, ignoreres filtre, og hvis du erstatter **ALL** med **DISTINCT**, overvåges de.

## <a name="counting-values-with-dax"></a>Tæl værdier med DAX
Et almindeligt spørgsmål, som Power BI-rapportgeneratorer ønsker at besvare, er følgende:

* Hvor mange værdier har jeg til denne kolonne?

Det kan være et simpelt spørgsmål at besvare med en tabel foran dig, men DAX griber det an på en anden måde, særligt når der er en relation mellem tabellerne.

Power BI og DAX indeholder værdier, der ikke er korrekt krydsindekseret. Hvis den indgående relationen brydes, tilføjer DAX en ny række til den relaterede tabel, der indeholder de tomme celler i alle felter, og tilknytter den nye række til den ikke-indekserede række for at garantere referentiel integritet. Hvis din funktion indeholder tomme rækker, hvilket ofte er tilfældet, når man bruger **ALLE**, vil de tomme rækker derefter blive medtaget i antallet af værdier, der returneres for den pågældende kolonne.

Du kan også oprette hele beregnede tabeller ved hjælp af DAX-funktioner. Beregnede tabeller, der er oprettet ved hjælp af DAX, kræver funktionerne **NAVN** og **TABEL**. Beregnede tabeller kan bruges som enhver anden tabel, herunder ved oprettelse af relationer.

> Videoindholdet er fra [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax)
> 
> 

