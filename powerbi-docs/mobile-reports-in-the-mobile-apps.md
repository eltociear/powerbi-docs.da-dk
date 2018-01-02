---
title: Udforsk rapporter i Power BI-mobilappsene
description: "Se, hvordan du kan få vist og interagere med rapporter i Power BI-mobilappsene på din telefon eller tablet. Du kan oprette rapporter i Power BI-tjenesten eller Power BI Desktop og derefter interagere med dem i mobilappsene. "
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3515a57f88db1c8a7b12706680c0aade8b2cdbfa
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Udforsk rapporter i Power BI-mobilappsene
Gælder for:

| ![iPhone](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android-telefon](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android-tablet](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10-enheder](media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone-telefoner |iPad-tablets |Android-telefoner |Android-tablets |Windows 10-enheder |

En Power BI-rapport er en interaktiv visning af dine data, hvor visualiseringer repræsenterer forskellige resultater og indsigter fra disse data. At få vist rapporter i Power BI-mobilapps er det sidste trin i en proces med tre trin.

1. [Opret rapporter i Power BI Desktop](desktop-report-view.md). Du kan endda [optimere en rapport til telefoner](mobile-apps-view-phone-report.md) i Power BI Desktop. 
2. Publicer disse rapporter til Power BI-tjenesten [(https://powerbi.com)](https://powerbi.com) eller [Power BI-rapportserver](report-server/get-started.md).  
3. Derefter kan du interagere med rapporterne i Power BI-mobilappsene.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Åbn en Power BI-rapport i mobilappen
Power BI-rapporter er gemt på forskellige steder i mobilappen, afhængigt af hvor du har fået dem. De kan være placeret under Apps, Delt med mig, Arbejdsområder(herunder Mit arbejdsområde) eller på en rapportserver. Nogle gange skal du gennem et relateret dashboard for at komme til en rapport. Andre gange vises de på en liste.

* Tryk på de tre prikker (...) i øverste højre hjørne af et felt på et dashboard, og vælg **Åbn rapport**.
  
  ![Åbn rapport](media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Det er ikke alle felter, der kan åbnes i en rapport. De felter, der er oprettet ved at stille spørgsmål i feltet Spørgsmål og svar, kan for eksempel ikke åbnes i en rapport, når du trykker på dem. 
  
  På en telefon åbnes rapporten i liggende format, medmindre den er [optimeret til visning på en telefon](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones).
  
  ![Telefonrapport i liggende format](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Vis rapporter, der er optimeret til telefoner
Den, der opretter en rapport i Power BI, kan oprette et rapportlayout, som er specifikt optimeret til telefoner. Hvis en rapport er optimeret til telefoner, vises den med et særligt ikon på listen over rapporter ![Ikon for rapport, der er optimeret til telefoner](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Åbn en rapport, der er optimeret til telefoner](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Når du får vist rapporten på en telefon, åbnes den i stående format.

![Rapport i stående format](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

En rapport kan have flere sider, hvor nogle er optimeret til telefoner, mens andre sider ikke er. Hvis det er tilfældet, skifter visningen fra stående til liggende format på de enkelte sider, når du bladrer i rapporten.

Læs mere om [rapporter, der er optimeret til visning på telefoner](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report-page"></a>Brug udsnit til at filtrere en rapportside
Når du designer en rapport i Power BI-tjenesten [(https://powerbi.com)](https://powerbi.com), skal du huske på, at ruden Filtre ikke vises på telefoner, men du kan [se udsnit på en rapportside](power-bi-visualization-slicers.md). Du kan tilføje udsnit i en rapport, så du og dine kolleger kan bruge udsnittene til at filtrere siden på en telefon.

* Når du vælger en værdi i et udsnit på rapportsiden, filtreres de andre visualiseringer på siden.
  
  ![Rapportudsnit](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  I denne illustration filtrerer udsnittet søjlediagrammet, så der kun vises værdier for juli måned.

## <a name="cross-filter-and-highlight-a-power-bi-report-page"></a>Krydsfiltrer og fremhæv en Power BI-rapportside
Når du vælger en værdi i en visualisering, filtreres de øvrige visualiseringer ikke. I stedet fremhæves de relaterede værdier i de andre visualiseringer.

* Tryk på en værdi i en visualisering.
  
  ![Krydsfiltrer en side](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Hvis du trykker på kolonnen Stor i en visualisering, fremhæves de relaterede værdier i andre visualiseringer. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Sortér en visualisering på en iPad eller en tablet
* Tryk på diagrammet, tryk på de tre prikker (**...**), og tryk på feltnavnet.
  
   ![Sortér en visualisering](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Hvis du vil vende sorteringsrækkefølgen, skal du trykke på de tre prikker (**...**) igen og derefter trykke på det samme feltnavn igen.

## <a name="drill-down-and-up-in-a-visual-on-an-ipad-or-a-tablet"></a>Detailudledning i en visualisering på en iPad eller en tablet
Hvis forfatteren til en rapport har tilføjet denne funktion i en visualisering, kan du bruge detailudledning i visualiseringer på en iPad eller tablet for at se de værdier, som er brugt til en del af visualiseringen. Du kan [tilføje detailudledning i en visualisering](power-bi-visualization-drill-down.md) i Power BI Desktop eller Power BI-tjenesten. 

> [!NOTE]
> I øjeblikket kan du ikke bruge detailudledning i kort på iPad eller andre tablets.
> 
> 

* Tryk på en visualisering. Hvis der vises pil op og pil ned i hjørnerne i toppen ![Ikonerne Vis færre detaljer og Analysér ned](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-down.png), kan du bruge detailudledning. Hvis du vil have vist flere detaljer om en værdi, skal du trykke på pilen i øverste højre hjørne og derefter trykke på en værdi i visualiseringen &#150; i dette tilfælde den mørkeblå FD-04-boble.
  
  ![Detailudledning i en visualisering](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-one.png)
* Hvis du vil have vist færre detaljer igen, skal du trykke på pil op i øverste venstre hjørne.
  
  ![Færre detaljer](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up.png)

## <a name="go-back-to-my-workspace"></a>Gå tilbage til Mit arbejdsområde
* Tryk på pilen ud for rapportnavnet, og tryk på **Mit arbejdsområde**.
  
  ![Gå op igen](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-back.png)

## <a name="next-steps"></a>Næste trin
* [Få vist og interager med Power BI-rapporter, der er optimeret til din telefon](mobile-apps-view-phone-report.md)
* [Opret en version af en rapport, der er optimeret til telefoner](desktop-create-phone-report.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

