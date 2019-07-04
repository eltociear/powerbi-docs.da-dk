---
title: Vandfaldsdiagrammer i Power BI
description: Vandfaldsdiagrammer i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c9ad87d851f52db6cd2720c9e3bd5d4bb7b189a7
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2019
ms.locfileid: "67409128"
---
# <a name="waterfall-charts-in-power-bi"></a>Vandfaldsdiagrammer i Power BI

Vandfaldsdiagrammer viser en løbende total, efterhånden som Power BI lægger værdier til eller trækker dem fra. Det er nyttigt at forstå dem for at se, hvordan en indledende værdi (f.eks. årets resultat) påvirkes af en række positive og negative ændringer.

Kolonnerne er farvekodet, så du hurtigt kan se stigninger og fald. Kolonnerne med den indledende og endelige værdi [starter ofte på den vandrette akse](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "start på den vandrette akse"), mens de mellemliggende værdier er flydende kolonner. Vandfaldsdiagrammer kaldes også brodiagrammer på grund af deres format.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Hvornår skal du bruge et vandfaldsdiagram?

Vandfaldsdiagrammer er et godt valg:

* Når der er ændringer af målingen på tværs af tid, en serie eller forskellige kategorier.

* Til overvågning af overordnede ændringer, der bidrager til den samlede værdi.

* Til afbildning af virksomhedens årsresultatet ved at vise flere omsætningskilder og opnå det samlede resultat.

* Til illustration af antal medarbejdere ved årets start og slutning.

* Til visualisering af, hvor mange penge du tjener og bruger hver måned, samt den løbende kontosaldo.

## <a name="prerequisites"></a>Forudsætninger

* Power BI-tjenesten eller Power BI Desktop

* Rapporten Retail Analysis Sample

## <a name="get-the-retail-analysis-sample-report"></a>Hent rapporten Retail Analysis Sample

I denne vejledning bruges Retail Analysis Sample (Eksempel på detailhandelsanalyse). Oprettelse af en visualisering kræver redigeringsrettigheder til datasættet og rapporten. Heldigvis kan alle Power BI-eksemplerne redigeres. Hvis en person deler en rapport med dig, kan du ikke oprette visualiseringer i rapporter. Hvis du vil følge med, skal du hente [rapporten Retail Analysis Sample](../sample-datasets.md).

Når du har hentet datasættet for **Retail Analysis Sample**, kan du komme i gang.

## <a name="create-a-waterfall-chart"></a>Opret et vandfaldsdiagram

Du opretter et vandfaldsdiagram, der viser afvigelsen i salg (anslået salg i forhold til faktisk salg) pr. måned.

1. Vælg **Datasæt** > **Opret en rapport** fra **Mit arbejdsområde**.

    ![Skærmbillede af Datasæt > Opret en rapport.](media/power-bi-visualization-waterfall-charts/power-bi-create-a-report.png)

1. I ruden **Felter** skal du markere **Sales** > **Total Sales Variance**.

   ![Skærmbillede, hvor Sales > Total Sales Varience er valgt, og af den visualisering, der oprettes.](media/power-bi-visualization-waterfall-charts/power-bi-first-value.png)

1. Vælg ikonet for vandfaldsdiagram ![Skærmbillede af ikonet for vandfaldsdiagram](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png) for at konvertere diagrammet til en træstruktur.

    Hvis **Total Sales Variance** ikke findes på **Y-aksen**, skal du trække den derhen.

    ![Visualiseringsskabeloner](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)

1. Vælg **Time** > **FiscalMonths** for at føje det til området **Category**.

    ![Vandfaldsdiagram](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)

1. Kontrollér, at Power BI har sorteret vandfaldsdiagrammet kronologisk. Vælg ellipsen (...) i diagrammets øverste højre hjørne.

    Kontrollér, at der er en gul indikator til venstre for indstillingerne **Sortér stigende** og **FiscalMonth**

    ![Vælg Sortér efter > FiscalMonth](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)

    Du kan også kigge på værdierne for X-aksen og se, at de vises i rækkefølge fra **Jan** til **Aug**.

    Se lidt nærmere på, hvad der bidrager mest til ændringerne måned for måned.

1. Træk **Butiks** > **området** til beholderen **Opdeling**.

    ![Viser Store i opdelingsbucket](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Som standard tilføjes de øverste fem bidragydere for stigninger eller fald pr. måned i Power BI.

    ![Viser Store i opdelingsbucket](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-initial.png)

    Du er kun interesseret i de øverste to bidragydere.

1. I ruden **Formatér** skal du vælge **Breakdown** og angive **Max breakdowns** til **2**.

    ![Formatér > Breakdown](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)

    En hurtig gennemgang viser, at områderne Ohio og Pennsylvania er de største bidragydere til bevægelser, både negative og positive, i vandfaldsdiagrammet.

    ![vandfaldsdiagram](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)

    Det er et interessant resultat. Har Ohio og Pennsylvania en væsentlig indvirkning, fordi salg i disse to områder er meget større end de andre områder? Det kan du kontrollere.

1. Opret et kort, som ser nærmere på salgsværdien i år og sidste år efter distrikt.

    ![nærbillede af kort på PA og Ohio](media/power-bi-visualization-waterfall-charts/power-bi-map.png)

    Kortet understøtter din teori. Det viser, at disse to områder havde den højeste salgsværdi sidste år (boblestørrelse) og i år (bobleskygge).

## <a name="highlighting-and-cross-filtering"></a>Fremhævning og krydsfiltrering

Du kan få mere at vide om brug af ruden **Filtre** under [Føj et filter til en rapport i redigeringsvisning](../power-bi-report-add-filter.md).

Hvis du fremhæver en kolonne i et vandfaldsdiagram, krydsfiltreres de andre visualiseringer på rapportsiden og omvendt. Kolonnen **Total** udløser dog ikke fremhævning og reagerer ikke på krydsfiltrering.

## <a name="next-steps"></a>Næste trin

* [Rediger, hvordan visualiseringer interagerer i en Power BI-rapport](../service-reports-visual-interactions.md)

* [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
