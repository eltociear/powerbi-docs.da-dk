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
ms.date: 06/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c5838d12351c06d0a76a975c9c473b1c00856d97
ms.sourcegitcommit: 90aa7ea5fcc7cf0fd7f6c3c1efeff5f27e8ef0dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/20/2019
ms.locfileid: "67299289"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>Del 1, Føj visualiseringer til en rapport i Power BI

I denne artikel får du en hurtig introduktion til at oprette en visualisering i en rapport. Det gælder for både Power BI-tjenesten og Power BI Desktop. Hvis det drejer sig om mere avanceret indhold, kan du [se del 2](power-bi-report-add-visualizations-ii.md) i denne serie. Se Amanda demonstrere nogle få metoder til at oprette, redigere og formatere visualiseringer på et rapportcanvas. Prøv det derefter selv ved hjælp af [Sales and Marketing-eksemplet](../sample-datasets.md) for at oprette din egen rapport.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="open-a-report-and-add-a-new-page"></a>Åbn en rapport, og tilføj en ny side

1. Åbn en [rapport i redigeringsvisning](../service-interact-with-a-report-in-editing-view.md).

    Dette selvstudium er baseret på [Sales and Marketing-eksemplet](../sample-datasets.md).

1. Hvis ruden **Felter** ikke vises, skal du vælge pileikonet for at åbne den.

   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)

1. Tilføj en tom side i rapporten.

## <a name="add-visualizations-to-the-report"></a>Tilføj visualiseringer i rapporten

1. Opret en visualisering ved at vælge et felt i ruden **Felter**.

    Start med et numerisk felt som **SalesFact** > **Sales $** . Power BI opretter et søjlediagram med en enkelt kolonne.

    ![Skærmbillede af et søjlediagram med en enkelt kolonne.](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)

    Eller du kan starte med et kategorifelt, f.eks **Name** eller **Product**. Power BI opretter en tabel og føjer dette felt til området **Values**.

    ![GIF-billede af en person, der vælger Product og derefter kategori for at oprette en tabel.](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)

    Du kan også starte med et geografisk felt, f.eks. **Geo** > **City**. Power BI og Bing Maps opretter en kortvisualisering.

    ![Skærmbillede af en kortvisualisering.](media/power-bi-report-add-visualizations-i/power-bi-map.png)

1. Opret en visualisering, og ret derefter typen. Vælg **Product** > **Category** og derefter **Product** > **Count of Product** for at tilføje dem begge i området **Values**.

   ![Skærmbillede af ruden Felter, hvor området Values er fremhævet.](media/power-bi-report-add-visualizations-i/part1table1.png)

1. Ret visualiseringen til et søjlediagram ved at vælge ikonet **Stablet søjlediagram**.

   ![Skærmbillede af ruden med visualiseringer, hvor ikonet Stablet søjlediagram er fremhævet.](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)

1. Når du opretter visualiseringer i din rapport, kan du [fastgøre dem til dit dashboard](../service-dashboard-pin-tile-from-report.md). Vælg ikonet med tegnestiftikonet for at fastgøre visualiseringen ![Skærmbillede af tegnestiftikon](media/power-bi-report-add-visualizations-i/pinnooutline.png).

   ![Skærmbillede af en visualisering af et søjlediagram, hvor tegnestiftikonet er fremhævet.](media/power-bi-report-add-visualizations-i/part1pin1.png)
  
## <a name="next-steps"></a>Næste trin

 Fortsæt til:

* [Del 2: Føj visualiseringer til en rapport i Power BI](power-bi-report-add-visualizations-ii.md)

* [Interagere med visualiseringerne](../consumer/end-user-reading-view.md) i rapporten.

* [Gøre endnu mere med dine visualiseringer](power-bi-report-visualizations.md).

* [Gemme din rapport](../service-report-save.md).
