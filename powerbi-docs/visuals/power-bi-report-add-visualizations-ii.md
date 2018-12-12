---
title: Del 2, Føj visualiseringer til en rapport i Power BI
description: Del 2, Føj visualiseringer til en rapport i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 01051ab47304713fe3cf0f9128f5cd99af58bffe
ms.sourcegitcommit: e17fc3816d6ae403414cf5357afbf6a492822ab8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/04/2018
ms.locfileid: "52830211"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>Del 2, Føj visualiseringer til en rapport i Power BI
I [Del 1](power-bi-report-add-visualizations-ii.md) oprettede du en grundlæggende visualisering ved at markere afkrydsningsfelter ud for feltnavne.  I Del 2 lærer du, hvordan du bruger træk og slip samt benytter ruderne **Felter** og **Visualiseringer** til at oprette og redigere visualiseringer.

### <a name="prerequisites"></a>Forudsætninger
- [Del 1](power-bi-report-add-visualizations-ii.md)
- Power BI Desktop – visualiseringer kan føjes til rapporter ved hjælp af Power BI-tjenesten eller Power BI Desktop. I dette selvstudium bruges Power BI Desktop. 
- [Eksempel på detailhandelsanalyse](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="create-a-new-visualization"></a>Opret en ny visualisering
I dette selvstudium gennemgår vi vores Retail Analysis-datasæt og opretter nogle få vigtige visualiseringer.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Åbn en rapport, og tilføj en ny tom side.
1. Åbn .PBIX-filen med Eksempel på detailhandelsanalyse i Power BI Desktop. 
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-desktop.png)   

2. Tilføj en ny side ved at vælge det gule plusikon nederst på lærredet.

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Tilføj en visualisering, som indeholder en oversigt over dette års salg sammenlignet med sidste år.
1. I tabellen **Sales** skal du vælge **This Year Sales** > **Value** og **Last Year Sales**. Power BI opretter et søjlediagram.  Dette er lidt interessant, og du vil gerne se mere. Hvordan ser salget ud pr. måned?  
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-barchart.png)
2. I tabellen Tid skal du trække **Regnskabsmåned** ind i området **Akse**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-month.png)
3. [Ret visualiseringen](power-bi-report-change-visualization-type.md) til et områdediagram.  Der er mange visualiseringstyper at vælge imellem. Se [beskrivelser af hver, tips til bedste praksis og selvstudier](power-bi-visualization-types-for-reports-and-q-and-a.md) for at få hjælp til at vælge, hvilken type du vil bruge. Vælg ikonet Områdediagram ![](media/power-bi-report-add-visualizations-ii/power-bi-areachart.png) i ruden Visualiseringer.
4. Sortér visualiseringen ved at vælge ellipsen og vælge **Sortér efter Regnskabsmåned**.
5. [Tilpas størrelsen af visualiseringen](power-bi-visualization-move-and-resize.md) ved at vælge visualiseringen, tage fat i en af konturcirklerne og trække. Gør den bred nok, så rullepanelet fjernes, men lille nok, så der er plads nok til at tilføje endnu en visualisering.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Gem rapporten](../service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Tilføj en kortvisualisering med salg efter placering
1. I tabellen **Store** skal du vælge **Område**. Power BI genkender, at Område er en placering, og opretter en visualisering med et kort.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map.png)
2. Træk **Total Stores** ind i området Størrelse.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map2.png)
3. Tilføj en forklaring.  Hvis du vil se dataene efter butiksnavn, skal du trække **Chain** ind i området Forklaring.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-legend.png)

## <a name="next-steps"></a>Næste trin
* Få mere at vide om [Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md).  
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

