---
title: Udtryksbaseret titler i Power BI Desktop
description: Opret dynamiske titler i Power BI Desktop, der ændres baseret på programmatisk udtryk, ved hjælp af betinget programmatisk formatering
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b90ef66d2c118a70f1b18ed4fe302ce1db23e45c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769756"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Udtryksbaseret titler i Power BI Desktop

Du kan oprette dynamiske, tilpasset titlerne på dine Power BI-visualiseringer. Ved at oprette Data Analysis Expressions (DAX) baseret på felter, variabler eller andre programmatisk elementer, kan dine visuelle elementer titler automatisk tilpasse efter behov. Disse ændringer er baseret på filtre, valg, eller andre Brugerinteraktioner og konfigurationer.

![Skærmbillede af Power BI Desktop betinget formatering indstilling](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

Oprettelse af dynamiske titler, kaldes *udtryksbaseret titler*, det er nemt. 

## <a name="create-a-field-for-your-title"></a>Opret et felt til din titel

Det første trin i oprettelsen af et udtryk-baserede titel er at oprette et felt i din model skal bruge for titlen. 

Der er alle mulige forskellige kreative måder at have din visual titel afspejler det, du ønsker det, at sige, eller hvad du vil express. Lad os se nærmere på et par eksempler.

Du kan oprette et udtryk, der ændres på baggrund af filterkonteksten, der modtager det visuelle element til produktnavnet brand. Det følgende billede viser DAX-formlen for dette felt.

![Skærmbillede af DAX-formel](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

Et andet eksempel bruger en dynamisk titel, der ændres på baggrund af brugerens sprog eller kultur. Du kan oprette sprogspecifikke titler i en DAX-måling ved hjælp af den `USERCULTURE()` funktion. Denne funktion returnerer kultur koden for den bruger, der er baseret på deres operativsystemet eller browserindstillinger. Du kan bruge følgende DAX switch-sætning til at vælge den korrekte oversatte værdi. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

Eller du kan hente en streng fra en opslagstabel, der indeholder alle oversættelser. Du kan placere tabellen i din model. 

Disse er bare et par eksempler, du kan bruge til at oprette dynamiske, udtryksbaseret titlerne på dine visuelle elementer i Power BI Desktop. Hvad du kan gøre med din titler er kun begrænset af din fantasi, og din model.


## <a name="select-your-field-for-your-title"></a>Vælg feltet for din titel

Når du har oprettet DAX-udtrykket for det felt, du opretter i din model, skal du anvende den til din visual titel.

For at markere feltet og anvende den, skal du gå til den **visualiseringer** rude. I den **Format** område, Vælg **titel** til at vise titlen indstillingerne for det visuelle element. 

Når du højreklikker på **titeltekst**, vises en genvejsmenu, der gør det muligt at vælge ***fx* betinget formatering**. Når du vælger denne menu-element, en **titeltekst** dialogboksen vises. 

![Skærmbillede af titel dialogboksen for tekst](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

Dette vindue, kan du vælge det felt, du har oprettet, hvis du vil bruge din titel.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Der er et par begrænsninger for den aktuelle implementering af udtrykket-baserede titlerne på visuelle elementer:

* Udtryksbaseret formatering understøttes ikke i øjeblikket på visuelle elementer Python, R-visualiseringer eller nøgle Lobbyister Visualiseringen.
* Det felt, du opretter for titlen skal være af datatypen streng. Målinger, der returnerer tal eller dato/klokkeslæt (eller en anden datatype) understøttes ikke i øjeblikket.

## <a name="next-steps"></a>Næste trin

I denne artikel beskrives, hvordan du opretter DAX-udtryk, der omdanner titlerne på dine visuelle elementer til dynamiske felter, der kan ændres, når brugerne interagerer med dine rapporter. Du kan finde i følgende artikler nyttige samt.

* [Brug detaljeadgang på tværs af-rapport i Power BI Desktop](desktop-cross-report-drill-through.md)
* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)