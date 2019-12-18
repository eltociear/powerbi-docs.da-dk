---
title: Vejledning til automatisk dato/klokkeslæt i Power BI Desktop
description: Vejledning i brug af automatisk dato/klokkeslæt i Power BI Desktop.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/23/2019
ms.author: v-pemyer
ms.openlocfilehash: 30bfacc1024035f0849440eec8b1c7051ff4d82a
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/11/2019
ms.locfileid: "75002437"
---
# <a name="auto-datetime-guidance-in-power-bi-desktop"></a>Vejledning til automatisk dato/klokkeslæt i Power BI Desktop

Denne artikel henvender sig til designere af datamodeller, der udvikler importmodeller og sammensatte modeller i Power BI Desktop. Den indeholder vejledning, anbefalinger og overvejelser, når _Automatisk dato/klokkeslæt_ i Power BI Desktop bruges i bestemte situationer. Du finder en oversigt og en generel introduktion til _Automatisk dato/klokkeslæt_ under [Automatisk dato/klokkeslæt i Power BI Desktop](../desktop-auto-date-time.md).

Med indstillingen _Automatisk dato/klokkeslæt_ får du praktisk, hurtig og brugervenlig time intelligence. Rapportforfattere kan arbejde med time intelligence, når de filtrerer, grupperer og zoomer ind på detaljeniveauet gennem tidsperioder i kalendere.

## <a name="considerations"></a>Overvejelser

I følgende punktopstilling beskrives overvejelser – og mulige begrænsninger – relateret til indstillingen _Automatisk dato/klokkeslæt_.

- **Gælder for alle eller ingen:** Når indstillingen _Automatisk dato/klokkeslæt_ er aktiveret, gælder den for alle datokolonner i importtabeller, som ikke er på &quot;mange&quot;-siden af en relation. Den kan ikke selektivt aktiveres eller deaktiveres for hver enkelt kolonne.
- **Kun kalenderperioder:** Kolonnerne År og Kvartal er relateret til kalenderperioder. Det betyder, at året starter den 1. januar og slutter den 31. december. Der er ingen mulighed for at tilpasse årets startdato (eller slutdato).
- **Tilpasning:** Det er ikke muligt at tilpasse de værdier, der bruges til at beskrive tidsperioder. Det er desuden ikke muligt at tilføje yderligere kolonner for at beskrive andre tidsperioder, f.eks. uger.
- **Filtrering af år:** Værdierne for kolonnerne **Kvartal**, **Måned** og **Dag** indeholder ikke værdien År. Kolonnen **Måned** indeholder f.eks. kun månedsnavne (dvs. januar, februar osv.). Værdierne er ikke helt selvbeskrivende, og i nogle rapportdesign kommunikerer de muligvis ikke filterkonteksten for år.

    Det er derfor vigtigt, at filtrering eller gruppering udføres på kolonnen **År**. Når der zoomes ind på detaljeniveauet ved hjælp af hierarkiet, filtreres år, medmindre niveauet **År** er fjernet med vilje. Hvis der ikke er et filter eller en gruppe for år, vil en gruppering efter måned f.eks. opsummere værdier på tværs af alle år for den pågældende måned.
- **Filtrering af dato for en enkelt tabel:** Da hver datokolonne producerer sin egen (skjulte) tabel med automatisk dato/klokkeslæt, er det ikke muligt at anvende et tidsfilter på én tabel og overføre den til flere modeltabeller. Filtrering på denne måde er et almindeligt modelkrav, når der rapporteres om flere emner (tabellen af faktatypen), f.eks. salg og salgsbudget. Når automatisk dato/klokkeslæt bruges, skal rapportforfatteren anvende filtre på hver enkelte datokolonne.
- **Modelstørrelse:** Hver datokolonne, der genererer en skjult tabel med automatisk dato/klokkeslæt, vil resultere i en øget modelstørrelse og også forlænge opdateringstiden for data.

## <a name="recommendations"></a>Anbefalinger

Det anbefales, at du bevarer indstillingen _Automatisk dato/klokkeslæt_ aktiveret, når du arbejder med tidsperioder i kalendere, og når du har forenklede modelkrav i forhold til tid. Det kan også være praktisk at bruge denne indstilling, når du opretter ad hoc-modeller eller udfører dataudforskning eller -profilering.

Når din datakilde allerede definerer en dimensionstabel for dato, bør denne tabel bruges til at definere tid på en ensartet måde i din organisation. Det vil helt sikkert være tilfældet, hvis din datakilde er et data warehouse. Ellers kan du generere datotabeller i din model ved hjælp af DAX-funktionerne [CALENDAR](/dax/calendar-function-dax) eller [CALENDARAUTO](/dax/calendarauto-function-dax). Du kan derefter tilføje beregnede kolonner for at understøtte de kendte filtrerings- og grupperingskrav for tid. Denne designmetode kan give dig mulighed for at oprette en enkelt datotabel, der overføres til alle tabeller af faktatypen, hvilket kan resultere i, at der anvendes tidsfiltre for en enkelt tabel. Du kan finde flere oplysninger om oprettelse af datotabeller i artiklen [Angiv og brug datotabeller i Power BI Desktop](../desktop-date-tables.md).

Hvis indstillingen _Automatisk dato/klokkeslæt_ ikke er relevant for dine projekter, anbefales det, at du deaktiverer den globale indstilling _Automatisk dato/klokkeslæt_. Det sikrer, at alle nye Power BI Desktop-filer, du opretter, ikke aktiverer indstillingen _Automatisk dato/klokkeslæt_.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger, der er relateret til denne artikel, i følgende ressourcer:

- [Automatisk dato/klokkeslæt i Power BI Desktop](../desktop-auto-date-time.md)
- [Angiv og brug datotabeller i Power BI Desktop](../desktop-date-tables.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
