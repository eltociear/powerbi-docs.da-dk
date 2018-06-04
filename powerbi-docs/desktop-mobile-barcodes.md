---
title: Markér et stregkodefelt i Power BI Desktop til mobilapps
description: Når du markerer et stregkodefelt i modellen i Power BI Desktop, kan du automatisk filtrere data efter stregkoder i Power BI-appen på din iPhone.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: ae6c7ba3603136aeea3daa412595b9f42ed13d6a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34286905"
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>Markér stregkoder i Power BI Desktop til mobilapps
I Power BI Desktop kan du [kategorisere data](desktop-data-categorization.md) i en kolonne, så Power BI Desktop ved, hvordan værdier skal behandles i visualiseringer i en rapport. Du kan også kategorisere en kolonne som **stregkode**. Når du eller dine kollegaer [scanner en stregkode på et produkt med Power BI-appen](mobile-apps-scan-barcode-iphone.md) på jeres iPhone, får I vist alle de rapporter, der indeholder denne stregkode. Når du åbner rapporten i mobilappen, filtrerer Power BI automatisk rapporten efter data, der er relateret til denne stregkode.

1. Skift til Datavisning i Power BI Desktop.
2. Vælg en kolonne med stregkodedata. Se en liste over [understøttede stregkodeformater](#supported-barcode-formats) nedenfor.
3. På fanen **Modellering** skal du vælge **Datakategori** > **Stregkode**.
   
    ![Liste over datakategorier](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. I Rapportvisning skal du føje dette felt til de visualiseringer, du vil have filtreret efter stregkoden.
5. Gem rapporten, og publicer den i Power BI-tjenesten.

Når du nu åbner scanneren i [Power BI-appen til iPhone](mobile-ios-ipad-iphone-apps.md) og scanner en stregkode, kan du se denne rapport på listen over rapporter. Når du åbner rapporten, filtreres visualiseringerne efter den produktstregkode, du scannede.

## <a name="supported-barcode-formats"></a>Understøttede stregkodeformater
Power BI genkender følgende stregkoder, hvis du kan tagge dem i en Power Bi-rapport: 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>Næste trin
* [Scan en stregkode fra Power BI-appen på din iPhone](mobile-apps-scan-barcode-iphone.md)
* [Problemer med scanning af stregkoder på en iPhone](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Datakategorisering i Power BI Desktop](desktop-data-categorization.md)  
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

