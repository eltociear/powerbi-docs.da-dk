---
ms.openlocfilehash: 06ee6ad7ade46d811c6340d905150c6dd3810c55
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273235"
---
Med DAX er der mange funktioner, der er tilgængelige til at forme eller på anden måde at analysere dataene. Disse funktioner kan grupperes i en række kategorier:

* **Sammenlægningsfunktioner**
* **Optællingsfunktioner**
* **Logiske**  funktioner
* **Informationsfunktioner**
* **Tekstfunktioner**
* **Datofunktioner**

Svarer til Excel: Når du begynder at indtaste formlen i Power BI Desktops **formellinje**, vises der en liste over tilgængelige funktioner som hjælp til at afgøre, hvilken tilgængelig funktion du vil vælge. Og ved at bruge pil **op** og **ned** på tastaturet kan du fremhæve enhver af de tilgængelige funktioner, og der vises en kort beskrivelse.

Power BI viser de funktioner, der svarer til de bogstaver, du har skrevet indtil videre, så hvis du skriver *S*, vises der på listen kun funktioner, som starter med *S*. Hvis du skriver *Su*, vises kun funktioner, der *indeholder* bogstavsekvensen *Su* i navnet, på listen (de behøver ikke at starte med *Su*, de skal bare indeholde denne bogstavsekvens).

![](media/7-3-dax-functions/dax-functions_1.png)

Det er nemt at eksperimentere med DAX på denne måde og finde hver af de forskellige DAX-funktioner, der er tilgængelige i Power BI. Du skal blot begynde at skrive, og Power BI hjælper dig på vej.

Nu, hvor vi ved, hvordan vi får denne DAX-formel startet, kan vi igen se på hver af disse funktionskategorier.

## <a name="aggregation-functions"></a>Sammenlægningsfunktioner
DAX har en række **sammenlægningsfunktioner**, herunder følgende ofte benyttede funktioner:

* SUM
* AVERAGE
* MIN
* MAX
* SUMX (og andre *X*-funktioner)

Disse funktioner kan kun bruges på numeriske kolonner og kan generelt kun lægge én kolonne sammen ad gangen.

Men særlige sammenlægningsfunktioner, der slutter med **X**, f.eks. **SUMX**, kan fungere over flere kolonner. Disse funktioner løber gennem tabellen og evaluerer udtrykket for hver række.

## <a name="counting-functions"></a>Optællingsfunktioner
Ofte brugte **optællingsfunktioner** i DAX omfatter følgende:

* COUNT
* COUNTA
* COUNTBLANK
* COUNTROWS
* DISTINCTCOUNT

Disse funktioner tæller forskellige elementer, f.eks. entydige værdier, ikke-tomme værdier og rækker i tabellen.

## <a name="logical-functions"></a>Logiske funktioner
Samlingen af **logiske** funktioner i DAX omfatter:

* AND
* OR
* NOT
* IF
* IFERROR

Disse specialfunktioner kan også udtrykkes med *operatorer*. For eksempel kan **AND** skrives som (erstattet med) **&&** i DAX-formlen.

Du kan bruge operatorer (f.eks. **&&** ), når du har brug for mere end to betingelser i formlen, men det er på den anden side bedste praksis at bruge selve funktionsnavnet (f.eks. **AND**) for at gøre DAX-koden mere læselig.

## <a name="information-functions"></a>Informationsfunktioner
**Informationsfunktioner** i DAX omfatter:

* ISBLANK
* ISNUMBER
* ISTEXT
* ISNONTEXT
* ISERROR

Selv om disse funktioner af og til kan være nyttige, er det værdifuldt at kende kolonnernes datatype på forhånd i stedet for at være afhængig af, at disse funktioner angiver datatypen.

DAX bruger funktionerne **MAX** og **MIN** til både at *sammenlægge* værdier og til at *sammenligne* værdier.

## <a name="text-functions"></a>Tekstfunktioner
**Tekstfunktioner** i DAX omfatter følgende:

* CONCATENTATE
* REPLACE
* SEARCH
* UPPER
* FIXED

Disse **tekstfunktioner** ligger meget tæt på Excel-funktioner, der har det samme navn, så hvis du ved, hvordan Excel håndterer tekstfunktioner, er du allerede et skridt videre. Hvis ikke, kan du altid eksperimentere med disse funktioner i Power BI og lære mere om, hvordan de fungerer.

## <a name="date-functions"></a>Datofunktioner
DAX indeholder følgende **datofunktioner**:

* DATE
* TIME
* NOW
* EOMONTH
* WEEKDAY

Selvom disse funktioner kan bruges til at beregne og udtrække oplysninger fra *datoværdier*, gælder de ikke for tidsintelligens, som bruger en datotabel.

> Videoindholdet er fra [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

