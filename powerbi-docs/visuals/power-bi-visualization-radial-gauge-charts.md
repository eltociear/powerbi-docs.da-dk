---
title: Radiale målerdiagrammer i Power BI
description: Radiale målerdiagrammer i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6Epqa
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8b0db9aebe72d54aa464ec012e614ae0ec5bc723
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390638"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Radiale målerdiagrammer i Power BI

Et radialt målerdiagram har en cirkulær bue og viser en enkelt værdis status i forhold til et mål eller en KPI (Key Performance Indicator). Linjen (eller *nålen*) repræsenterer målet eller målværdien. Skyggen repræsenterer status i forhold til målet. Værdien i buen repræsenterer statusværdien. Power BI spreder alle de mulige værdier langs buen fra minimumværdien (længst til venstre) til maksimumværdien (længst til højre).

![Skærmbillede af radial måler.](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

I dette eksempel er du en bilhandler, der sporer det gennemsnitlige salg pr. måned for salgsteamet. Nålen repræsenterer et salgsmål på 140 biler. Det mindst mulige gennemsnitssalg er 0, og maksimum er 200.  Den blå farve viser, at teamet i øjeblikket er på et salg på 120 i denne måned. Der er heldigvis stadig en uge til at nå målet.

Se med, når Will viser, hvordan du opretter visualiseringer med en enkelt måling: målere, kort og KPI'er.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="when-to-use-a-radial-gauge"></a>Situationer, hvor du kan bruge en radial måler

Radiale målere er fantastiske til:

* at vise status i forhold til et mål

* at repræsentere en måling i procenter, f.eks. KPI

* at vise tilstanden for en enkelt måling.

* Viser oplysninger, du hurtigt kan gennemse og forstå.

## <a name="prerequisites"></a>Forudsætninger

* Power BI-tjenesten eller Power BI Desktop

* Projektmappen Financial Sample: [download eksemplet direkte](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>Opret en grundlæggende radial måler

Denne vejledning bruger Power BI-tjenesten. Følg med ved at logge på Power BI og åbne filen Excel Financial Sample.

### <a name="step-1-open-the-financial-sample-excel-file"></a>Trin 1: Åbn filen Financial Sample i Excel

1. Download [Excel-filen Financial Sample](../sample-financial-download.md), hvis du ikke allerede har gjort det. Husk, hvor du gemmer den.

1. Vælg **Hent data** > **Filer** i Power BI-tjenesten.

1. Vælg **Lokal fil**, og gå til den eksempelfilens placering.

1. Vælg **Importér**. Power BI tilføjer Financial Sample-filen i dit arbejdsområde som et datasæt.

1. På indholdslisten **Datasæt** skal du vælge ikonet **Opret rapport** for **Financial Sample**.

    ![Skærmbillede af listen over datasæt med en pil, der peger på ikonet Opret rapport for Financial Sample.](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>Trin 2: Opret en måler for at spore bruttoomsætningen (Gross Sales)

Da du valgte ikonet **Opret rapport** i det sidste afsnit, oprettede Power BI en tom rapport i redigeringsvisning.

1. Vælg **Gross Sales** i ruden **Felter**.

   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)

1. Ret aggregeringen til **Gennemsnit**.

   ![Skærmbillede af ruden Felter, hvor Gross Sales og aggregeringen Gennemsnit er fremhævet.](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)

1. Vælg målerikonet ![Skærmbillede af målerikonet.](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) for at konvertere søjlediagrammet til et målerdiagram.

    ![Skærmbillede af målerdiagrammet.](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

    Afhængigt af, hvornår du henter filen **Financial Sample**, får du muligvis vist tal, der ikke stemmer overens med disse tal.

    > [!TIP]
    > Som standard opretter Power BI et målerdiagram, hvor det antages, at den aktuelle værdi (i dette tilfælde **Gennemsnit af Gross Sales**) er midtvejspunktet for måleren. Da værdien i **Gennemsnit af Gross Sales** er 182,76tusind, er startværdien (Minimum) indstillet til 0, og slutværdien (Maksimum) er indstillet til det dobbelte af den aktuelle værdi.

### <a name="step-3-set-a-target-value"></a>Trin 3: Indstil en målværdi

1. Træk **COGS** fra ruden **Felter** til området **Målværdi**.

1. Ret aggregeringen til **Gennemsnit**.

   Power BI tilføjer en nål, der repræsenterer målværdien **145,48tusind**.

   ![Skærmbillede af målerdiagrammet, hvor vareforbruget er tilføjet.](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)

    Bemærk, at vi er over vores mål.

   > [!NOTE]
   > Du kan også angive en målværdi manuelt. Se afsnittet [Brug manuelle formateringsindstillinger til at angive værdierne for Minimum, Maksimum og Mål](#use-manual-format-options-to-set-minimum-maximum-and-target-values).

### <a name="step-4-set-a-maximum-value"></a>Trin 4: Angiv en maksimumværdi

I trin 2 brugte Power BI feltet **Værdi** til automatisk at angive minimum- og maksimumværdier. Hvordan kan du angive din egen maksimumværdi? Lad os antage, at i stedet for at anvende det dobbelte af den aktuelle værdi som maksimumværdi vil du anvende det højeste tal i Gross Sales fra datasættet.

1. Træk **Gross Sales** fra ruden **Felter** til området **Maksimumværdi**.

1. Ret aggregeringen til **Maksimum**.

   ![Skærmbillede af ruden Felter, hvor Gross Sales og aggregeringen Maksimum er fremhævet.](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)

   Måleren gentegnes med en ny slutværdi, som er på bruttoomsætningen 1,21 millioner.

   ![Skærmbillede af det færdige målerdiagram.](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>Trin 5: Gem din rapport

1. [Gem rapporten](../service-report-save.md).

1. [Tilføj målerdiagram som et dashboardfelt](../service-dashboard-pin-tile-from-report.md). 

## <a name="use-manual-format-options-to-set-minimum-maximum-and-target-values"></a>Brug manuelle formateringsindstillinger til at angive værdierne for Minimum, Maksimum og Mål

1. Fjern **Maks. af Gross Sales** fra **Maksimumværdi**.

1. Vælg malerrulleikonet for at åbne ruden **Formatér**.

   ![Skærmbillede af målerdiagrammet og ruden Formatér, hvor malerrulleikonet er fremhævet.](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)

1. Udvid **Målerakse**, og angiv værdier for **Min.** og **Maks.**

    ![Skærmbillede af indstillingerne for måleraksen.](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)

1. Fjern markeringen i indstillingen **COGS** i ruden **Felter** for at fjerne målværdien.

    ![Skærmbillede af indstillingen COGS, hvor markeringen er fjernet.](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)

1. Når feltet **Mål** vises under **Målerakse**, skal du angive en værdi.

     ![Skærmbillede af indstillingerne for måleraksen, hvor Mål er fremhævet.](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)

1. Fortsæt eventuelt med at formatere dit målerdiagram.

Når du er færdig med disse trin, har du et målerdiagram, der ser nogenlunde sådan ud:

![Skærmbillede af det endelige målerdiagram.](media/power-bi-visualization-radial-gauge-charts/power-bi-final.png)

## <a name="next-step"></a>Næste trin

* [KPI-visualiseringer (Key Performance Indicator)](power-bi-visualization-kpi.md)

* [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)