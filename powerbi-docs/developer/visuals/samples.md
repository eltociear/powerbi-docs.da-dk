---
title: Eksempler på Power BI-visualiseringer
description: I denne artikel præsenteres eksempler på Power BI-visualiseringer, herunder udsnit, mere end 20 typer diagrammer, WebGL og R-visualiseringer og -scripts.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/17/2019
ms.openlocfilehash: 5e2ad0fa43a186be76a58f1ab3bb4bf054a677a5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83132943"
---
# <a name="samples-of-power-bi-visuals"></a>Eksempler på Power BI-visualiseringer

Du kan downloade, bruge og ændre disse Power BI-visualiseringer fra GitHub. Disse eksempler illustrerer, hvordan du kan håndtere almindelige situationer, når du udvikler med Power BI.

## <a name="slicers"></a>Udsnit

Et udsnit begrænser den del af data, der vises i andre visualiseringer i en rapport. Udsnit er en af flere måder at filtrere data på i Power BI.

| <img src="media/samples/chiclet-slicer.png" width="200">  | <img src="media/samples/timeline-slicer.png" width="200"> | <img src="media/samples/sample-slicer.png" width="200">|
| ------------- | ------------- | -------------|
| [Firkantudsnitsværktøj](https://github.com/Microsoft/powerbi-visuals-chicletslicer/)  </br>Vis billede og/eller tekstknapper, der fungerer som et lærredsfilter på andre visualiseringer | [Tidslinjeudsnitsværktøj](https://github.com/Microsoft/powerbi-visuals-timeline/) </br>Valg af grafisk datoområde, der filtrerer efter dato | [Eksempel på udsnit](https://github.com/Microsoft/powerbi-visuals-sampleslicer/) </br>Demonstrerer brugen af API'en til avanceret filtrering

## <a name="charts"></a>Diagrammer

Hent inspiration i vores galleri, herunder søjlediagrammer, cirkeldiagrammer, Word Cloud med flere.

| <img src="media/samples/aster-plot.png" width="200">  | <img src="media/samples/bullet-chart.png" width="200"> | <img src="media/samples/Chord.png" width="200">|
| ------------- | ------------- | -------------|
| [Aster-diagram](https://github.com/Microsoft/powerbi-visuals-asterplot/)  </br>En ny vinkel på et standardkransediagram med en anden værdi til at køre udfaldsvinklen | [Punktdiagram](https://github.com/Microsoft/powerbi-visuals-bulletchart/) </br>Et søjlediagram med ekstra visualiseringer, der tilfører yderligere nyttige sammenhænge til at spore mål | [Korde](https://github.com/Microsoft/powerbi-visuals-chord/) </br>En grafisk metode til at vise de indbyrdes relationer mellem data i en matrix
| <img src="media/samples/dot-plot.png" width="200"> | <img src="media/samples/dual-kpi.png" width="200">| <img src="media/samples/enhanced-scatter.png" width="200"> 
| [Punktvisning](https://github.com/Microsoft/powerbi-visuals-dotplot/) </br>Vis hyppighedsfordelingen på en flot måde | [Dobbelt-KPI](https://github.com/Microsoft/powerbi-visuals-dualkpi/) </br>Visualiserer effektivt to målinger over tid og viser deres tendens på en fælles tidslinje | [Forbedret punktdiagram](https://github.com/Microsoft/powerbi-visuals-enhancedscatter/) </br>Forbedringer af det eksisterende punktdiagram
| <img src="media/samples/forcegraph.png" width="200">| <img src="media/samples/gantt.png" width="200">| <img src="media/samples/table-heatmap.png" width="200">
| [Force-graf](https://github.com/Microsoft/powerbi-visuals-forcegraph/) </br>Force-layoutdiagram med kurvet sti, der er velegnet til at vise forbindelser mellem enheder | [Gantt](https://github.com/Microsoft/powerbi-visuals-gantt/) </br>En type søjlediagram, som illustrerer et projekts tidslinje eller tidsplan med ressourcer | [Heatmaptabel](https://github.com/Microsoft/powerbi-visuals-heatmap/) </br>Sammenlign data let og intuitivt ved hjælp af farver i en tabel
| <img src="media/samples/histogram-chart.png" width="200"> | <img src="media/samples/linedot-chart.png" width="200"> | <img src="media/samples/mekko-chart.png" width="200"> 
| [Histogram](https://github.com/Microsoft/powerbi-visuals-histogram/) </br>Visualiserer distribution af data over et fortløbende interval eller en bestemt tidsperiode | [LineDot-diagram](https://github.com/Microsoft/powerbi-visuals-linedotchart/) </br>Et animeret kurvediagram med animerede punkter, der er velegnet til at engagere en målgruppe med data | [Mekko-diagram](https://github.com/Microsoft/powerbi-visuals-mekkochart/) </br>En blanding af 100 % stablet søjlediagram og 100 % stablet liggende søjlediagram kombineret i én visning
| <img src="media/samples/multikpi.png" width="200"> | <img src="media/samples/powerkpi.png" width="200"> | <img src="media/samples/powerkpi-matrix.png" width="200"> 
| [Multi-KPI](https://github.com/microsoft/PowerBI-visuals-MultiKPI/) </br> En effektiv visualisering med flere KPI'er med en vigtig KPI sammen med flere minidiagrammer med understøttende data | [Power-KPI](https://github.com/microsoft/PowerBI-visuals-PowerKPI/) </br>En effektiv KPI-indikator med flerkurvediagram og mærkater for dags dato, værdi og afvigelser | [Power-KPI-matrix](https://github.com/microsoft/PowerBI-visuals-PowerKPIMatrix/) </br>Overvåg videnregnskaber og et ubegrænset antal målepunkter og KPI'er på en kompakt og letlæselig liste
| <img src="media/samples/pulse-chart.png" width="200">| <img src="media/samples/radar-chart.png" width="200"> | <img src="media/samples/sankey-chart.png" width="200"> 
| [Impulsdiagram](https://github.com/Microsoft/powerbi-visuals-pulsechart/) </br>Dette kurvediagram med vigtige begivenheder er perfekt til at fortælle historier med data| [Radardiagram](https://github.com/Microsoft/powerbi-visuals-radarchart/) </br>Repræsenterer flere målinger, der er afbildet over en kategoriakse, og er nyttigt til at sammenligne attributter | [Sankey-diagram](https://github.com/Microsoft/powerbi-visuals-sankey/) </br>Rutediagram, hvor bredden på serien er proportional med mængden af strømmen
| <img src="media/samples/stream-graph.png" width="200"> | <img src="media/samples/sunburst.png" width="200">| <img src="media/samples/tornado.png" width="200">
| [Stream-graf](https://github.com/Microsoft/powerbi-visuals-streamgraph/) </br>Et stablet områdediagram med jævn interpolering, som ofte bruges til at vise værdier over tid | [Solstrålediagram](https://github.com/Microsoft/powerbi-visuals-sunburst/) </br>Kransediagram med flere niveauer til effektiv visualisering af hierarkiske data| [Tornadodiagram](https://github.com/Microsoft/powerbi-visuals-tornado/) </br>Sammenlign den relative vigtighed af variabler mellem to grupper
 | <img src="media/samples/word-cloud.png" width="200">
 | [Ordcloud](https://github.com/Microsoft/powerbi-visuals-wordcloud/) </br>Opret en sjov visualisering fra hyppig tekst i dine data

## <a name="webgl"></a>WebGL

WebGL gør det muligt at bruge en API på webindhold, der er baseret på OpenGL ES 2.0, til at foretage gengivelse i 2D og 3D på et HTML-lærred.

| <img src="media/samples/globe-map.png" width="250">|
| ------------- |
| [Globuskort](https://github.com/Microsoft/powerbi-visuals-globemap/) </br>Afbild placeringer på et interaktivt 3D-kort

## <a name="r-visuals"></a>R-visualiseringer

Disse eksempler viser, hvordan du kan udnytte den analytiske og visuelle styrke af R-visualiseringer og R-scripts.

| <img src="media/samples/association-rules.png" width="200">| <img src="media/samples/clustering.png" width="200">| <img src="media/samples/clustering-with-outliers.png" width="200">|
|------------- |------------- |------------- |------------- |
| [Tilknytningsregler](https://github.com/Microsoft/powerbi-visuals-assorules/) </br>Afdæk relationer mellem tilsyneladende ikke-relaterede data ved hjælp af if-then-sætninger | [Clustering](https://github.com/Microsoft/powerbi-visuals-clustering-kmeans/) </br>Find lighedsgrupper i dine data ved hjælp af k-means-algoritmen | [Clustering med udenforliggende værdier](https://github.com/microsoft/PowerBI-visuals-dbscan/) </br>Find lighedsgrupper og udenforliggende værdier i dine data
| <img src="media/samples/correlation-plot.png" width="200"> | <img src="media/samples/decision-tree-chart.png" width="200"> | <img src="media/samples/forecasting-tbats.png" width="200"> 
| [Korrelationsdiagram](https://github.com/Microsoft/powerbi-visuals-corrplot/) </br>Fremhæv de mest korrelerede variabler i en datatabel | [Beslutningstrædiagram](https://github.com/Microsoft/powerbi-visuals-decision-tree/) </br>Skematisk træformet diagram til bestemmelse af statistisk sandsynlighed ved hjælp af rekursiv partitionering | [Prognose-TBATS](https://github.com/Microsoft/powerbi-visuals-forcasting-tbats/) </br>Tidsserieprognose for serier, der har flere sæsonudsving, ved hjælp af TBATS-modellen
| <img src="media/samples/forecasting-with-ARIMA.png" width="200"> | <img src="media/samples/funnel-plot.png" width="200"> | <img src="media/samples/outliers-detection.png" width="200"> 
| [Prognose med ARIMA](https://github.com/Microsoft/powerbi-visuals-forcastingarima/) </br>Forudsig fremtidige værdier på baggrund af historiske data ved hjælp af ARIMA (Autoregressive Integrated Moving Avg) | [Tragtafbildning](https://github.com/Microsoft/powerbi-visuals-funnel/) </br>Find udenforliggende værdier i dine data ved hjælp af en tragtafbildning | [Registrering af udenforliggende værdier](https://github.com/Microsoft/powerbi-visuals-outliers-det/) </br>Find udenforliggende værdier i dine data ved hjælp af den mest passende metode og afbildning
| <img src="media/samples/spline-chart.png" width="200"> | <img src="media/samples/time-series-decomposition-chart.png" width="200"> | <img src="media/samples/time-series-forecasting-chart.png" width="200">
| [Sløjfediagram](https://github.com/Microsoft/powerbi-visuals-spline/) </br>Visualiser og forstå støjende data | [Diagram med tidsserieopdeling](https://github.com/Microsoft/powerbi-visuals-timeseriesdecomposition/) </br>Forstå tidsseriekomponenterne ved hjælp af "Seasonal and Trend decomposition using Loess" | [Diagram med tidsserieprognose](https://github.com/Microsoft/powerbi-visuals-forcasting-exp/) </br>Brug af en eksponentiel udjævningsmodel til at forudsige fremtidige værdier, der er baseret på tidligere observerede værdier

## <a name="next-steps"></a>Næste trin

Hvis du vil prøve at oprette Power BI-visualiseringer, kan du se [Selvstudium: Udvikling af en Power BI-visualisering](custom-visual-develop-tutorial.md).
