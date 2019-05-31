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
ms.date: 09/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 079494a47452ca0ca043032f78fa35c7d1755d11
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61068086"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Radiale målerdiagrammer i Power BI
Et radialt målerdiagram har en cirkulær bue og viser en enkelt værdis status i forhold til et mål/en KPI.  Målet, eller målværdien, er repræsenteret med en streg (nål). Statussen mod målet repræsenteres med en skygge.  Den værdi, der repræsenterer statussen, vises med fed i buen. Alle de mulige værdier er fordelt langs buen fra minimumværdien (længst til venstre) til maksimumværdien (længst til højre).

I eksemplet nedenfor spores det gennemsnitlige salg pr. måned for salgsteamet hos en bilforhandler. Målet er 140, hvilket repræsenteres med den sorte nål.  Det mindst mulige salg er 0, og vi har angivet maksimum til 200.  Den blå farve viser, at vi i øjeblikket er på 120 salg i denne måned. Der er heldigvis stadig en uge til at nå målet.

![](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

## <a name="when-to-use-a-radial-gauge"></a>Situationer, hvor du kan bruge en radial måler
Radiale målere er fantastiske til:

* At se statussen mod et mål.
* Repræsentere en percentil måling, for eksempel en KPI.
* Vise statussen for en enkelt måling.
* Vise oplysninger, der er hurtige at skimme og forstå.

### <a name="prerequisites"></a>Forudsætninger
 - Power BI-tjenesten eller Power BI Desktop
 - Projektmappen Financial Sample: [download eksemplet direkte](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>Opret en grundlæggende radial måler
Denne vejledning bruger Power BI-tjenesten. Følg med ved at logge på Power BI og åbne filen Excel Financial Sample.  

Eller du kan se med, når Will viser, hvordan du opretter visualiseringer med en enkelt måling: målere, kort og KPI'er.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

### <a name="step-1-open-the-financial-sample-excel-file"></a>Trin 1: Åbn filen Financial Sample i Excel
1. [Download Excel-filen med eksemplet Financial Sample](../sample-financial-download.md), hvis du ikke allerede har gjort det. Husk, hvor du gemmer den.

2. Åbn filen i ***Power BI-tjeneste*** ved at vælge **Hent data\> Filer**, og gå til det sted, hvor du gemte filen. Vælg **Importér**. Financial Sample-filen tilføjes i dit arbejdsområde som et datasæt.

3. Vælg **Financial Sample** på indholdslisten **Datasæt** for at åbne det i udforskningstilstand.

    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>Trin 2: Opret en måler for at spore bruttoomsætningen (Gross Sales)
1. Vælg **Gross Sales** i ruden **Felter**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)
2. Ret aggregeringen til **Gennemsnit**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)
3. Vælg målerikonet ![](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) for at konvertere søjlediagrammet til en måler.
   
   Som standard vil Power BI oprette et målerdiagram, hvor den aktuelle værdi (i dette tilfælde Gennemsnit af Gross Sales) antages at være midtvejspunktet for måleren. Da gennemsnittet af Gross Sales er 182,76tusind, er startværdien (Minimum) indstillet til 0, og slutværdien (Maksimum) er indstillet til det dobbelte af den aktuelle værdi.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

### <a name="step-3-set-a-target-value"></a>Trin 3: Indstil en målværdi
1. Træk **COGS** til området **Målværdi**.
2. Ret aggregeringen til **Gennemsnit**.
   Power BI tilføjer en nål, der repræsenterer målværdien **145,48tusind**. Bemærk, at vi er over vores mål.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)
   
   > [!NOTE]
   > Du kan også angive en målværdi manuelt.  Se "Brug formateringsindstillinger til manuelt at angive værdierne Minimum, Maksimum og Mål" nedenfor.
   > 
   > 

### <a name="step-4-set-a-maximum-value"></a>Trin 4: Angiv en maksimumværdi
På trin 2 brugte Power BI feltet Værdi til automatisk at angive en minimum- (start) og maksimumværdi (slut).  Men, hvordan kan du angive din egen maksimumværdi?  Lad os antage, at i stedet for at anvende det dobbelte af den aktuelle værdi som maksimumværdi, vil du anvende det højeste tal i Gross Sales fra datasættet? 

1. Træk **Gross Sales** fra listen **Felter** til **Maksimumværdi**.
2. Ret aggregeringen til **Maksimum**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)
   
   Måleren gentegnes med en ny slutværdi, som er på bruttoomsætningen 1,21 millioner.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>Trin 5: Gem din rapport
1. [Gem rapporten](../service-report-save.md).
2. [Tilføj målerdiagram som et dashboardfelt](../service-dashboard-pin-tile-from-report.md). 

## <a name="use-formatting-options-to-manually-set-minimum-maximum-and-target-values"></a>Brug formateringsindstillinger til manuelt at angive værdierne Minimum, Maksimum og Mål
1. Fjern **Maks. af Gross Sales** fra **Maksimumværdi**.
2. Åbn formateringsruden ved at vælge ikonet med malerullen.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)
3. Udvid **Målerakse**, og angiv værdier for **Min** og **Maks**.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)
4. Fjern den aktuelle målværdi ved at fjerne afkrydsningsfeltet ud for **COGS**.
   
    ![](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)
5. Når feltet **Mål** vises under **Målerakse**, skal du angive en værdi.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)
6. Fortsæt eventuelt med at formatere dit målerdiagram.

## <a name="next-step"></a>Næste trin

[Målere i Power BI](power-bi-visualization-kpi.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
