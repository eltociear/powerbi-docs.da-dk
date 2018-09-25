---
title: Del 1, Føj visualiseringer til en rapport i Power BI
description: Del 1, Føj visualiseringer til en rapport i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: df53cf238a52502cecb4d1f77482b7b1a09c6b7a
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545262"
---
# <a name="part-i-add-visualizations-to-a-power-bi-report"></a>Del 1, Føj visualiseringer til en rapport i Power BI
I denne artikel får du en hurtig introduktion til at oprette en visualisering i en rapport ved enten at bruge Power BI-tjenesten eller Power BI Desktop.  Hvis du vil læse om mere avanceret indhold, skal du [se Del II](power-bi-report-add-visualizations-ii.md). Se Amanda demonstrere nogle få metoder til at oprette, redigere og formatere visualiseringer på et rapportcanvas. Prøv det derefter selv ved hjælp af [Sales and Marketing-eksemplet](../sample-datasets.md) for at oprette din egen rapport.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>Åbn en rapport, og tilføj en ny side
1. Åbn en [rapport i redigeringsvisning](../consumer/end-user-reading-view.md). Dette selvstudium er baseret på [Sales and Marketing-eksemplet](../sample-datasets.md).
2. Hvis ruden Felter ikke vises, skal du vælge pilikonet for at åbne den. 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. [Tilføj en tom side i rapporten](../power-bi-report-add-page.md).

## <a name="add-visualizations-to-the-report"></a>Tilføj visualiseringer i rapporten
1. Opret en visualisering ved at vælge et felt i ruden **Felter**.  
   
   **Start med et numerisk felt** som SalesFact > Sales $. Power BI opretter et søjlediagram med en enkelt kolonne.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **Du kan også starte med et kategorifelt**, f.eks. Name eller Product: Power BI opretter en tabel og tilføjer feltet under **Værdier**.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **Du kan også starte med et geografisk felt** , f.eks. Geo > City. Power BI og Bing Maps opretter en kortvisualisering.
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. Opret en visualisering, og ret derefter typen. Vælg **Product > Category** og derefter **Product > Count of Product** for at tilføje dem begge under **Values**.
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. Ret visualiseringen til et søjlediagram ved at vælge ikonet for søjlediagrammer.
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. Når du opretter visualiseringer i din rapport, kan du [fastgøre dem til dit dashboard](../service-dashboard-pin-tile-from-report.md). Vælg ikonet med tavlenålen ![](media/power-bi-report-add-visualizations-i/pinnooutline.png) for at fastgøre visualiseringen.
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
  

## <a name="next-steps"></a>Næste trin
 Fortsætte til [Del 2: Føj visualiseringer til en Power BI-rapport](power-bi-report-add-visualizations-ii.md)
   
   [Interagere med visualiseringerne](../consumer/end-user-reading-view.md) i rapporten.
   
   [Gøre endnu mere med dine visualiseringer](power-bi-report-visualizations.md).
   
   [Gemme din rapport](../service-report-save.md).
