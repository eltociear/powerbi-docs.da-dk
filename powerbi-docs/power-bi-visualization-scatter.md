---
title: Punktdiagrammer i Power BI (selvstudium)
description: 'Selvstudium: Punktdiagrammer i Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: PVcfPoVE3Ys
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: 2d8ed3c30d289646504071daca098df1f41f6aab
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi-tutorial"></a>Punktdiagrammer og boblediagrammer i Power BI (selvstudium)
Et punktdiagram har altid to værdiakser for at vise ét sæt numeriske data langs en vandret akse og et andet sæt numeriske værdier langs en lodret akse. Diagrammet viser punkter ved skæringspunktet for en numerisk x- og y-værdi og kombinerer disse værdier i enkelte datapunkter. Disse datapunkter kan være fordelt jævnt eller ujævnt på tværs af den vandrette akse afhængigt af dataene.

Et boblediagram erstatter datapunkterne med bobler, hvor boble*størrelsen* repræsenterer en yderligere dimension af dataene.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Du kan fastsætte antallet af datapunkter  

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Hvornår skal man bruge et punktdiagram eller boblediagram?
### <a name="scatter-charts-are-a-great-choice"></a>Punktdiagrammer er praktiske til følgende situationer:
* Vis relationer mellem 2 (punktdiagram) eller 3 (boblediagram) **numeriske** værdier.
* Afbild to grupper af tal som en serie af x- og y-koordinater.
* I stedet for et kurvediagram, når du vil ændre skalaen for den vandrette akse.    
* Hvis du vil ændre den vandrette akse til en logaritmisk skala.
* Hvis du vil vise projektmappedata, der inkluderer par eller grupperede værdisæt. I et punktdiagram kan du tilpasse akseskalaerne uafhængigt af hinanden for at afsløre flere oplysninger om grupperede værdier.
* Til at vise mønstre i store datasæt, for eksempel ved at vise lineære eller ikke-lineære tendenser, klynger og udenforliggende værdier.
* Til at sammenligne store antal datapunkter uden hensyntagen til tiden.  Jo flere data, du medtager i et punktdiagram, jo bedre er sammenligningerne, du kan udføre.

### <a name="bubble-charts-are-a-great-choice"></a>Boblediagrammer er praktiske til følgende situationer:
* Hvis dine data har 3 dataserier, som hver indeholder et sæt af værdier.
* Til præsentation af finansielle data.  Forskellige boblestørrelser er praktiske til visuel fremhævning af specifikke værdier.
* Til brug med kvadranter.

## <a name="create-a-scatter-chart"></a>Opret et punktdiagram
Se denne video for at se Will oprette et punktdiagram, og følg derefter nedenstående trin for at oprette et selv.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


I denne vejledning bruges Retail Analysis Sample (Eksempel på detailhandelsanalyse). Du skal [downloade eksemplet](sample-datasets.md) til Power BI-tjenesten (app.powerbi.com) eller Power BI Desktop, så du kan følge med.   

1. Start på en [tom rapportside](power-bi-report-add-page.md), og vælg felterne **Sales** \> **Sales Per Sq Ft** og **Sales** > **Total Sales Variance %**. Hvis du bruger Power BI-tjenesten, skal du åbne rapporten i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md).
 
2. Vælg **District > District** i ruden Felter.
   
    ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)
4. Konvertér til et punktdiagram. Vælg ikonet Punktdiagram i ruden Visualiseringer.
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).
5. Træk **District** fra **Detaljer** til **Forklaring**.
   
    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

Nu har jeg et punktdiagram, der viser Total Sales Variance % langs Y-aksen og Sales Per Square Feet langs X-aksen.  Datapunkternes farver repræsenterer distrikterne.  Nu tilføjer jeg en tredje dimension.

## <a name="create-a-bubble-chart"></a>Opret et boblediagram
1. Træk **Sales** > **This Year Sales** > **Value** til området **Størrelse**. 
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)
2. Peg på en boble.  Boblens størrelse afspejler værdien af **This Year Sales**.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. Du kan eventuelt [formatere farver, navne, titler, baggrund og mere i dine visualiseringer](service-getting-started-with-color-formatting-and-axis-properties.md).

   Du kan også ændre mærkeformen til diamant, trekant eller firkant:

   ![Firkantet mærke](media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)

4. Du kan også vælge at indstille antallet af datapunkter, der skal vises i dit boblediagram, i afsnittet **Format** på ruden **Visualiseringer** ved at udvide kortet **Generelt** og justere **Datamængde**. Standarden er 3500. 
 
    ![Datamængde](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   > [!NOTE]
   > Da flere datapunkter kan føre til en længere indlæsningstid, hvis du vælger at publicere rapporter med grænser i den højere ende af skalaen, skal du sørge for at afprøve dine rapporter på tværs af internettet og mobilnettet samt sørge for, at ydeevnen opfylder dine brugeres forventninger.

5.   Hvis du evt. vil vælge mærkeformen, skal du udvide kortet **Figurer** og derefter vælge en mærkeform.

      ![Mærkeform](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
### <a name="your-scatter-chart-has-only-one-data-point"></a>**Dit punktdiagram har kun ét datapunkt**
Har dit punktdiagram kun ét datapunkt, der aggregerer alle værdierne på X- og Y-aksen?  Eller aggregeres alle værdierne langs en enkelt vandret eller lodret linje?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Tilføj et felt i området **Detaljer** for at angive, hvordan værdierne skal grupperes i Power BI. Feltet skal være entydigt for hver punkt, der skal afbildes.  
Som et enkelt rækkenummer eller et id-felt:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Hvis det ikke findes i dine data, kan du oprette et felt, der sammensætter X- og Y-værdierne til noget entydigt pr. punkt:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Du kan oprette et nyt felt ved at [bruge Forespørgselseditor i Power BI Desktop til at tilføje en indekskolonne](desktop-add-custom-column.md) i dit datasæt.  Tilføj derefter denne kolonne i området **Detaljer** for din visualisering.

## <a name="next-steps"></a>Næste trin
 [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Prøv det – det er gratis!](https://powerbi.com/)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

