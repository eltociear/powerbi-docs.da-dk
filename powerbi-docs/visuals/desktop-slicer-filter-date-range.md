---
title: Brug et relativt datoudsnit eller -filter i Power BI Desktop
description: Lær, hvordan du bruger et udsnitsværktøj eller -filter til at begrænse relative datoområder i Power BI Desktop
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: c29145e4a51821bab284693bc13a508cb9c046c6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279153"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>Brug et relativt datoudsnit og -filter i Power BI Desktop
Med det **relative datoudsnit** eller det **relative datofilter** kan du anvende tidsbaserede filtre på en hvilken som helst datokolonne i datamodellen. Du kan f.eks. bruge det **relative datoudsnit** til kun at vise salgsdata, der er oprettet i løbet af de sidste 30 dage (eller måned eller kalendermåneder osv.). Og når du opdaterer dataene, anvender den relative tidsperiode automatisk den relevante relative datobegrænsning.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>Brug det relative datoområdeudsnit
Du kan bruge det relative datoudsnit på samme måde som alle andre udsnit. Du skal bare oprette et **udsnit**, der er synligt for din rapport, og derefter vælge en datoværdi for **Felt**-værdien. På følgende billede er feltet *OrderDate* markeret.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

Hvis du vælger karaten i øverste højre hjørne af det **relative datoudsnit**, vises der en menu.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

For det relative datoudsnit skal du vælge *Relativ*.

Du kan derefter vælge indstillingerne. Du har følgende valgmuligheder for den første rulleliste i det *relative datoudsnit*:

* Sidste
* Næste
* Denne

Disse valg vises på billedet nedenfor.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

Den næste (midterste) indstilling i det *relative datoudsnit* gør det muligt at indtaste et tal for at definere det relative datoområde.

Den tredje indstilling giver dig mulighed for at vælge datomålingen. Du har følgende valgmuligheder:

* Dage
* Uger
* Uger (kalender)
* Måneder
* Måneder (kalender)
* År
* År (kalender)

Disse valg vises på billedet nedenfor.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

Hvis du vælger *Måned* på denne liste og angiver 2 i den midterste indstilling, sker følgende: Hvis dags dato er 20. juli, viser de data, der er inkluderet i de visuals, som er begrænset af udsnittet, data for de to forrige måneder fra og med 20. maj og frem til 20. juli (dags dato).

Hvis du til sammenligning har valgt *Måneder (kalender)*, viser de begrænsede visuelle elementer data fra 1. maj til 30. juni (de to sidste hele kalendermåneder).

## <a name="using-the-relative-date-range-filter"></a>Brug det relative datoområdefilter
Du kan også oprette et relativt datoområdefilter for din rapportside eller hele rapporten. Det kan du gøre ved blot at trække datofeltet til området **Filtre på sideniveau** eller **Filtre på rapporteringsniveau** i ruden **Felt** som vist på følgende billede.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

Når du er der, kan du ændre det relative datoområde i forhold til den måde, som det **relative datoudsnit** er tilpasset. Vælg **Filtrering af relativ dato** på rullelisten **Filtertype**.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

Når du har valgt **Filtrering af relativ dato**, du kan se tre sektioner, der skal redigeres, herunder et numerisk felt i midten, på samme måde som udsnittet.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

Og det er det eneste, du skal gøre, når du bruger disse relative datobegrænsninger i dine rapporter.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Følgende begrænsninger og overvejelser, der aktuelt gælder for det **relative datoområdeudsnit** og -filter.

* Datamodeller i **Power BI** indeholder ikke oplysninger om tidszone. Modeller kan gemme tider, men der er ingen angivelse af den tidszone, de er i.
* Udsnittet og filteret er altid baseret på tidspunktet i UTC-tid, så hvis du konfigurerer et filter i en rapport og sender det til en kollega i en anden tidszone, kan I begge to se de samme data. Du kan få vist data for et andet tidspunkt, end du forventer, hvis du ikke er i UTC-tidszonen.
* Data, der er registreret i en lokal tidszone, kan konverteres til UTC ved hjælp af **forespørgselseditoren**.

