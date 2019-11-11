---
title: Kransediagrammer i Power BI
description: Kransediagrammer i Power BI
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/11/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 4dd6f185ea7d4f4664626586f1374f67bd34f784
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73870939"
---
# <a name="doughnut-charts-in-power-bi"></a>Kransediagrammer i Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Et kransediagram ligner meget et cirkeldiagram og viser relationen mellem dele af en helhed. Den eneste forskel er, at centreret i det er tomt og giver plads til en etiket eller et ikon.

## <a name="prerequisite"></a>Forudsætning

I dette selvstudium bruges [PBIX-filen med eksemplet Detailhandelsanalyse](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Vælg **Fil** > **Åbn** i øverste venstre afsnit af menulinjen
   
2. Find din kopi af **PBIX-filen med eksemplet Detailhandelsanalyse**

1. Åbn **PBIX-filen med eksemplet Detailhandelsanalyse** i rapportvisning ![ikon for skærmbillede af rapportvisning.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Markér ![Skærmbillede af den gule fane.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) for at tilføje en ny side.


## <a name="create-a-doughnut-chart"></a>Opret et kransediagram

1. Start på en tom rapportside, og vælg **Salg** \> **Sidste års salg** i ruden Felter.  
   
3. Vælg ikonet for kransediagram ![ikon for kransediagram](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) i ruden Visualiseringer for at konvertere dit liggende søjlediagram til et kransediagram. Hvis **Last Year Sales** ikke findes i området **Værdier**, skal du trække det derhen.
     
   ![Visualiseringsrude med kransediagram valgt](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Vælg **Element** \> **Kategori** for at føje det til området **Forklaring**. 
     
    ![kransediagram ud for ruden Felter](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Du kan eventuelt [tilpasse størrelsen og farven på diagrammets tekst](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Summen af kransediagrammets værdier skal give 100 %.
* Er der for mange kategorier, er det svært at læse og fortolke diagrammet.
* Kransediagrammer er bedst egnet til at sammenligne en bestemt del med helheden og ikke sammenligne de enkelte dele med hinanden. 

## <a name="next-steps"></a>Næste trin
[Tragtformede diagrammer i Power BI](power-bi-visualization-funnel-charts.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)


