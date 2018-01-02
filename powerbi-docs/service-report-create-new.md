---
title: "Opret en ny rapport ud fra et datasæt "
description: "Opret en ny Power BI-rapport ud fra et datasæt."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: f4afb1eaa1b3012fdbdb0eff35e9eff695cc32e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Opret en ny Power BI-rapport ved at importere et datasæt
Du har læst [Rapporter i Power BI](service-reports.md), og nu vil du oprette din egen. Der er mange forskellige måder at oprette en rapport på, og i denne artikel starter vi med at oprette en meget grundlæggende rapport ud fra et Excel-datasæt. Når du har forstået de grundlæggende ting i forbindelse med at oprette en rapport, vejleder de **Næste trin** for neden dig gennem de mere avancerede rapportemner.  

> **TIP!** Hvis du vil oprette en rapport ved at kopiere en eksisterende rapport, skal du se [Kopiér en rapport](power-bi-report-copy.md)
> 
> 

## <a name="import-the-dataset"></a>Importér datasættet
Denne metode til oprettelse af en rapport starter med et datasæt og et tomt rapportlærred. For at kunne følge med skal du [downloade Excel-datasættet Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkId=529778) og gemme det på OneDrive for Business (anbefales) eller lokalt.

1. Vi opretter rapporten i et arbejdsområde i Power BI-tjenesten, så vælg et eksisterende arbejdsområde eller opret et nyt.
   
   ![](media/service-report-create-new/power-bi-workspaces2.png)
2. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-report-create-new/power-bi-get-data3.png)
3. Vælg **Filer**, og naviger til den placering, hvor du har gemt Retail Analysis-eksemplet.
   
    ![](media/service-report-create-new/power-bi-select-files.png)
4. Til denne øvelse skal du vælge **Importér**.
   
   ![](media/service-report-create-new/power-bi-import.png)
5. Når datasættet er importeret, skal du vælge **Vis datasæt**.
   
   ![](media/service-report-create-new/power-bi-view-dataset.png)
6. Når du får vist et datasæt, åbnes rapporteditoren faktisk.  Du får vist et tomt lærred og værktøjerne til redigering af rapporten.
   
   ![](media/service-report-create-new/power-bi-blank-report.png)

> **TIP!** Hvis du ikke kender til lærredet til redigering af rapporten, eller hvis du har brug for at få det genopfrisket, kan du [få en introduktion til rapporteditoren ](service-the-report-editor-take-a-tour.md), før du fortsætter.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Føj en radial måler til rapporten
Nu hvor vores datasæt er blevet importeret, så lad os komme i gang med at besvare nogle spørgsmål.  Vores marketingchef (CMO) vil vide, hvor tæt vi er på at nå dette års salgsmål. En måler er et [godt visualiseringsvalg](power-bi-report-visualizations.md) til at vise denne type oplysninger.

1. I ruden Fields skal du vælge **Sales** > **This Year Sales** > **Værdi**.
   
    ![](media/service-report-create-new/power-bi-report-step1.png)
2. Konvertér dit visuelle element til en måler ved at vælge skabelonen Gauge ![](media/service-report-create-new/powerbi-gauge-icon.png) fra ruden **Visualizations**.
   
    ![](media/service-report-create-new/power-bi-report-step2.png)
3. Træk **Sales** > **This Year Sales** > **Goal** til feltet **Target value**. Det ser ud til, at vi er meget tæt på vores mål.
   
    ![](media/service-report-create-new/power-bi-report-step3.png)
4. Nu ville det være en god ide at [gemme rapportén](service-report-save.md).
   
   ![](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Tilføj et områdediagram og et udsnit i rapporten
Vores marketingchef har nogle yderligere spørgsmål, vi skal besvare. Hun vil gerne vide, hvordan salget i år er i sammenligning med sidste år. Og hun vil gerne have vist resultaterne efter område.

1. Vi starter med at lave plads på vores lærred. Markér måleren, og flyt den til øverste højre hjørne. Træk derefter i hjørnerne for at gøre den mindre.
2. Fjern markeringen af måleren. I ruden Felter skal du vælge **Sales** > **This Year Sales** > **Value**og vælge **Sales** > **Last Year Sales**.
   
    ![](media/service-report-create-new/power-bi-report-step4.png)
3. Konvertér dit visuelle element til et områdediagram ved at vælge skabelonen Area chart ![](media/service-report-create-new/power-bi-areachart-icon.png) i ruden **Visualizations**.
4. Vælg **Time** > **Period** for at føje den til feltet **Axis**.
   
    ![](media/service-report-create-new/power-bi-report-step5.png)
5. For at sortere visualiseringen skal du vælge ellipsen og vælge **Sort by Period**.
6. Nu vil vi tilføje udsnittet. Markér et tomt område på lærredet, og vælg skabelonen Slicer ![](media/service-report-create-new/power-bi-slicer-icon.png). Så tilføjes der et tomt udsnitsværktøj på lærredet.
   
    ![](media/service-report-create-new/power-bi-report-step6.png)    
7. Vælg **District** > **District** i ruden Fields. Flyt og tilpas størrelsen af udsnitsværktøjet.
   
    ![](media/service-report-create-new/power-bi-report-step7.png)  
8. Brug udsnitsværktøjet til at søge efter mønstre og indsigt efter område (District).
   
   ![](media/service-report-create-new/power-bi-slicer-video2.gif)  
9. Du kan eventuelt fortsætte med at tilføje visuelle elementer.

## <a name="next-steps"></a>Næste trin
* [Opret en kopi af en rapport](power-bi-report-copy.md)
* [Gem rapporten](service-report-save.md)    
* [Tilføj en ny side i rapporten](power-bi-report-add-page.md)  
* Se, hvordan du kan [fastgøre visuelle elementer til et dashboard](service-dashboard-pin-tile-from-report.md)    
* Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

