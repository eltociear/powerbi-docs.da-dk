---
title: "Del 2 – Føj visualiseringer til en Power BI-rapport (selvstudium)"
description: "Selvstudium: Del 2 – Føj visualiseringer til en Power BI-rapport"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 2b3f25c772a049d10bc03941db677c67c844da8b
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="part-2-add-visualizations-to-a-power-bi-report-tutorial"></a>Del 2 – Føj visualiseringer til en Power BI-rapport (selvstudium)
I [Del 1](power-bi-report-add-visualizations-ii.md) oprettede du en grundlæggende visualisering ved at markere afkrydsningsfelter ud for feltnavne.  I Del 2 lærer du, hvordan du bruger træk og slip samt benytter ruderne **Felter** og **Visualiseringer** til at oprette og redigere visualiseringer.

## <a name="create-a-new-visualization"></a>Opret en ny visualisering
I dette selvstudium gennemgår vi vores Retail Analysis-datasæt og opretter nogle få vigtige visualiseringer.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Åbn en rapport, og tilføj en ny tom side.
1. Åbn det arbejdsområde, hvor du gemte filen Retail Analysis Sample. Vælg **Retail Analysis Sample** for at åbne rapporten i Læsevisning.
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. Vælg **Rediger rapporten** for at åbne rapporten i Redigeringsvisning.
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. [Tilføj en ny side](power-bi-report-add-page.md) ved at vælge det gule plusikon nederst på canvasset.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Tilføj en visualisering, som indeholder en oversigt over dette års salg sammenlignet med sidste år.
1. I tabellen **Sales** skal du vælge **This Year Sales** > **Value** og **Last Year Sales**. Power BI opretter et søjlediagram.  Dette er lidt interessant, og du vil gerne se mere. Hvordan ser salget ud pr. måned?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. I tabellen Time skal du trække **Måned** ind i området **Akse**.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [Ret visualiseringen](power-bi-report-change-visualization-type.md) til et områdediagram.  Der er mange visualiseringstyper at vælge imellem. Se [beskrivelser af hver, tips til bedste praksis og selvstudier](power-bi-visualization-types-for-reports-and-q-and-a.md) for at få hjælp til at vælge, hvilken type du vil bruge. Vælg ikonet Områdediagram i ruden Visualiseringer.
4. Sortér visualiseringen ved at vælge ellipsen og vælge **Sortér efter måned**.
5. [Tilpas størrelsen af visualiseringen](power-bi-visualization-move-and-resize.md) ved at vælge visualiseringen, tage fat i en af konturcirklerne og trække. Gør den bred nok, så rullepanelet fjernes, men lille nok, så der er plads nok til at tilføje endnu en visualisering.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Gem rapporten](service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Tilføj en kortvisualisering med salg efter placering
1. I tabellen **Store** skal du vælge **Område**. Power BI genkender, at Område er en placering, og opretter en visualisering med et kort.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. Træk **Total Stores** ind i området Størrelse.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. Tilføj en forklaring.  Hvis du vil se dataene efter butiksnavn, skal du trække **Chain** ind i området Forklaring.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>Næste trin
* Du kan finde flere oplysninger om ruden Felter under [Rapporteditoren... få en præsentation](service-the-report-editor-take-a-tour.md).   
* Hvis du vil vide, hvordan du filtrerer og fremhæver dine visualiseringer, skal du se [Filtre og fremhævning i Power BI-rapporter](power-bi-reports-filters-and-highlighting.md).  
* Hvis du vil vide, hvordan bruger og ændrer sammenlægninger, skal du se [Sammenlægninger i rapporter](service-aggregates.md).  
* Få mere at vide om [Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md).  
* Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/).

