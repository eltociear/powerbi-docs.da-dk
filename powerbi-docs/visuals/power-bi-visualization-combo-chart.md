---
title: Kombinationsdiagram i Power BI
description: Dette selvstudium om kombinationsdiagrammer forklarer, hvornår de bruges, og hvordan de oprettes i Power BI-tjenesten og Desktop.
author: mihart
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 11be774515552d10846b51863eda6c155b92b57f
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2020
ms.locfileid: "75758077"
---
# <a name="create-and-use-combo-charts-in-power-bi"></a>Opret og brug kombinationsdiagrammer i Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

I Power BI er et kombinationsdiagram en enkelt visualisering, der kombinerer et kurvediagram og et søjlediagram. Ved at kombinere disse to diagrammer kan du hurtigere sammenligne dine data.

Kombinationsdiagrammer kan have en eller to Y-akser.

## <a name="when-to-use-a-combo-chart"></a>Hvornår skal et kombinationsdiagram bruges
Kombinationsdiagrammer er et fantastisk valg i følgende tilfælde:

* Når du har et kurvediagram og et søjlediagram med den samme X-akse.
* Til at sammenligne flere målinger med forskellige værdiintervaller.
* Til at illustrere sammenhængen mellem to målinger i én visualisering.
* Til at kontrollere, om en måling opfylder målet, der er defineret af en anden måling
* Til at spare plads på lærredet.

### <a name="prerequisites"></a>Forudsætninger
I dette selvstudium bruges [PBIX-filen med eksemplet Detailhandelsanalyse](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Vælg **Fil** > **Åbn** i øverste venstre afsnit af menulinjen
   
2. Find din kopi af **PBIX-filen med eksemplet Detailhandelsanalyse**

1. Åbn **PBIX-filen med eksemplet Detailhandelsanalyse** i rapportvisning ![ikon for skærmbillede af rapportvisning.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Markér ![Skærmbillede af den gule fane.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) for at tilføje en ny side.



## <a name="create-a-basic-single-axis-combo-chart"></a>Opret et grundlæggende kombinationsdiagram med én akse
Se, hvordan Will opretter et kombinationsdiagram ved hjælp af salgs- og marketingeksemplet.
   > [!NOTE]
   > I denne video bruges en ældre version af Power BI Desktop.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a>

1. Start på en tom rapportside, og opret et søjlediagram, der viser dette års salg og bruttomargen pr. måned.

    a.  I ruden Felter skal du vælge **Sales** \> **This Year Sales** > **Value**.

    b.  Træk **Sales** \> **Gross Margin This Year** til beholderen **Value**.

    c. Vælg **Time**  \> **FiscalMonth** for at føje elementet til beholderen **Axis**.

    ![eksempel på selvstudium med kombinationsdiagram](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Vælg **Flere indstillinger** (...) i øverste højre hjørne af visualiseringen, og vælg **Sortér efter > FiscalMonth**. Hvis du vil ændre sorteringsrækkefølgen, skal du vælge ellipsen igen og vælge enten **Sortér stigende** eller **Sortér faldende**. I dette eksempel bruger vi **Sortér stigende**.

6. Konvertér søjlediagrammet til et kombinationsdiagram. Der er to kombinationsdiagrammer: **Kurvediagram og stablet søjlediagram** og **Kurvediagram og grupperet søjlediagram**. Vælg søjlediagrammet, og vælg derefter **Line and clustered column chart** fra fanen **Visualizations**.

    ![eksempel på konvertering af kombinationsdiagram](media/power-bi-visualization-combo-chart/converttocombo-new2.png)
7. Fra ruden **Felter** kan du derefter trække **Sales** \> **Last Year Sales** til beholderen **Line Values**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Dit kombinationsdiagram bør ligne dette:

   ![eksempel på udført kombinationsdiagram](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Opret et kombinationsdiagram med to akser
I denne opgave skal vi sammenligne bruttomargen og salg.

1. Opret et nyt kurvediagram, der sporer **Bruttoavancen sidste år %** efter **FiscalMonth**. Vælg ellipsen for at sortere den efter **måned** og **stigende**.  
I januar var BM% på 35 %, den steg til 45 % i april, faldt i juli og steg igen i august. Kan vi se et tilsvarende mønster for salget i dette og sidste år?

   ![eksempel på salg i kombinationsdiagram](media/power-bi-visualization-combo-chart/combo1-new.png)
2. Tilføj **This Year Sales > Value** og **Last Year Sales** i kurvediagrammet. Skalaen for **Gross Margin Last Year %** er meget mindre end skalaen for **Sales**, hvilket gør det svært at sammenligne.      

   ![eksempel på flatline i kombinationsdiagram](media/power-bi-visualization-combo-chart/flatline-new.png)
3. Hvis du vil gøre det nemmere at læse og fortolke en visual, skal du konvertere kurvediagrammet til et Kurve- og stablet søjlediagram.

   ![eksempel på konvertering til kombinationsdiagram](media/power-bi-visualization-combo-chart/converttocombo-new.png)

4. Træk **Gross Margin Last Year %** fra **Kolonneværdier** til **Kurveværdier**. Der oprettes to akser i Power BI, og datasættene kan derfor skaleres forskelligt. Det kan ses ved, at den venstre akse for salg måles i dollar, mens den højre akse måles i procent. Og vi kan se svaret på vores spørgsmål. Ja, vi kan se et lignende mønster.

   ![eksempel på klynge i kombinationsdiagram](media/power-bi-visualization-combo-chart/power-bi-clustered-combo.png)    

## <a name="add-titles-to-the-axes"></a>Føj titler til akserne
1. Vælg malerrulleikonet 
1. ![malerrulleikon](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) for at åbne formateringsruden.
1. Udvid indstillingerne for **Y-axis** ved at vælge den nedadvendte pil.
1. For **Y-aksen (søjle)** skal du angive **Placering** til **Venstre**, angive **Titel** til **Til**, **Type** til **Vis kun titel** og **Vis enheder** som **Millioner**.

   ![eksempel på kombinationsdiagram med y åben](media/power-bi-visualization-combo-chart/power-bi-open-y.png)
4. Under **Y-akse (søjle)** skal du rulle ned, indtil du kan se **Vis sekundær**. Da der er så mange muligheder for Y-akserne, skal du muligvis bruge begge rullepaneler. I afsnittet Vis sekundær vises indstillingerne for formatering af kurvediagramdelen af kombinationsdiagrammet.

   ![eksempel på sekundær i kombinationsdiagram](media/power-bi-visualization-combo-chart/power-bi-secondary.png)
5. For **Y-Axis (Line)** skal du lade **Position** forblive **Right**, aktivere **Title** til **On** og indstille **Style** til **Show title only**.

   Dit kombinationsdiagram viser nu to akser, som begge har en titel.

   ![eksempel på titler i kombinationsdiagram](media/power-bi-visualization-combo-chart/power-bi-2-titles.png)

6. Du har mulighed for at tilpasse tekstens skrifttype, størrelse og farve og ændre andre formatindstillinger for at forbedre diagrammets visning og læsbarhed.

Nu kan du f.eks.:

* [Tilføje kombinationsdiagrammet som et dashboardfelt](../service-dashboard-tiles.md).
* [Gem rapporten](../service-report-save.md).
* [Gør rapporten tilgængelig for personer med handicap](../desktop-accessibility.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Tværgående fremhævning og krydsfiltrering

Fremhævning af en kolonne eller kurve i kombinationsdiagrammet fører til tværgående fremhævning og krydsfiltrering af andre visualiseringer på rapportsiden... og omvendt. Hvis du vil ændre denne standardfunktionsmåde, skal du bruge [visuelle interaktioner](../service-reports-visual-interactions.md).

## <a name="next-steps"></a>Næste trin

[Kransediagrammer i Power BI](power-bi-visualization-doughnut-charts.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
