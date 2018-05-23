---
title: Brug udsnitsværktøjet til numerisk område i Power BI Desktop
description: Læs om, hvordan du kan bruge et udsnitsværktøj til at begrænse resultatet til numeriske intervaller i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1e380a6821db7207d14e719fa5e070af38196b97
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Brug udsnitsværktøjet til numerisk område i Power BI Desktop
Med **udsnitsværktøjet til numerisk område** kan du anvende alle former for filtre på alle numeriske kolonner i din datamodel. Du kan vælge at filtrere **mellem** tal, **mindre end eller lig med** et tal eller **større end eller lig med** et tal. Det lyder måske meget enkelt, men det er en effektiv måde at filtrere dine data på.

![Visual med udsnitsværktøjet til numerisk område](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>Brug udsnitsværktøjet til numerisk område
Du kan bruge udsnitsværktøjet til numerisk område på samme måde som alle andre udsnitsværktøjer. Du skal bare oprette et **udsnitsværktøj**, der er synligt for din rapport, og derefter vælge en numerisk værdi for **Felt**-værdien. På følgende billede er feltet *LineTotal* markeret.

![Opret et numerisk interval-udsnitsværktøj](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Hvis du vælger linket pil ned i øverste højre hjørne af **udsnitsværktøjet til numerisk område**, vises der en menu.

![Menu for udsnitsværktøj til numerisk område](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

I forbindelse med det numeriske område kan du vælge mellem følgende tre muligheder:

* Mellem
* Mindre end eller lig med
* Større end eller lig med

Når du vælger **Mellem** i menuen, vises der en skyder, og du kan filtrere efter numeriske værdier, der ligger mellem tallene. Udover at bruge selve skyderen kan du også klikke i felterne og skrive værdierne. Det er praktisk, når du vil opdele specifikke tal, men kornetheden ved at flytte skyderen gør det vanskeligt at lande nøjagtigt på tallet.

På følgende billede er rapportsiden filtreret for *LineTotal*-værdier mellem 2500.00 og 6000.00.

![Udsnitsværktøjet til numerisk område med Mellem](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Når vi vælger **Mindre end eller lig med**, forsvinder venstre håndtag (den laveste værdi) for skyderen, og vi kan kun justere den øvre grænse for skyderen. På følgende billede angiver vi skyderen til maksimalt 5928.19.

![Udsnitsværktøjet til numerisk område med Mindre end](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Og endelig, hvis vi vælger **Større end eller lig med** forsvinder højre håndtag til skyderen (den højeste værdi), og vi kan justere den laveste værdi, som vist på følgende billede. Nu vises der kun elementer, der har en *LineTotal*, som er større end eller lig med 4902.99, i de visuelle elementer på rapportsiden.

![Udsnitsværktøjet til numerisk område med Større end](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Fastgør til hele tal ved hjælp af udsnitsværktøj til numerisk område

Udsnitsværktøjet til numerisk område fastgøres til heltal, medmindre det er et decimalområde. Dermed kan udsnitsværktøjet nemt afstemme to hele tal. 


## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Følgende begrænsninger og overvejelser, der aktuelt gælder for **udsnitsværktøjet til numerisk område**:

* **Udsnitsværktøjet til numerisk område** filtrerer i øjeblikket alle underliggende rækker i dataene, ingen aggregerede værdier. Hvis f.eks. feltet *Sales Amount* bruges, filtreres der efter alle transaktioner, der er baseret på *Sales Amount*, ikke summen af *Sales Amount* for hvert datapunkt i et visuelt element.
* Den fungerer i øjeblikket ikke sammen med målinger.
