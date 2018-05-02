---
title: 'Selvstudium – Opret en ny rapport ud fra et datasæt '
description: Opret en ny Power BI-rapport ud fra et datasæt.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e6c4a614f19a6ba7b9e24c199b7f291e7f57f098
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-new-report-in-power-bi-service-by-importing-a-dataset"></a>Opret en ny rapport i Power BI-tjenesten ved at importere et datasæt
Du har læst [Rapporter i Power BI](service-reports.md), og nu vil du oprette din egen. Der er mange forskellige måder at oprette en rapport på, og i denne artikel starter vi med at oprette en meget grundlæggende rapport ud fra et Excel-datasæt ved hjælp af Power BI-tjenesten. Når du har forstået de grundlæggende ting i forbindelse med at oprette en rapport, vejleder de **Næste trin** for neden dig gennem de mere avancerede rapportemner.  

> **TIP!** Hvis du vil oprette en rapport ved at kopiere en eksisterende rapport, skal du se [Kopiér en rapport](power-bi-report-copy.md)
> 
### <a name="prerequisites"></a>Forudsætninger
- Power BI-tjenesten (se [Desktop-rapportvisning](desktop-report-view.md) for at få oplysninger om oprettelse af rapporter ved hjælp af Power BI Desktop)  
- Eksempel på detailhandelsanalyse

## <a name="import-the-dataset"></a>Importér datasættet
Denne metode til oprettelse af en rapport starter med et datasæt og et tomt rapportlærred. For at kunne følge med skal du [downloade Excel-datasættet Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkId=529778) og gemme det på OneDrive for Business (anbefales) eller lokalt.

1. Vi opretter rapporten i et arbejdsområde i Power BI-tjenesten, så vælg et eksisterende arbejdsområde eller opret et nyt.
   
   ![liste over apparbejdsområder](media/service-report-create-new/power-bi-workspaces2.png)
2. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![Hent data](media/service-report-create-new/power-bi-get-data3.png)
3. Vælg **Filer**, og naviger til den placering, hvor du har gemt Retail Analysis-eksemplet.
   
    ![vælg Filer](media/service-report-create-new/power-bi-select-files.png)
4. Til denne øvelse skal du vælge **Importér**.
   
   ![vælg Importér](media/service-report-create-new/power-bi-import.png)
5. Når datasættet er importeret, skal du vælge **Vis datasæt**.
   
   ![vælg Vis datasæt](media/service-report-create-new/power-bi-view-dataset.png)
6. Når du får vist et datasæt, åbnes rapporteditoren faktisk.  Du får vist et tomt lærred og værktøjerne til redigering af rapporten.
   
   ![rapporteditor](media/service-report-create-new/power-bi-blank-report.png)

> **TIP!** Hvis du ikke kender til lærredet til redigering af rapporten, eller hvis du har brug for at få det genopfrisket, kan du [få en introduktion til rapporteditoren ](service-the-report-editor-take-a-tour.md), før du fortsætter.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Føj en radial måler til rapporten
Nu hvor vores datasæt er blevet importeret, så lad os komme i gang med at besvare nogle spørgsmål.  Vores marketingchef (CMO) vil vide, hvor tæt vi er på at nå dette års salgsmål. En måler er et [godt visualiseringsvalg](power-bi-report-visualizations.md) til at vise denne type oplysninger.

1. I ruden Fields skal du vælge **Sales** > **This Year Sales** > **Værdi**.
   
    ![liggende søjlediagram i rapporteditor](media/service-report-create-new/power-bi-report-step1.png)
2. Konvertér din visual til en måler ved at vælge skabelonen Gauge ![ målerikon](media/service-report-create-new/powerbi-gauge-icon.png) i ruden **Visualiseringer**.
   
    ![Målervisualisering i rapporteditor](media/service-report-create-new/power-bi-report-step2.png)
3. Træk **Sales** > **This Year Sales** > **Goal** til feltet **Target value**. Det ser ud til, at vi er meget tæt på vores mål.
   
    ![Målervisualiseringer med Mål som Målværdi](media/service-report-create-new/power-bi-report-step3.png)
4. Nu ville det være en god ide at [gemme rapportén](service-report-save.md).
   
   ![Filmenu](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Tilføj et områdediagram og et udsnit i rapporten
Vores marketingchef har nogle yderligere spørgsmål, vi skal besvare. Hun vil gerne vide, hvordan salget i år er i sammenligning med sidste år. Og hun vil gerne have vist resultaterne efter område.

1. Vi starter med at lave plads på vores lærred. Markér måleren, og flyt den til øverste højre hjørne. Træk derefter i hjørnerne for at gøre den mindre.
2. Fjern markeringen af måleren. I ruden Felter skal du vælge **Sales** > **This Year Sales** > **Value**og vælge **Sales** > **Last Year Sales**.
   
    ![rapporteditor med Måler og liggende søjlediagram](media/service-report-create-new/power-bi-report-step4.png)
3. Konvertér din visualisering til et områdediagram ved at vælge skabelonen Area chart ![diagramikon](media/service-report-create-new/power-bi-areachart-icon.png) i ruden **Visualiseringer**.
4. Vælg **Time** > **Period** for at føje den til feltet **Axis**.
   
    ![rapporteditor med aktivt områdediagram](media/service-report-create-new/power-bi-report-step5.png)
5. Hvis du vil sortere visualiseringen efter tidsperiode, skal du vælge ellipsen og vælge **Sortér efter periode**.
6. Nu vil vi tilføje udsnittet. Markér et tomt område på lærredet, og vælg skabelonen Udsnit ![Udsnit-ikon](media/service-report-create-new/power-bi-slicer-icon.png)    . Så tilføjes der et tomt udsnitsværktøj på lærredet.
   
    ![rapportcanvas](media/service-report-create-new/power-bi-report-step6.png)    
7. Vælg **District** > **District** i ruden Fields. Flyt og tilpas størrelsen af udsnitsværktøjet.
   
    ![Rapporteditor, tilføj District](media/service-report-create-new/power-bi-report-step7.png)  
8. Brug udsnitsværktøjet til at søge efter mønstre og indsigt efter område (District).
   
   ![video om brugen af udsnitsværktøj](media/service-report-create-new/power-bi-slicer-video2.gif)  

Fortsæt med at udforske dine data og tilføje visualiseringer. Når du finder interessant viden, kan du [fastgøre den til et dashboard](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Næste trin
* [Tilføj en ny side i rapporten](power-bi-report-add-page.md)  
* Se, hvordan du kan [fastgøre visualiseringer til et dashboard](service-dashboard-pin-tile-from-report.md)   
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

