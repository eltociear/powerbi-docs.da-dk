---
title: Selvstudium – Kombinationsdiagram
description: Dette selvstudium om kombinationsdiagrammer forklarer, hvornår de bruges, og hvordan de oprettes i Power BI-tjenesten og Desktop.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: b5e89a9a1f2e88ed793dff6457b58fd9ac609ef5
ms.sourcegitcommit: e571de2afa3f34fac06a6aab0df0e8940cb00a0d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/05/2018
---
# <a name="combo-chart-in-power--tutorial"></a>Kombinationsdiagram i Power  (selvstudium)
I Power BI er et kombinationsdiagram en enkelt visualisering, der kombinerer et kurvediagram og et søjlediagram. Ved at kombinere disse to diagrammer kan du hurtigere sammenligne dine data.

Kombinationsdiagrammer kan have en eller to Y-akser.

## <a name="when-to-use-a-combo-chart"></a>Hvornår er et kombinationsdiagram nyttigt?
Kombinationsdiagrammer er et fantastisk valg i følgende tilfælde:

* Når du har et kurvediagram og et søjlediagram med den samme X-akse.
* Til at sammenligne flere målinger med forskellige værdiintervaller.
* Til at illustrere sammenhængen mellem to målinger i én visualisering.
* Til at kontrollere, om en måling opfylder målet, der er defineret af en anden måling
* Til at spare plads på lærredet.

### <a name="prerequisites"></a>Forudsætninger
Kombinationsdiagrammer er tilgængelige i Power BI-tjenesten og i Power BI Desktop. Dette selvstudium bruger Power BI-tjenesten til at oprette et kombinationsdiagram. Du kan følge med ved at åbne Power BI-tjenesten og oprette forbindelse til eksemplet på "detailhandelsanalyse" – se [ nedenstående vejledning](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Opret et grundlæggende kombinationsdiagram med én akse
Se, hvordan Will opretter et kombinationsdiagram ved hjælp af salgs- og marketingeksemplet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a> Log på Power BI-tjenesten for at oprette dit eget kombinationsdiagram, og vælg **Hent data \>Eksempler \> Eksempel på detailhandelsanalyse > Opret forbindelse > Gå til dashboard**.

1. Vælg feltet **Butikker i alt** fra dashboardet "Eksempel på detailhandelsanalyse" for at åbne rapporten "Eksempel på detailhandelsanalyse".
2. Vælg **Rediger rapport** for at åbne rapporten i redigeringsvisning.
3. [Tilføj en ny rapportside](power-bi-report-add-page.md).
4. Opret et søjlediagram, der viser dette års salg og bruttomargen pr. måned.

    a.  I ruden Fields skal du vælge **Sales**\> **This Year Sales** > **Value**.

    b.  Træk **Sales** \> **Gross Margin This Year** til beholderen **Value**.

    c.  Vælg **Time**\>**FiscalMonth** for at føje det til beholderen **Axis**.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Vælg ellipsen (...) i øverste højre hjørne af visualiseringen, og vælg **Sort by FiscalMonth**. Du skal muligvis vælge den to gange for at sortere i stigende eller faldende rækkefølge.

6. Konvertér søjlediagrammet til et kombinationsdiagram. Vælg søjlediagrammet, og vælg derefter **Line and clustered column chart** fra fanen **Visualizations**.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. Fra ruden **Fields** kan du derefter trække **Sales** \> **Last Year Sales** til beholderen **Line Values**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Dit kombinationsdiagram bør ligne dette:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Opret et kombinationsdiagram med to akser
I denne opgave skal vi sammenligne bruttomargen og salg.

1. Opret et nyt kurvediagram, der sporer **Gross Margin Last Year %** efter **Month**.  I januar var BM% på 35 %, den steg til 45 % i april, faldt i juli og steg igen i august. Kan vi se et tilsvarende mønster for salget i dette og sidste år?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Tilføj **This Year Sales > Value** og **Last Year Sales** i kurvediagrammet. Skalaen for **Gross Margin Last Year %** er meget mindre end skalaen for **Sales**, hvilket gør det svært at sammenligne.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Hvis du vil gøre det nemmere at læse og fortolke en visual, skal du konvertere kurvediagrammet til et Kurve- og stablet søjlediagram.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Træk **Gross Margin Last Year %** fra **Kolonneværdier** til **Kurveværdier**. Der oprettes to akser i Power BI, og datasættene kan derfor skaleres forskelligt. Det kan ses ved, at den venstre akse for salg måles i dollar, mens den højre akse måles i procent.

   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Føj titler til akserne
1. Vælg ikonet med malerullen ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) for at åbne fanen Formatering.
2. Udvid indstillingerne for **Y-axis** ved at vælge den nedadvendte pil.
3. For **Y-Axis (Column)** skal du angive **Position** til **Left**, indstille **Title** til **On**, **Style** til **Show title only** og **Display** som **Millions**.

   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. Under **Y-Axis (Column)** skal du rulle ned og sikre dig, at **Show Secondary** er indstillet til **On**. Dette viser indstillingerne for formatering af kurvediagramdelen af kombinationsdiagrammet.

   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. For **Y-Axis (Line)** skal du lade **Position** forblive **Right**, aktivere **Title** til **On** og indstille **Style** til **Show title only**.

   Dit kombinationsdiagram viser nu to akser, som begge har en titel.

   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

6. Du har mulighed for at tilpasse tekstens skrifttype, størrelse og farve og ændre andre formatindstillinger for at forbedre diagrammets visning og læsbarhed.

Nu kan du f.eks.:

* [Tilføje kombinationsdiagrammet som et dashboardfelt](service-dashboard-tiles.md).
* [Gem rapporten](service-report-save.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Tværgående fremhævning og krydsfiltrering

Fremhævning af en kolonne eller kurve i kombinationsdiagrammet fører til tværgående fremhævning og krydsfiltrering af andre visualiseringer på rapportsiden... og omvendt. Hvis du vil ændre denne standardfunktionsmåde, skal du bruge [visuelle interaktioner](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Næste trin

[Overblik over visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)

[Typer af visualiseringer i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
