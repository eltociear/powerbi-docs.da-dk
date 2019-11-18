---
title: Del 1, Føj visualiseringer til en rapport i Power BI
description: Del 1, Føj visualiseringer til en rapport i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e25db5ab57e3a52ffc08020dc980553e515256bf
ms.sourcegitcommit: 2a61d8b1e2707a24fe1284a8a4034b11c3999842
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/29/2019
ms.locfileid: "73048893"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>Del 1, Føj visualiseringer til en rapport i Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

I denne artikel får du en hurtig introduktion til at oprette en visualisering i en rapport. Det gælder for både Power BI-tjenesten og Power BI Desktop. Hvis det drejer sig om mere avanceret indhold, kan du [se del 2](power-bi-report-add-visualizations-ii.md) i denne serie. Se Amanda demonstrere nogle få metoder til at oprette, redigere og formatere visualiseringer på et rapportcanvas. Prøv det derefter selv ved hjælp af [Sales and Marketing-eksemplet](../sample-datasets.md) for at oprette din egen rapport.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Forudsætninger

I dette selvstudium bruges [PBIX-filen til Salg og marketing](http://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix).

1. Vælg **Fil** > **Åbn** på menulinjen i øverste venstre afsnit af Power BI Desktop
   
2. Find din kopi af **PBIX-filen med eksemplet til Salg og marketing**

1. Åbn **PBIX-filen med eksemplet til Salg og marketing** i rapportvisning ![ikon for skærmbillede af rapportvisning.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Markér ![Skærmbillede af den gule fane.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) for at tilføje en ny side.

## <a name="add-visualizations-to-the-report"></a>Tilføj visualiseringer i rapporten

1. Opret en visualisering ved at vælge et felt i ruden **Felter**.

    Start med et numerisk felt som **Sales** > **TotalSales**. Power BI opretter et søjlediagram med en enkelt kolonne.

    ![Skærmbillede af et søjlediagram med en enkelt kolonne.](media/power-bi-report-add-visualizations-i/power-bi-column-chart.png)

    Eller du kan starte med et kategorifelt, f.eks **Name** eller **Product**. Power BI opretter en tabel og føjer dette felt til området **Values**.

    ![Skærmbillede af en tabel med fire kategorier](media/power-bi-report-add-visualizations-i/power-bi-product.png)

    Du kan også starte med et geografisk felt, f.eks. **Geo** > **City**. Power BI og Bing Maps opretter en kortvisualisering.

    ![Skærmbillede af en kortvisualisering.](media/power-bi-report-add-visualizations-i/power-bi-maps.png)

## <a name="change-the-type-of-visualization"></a>Skift visualiseringstype

 Opret en visualisering, og ret derefter typen. 
 
 1. Vælg **Product** > **Category** og derefter **Product** > **Count of Product** for at tilføje dem begge i området **Values**.

    ![Skærmbillede af ruden Felter, hvor området Values er fremhævet.](media/power-bi-report-add-visualizations-i/power-bi-create-visual.png)

1. Ret visualiseringen til et søjlediagram ved at vælge ikonet **Stablet søjlediagram**.

   ![Skærmbillede af ruden med visualiseringer, hvor ikonet Stablet søjlediagram er fremhævet.](media/power-bi-report-add-visualizations-i/power-bi-convert.png)

1. Hvis du vil ændre den måde, visualiseringen sorteres på, skal du vælge **Flere handlinger** (...).  Brug sorteringsindstillingerne til at ændre sorteringsrækkefølgen (stigende eller faldende), og rediger den kolonne, der bruges til at sortere (**Sorteret efter**).

   ![Skærmbillede af rullelisten Flere handlinger.](media/power-bi-report-add-visualizations-i/power-bi-sort.png)
  
## <a name="next-steps"></a>Næste trin

 Fortsæt til:

* [Del 2: Føj visualiseringer til en rapport i Power BI](power-bi-report-add-visualizations-ii.md)

* [Interagere med visualiseringerne](../consumer/end-user-reading-view.md) i rapporten.

