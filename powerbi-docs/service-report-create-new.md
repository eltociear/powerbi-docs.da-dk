---
title: Opret en rapport ud fra et datasæt
description: Opret en Power BI-rapport ud fra et datasæt.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: c3f30206a01dce9cf9fd3ce0600b46b401df2b1f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73871756"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>Opret en rapport i Power BI-tjenesten ved at importere et datasæt
Du har læst [Rapporter i Power BI](consumer/end-user-reports.md), og nu vil du oprette din egen. Der er forskellige måder at oprette en rapport på. I denne artikel starter vi med at oprette en grundlæggende rapport i Power BI-tjenesten ud fra et Excel-datasæt. Når du har forstået de grundlæggende ting i forbindelse med at oprette en rapport, skal du se de [Næste trin](#next-steps) nederst for at se mere avancerede rapportemner.  

## <a name="prerequisites"></a>Forudsætninger
- [Tilmeld dig Power BI-tjenesten](service-self-service-signup-for-power-bi.md). Se [Desktop-rapportvisning](desktop-report-view.md) for at se, hvordan du opretter rapporter ved hjælp af Power BI Desktop. 
- [Download Excel-datasættet med Retail Analysis-eksemplet](https://go.microsoft.com/fwlink/?LinkId=529778), og gem det i OneDrive for Business eller lokalt.

## <a name="import-the-dataset"></a>Importér datasættet
Denne metode til oprettelse af en rapport starter med et datasæt og et tomt rapportlærred. Du kan følge med ved at se Excel-datasættet med Retail Analysis-eksemplet.

1. Vi opretter rapporten i et arbejdsområde i Power BI-tjenesten, så vælg et eksisterende arbejdsområde eller opret et.
   
   ![liste over arbejdsområder](media/service-report-create-new/power-bi-workspaces2.png)
2. Vælg **Hent data** nederst i navigationsruden.
   
   ![Hent data](media/service-report-create-new/power-bi-get-data3.png)
3. Vælg **Filer**, og naviger til den placering, hvor du har gemt Retail Analysis-eksemplet.
   
    ![vælg Filer](media/service-report-create-new/power-bi-select-files.png)
4. Til denne øvelse skal du vælge **Importér**.
   
   ![vælg Importér](media/service-report-create-new/power-bi-import.png)
5. Når datasættet er importeret, skal du vælge **Vis datasæt**.
   
   ![vælg Vis datasæt](media/service-report-create-new/power-bi-view-dataset.png)
6. Når du får vist et datasæt, åbnes rapporteditoren faktisk.  Du får vist et tomt lærred og værktøjerne til redigering af rapporten.
   
   ![rapporteditor](media/service-report-create-new/power-bi-blank-report.png)

> [!TIP]
> Hvis du ikke kender til lærredet til redigering af rapporten, eller hvis du har brug for at få det genopfrisket, kan du [få en introduktion til rapporteditoren](service-the-report-editor-take-a-tour.md), før du fortsætter. 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Føj en radial måler til rapporten
Nu hvor vores datasæt er blevet importeret, så lad os komme i gang med at besvare nogle spørgsmål.  Vores marketingchef (CMO) vil vide, hvor tæt vi er på at nå dette års salgsmål. En måler er et [godt visualiseringsvalg](visuals/power-bi-report-visualizations.md) til at vise denne type oplysninger.

1. I ruden Fields skal du vælge **Sales** > **This Year Sales** > **Værdi**.
   
    ![liggende søjlediagram i rapporteditor](media/service-report-create-new/power-bi-report-step1.png)
2. Konvertér din visual til en måler ved at vælge skabelonen Gauge ![ målerikon](media/service-report-create-new/powerbi-gauge-icon.png) i ruden **Visualiseringer**.
   
    ![Målervisualisering i rapporteditor](media/service-report-create-new/power-bi-report-step2.png)
3. Træk **Sales** > **This Year Sales** > **Goal** til feltet **Target value**. Det ser ud til, at vi er meget tæt på vores mål.
   
    ![Målervisualiseringer med Mål som Målværdi](media/service-report-create-new/power-bi-report-step3.png)
4. Det er nu en god idé at gemme rapporten.
   
   ![Filmenu](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Tilføj et områdediagram og et udsnit i rapporten
Vores marketingchef har nogle yderligere spørgsmål, vi skal besvare. Vedkommende vil gerne vide, hvordan salget i år er sammenlignet med sidste år. Og vedkommende vil gerne have vist resultaterne efter område.

1. Vi starter med at lave plads på vores lærred. Markér måleren, og flyt den til øverste højre hjørne. Træk derefter i hjørnerne for at gøre den mindre.
2. Fjern markeringen af måleren. I ruden Felter skal du vælge **Sales** > **This Year Sales** > **Value**og vælge **Sales** > **Last Year Sales**.
   
    ![rapporteditor med Måler og liggende søjlediagram](media/service-report-create-new/power-bi-report-step4.png)
3. Konvertér din visualisering til et områdediagram ved at vælge skabelonen Area chart ![diagramikon](media/service-report-create-new/power-bi-areachart-icon.png) i ruden **Visualiseringer**.
4. Vælg **Time** > **Period** for at føje den til feltet **Axis**.
   
    ![rapporteditor med aktivt områdediagram](media/service-report-create-new/power-bi-report-step5.png)
5. Hvis du vil sortere visualiseringen efter tidsperiode, skal du vælge ellipsen og vælge **Sortér efter periode**.
6. Nu vil vi tilføje udsnittet. Markér et tomt område på lærredet, og vælg skabelonen Udsnit ![Udsnit-ikon](media/service-report-create-new/power-bi-slicer-icon.png) . Vi har nu et tomt udsnit på vores lærred.
   
    ![rapportcanvas](media/service-report-create-new/power-bi-report-step6.png)    
7. Vælg **District** > **District** i ruden Fields. Flyt og tilpas størrelsen af udsnitsværktøjet.
   
    ![Rapporteditor, tilføj District](media/service-report-create-new/power-bi-report-step7.png)  
8. Brug udsnitsværktøjet til at søge efter mønstre og indsigt efter område (District).
   
   ![video om brugen af udsnitsværktøj](media/service-report-create-new/power-bi-slicer-video2.gif)  

Fortsæt med at udforske dine data og tilføje visualiseringer. Når du finder interessant viden, kan du [fastgøre den til et dashboard](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Næste trin

* Se, hvordan du kan [fastgøre visualiseringer til et dashboard](service-dashboard-pin-tile-from-report.md)   
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

