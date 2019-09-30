---
title: Indsigtstyper, der understøttes af Power BI
description: Hurtige indsigter og Vis indsigter i Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 9/23/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 991dd7bb94e79a21c8e4ec877093b81d2ed9b285
ms.sourcegitcommit: e2c5d4561455c3a4806ace85defbc72e4d7573b4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/27/2019
ms.locfileid: "71327768"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Indsigtstyper, der understøttes af Power BI
## <a name="how-does-insights-work"></a>Hvordan fungerer indsigter?
Power BI søger hurtigt gennem forskellige undersæt i datasættet og anvender samtidig et sæt avancerede algoritmer for at finde indsigt, der kan være interessant. Power BI scanner så meget af et datasæt som muligt i et tildelt tidsrum.

Du kan køre indsigt i forhold til et datasæt eller et dashboardfelt.   

## <a name="what-types-of-insights-can-we-find"></a>Hvilke typer indsigter kan vi finde?
Det er nogle af de algoritmer, vi bruger:

## <a name="category-outliers-topbottom"></a>Kategori med udenforliggende værdier (top/bund)
Fremhæver tilfælde, hvor et eller to medlemmer i en dimension for en måling i modellen har meget større værdier end andre medlemmerne i dimensionen.  

![Eksempel på kategori med udenforliggende værdier](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Skift punkter i en tidsserie
Fremhæver, når der er betydelige ændringer i tendenser i en tidsserie af data.

![Eksempel på skift af punkter i en tidsserie](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelation
Registrerer tilfælde, hvor flere målinger viser en korrelation mellem hinanden, når de afbildes mod en dimension i datasættet.

![Eksempel på korrelation](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Lav varians
Registrerer tilfælde, hvor datapunkter ikke er langt fra middelværdien.

![Eksempel på lav varians](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Majoritet (overordnede faktorer)
Finder tilfælde, hvor en majoritet af en samlet værdi kan tilskrives en enkelt faktor, når den opdeles på en anden dimension.  

![Eksempel på vigtige faktorer](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Samlede tendenser i tidsserie
Registrerer op- eller nedadgående tendenser i tidsseriedata.

![Eksempel på generelle tendenser i tidsserie](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Sæsonudsving i tidsserie
Finder periodiske mønstre i tidsseriedata, f.eks. ugentlige, månedlige eller årlige sæsonudsving.

![Eksempel på sæsonudsving](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Konstant deling
Fremhæver tilfælde, hvor der er en overordnet-underordnet-korrelation mellem andelen af en underordnet værdi i forhold til den samlede værdi af den overordnede på tværs af en kontinuerlig variabel.

![Eksempel på konstant deling](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Tidsserier med udenforliggende værdier
Registrerer for data på tværs af en tidsserie, når der er specifikke datoer og klokkeslæt med værdier, som er væsentligt anderledes end de andre dato-/klokkeslætsværdier.

![Eksempel på tidsserier med udenforliggende værdier](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Næste trin
[Power BI-indsigter](end-user-insights.md)

Hvis du ejer et datasæt, [kan du optimere det til indsigter](../service-insights-optimize.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

