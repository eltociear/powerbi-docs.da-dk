---
title: Opret en detaljeniveauknap i Power BI
description: Du kan tilføje detaljeniveauknapper i Power BI-rapporter, der får dine rapporter til at fungere som apps, og sørge for, at brugerne bliver mere involveret.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: d3cb3c8093446d4417a59c5f64ab6b85a765e3c8
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "79206441"
---
# <a name="create-a-drill-through-button-in-power-bi-preview"></a>Opret en detaljeniveauknap i Power BI (prøveversion)

Når du opretter en knap i Power BI, kan du vælge handlingen **Detaljeadgang (prøveversion)** . Denne handlingstype opretter en knap, der giver detaljeadgang til en fokuseret side, så der kan hentes oplysninger, der er filtreret til en bestemt kontekst.

En detaljeniveauknap kan være nyttig, hvis du vil øge synligheden af vigtige detaljeadgangsscenarier i dine rapporter.

Når brugeren har valgt Word-panelet i diagrammet i dette eksempel, er knappen **Se detaljer** aktiveret.

![Knappen Se detaljer](media/desktop-drill-through-buttons/power-bi-drill-through-visual-button.png)

Når brugerne vælger knappen **Se detaljer**, får de detaljeadgang til siden Market Basket Analysis. Som du kan se af visual'et til venstre, er siden med detaljeadgang nu filtreret for Word.

![Filtreret visual](media/desktop-drill-through-buttons/power-bi-drill-through-destination.png)

## <a name="set-up-a-drill-through-button"></a>Konfigurer en detaljeniveauknap

Hvis du vil konfigurere en detaljeniveauknap, skal du først [konfigurere en gyldig side med detaljeadgang](desktop-drillthrough.md) i din rapport. Derefter skal du oprette en knap med **Detaljeadgang** som handlingstype og vælge siden med detaljeadgang som **Destination**.

Da detaljeniveauknappen har to tilstande (når detaljeadgang er aktiveret i forhold til deaktiveret), kan du se, at der er to indstillinger for værktøjstip.

![Konfigurer detaljeniveauknappen](media/desktop-drill-through-buttons/power-bi-create-drill-through-button.png)

Hvis du lader værktøjstipfelterne være tomme, opretter Power BI automatisk værktøjstip. Disse værktøjstips er baseret på destinations- og detaljeniveaufelterne.

Her er et eksempel på det automatisk oprettede værktøjstip, når knappen er deaktiveret:

"Hvis du vil have detaljeadgang til Market Place Analysis (destinationssiden), skal du vælge et enkelt datapunkt fra Product (detaljeniveaufeltet)".

![Deaktiveret automatisk oprettet værktøjstip](media/desktop-drill-through-buttons/power-bi-drill-through-tooltip-disabled.png)

Og her er et eksempel på det automatisk oprettede værktøjstip, når knappen er aktiveret:

"Klik her for at få detaljeadgang til Market Basket Analysis (destinationssiden)".

![Aktiveret automatisk oprettet værktøjstip](media/desktop-drill-through-buttons/power-bi-drill-through-visual-button.png)

Men hvis du vil angive brugerdefinerede værktøjstip, kan du altid angive en statisk streng. Vi understøtter endnu ikke betinget formatering af værktøjstip.

Du kan bruge betinget formatering til at ændre knapteksten på basis af den valgte værdi for et felt. Hvis du vil gøre dette, skal du oprette en måling, der returnerer den ønskede streng på basis af DAX-funktionen SELECTEDVALUE.

Her er en eksempelmåling, der returnerer "Se produktoplysninger", hvis der IKKE er valgt en enkelt produktværdi. I modsat falde returnerer den "Se detaljer for [det valgte produkt]":

```
String_for_button = If(SELECTEDVALUE('Product'[Product], 0) == 0), "See product details", "See details for " & SELECTEDVALUE('Product'[Product]))
```

Når du har oprettet denne måling, skal du vælge indstillingen **Betinget formatering** for knapteksten:

![Vælg Betinget formatering](media/desktop-drill-through-buttons/power-bi-button-conditional-tooltip.png)

Derefter skal du vælge den måling, du har oprettet til knapteksten:

![Værdi baseret på felt](media/desktop-drill-through-buttons/power-bi-conditional-measure.png)

Når der er valgt et enkelt produkt, er knapteksten:

"Se oplysninger om Word"

![Når der er valgt en enkelt værdi](media/desktop-drill-through-buttons/power-bi-conditional-button-text.png)

Når der enten ikke er valgt noget produkt, eller hvis der er valgt mere end ét produkt, er knappen deaktiveret, og knapteksten er:

"Se produktoplysninger"

![Når der er valgt flere værdier](media/desktop-drill-through-buttons/power-bi-button-conditional-text-2.png)

## <a name="pass-filter-context"></a>Overfør filterkontekst

Knappen fungerer som normal detaljeadgang, så du kan også overføre filtre til ekstra felter ved at foretage krydsfiltrering af de visuals, der indeholder detaljeniveaufeltet. Hvis du f. eks. bruger **Ctrl** + **klik** og krydsfiltrering, kan du overføre flere filtre i Store til siden med detaljeadgang, fordi dine valg på krydsfiltrerer det visual, der indeholder detaljeniveaufeltet Product:

![Overførsel af filterkontekst](media/desktop-drill-through-buttons/power-bi-cross-filter-drill-through-button.png)

Når du vælger detaljeniveauknappen, får du vist filtre for både Store og Product, der overføres til destinationssiden:

![Filtre på denne side](media/desktop-drill-through-buttons/power-bi-button-filters-passed-through.png)

### <a name="ambiguous-filter-context"></a>Tvetydig filterkontekst

Da detaljeniveauknappen ikke er bundet til et enkelt visual, er knappen deaktiveret, hvis dit valg er tvetydigt.

I dette eksempel er knappen deaktiveret, fordi to visuals begge indeholder et enkelt produktvalg. Det er uklart, hvilket datapunkt fra hvilket visual detaljeadgangshandlingen skal knyttes til:

![Tvetydig filterkontekst](media/desktop-drill-through-buttons/power-bi-button-disabled-ambiguity.png)

## <a name="limitations"></a>Begrænsninger

- Denne knap tillader ikke, at flere destinationer bruger en enkelt knap.
- Denne knap understøtter kun detaljeadgang i den samme rapport, hvilket med andre ord vil sige, at den ikke understøtter detaljeadgang på tværs af rapporter.
- Knappens formatering som deaktiveret er knyttet til farveklasserne i rapporttemaet. Få mere at vide om [farveklasser](desktop-report-themes.md#setting-structural-colors).
- Detaljeadgangshandlingen virker i alle indbyggede visuals og kan bruges sammen med *nogle* visuals, der er importeret fra AppSource. Det er dog ikke sikkert, at de kan bruges sammen med *alle* visuals, der er importeret fra AppSource.

## <a name="next-steps"></a>De næste trin
Du kan finde flere oplysninger om de funktioner, der er ens eller interagerer med knapper, i følgende artikler:

* [Opret knapper](desktop-buttons.md)
* [Brug detaljeadgang i Power BI-rapporter](desktop-drillthrough.md)
* [Brug bogmærker til at dele indsigt og oprette historier i Power BI](desktop-bookmarks.md)

