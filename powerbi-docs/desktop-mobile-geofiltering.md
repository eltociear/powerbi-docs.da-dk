---
title: Angiv geografiske filtre i Power BI Desktop til mobilapps
description: "Når du har angivet geografisk filtrering i din model i Power BI Desktop, kan du automatisk filtrere data efter din placering i Power BI-mobilapps."
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
ms.date: 07/18/2017
ms.author: maggies
ms.openlocfilehash: ac03f3e97c2e2cef7d4f083e5b835aa4c87de633
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="set-geographic-filters-in-power-bi-desktop-for-the-mobile-apps"></a>Angiv geografiske filtre i Power BI Desktop til mobilapps
I Power BI Desktop kan du [kategorisere geografiske data](desktop-data-categorization.md) i en kolonne, så Power BI Desktop ved, hvordan værdier skal behandles i visualiseringer i en rapport. En yderligere fordel er, at når du eller dine kollegaer får vist den pågældende rapport i Power BI-mobilappsene, leverer Power BI automatisk de geografiske filtre, der stemmer overens med jeres placering. 

Lad os f.eks. sige, at du er en salgschef, der rejser for at møde kunder, og du vil gerne hurtigt filtrere samlet salg og omsætning for den specifikke kunde, du planlægger at besøge. Du vil gerne have vist dataene for din aktuelle placering enten efter delstat, by eller en faktiske adresse. Hvis du senere har mere tid, vil du gerne besøge andre kunder i nærheden. Du kan [filtrere rapporten efter din placering for at finde disse kunder](mobile-apps-geographic-filtering.md).

> [!NOTE]
> Du kan kun filtrere efter placering i mobilappen, hvis de geografiske navne i rapporten er på engelsk &#150; f.eks. "New York City" eller "Germany".
> 
> 

## <a name="identify-geographic-data-in-your-report"></a>Identificer geografiske data i din rapport
1. Skift til Datavisning i Power BI Desktop ![Ikonet Datavisning](media/desktop-mobile-geofiltering/pbi_desktop_data_icon.png).
2. Vælg en kolonne med geografiske data &#150; f.eks. kolonnen By.
   
    ![Kolonnen By](media/desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)
3. På fanen **Udformning** skal du vælge **Datakategori** og derefter den korrekte kategori &#150; i dette eksempel **By**.
   
    ![Boksen Datakategori](media/desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)
4. Du kan fortsætte med at angive geografisk datakategorier for alle andre felter i modellen. 
   
   > [!NOTE]
   > Du kan angive flere kolonner for hver datakategori i en model, men hvis du gør det, kan modellen ikke filtrere efter geografi i Power BI-mobilappen. Hvis du vil bruge geografisk filtrering i mobilappsene, skal du kun angive én kolonne for hver datakategori &#150; f.eks. kun én kolonne med **By**, en kolonne med **Delstat eller provins** og én kolonne med **Land**. 
   > 
   > 

## <a name="create-visuals-with-your-geographic-data"></a>Opret visualiseringer med din geografiske data
1. Skift til Rapportvisning ![Ikonet Rapportvisning](media/desktop-mobile-geofiltering/power-bi-desktop-report-icon.png), og opret visualiseringer, der bruger de geografiske felter i dine data. 
   
    ![Rapport med kort](media/desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)
   
    I dette eksempel indeholder modellen også en beregnet kolonne, hvor by og delstat sammenlægges i en kolonne. Læs om, hvordan du [opretter beregnede kolonner i Power BI Desktop](desktop-calculated-columns.md).
   
    ![Feltet By + Delstat](media/desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)
2. Udgiv rapporten i Power BI-tjenesten.

## <a name="view-the-report-in-power-bi-mobile-app"></a>Få vist rapporten i Power BI-mobilappen
1. Åbn rapporten i en hvilken som helst af [Power BI-mobilappsene](mobile-apps-for-mobile-devices.md).
2. Hvis du befinder dig på en geografisk placering med data i rapporten, kan du filtrere den automatisk efter din placering.
   
    ![Geografisk filter i mobilappen](media/desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

Læs mere om, hvordan du [filtrerer en rapport efter placering i Power BI-mobilapps](mobile-apps-geographic-filtering.md).

## <a name="next-steps"></a>Næste trin
* [Datakategorisering i Power BI Desktop](desktop-data-categorization.md)  
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

