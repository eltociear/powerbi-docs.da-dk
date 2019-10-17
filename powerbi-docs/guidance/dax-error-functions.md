---
title: 'DAX: Passende brug af fejlfunktioner'
description: Vejledning til, hvornår du skal bruge DAX-fejlfunktioner.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: 0855a9ee4c699c4a3b65e4331b5af2fa68a5610c
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/07/2019
ms.locfileid: "72021062"
---
# <a name="dax-appropriate-use-of-error-functions"></a>DAX: Passende brug af fejlfunktioner

Denne artikel er beregnet til datamodeldesignere, der definerer DAX-udtryk.

## <a name="background"></a>Baggrund

Når du skriver et DAX-udtryk, som muligvis udløser en fejl af typen evalueringstid, kan du overveje at bruge to nyttige DAX-funktioner.

- Funktionen [ER.FEJL](/dax/iserror-function-dax), som kræver et enkelt udtryk og returnerer SAND, hvis det pågældende udtryk resulterer i en fejl.
- Funktionen [HVIS.FEJL](/dax/iferror-function-dax), som kræver to udtryk. Hvis det første udtryk resulterer i en fejl, returneres værdien for det andet udtryk. Det er faktisk en mere optimeret implementering af indlejring af funktionen ER.FEJL inde i en [HVIS](/dax/if-function-dax)-funktion.

Men selvom disse funktioner kan være nyttige og kan bidrage til at skrive udtryk, der er nemme at forstå, kan de også degradere ydeevnen af beregninger markant. Det skyldes, at disse funktioner øger antallet af påkrævede scanninger af lagringsprogrammet.

Bemærk, at de fleste fejl af typen evalueringstid skyldes uventede TOMME VÆRDIER eller nulværdier eller ugyldig konvertering af datatypen.

## <a name="recommendations"></a>Anbefalinger

Det er bedre at undgå at bruge funktionerne ER.FEJL og HVIS.FEJL. Anvend i stedet defensive strategier, når du udvikler modellen og skriver udtryk. Disse kan omfatte:

- **Sørg for, at kvalitetsdata indlæses i modellen:** Brug Power Query-transformationer til at fjerne eller erstatte ugyldige eller manglende værdier og til at angive korrekte datatyper. En Power Query-transformation kan også bruges til at filtrere rækker, når der opstår fejl, f.eks. ugyldig datakonvertering.

    Datakvaliteten kan også styres ved at angive egenskaben **Kan være nul** for kolonnen i modellen til Fra, hvorved dataopdateringen mislykkes, hvis der opleves TOMME VÆRDIER. Bemærk! Hvis denne fejl opstår, forbliver de data, der indlæses som følge af en vellykket opdatering, i tabellerne.
- **Brug af HVIS-funktionen:** Det logiske testudtryk med HVIS-funktionen kan bruges til at afgøre, om der ville opstå et fejlresultat. Bemærk! Ligesom funktionerne ER.FEJL og HVIS.FEJL kan denne funktion resultere i yderligere scanninger af lagringsprogrammet, men den vil sandsynligvis have en bedre ydeevne end dem, da der ikke skal udløses nogen fejl.
- **Brug af fejltolerante funktioner:** Nogle DAX-funktioner tester og kompenserer for fejltilstande. Disse funktioner gør det muligt for dig at angive et alternativt resultat, som bliver returneret i stedet. Funktionen [DIVIDER](/dax/divide-function-dax) er præcist sådan et eksempel. Hvis du har brug for yderligere vejledning om denne funktion, kan du læse artiklen [DAX: DIVIDER-funktion vs. divisionsoperator (/)](dax-divide-function-operator.md).

## <a name="example"></a>Eksempel

Følgende målingsudtryk tester, om der skal udløses en fejl. Den returnerer TOMME VÆRDIER i denne forekomst (hvilket er tilfældet, når du ikke angiver funktionen HVIS med et udtryk af typen værdi-hvis-falsk).
```dax
= IF(ISERROR([Profit] / [Sales]))
```
Denne næste version af målingsudtrykket er blevet forbedret ved hjælp af funktionen HVIS.FEJL i stedet for funktionerne HVIS og ER.FEJL.
```dax
= IFERROR([Profit] / [Sales], BLANK())
```
Denne endelige version af målingsudtrykket opnår samme resultat, men på en mere effektiv og elegant måde.
```dax
= DIVIDE([Profit], [Sales])
```