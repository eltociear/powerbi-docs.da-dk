---
title: Udtryksbaserede titler i Power BI Desktop
description: Du kan oprette dynamiske titler i Power BI Desktop, der ændres på baggrund af programmeringsudtryk, ved hjælp af betinget programformatering.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1b4e134ef6f8da43a1856c8a5458c8c09b2c42b5
ms.sourcegitcommit: f05ba39a0e46cb9cb43454772fbc5397089d58b4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/26/2019
ms.locfileid: "68522186"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Udtryksbaserede titler i Power BI Desktop

Du kan oprette dynamiske, tilpassede titler til dine visuelle elementer i Power BI. Ved at oprette DAX-udtryk (Data Analysis Expressions), der er baseret på felter, variabler eller andre programelementer, kan titlerne for dine visuelle elementer justeres automatisk efter behov. Disse ændringer er baseret på filtre, valg eller andre brugerinteraktioner og -konfigurationer.

![Skærmbillede af indstilling for betinget formatering i Power BI Desktop](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

Det er ligetil at oprette dynamiske titler (også nogle gange kaldet *udtryksbaserede titler*). 

## <a name="create-a-field-for-your-title"></a>Opret et felt til din titel

Det første trin i oprettelsen af en udtryksbaseret titel er at oprette et felt i din model, der skal bruges til titlen. 

Der er alle mulige forskellige kreative metoder til at få titlen på dit visuelle element til at afspejle, hvad du vil have det til at sige, eller hvad du vil udtrykke. Lad os tage et kig på et par eksempler.

Du kan oprette et udtryk, der er baseret på den filterkontekst, som det visuelle element modtager for produktets brandnavn. På følgende billede vises DAX-formlen for et sådant felt.

![Skærmbillede af DAX-formel](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

Et andet eksempel er brug af en dynamisk titel, der ændres på baggrund af brugerens sprog eller kultur. Du kan oprette sprogspecifikke titler i en DAX-måling ved hjælp funktionen `USERCULTURE()`. Denne funktion returnerer kulturkoden for brugeren baseret på vedkommendes operativsystem eller browserindstillinger. Du kan bruge følgende DAX-switch-sætning til at vælge den korrekte oversatte værdi. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

Eller du kan hente strengen fra en opslagstabel, der indeholder alle oversættelserne. Denne tabel placeres i din model. 

Dette er blot et par eksempler, som du kan bruge til at oprette dynamiske udtryksbaserede titler til dine visuelle elementer i Power BI Desktop. Det er kun din fantasi – og din model – der sætter grænser for det, du kan foretage dig med titler.


## <a name="select-your-field-for-your-title"></a>Vælg et felt til titlen

Når du har oprettet DAX-udtrykket for det felt, du opretter i din model, skal du anvende det i titlen på dit visuelle element.

Gå vil ruden **Visualiseringer** for at vælge feltet og anvende det. I området **Format** skal du vælge **Titel** for at få vist titelindstillingerne for det visuelle element. 

Når du højreklikker på **titeltekst**, vises en genvejsmenu, der giver dig mulighed for at vælge***f.eks.*betinget formatering**. Når du vælger dette menupunkt, vises dialogboksen **Titeltekst**. 

![Skærmbillede af dialogboksen Titeltekst](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

Fra vinduet kan du vælge det felt, som du har oprettet til din titel.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Der er nogle få begrænsninger for den aktuelle implementering af udtryksbaserede titler til visualiseringer:

* Udtryksbaseret formatering understøttes ikke i øjeblikket i Python-visualiseringer, R-visualiseringer eller visualiseringer af nøglefaktorer.
* Det felt, du opretter til titlen, skal være en strengdatatype. Målinger, der returnerer tal eller dato/klokkeslæt (eller andre datatyper), understøttes ikke i øjeblikket.
* Udtryksbaserede titler overføres ikke, når du fastgør en visualisering til et dashboard.

## <a name="next-steps"></a>Næste trin

Denne artikel beskrev, hvordan du opretter DAX-udtryk, der ændrer titlerne på dine visuelle elementer til dynamiske felter, der kan ændres, når brugere interagerer med dine rapporter. Følgende artikler kan også være nyttige.

* [Betinget formatering af tabeller](desktop-conditional-table-formatting.md)
* [Brug tværgående detaljeadgang i rapport i Power BI Desktop](desktop-cross-report-drill-through.md)
* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)
