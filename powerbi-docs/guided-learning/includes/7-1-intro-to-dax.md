---
ms.openlocfilehash: 6366dbe4d7c58b49b4085d80aa690fd6c64fee59
ms.sourcegitcommit: 226b47f64e6749061cd54bf8d4436f7deaed7691
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/09/2019
ms.locfileid: "70847671"
---
Velkommen til afsnittet Power BI **Kursus med vejledning**, der er lavet for at introducere dig til **DAX**.

**DAX** står for **Data Analysis Expressions** og er det formelsprog, der bruges i hele Power BI (det bruges også i kulissen af Power BI). DAX findes også i andre tilbud fra Microsoft, f.eks. Power Pivot og SSAS-tabel, men i disse emner i Kursus med vejledning fokuseres der på, hvordan DAX bruges – og kan bruges af dig – i Power BI.

## <a name="dax-and-this-guided-learning-video-series"></a>DAX og denne videoserie om Kursus med vejledning
Målet for dette afsnit af **Kursus med vejledning** er at lære dig de grundlæggende elementer i DAX – hvordan du skal tænke om DAX, hvordan det fungerer og de mest nyttige funktioner som forklaret (og som lært med masser af erfaring) af den anerkendte DAX-ekspert, [ Alberto Ferrari](http://www.sqlbi.com/learning-dax).

![Portræt af Alberto Ferrari](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

Videoer i dette afsnit af **Kursus med vejledning** om **DAX** lærer dig de grundlæggende funktioner i DAX, ud fra hvordan DAX-formelsproget fungerer. Dette er nyttigt, når du opretter DAX-formler fra bunden, men det er også meget nyttigt for at forstå, hvordan Power BI opretter de DAX-formler, når du opretter forespørgsler i **Forespørgselseditoren**.

## <a name="in-this-video---introduction-to-dax"></a>I denne video – Introduktion til DAX
DAX-begreber er enkle og ligetil, men DAX er et stærkt redskab. DAX bruger nogle unikke programmeringsbegreber og -mønstre, hvilket kan gøre det svært at bruge og forstå fuldt ud. De traditionelle metoder til at lære et nyt sprog er muligvis ikke den bedste tilgang til DAX, så målet for denne video er at lære dig begreber og teori, der kan hjælpe dig senere, når du arbejder med Power BI.

DAX er et *funktionelt sprog*, hvilket betyder, at den fulde udførte kode er indeholdt i en funktion.

I DAX kan funktioner indeholde andre indlejrede funktioner, betingede sætninger og værdireferencer. Udførelse i DAX starter fra den inderste funktion eller parameter og arbejder sig udad. I Power BI skrives DAX-formler i en enkelt linje, så det er vigtigt for læsbarheden at formatere dine funktioner korrekt.

DAX er designet til at fungere med tabeller, så der er kun to primære datatyper: **Numerisk** og **Andet**. **Numerisk** kan indeholde *heltal*, *decimaler* og *valuta*. **Andet** kan indeholde *strenge* og *binære objekter*. Det betyder, at hvis du opbygger DAX-funktionen til at fungere på én type tal, kan du være sikker på, at den fungerer på andre numeriske data.

DAX bruger overbelastning af operatorer, hvilket betyder, at du kan blande datatyper i dine beregninger, og så ændres resultaterne baseret på typen af data, der bruges i input. Konverteringen sker automatisk, hvilket betyder, at du ikke behøver at kende datatyperne for de kolonner, du arbejder med i Power BI, men det betyder også, at konvertering ind imellem kan forekomme på uventede måder. Det er en god idé at forstå de data, du bruger, for at sikre, at dine operatorer fungerer som forventet.

Der er især én datatype, som du sandsynligvis kommer til at arbejde meget med i Power BI: **Dato/klokkeslæt**. **Dato/klokkeslæt** gemmes som et reelt tal med både heltal og decimaldele. Dato/klokkeslæt kan bruges præcist til beregning af en periode efter 1. marts 1900.

> Videoindholdet er fra [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

