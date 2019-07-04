---
title: Tilpas egenskaberne for X- og Y-aksen
description: Tilpas egenskaberne for X- og Y-aksen
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3bfe84acdf73fcb5ace791c9a84943262d0f73ab
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390096"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>Tilpas egenskaberne for X- og Y-aksen

I dette selvstudium lærer, hvordan du kan tilpasse X- og Y-aksen for dine visualiseringer på mange forskellige måder. Ikke alle visualiseringer har akser. Cirkeldiagrammer har f.eks. ikke akser. Og indstillinger for tilpasning varierer fra visualisering til visualisering. Der er for mange indstillinger til, at de kan dækkes i en enkelt artikel, så du får vist nogle af de aksetilpasninger, der oftest bruges. Samtidig lærer du at bruge fanen **Formatér** for visualiseringer på dit rapportlærred i Power BI.  

> [!NOTE]
> Oplysningerne på denne side er relevante for både Power BI-tjenesten og Power BI Desktop. Disse tilpasninger, som vises, når du vælger ikonet **Formatér** (ikonet med malerrullen ![Skærmbillede af malerrulleikonet](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)), findes også i Power BI Desktop.

Se, hvordan Amanda tilpasser sine X- og Y-akser. Hun viser de forskellige måder, sammenkædning kan styres på, når der bruges detailudledning og færre detaljer.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Forudsætninger

- Power BI-tjenesten

- Rapporten Retail Analysis Sample

## <a name="customize-visualization-x--and-y-axes-in-reports"></a>Tilpas visualisering af X- og Y-akser i rapporter

Hvis du vil følge med, skal du logge på [Power BI-tjenesten](https://app.powerbi.com) og åbne rapporten [Retail Analysis Sample](../sample-datasets.md) i visningen [Rediger rapport](../service-interact-with-a-report-in-editing-view.md).

### <a name="create-a-stacked-column-chart-visualization"></a>Opret en visualisering af et stablet søjlediagram

Før du kan tilpasse din visualisering, skal du oprette den.

1. Udvid **Mit arbejdsområde** i Power BI-tjenesten.

1. Rul ned, og vælg **Retail Analysis Sample** på listen over **datasæt**.

1. Vælg ikonet for stablet søjlediagram i ruden **Visualiseringer**.

    ![Skærmbillede af ruden Visualiseringer og et tomt stablet søjlediagram](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-stacked-column-chart.png)

1. Hvis du vil angive værdierne på X-aksen, skal du gå til ruden **Felter** og vælge **Time** > **FiscalMonth**.

1. Hvis du vil angive værdier for Y-aksen, skal du gå til ruden **Felter** og vælge **Sales** > **Last Year Sales** og **Sales** > **This Year Sales** > **Value**.

    ![Skærmbillede af det udfyldte stablede søjlediagram.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

### <a name="customize-the-x-axis"></a>Tilpas X-aksen

Du kan nu tilpasse X-aksen.

1. I ruden **Visualiseringer** skal du vælge **Formatér** (ikonet med malerrullen ![Skærmbillede af malerrulleikonet](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) for at få vist indstillinger for tilpasning.

1. Udvid indstillingerne under X-akse.

   ![Skærmbillede af indstillingerne for X-aksen.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)

1. Flyt skyderen for **X-aksen** til **Til**.

    ![Skærmbillede af skyderen slået til.](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    Du kan for eksempel vælge at slå X-aksen fra, hvis du vil have mere plads til data.

1. Formatér tekstfarven, tekststørrelsen og skrifttypen:

    - **Farve**: Vælg sort

    - **Tekststørrelse**: Skriv *14*

    - **Skrifttypefamilie**: Vælg **Arial Black**

1. Skub indstillingen **Titel** til **Til** for at få vist navnet på X-aksen. I dette tilfælde er det **FiscalMonth**.

1. Formatér tekstfarven, tekststørrelsen og skrifttypen:

    - **Titelfarve**: Vælg orange

    - **Aksetitel**: Skriv *Fiscal Month*

    - **Tekststørrelse på titel**: Skriv *21*

Når du er færdig med tilpasningerne, ser dit stablede søjlediagram nogenlunde sådan ud:

![Skærmbillede af det tilpassede stablede søjlediagram.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

Gem de ændringer, du har foretaget, og gå til næste sektion.

Hvis du vil genindlæse alle ændringerne, skal du vælge **Vend tilbage til standard** nederst i tilpasningsruden **X-akse**.

### <a name="customize-the-y-axis"></a>Tilpas Y-aksen

Derefter skal du tilpasse Y-aksen.

1. Udvid indstillingerne under Y-akse.

   ![Skærmbillede af indstillingerne for Y-aksen.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

1. Flyt skyderen for **Y-aksen** til **Til**.  

    ![Skærmbillede af skyderen slået til.](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    Du kan for eksempel vælge at slå Y-aksen fra, hvis du vil frigøre mere plads til data.

1. Angiv **Placering** for Y-aksen til **Højre**.

1. Formatér tekstfarven, tekststørrelsen og skrifttypen:

    - **Farve**: Vælg sort

    - **Tekststørrelse**: Skriv *14*

    - **Skrifttypefamilie**: Vælg **Arial Black**

1. Angiv **Vis enheder** til **Millioner** og **Værdi for antal decimaler** til *0*.

1. Denne visualisering bliver ikke bedre, hvis du viser titlen på Y-aksen, så lad **Titel** være slået **Fra**.  

1. Lad os få gitterlinjerne til at skille sig mere ud ved at ændre farven og øge penselstrøgsbredden:

    - **Farve**: Vælg mørkegrå

    - **Penselstrøgsbredde**: Skriv *2*

Efter alle disse tilpasninger bør dit kolonnediagram se ud som følgende:

![Skærmbillede af diagrammet med den tilpassede Y-akse.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Tilpas visualiseringer med to Y-akser

Start med at oprette et kombinationsdiagram, der viser, hvordan antallet af butikker påvirker salget. Det er det samme diagram, som blev oprettet i [Selvstudium med kombinationsdiagram](power-bi-visualization-combo-chart.md). Derefter skal du formatere de to Y-akser.

### <a name="create-a-chart-with-two-y-axes"></a>Opret et diagram med to Y-akser

1. Opret et nyt kurvediagram, der sporer **Sales > Gross Margin last year %** efter **Time > FiscalMonth**.

    ![Skærmbillede af det nye kurvediagram.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

    > [!NOTE]
    > Få hjælp til at sortere efter måned ved at gå til [Sortering ved hjælp af andre kriterier](../consumer/end-user-change-sort.md#other).

    I januar var procentdelen af bruttoavancen på 35 %, den nåede sit højeste i april med 45 %, faldt i juli og steg igen i august. Kan vi se et tilsvarende mønster for salget i dette og sidste år?

1. Tilføj **This Year Sales > Value** og **Last Year Sales** i kurvediagrammet.

    ![Skærmbillede af kurvediagrammet, hvor de nye data er tilføjet.](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)

    Skalaen for **Gross Margin Last Year %** (den blå streg, der kører langs gitterlinjen **0M%** ) er meget mindre end skalaen for **Sales**, hvilket gør det svært at sammenligne. Og procentsatserne på Y-aksen er vist ikke så meget værd.

1. Hvis du vil gøre det nemmere at læse og fortolke en visualisering, skal du konvertere kurvediagrammet til et kurve- og stablet søjlediagram.

   ![Skærmbillede af ruden Visualiseringer, hvor ikonet for kurvediagram og stablet søjlediagram er fremhævet.](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

1. Træk **Gross Margin Last Year %** fra **Kolonneværdier** til **Kurveværdier**.

    ![Skærmbillede af kurvediagram og stablet søjlediagram, hvor alle tre værdier vises tydeligt.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)

    Nu har du det stablede søjlediagram, som du oprettede i første afsnit, med et kurvediagram overlejret på det. Du kan evt. bruge de ting, du lærte tidligere, for at formatere skriftfarven og skriftstørrelsen for aksen.

   ![Skærmbillede af det tilpassede kurvediagram og stablede søjlediagram.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

   Power BI opretter to akser, så datasættene kan skaleres forskelligt. Den venstre akse måler dollar, og den højre akse måler procentdel.

### <a name="format-the-secondary-y-axis"></a>Formatér den sekundære Y-akse

1. I ruden **Visualiseringer** skal du vælge ikonet med malerrullen for at få vist formateringsindstillingerne.

1. Udvid indstillingerne under Y-akse.

1. Rul ned, indtil du finder indstillingen **Vis sekundær**. Kontrollér, at den er slået **Til**.

   ![Skærmbillede af indstillingen Vis sekundær.](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

1. (Valgfrit) Tilpas de to akser. Hvis du ændrer **Placering** for en af de to akser i søjlediagrammet eller aksen i kurvediagrammet, skifter de to akser side.

### <a name="add-titles-to-both-axes"></a>Føj titler til begge akser

Når en visualisering er så avanceret, hjælper det at tilføje aksetitler.  Titler hjælper dine kolleger med at forstå, hvad det er, din visualisering viser.

1. Slå **Titel** **Til** for **Y-akse (søjlediagram)** og **Y-akse (kurvediagram)** .

1. Angiv **Typografi** til **Vis kun titel** for begge.

   ![Skærmbillede af indstillingerne for Titel og Typografi.](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)

1. Dit kombinationsdiagram viser nu to akser, som begge har en titel.

   ![Skærmbillede af det tilpassede diagram med to Y-akser.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

Du kan finde flere oplysninger under [Tip og tricks til farveformatering i Power BI](service-tips-and-tricks-for-color-formatting.md).

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

Hvis X-aksen er kategoriseret som en datotype af rapportejeren, vises indstillingen **Type**, og du kan vælge mellem Fortløbende eller Efter kategori.

## <a name="next-steps"></a>Næste trin

- [Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)

- [Tilpas visualiseringernes titler, forklaringer og baggrunde](power-bi-visualization-customize-title-background-and-legend.md)

- [Introduktion til farveformatering og akseegenskaber](service-getting-started-with-color-formatting-and-axis-properties.md)

- [Grundlæggende begreber for forbrugere af Power BI-tjenesten](../consumer/end-user-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
