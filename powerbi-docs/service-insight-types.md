---
title: Indsigtstyper, der understøttes af Power BI
description: Hurtige indsigter og Vis indsigter i Power BI.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 44b59019f1955258716e23fb2dd55182134cc6a2
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "34250583"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Indsigtstyper, der understøttes af Power BI
## <a name="how-does-insights-work"></a>Hvordan fungerer indsigter?
Power BI søger hurtigt gennem forskellige undersæt i datasættet og anvender samtidig et sæt avancerede algoritmer for at finde indsigt, der kan være interessant. Power BI scanner så meget af et datasæt som muligt i et tildelt tidsrum.

Du kan køre indsigt i forhold til et datasæt eller et dashboardfelt.   

## <a name="what-types-of-insights-can-we-find"></a>Hvilke typer indsigter kan vi finde?
Det er nogle af de algoritmer, vi bruger:

## <a name="category-outliers-topbottom"></a>Kategori med udenforliggende værdier (top/bund)
Fremhæver tilfælde, hvor et eller to medlemmer i en dimension for en måling i modellen har meget større værdier end andre medlemmerne i dimensionen.  

![Eksempel på kategori med udenforliggende værdier](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Skift punkter i en tidsserie
Fremhæver, når der er betydelige ændringer i tendenser i en tidsserie af data.

![Eksempel på skift af punkter i en tidsserie](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelation
Registrerer tilfælde, hvor flere målinger viser en korrelation mellem hinanden, når de afbildes mod en dimension i datasættet.

![Eksempel på korrelation](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Lav varians
Registrerer tilfælde, hvor datapunkter ikke er langt fra middelværdien.

![Eksempel på lav varians](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Majoritet (overordnede faktorer)
Finder tilfælde, hvor en majoritet af en samlet værdi kan tilskrives en enkelt faktor, når den opdeles på en anden dimension.  

![Eksempel på vigtige faktorer](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Samlede tendenser i tidsserie
Registrerer op- eller nedadgående tendenser i tidsseriedata.

![Eksempel på generelle tendenser i tidsserie](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Sæsonudsving i tidsserie
Finder periodiske mønstre i tidsseriedata, f.eks. ugentlige, månedlige eller årlige sæsonudsving.

![Eksempel på sæsonudsving](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Konstant deling
Fremhæver tilfælde, hvor der er en overordnet-underordnet-korrelation mellem andelen af en underordnet værdi i forhold til den samlede værdi af den overordnede på tværs af en kontinuerlig variabel.

![Eksempel på konstant deling](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Tidsserier med udenforliggende værdier
Registrerer for data på tværs af en tidsserie, når der er specifikke datoer og klokkeslæt med værdier, som er væsentligt anderledes end de andre dato-/klokkeslætsværdier.

![Eksempel på tidsserier med udenforliggende værdier](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Næste trin
[Power BI-indsigter](service-insights.md)

Hvis du ejer et datasæt, [kan du optimere det til indsigter](service-insights-optimize.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

