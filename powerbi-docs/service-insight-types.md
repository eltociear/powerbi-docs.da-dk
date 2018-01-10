---
title: "Indsigtstyper, der understøttes af Power BI"
description: Hurtige indsigter og Vis indsigter i Power BI.
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 53e5e67da9bacd9fc9dcbb770747823647aa3a3c
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-insights-supported-by-power-bi"></a>Indsigtstyper, der understøttes af Power BI
## <a name="how-does-insights-work"></a>Hvordan fungerer indsigter?
Power BI søger hurtigt gennem forskellige undersæt i datasættet og anvender samtidig et sæt avancerede algoritmer for at finde indsigt, der kan være interessant. Power BI scanner så meget af et datasæt som muligt i et tildelt tidsrum.

Du kan køre indsigt i forhold til et datasæt eller et dashboardfelt.   

## <a name="what-types-of-insights-can-we-find"></a>Hvilke typer indsigter kan vi finde?
Det er nogle af de algoritmer, vi bruger:

## <a name="category-outliers-topbottom"></a>Kategori med udenforliggende værdier (top/bund)
Fremhæver tilfælde, hvor et eller to medlemmer i en dimension for en måling i modellen har meget større værdier end andre medlemmerne i dimensionen.  

![](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Skift punkter i en tidsserie
Fremhæver, når der er betydelige ændringer i tendenser i en tidsserie af data.

![](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelation
Registrerer tilfælde, hvor flere målinger viser en korrelation mellem hinanden, når de afbildes mod en dimension i datasættet.

![](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Lav varians
Registrerer tilfælde, hvor datapunkter ikke er langt fra middelværdien.

![](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Majoritet (overordnede faktorer)
Finder tilfælde, hvor en majoritet af en samlet værdi kan tilskrives en enkelt faktor, når den opdeles på en anden dimension.  

![](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Samlede tendenser i tidsserie
Registrerer op- eller nedadgående tendenser i tidsseriedata.

![](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Sæsonudsving i tidsserie
Finder periodiske mønstre i tidsseriedata, f.eks. ugentlige, månedlige eller årlige sæsonudsving.

![](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Konstant deling
Fremhæver tilfælde, hvor der er en overordnet-underordnet-korrelation mellem andelen af en underordnet værdi i forhold til den samlede værdi af den overordnede på tværs af en kontinuerlig variabel.

![](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Tidsserier med udenforliggende værdier
Registrerer for data på tværs af en tidsserie, når der er specifikke datoer og klokkeslæt med værdier, som er væsentligt anderledes end de andre dato-/klokkeslætsværdier.

![](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Næste trin
[Power BI-indsigter](service-insights.md)

Hvis du ejer et datasæt, [kan du optimere det til indsigter](service-insights-optimize.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

