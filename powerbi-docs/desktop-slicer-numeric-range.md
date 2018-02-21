---
title: "Brug udsnitsværktøjet til numerisk område i Power BI Desktop"
description: "Læs om, hvordan du kan bruge et udsnitsværktøj til at begrænse resultatet til numeriske intervaller i Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: 6d63236254906619f7244db9f57af162a19a70d6
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/09/2018
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Brug udsnitsværktøjet til numerisk område i Power BI Desktop
Med **udsnitsværktøjet til numerisk område** kan du anvende alle former for filtre på alle numeriske kolonner i din datamodel. Du kan vælge at filtrere **mellem** tal, **mindre end eller lig med** et tal eller **større end eller lig med** et tal. Det lyder måske meget enkelt, men det er en effektiv måde at filtrere dine data på.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>Brug udsnitsværktøjet til numerisk område
Du kan bruge udsnitsværktøjet til numerisk område på samme måde som alle andre udsnitsværktøjer. Du skal bare oprette et **udsnitsværktøj**, der er synligt for din rapport, og derefter vælge en numerisk værdi for **Felt**-værdien. På følgende billede er feltet *UnitPrice* markeret.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

Hvis du vælger karaten i øverste højre hjørne af **udsnitsværktøjet til numerisk område**, vises der en menu.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

I forbindelse med det numeriske område kan du vælge mellem følgende tre muligheder:

* Mellem
* Mindre end eller lig med
* Større end eller lig med

Når du vælger **Mellem** i menuen, vises der en skyder, og du kan filtrere efter numeriske værdier, der ligger mellem tallene. Udover at bruge selve skyderen kan du også klikke i felterne og skrive værdierne. Det er praktisk, når du vil opdele specifikke heltal, men kornetheden ved at flytte skyderen gør det vanskeligt at lande nøjagtigt på tallet.

På følgende billede er rapportsiden filtreret for *UnitPrice*-værdier mellem 500 og 1500.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

Når vi vælger **Mindre end eller lig med**, forsvinder venstre håndtag (den laveste værdi) for skyderen, og vi kan kun justere den øvre grænse for skyderen. På følgende billede angiver vi skyderen til 497.17.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

Og endelig, hvis vi vælger **Større end eller lig med** forsvinder højre håndtag til skyderen (den højeste værdi), og vi kan justere den laveste værdi, som vist på følgende billede. Nu vises der kun elementer, der har en *UnitPrice*, som er større end eller lig med 750.56, i de visuelle elementer på rapportsiden.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer-preview"></a>Fastgør til hele tal ved hjælp af udsnitsværktøj til numerisk område (prøveversion)

Fra og med udgivelsen af **Power BI Desktop** fra februar 2018, fastgør dit udsnitsværktøj til numerisk område til hele tal. Dermed kan udsnitsværktøjet nemt afstemme to hele tal. Fastgørelse til hele tal gælder ikke for decimalfiltre.


## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Følgende begrænsninger og overvejelser, der aktuelt gælder for **udsnitsværktøjet til numerisk område**

* **Udsnitsværktøjet til numerisk område** filtrerer i øjeblikket alle underliggende rækker i dataene, ingen aggregerede værdier. Hvis f.eks. feltet *Sales Amount* bruges, filtreres der efter alle transaktioner, der er baseret på *Sales Amount*, ikke summen af *Sales Amount* for hvert datapunkt i et visuelt element.
* Den fungerer i øjeblikket ikke sammen med målinger
* I øjeblikket er **udsnitsværktøjet til numerisk område** kun tilgængeligt i **Power BI Desktop**. Hvis en rapport, der bruger **udsnitsværktøjet til numerisk område**, er publiceret i **Power BI-tjenesten**, anvendes filteret stadig, men det vises som et listeudsnit.

