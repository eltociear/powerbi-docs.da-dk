---
title: Brug udsnitsværktøjet til numerisk område i Power BI Desktop
description: Læs om, hvordan du kan bruge et udsnitsværktøj til at begrænse resultatet til numeriske intervaller i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/19/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: fa1311f93cd6b543d552070b990f1bada551a699
ms.sourcegitcommit: 9d13ef7a257b5006fca5f92acf5b611f5cd143a2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2019
ms.locfileid: "68307024"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Brug udsnitsværktøjet til numerisk område i Power BI Desktop
Med udsnitsværktøjet til numerisk område kan du anvende forskellige filtre på en numerisk kolonne i din datamodel. Der er tre muligheder for at filtrere dine numeriske data: mellem tal, mindre end eller lig med et tal samt større end eller lig med et tal. Det lyder måske enkelt, men det er en effektiv måde at filtrere data på.

![Visualisering med udsnitsværktøjet til numerisk område](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="use-the-numeric-range-slicer"></a>Brug udsnitsværktøjet til numerisk område
Du kan bruge udsnitsværktøjet til numerisk område ligesom ethvert andet udsnitsværktøj. Du skal blot oprette et **udsnitsværktøj**, der er synligt for din rapport, og derefter vælge en numerisk værdi for **Felt**-værdien. På følgende billede er feltet **LineTotal** markeret.

![Opret et udsnitsværktøj til numerisk område](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Hvis du vælger linket pil ned i øverste højre hjørne af **udsnitsværktøjet til numerisk område**, vises der en menu.

![Menu for udsnitsværktøj til numerisk område](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

I forbindelse med det numeriske område kan du vælge mellem følgende tre muligheder:

* **Mellem**
* **Mindre end eller lig med**
* **Større end eller lig med**

Når du vælger **Mellem** i menuen, vises der en skyder. Du kan bruge skyderen til at vælge numeriske værdier, der ligger mellem tallene. Nogle gange gør kornetheden af skyderen det svært, at ramme det præcise tal. Du kan også bruge skyderen og skrive den ønskede værdi i et af felterne. Denne indstilling er praktisk, når du vil se et udsnit af bestemte tal. 

På følgende billede er rapportsiden filtreret for **LineTotal**-værdier i området mellem 2.500,00 og 6.000,00.

![Udsnitsværktøjet til numerisk område med Mellem](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Når du vælger **Mindre end eller lig med**, forsvinder skyderens venstre håndtag (lavere værdi), og du kan kun justere skyderens øvre grænse. På følgende billede angiver vi skyderen til maksimalt 5928.19.

![Udsnitsværktøjet til numerisk område med Mindre end](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Sidst men ikke mindst, hvis du vælger **Større end eller lig med**, forsvinder skyderens højre håndtag (højere værdi). Du kan derefter justere den lavere værdi som vist på følgende billede. Nu vises der kun elementer, der har en **LineTotal**, som er større end eller lig med 4.902,99, i visualiseringerne på rapportsiden.

![Udsnitsværktøjet til numerisk område med Større end](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Fastgør til heltal ved hjælp af udsnitsværktøjet til numerisk område

Et udsnitsværktøj til et numerisk område fastgøres til heltal, hvis datatypen for det underliggende felt er **Heltal**. Med denne funktion kan udsnitsværktøjet nemt afstemmes til heltal. I feltet **Decimaltal** kan du angive eller vælge brøkdele af et tal. Den formatering, der anvendes i tekstfeltet, matcher den formatering, der er anvendt i feltet, selvom du kan angive eller vælge mere præcise tal.

## <a name="display-formatting-with-the-date-range-slicer"></a>Vis formatering med udsnitsværktøjet til datoområder

Når du bruger et udsnit til at få vist eller angive et område for datoer, vises datoerne i det **korte datoformat**. Landestandarden for brugerens browser eller operativsystem bestemmer datoformatet. Dette er derfor det viste format, uanset hvilke indstillinger for datatype der er for den underliggende data eller model. 

Du kan f. eks. have et langt datoformat for den underliggende datatype. I dette tilfælde formaterer et datoformat såsom *dddd, d MMMM åååå* en dato i andre visualiseringer eller under andre forhold som *onsdag, 14. marts 2001*. Men i udsnitsværktøjet til datoområde vises denne dato i udsnittet som *14-03-2001.*

Visning af det **korte datoformat** i udsnitsværktøjet sikrer, at længden af strengen forbliver konsistent og kompakt i udsnitsværktøjet. 

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Følgende begrænsninger og overvejelser gælder for **udsnitsværktøjet til numerisk område**:

* **Udsnitsværktøjet til numerisk område** filtrerer alle underliggende rækker i dataene, men ingen aggregerede værdier. Lad os f.eks. sige, at du bruger feltet *Salgsbeløb*. Udsnitsværktøjet filtrerer derefter hver transaktion baseret på salgsbeløbet og ikke summen af salgsbeløbet for hvert enkelt datapunkt i en visualisering.
* Det fungerer i øjeblikket ikke sammen med målinger.
* Du kan skrive et vilkårligt tal i tekstfelterne i et numerisk udsnitsværktøj, selvom det er uden for området af værdier i den underliggende kolonne. Denne indstilling giver dig mulighed for at konfigurere filtre, hvis du ved, at dataene kan blive ændret i fremtiden.
