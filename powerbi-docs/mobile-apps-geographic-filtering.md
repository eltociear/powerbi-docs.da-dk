---
title: Filtrer rapporten efter geografisk placering i en Power BI-mobilapp
description: Se, hvordan du kan filtrere en rapport efter din geografiske placering i din Microsoft Power BI-mobilapp, hvis rapportens ejer har indstillet geografiske koder.
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
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
ms.openlocfilehash: 340df05c0fcf4e839f8c6223d513ec55964fb5de
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Filtrer en rapport efter geografisk placering i Power BI-mobilapps
Gælder for:

| ![iPhone](media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Android-telefon](media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Android-tablet](media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![Android-tablet](media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone-telefoner |iPad-tablets |Android-telefoner |Android-tablets |Windows 10-telefoner |

Når du får vist en Power BI-rapport på din mobilenhed, vises der da et lille ikon med en tavlenål i øverste højre hjørne? Hvis der gør det, kan du filtrere rapporten baseret på din geografiske placering.

> [!NOTE]
> Du kan kun filtrere efter placering, hvis de geografiske navne i rapporten er på engelsk #150; for eksempel "New York City" eller "Germany". Windows 10-tablets og -pc'er understøtter ikke geografisk filtrering, men Windows 10-telefoner gør.
> 
> 

## <a name="filter-your-report-by-your-geographic-location"></a>Filtrer din rapport efter din geografiske placering
1. Åbn en rapport i Power BI-mobilappen på din mobilenhed.
2. Hvis rapporten indeholder geografiske data, vises der en meddelelse, hvor du bliver bedt om at give Power BI adgang til din placering. Klik på **Tillad**, og tryk på **Tillad** igen.
3. Tryk på ikonet med tavlenålen ![Ikon med tavlenål](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Du kan filtrere efter by, stat/provins eller område/region afhængigt af dataene i rapporten. I filteret kan du kun se de indstillinger, der matcher din aktuelle placering.
   
    ![Filter med tavlenål](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Hvorfor kan jeg ikke se placeringskoder i en rapport?
Alle de tre følgende betingelser skal være opfyldt for at du kan se placeringskoder. 

* Den person, der oprettede rapporten i Power BI Desktop [kategoriserede geografiske data](desktop-mobile-geofiltering.md) for mindst én kolonne som By, Stat eller Land/Område.
* Du befinder dig på en af de placeringer, hvor der findes data i kolonnen.
* Du bruger en af disse mobilenheder:
  * iOS (iPad, iPhone, iPod).
  * Android-telefon eller -tablet.
  * Windows 10-telefon (andre typer Windows 10-enheder som pc'er og tablets understøtter ikke geografisk filtrering).

Læs mere om at [konfigurere geografisk filtrering](desktop-mobile-geofiltering.md) i Power BI Desktop.

### <a name="next-steps"></a>Næste trin
* [Opret forbindelse til Power BI-data fra den virkelige verden](mobile-apps-data-in-real-world-context.md) med mobilappen
* [Datakategorisering i Power BI Desktop](desktop-data-categorization.md) 
* Har du spørgsmål? [Prøv at spørge Power BI-communityet](http://community.powerbi.com/)
