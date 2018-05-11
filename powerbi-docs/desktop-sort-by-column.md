---
title: Sortér efter kolonne i Power BI Desktop
description: Sortér efter kolonne i Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: monitoring
qualitydate: 05/01/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: acd621a1763e29fc66a017294cc4d63008900a4f
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2018
---
# <a name="sort-by-column-in-power-bi-desktop"></a>Sortér efter kolonne i Power BI Desktop
I **Power BI Desktop** og **Power BI-tjenesten** kan du ændre, hvordan en visuel gengivelse ser ud, ved at sortere den efter forskellige datafelter. Ved at ændre, hvordan du sorterer en visuel gengivelse, kan du fremhæve de oplysninger, du vil formidle, og sikre, at den visuelle gengivelse afspejler den tendens, som du vil vise.

Uanset om du bruger numeriske data, f.eks salgstal, eller tekstdata, f.eks navne på byer, kan du sortere den visuelle gengivelse, som du vil, for at få den til at se ud, som du vil.  **Power BI** indeholder mange sorteringsmuligheder og genvejsmenuer, som du kan bruge. Vælg menuen med de tre prikker (...) i en visuel gengivelse, vælg **Sortér efter**, og vælg derefter det felt, som du vil sortere efter, som vist på følgende billede.

![](media/desktop-sort-by-column/sortbycolumn_2.png)

## <a name="more-depth-and-an-example"></a>Mere dybde og et eksempel
Lad os tage et eksempel med mere dybde og se, hvordan det fungerer i **Power BI Desktop**.

Følgende visuelle gengivelse viser de 15 højst rangerende stater i forhold til vejr (flest solskinsdage, rangeret fra 1 til 50, hvor 1 er den stat, der har flest solskinsdage). Her er et billede af den visuelle gengivelse inden nogen form for sortering.

![](media/desktop-sort-by-column/sortbycolumn_1.png)

Den visuelle gengivelse er i øjeblikket sorteret efter **Cost of living**. Det kan vi se ved at sammenligne farven på de faldende søjler med forklaringen, men der er en bedre måde at finde frem til den aktuelle sorteringskolonnen: dialogboksen **Sortér efter**, som er tilgængelig i menuen med de tre prikker (...) i øverste højre hjørne af den visuelle gengivelse. Når du klikker på menuen, får du vist følgende:

![](media/desktop-sort-by-column/sortbycolumn_2.png)

Der er nogle elementer, du bør lægge mærke til i den menu, der vises, når du klikker på de tre prikker:

* Den gule søjle ud for **Cost of living**, og at **Cost of living** er markeret med fed.
* Det lille ikon ud for ordene **Sortér efter**, der viser **Z/A** (Z over A) og en pil ned.

Disse vil blive gennemgået enkeltvist i de næste to afsnit.

## <a name="selecting-which-column-to-use-for-sorting"></a>Valg af kolonne, der skal sorteres efter
Du lagde mærke til den gule søjle ud for **Cost of living** i menuen **Sortér efter**, som angav, at kolonnen **Cost of living** blev brugt til sortering af den visuelle gengivelse. Det er nemt at sortere efter en anden kolonne. Du skal blot vælge menuen med de tre prikker for at få vist menuen **Sortér efter** og derefter vælge en anden kolonne. Så nemt er det.

I følgende billede har vi valgt at sortere efter kolonnen **Community well-being**. Den kolonne er rent faktisk en af kurverne på den visuelle gengivelse i stedet for en af søjlerne. Sådan ser det ud, efter at vi har valgt **Community well-being**.

![](media/desktop-sort-by-column/sortbycolumn_3.png)

Læg mærke til, hvordan den visuelle gengivelse er blevet ændret. Værdierne er nu sorteret fra højeste værdi i kolonnen "Community well-being" (i dette tilfælde RI for Rhode Island) for de stater, der er medtaget i denne visuelle gengivelse, ned til AZ (for Arizona), som har den laveste værdi. Husk, at det overordnede diagram stadig kun indeholder de 15 stater med flest solskinsdage. Vi har netop sorteres dem efter en anden kolonne, der er inkluderet i den visuelle gengivelse.

Men hvad nu, hvis vi vil sortere stigende i stedet for faldende? I næste afsnit kan du se, hvor nemt du kan gøre det.

## <a name="selecting-the-sort-order---smallest-to-largest-largest-to-smallest"></a>Valg af sorteringsrækkefølgen – mindste til største, største til mindste
Når vi ser nærmere på menuen **Sortér efter** i det foregående billede, kan vi se, at ikonet ud for **Sortér efter** viser **Z/A** (Z over A). Se her:

![](media/desktop-sort-by-column/sortbycolumn_4.png)

Når **Z/A** vises, betyder det, at den visuelle gengivelse sorteres efter den valgte kolonne fra den største værdi til den mindste værdi. Vil du ændre det? Det kan du nemt gøre ved at trykke eller klikke på ikonet **Z/A**. Det ændrer sorteringsrækkefølgen til **A/Z**, og den visuelle gengivelse (baseret på den valgte kolonne) sorteres fra mindste til største værdi.

Her kan du se den samme visuelle gengivelse, men her er der trykket på ikonet **Z/A** i menuen **Sortér efter** for at ændre rækkefølgen. Læg mærke til, at AZ (Arizona) nu er den første stat, der vises, og RI (Rhode Island) er den sidste. Det er den modsatte sortering i forhold til før.

![](media/desktop-sort-by-column/sortbycolumn_5.png)

Du kan sortere efter en hvilken som helst kolonne, der er inkluderet i den visuelle gengivelse. Vi kan f.eks. vælge Weather som den kolonne, der skal sorteres efter, og vælge **Z/A** i menuen **Sortér efter** for at få vist staterne med mest solskin først (højeste værdi – Weather er lig med antallet af solskinsdage i denne datamodel) og stadig bevare de andre kolonner i den visuelle gengivelse, uanset hvordan de nu tilfældigvis gælder for den stat. Her kan du se den visuelle gengivelse med disse indstillinger.

![](media/desktop-sort-by-column/sortbycolumn_6.png)

## <a name="sort-using-the-sort-by-column-button"></a>Sortering med knappen Sortér efter kolonne
Du kan også sortere dine data ved at bruge knappen **Sortér efter kolonne** på båndet **Udformning**.

![](media/desktop-sort-by-column/sortbycolumn_8.png)

Denne fremgangsmåde kræver, at du vælger en kolonne i ruden **Felter** og derefter vælger knappen **Sortér efter kolonne** for at vælge, hvordan (efter hvilken kolonne) du vil sortere den visuelle gengivelse. Du skal vælge den kolonne (det felt), som du vil sortere efter, i ruden **Felter** for at aktivere knappen **Sortér efter kolonne**. Ellers er knappen inaktiv.

Lad os se på et almindeligt eksempel: Du har data fra hver dag i ugen, og du vil sortere dataene i kronologisk rækkefølge. Nedenfor kan du se, hvordan du skal gøre.

1. Læg først mærke til, at når den visuelle gengivelse er valgt, men ingen kolonne er valgt i ruden **Felter**, er knappen **Sortér efter kolonne** inaktiv (nedtonet).
   
   ![](media/desktop-sort-by-column/sortbycolumn_9a.png)
2. Når vi vælge den kolonne, der skal sorteres efter, bliver knappen **Sortér efter kolonne** i ruden **Felter** aktiv.
   
   ![](media/desktop-sort-by-column/sortbycolumn_10.png)
3. Når den visuelle gengivelse er valgt, kan vi vælge *Day of Week* i stedet for standardkolonnen (*Name of Day*). Den visuelle gengivelse sorteres nu i den rækkefølge, vi vil have: efter ugedag.
   
   ![](media/desktop-sort-by-column/sortbycolumn_11.png)

Det var det hele. Husk, at du skal vælge en kolonne i ruden **Felter**, før knappen **Sortér efter kolonne** bliver aktiv.

## <a name="getting-back-to-default-column-for-sorting"></a>Sortering efter standardkolonnen igen
Du kan sortere efter en hvilken som helst kolonne, men der kan være tilfælde, hvor du vil nulstille den visuelle gengivelse, så den sorteres efter standardkolonnen igen. Intet problem. Hvis du har en visuel gengivelse med en valgt sorteringskolonne (en valgt sorteringskolonne vises med en gul søjle ud for den i menuen **Sortér efter**), skal du blot åbne menuen **Sortér efter** og vælge kolonnen igen. Det får den visuelle gengivelse til at blive sorteret efter standardkolonnen igen.

Her er f.eks. vores tidligere diagram:

![](media/desktop-sort-by-column/sortbycolumn_6.png)

Når vi gå tilbage til menuen og vælger **Weather** igen, bliver den visuelle gengivelse sorteret alfabetisk efter **State Code**, som vist i følgende billede.

![](media/desktop-sort-by-column/sortbycolumn_7.png)

Med så mange muligheder for sortering af dine visuelle gengivelser bliver det nemt for dig at oprette lige netop det diagram eller billede, du har brug for.

