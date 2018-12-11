---
title: Introduktion til dashboardfelter for Power BI-designere
description: Alt om dashboardfelter i Power BI. Det omfatter felter, der er oprettet på baggrund af SSRS-rapporter (SQL Server Reporting Services).
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: db6ed98f246eebba55b87fe383ffcab95c22f6dc
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180846"
---
# <a name="intro-to-dashboard-tiles-for-power-bi-designers"></a>Introduktion til dashboardfelter for Power BI-designere

Et felt er et snapshot af dine data, der er fastgjort til dashboardet. Et felt kan oprettes ud fra en rapport, et datasæt, et dashboard, feltet Spørgsmål og svar, Excel og SSRS-rapporter (SQL Server Reporting Services) med flere.  Dette skærmbillede viser mange forskellige felter, der er fastgjort til et dashboard.

![Power BI-dashboard](media/service-dashboard-tiles/power-bi-dashboard.png)

Dashboards og dashboardfelter er en funktion i Power BI-tjenesten ikke Power BI Desktop. Du kan ikke oprette dashboards på mobilenheder, men du kan [få vist og dele](mobile-apps-view-dashboard.md) dem der.

Ud over fastgørelse kan du oprette separate felter direkte på dashboardet ved hjælp af [Tilføj felt](service-dashboard-add-widget.md). Separate felter omfatter: tekstfelter, billeder, videoer, streamingdata og webindhold.

Har du brug for hjælp til at forstå de komponenter, der udgør Power BI?  Se [Power BI – Grundlæggende begreber](service-basic-concepts.md).

> [!NOTE]
> Hvis den oprindelige visualisering, der blev brugt til at oprette feltet, ændres, er det ikke tilfældet med feltet.  Hvis du f.eks. har fastgjort et kurvediagram fra en rapport, og du derefter har ændret kurvediagrammet til et søjlediagram, fortsætter dashboardfeltet med at vise et kurvediagram. Dataene opdateres, men visualiseringstypen bliver ikke.
> 
> 

## <a name="pin-a-tile-from"></a>Fastgør et felt fra...
Der er mange forskellige måder at føje (fastgøre) et felt til et dashboard på. Felter kan fastgøres fra:

* [Power BI Spørgsmål og svar](service-dashboard-pin-tile-from-q-and-a.md)
* [en rapport](service-dashboard-pin-tile-from-report.md)
* [et andet dashboard](service-pin-tile-to-another-dashboard.md)
* [Excel-projektmappe på OneDrive for Business](service-dashboard-pin-tile-from-excel.md)
* [Power BI Publisher til Excel](publisher-for-excel.md)
* [Hurtig indsigt](service-insights.md)
* [Reporting Services](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)

Og separate felter til billeder, tekstfelter, videoer, streamingdata og webindhold kan oprettes direkte på dashboardet ved hjælp af [Tilføj felt](service-dashboard-add-widget.md).

  ![Ikonet Tilføj felt](media/service-dashboard-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Interager med felter på et dashboard
### <a name="move-and-resize-a-tile"></a>Flyt og tilpas størrelsen på et felt
Tag et felt, og [flyt det rundt på dashboardet](service-dashboard-edit-tile.md). Peg, og vælg håndtaget ![håndtag](media/service-dashboard-tiles/resize-handle.jpg) for at tilpasse størrelsen på feltet.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Peg på et felt for at ændre udseende og funktionalitet
1. Peg på feltet for at vise ellipsen.
   
    ![feltellipse](media/service-dashboard-tiles/ellipses_new.png)
2. Vælg ellipsen for at åbne menuen med felthandlinger.
   
    ![ellipseikon](media/service-dashboard-tiles/power-bi-tile-menu.png)
   
    Herfra kan du:
   
   * [Åbne den rapport, der blev brugt til at oprette dette felt ](service-reports.md) ![rapportikon](media/service-dashboard-tiles/chart-icon.jpg)  
   
   * [Åbne det regneark, der blev brugt til at oprette dette felt ](service-reports.md) ![regnearksikon](media/service-dashboard-tiles/power-bi-open-worksheet.png)  
     
    * [Få vist i fokuseringstilstand ](service-focus-mode.md) ![fokusikon](media/service-dashboard-tiles/fullscreen-icon.jpg)  
     * [Eksportere data, der bruges i feltet](visuals/power-bi-visualization-export-data.md) ![eksportér data-ikon](media/service-dashboard-tiles/export-icon.png)
     * [Redigere titel og undertitel, tilføje et link](service-dashboard-edit-tile.md) ![redigeringsikon](media/service-dashboard-tiles/pencil-icon.jpg)
     * [Køre indsigt](service-insights.md) ![indsigtsikon](media/service-dashboard-tiles/power-bi-insights.png)
     * [Fastgøre feltet til et andet dashboard ](service-pin-tile-to-another-dashboard.md)
       ![fastgørelsesikon](media/service-dashboard-tiles/pin-icon.jpg)
     * [Fjerne feltet](service-dashboard-edit-tile.md)
     ![sletningsikon](media/service-dashboard-tiles/trash-icon.png)
3. Vælg et tomt område på canvasset for at lukke handlingsmenuen.

### <a name="select-click-a-tile"></a>Vælg (klik på) et felt
Når du vælger et felt, afhænger næste handling af, hvordan du oprettede feltet. Hvis det har et [brugerdefineret link](service-dashboard-edit-tile.md), føres du til linket ved at vælge feltet. Ellers vil valget af feltet føre dig til rapporten, Excel Online-projektmappen, Reporting Services-rapporten i det lokale miljø eller spørgsmålet i Spørgsmål og svar.

> [!NOTE]
> Undtagelsen til dette er videofelter, der er oprettet direkte på dashboardet ved hjælp af **Tilføj felt**. Hvis du vælger et videofelt (der blev oprettet på denne måde), afspilles videoen direkte på dashboardet.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

* Hvis den rapport, der blev brugt til at oprette visualiseringen, ikke blev gemt, sker der ikke noget, når feltet vælges.
* Hvis feltet blev oprettet vha. en projektmappe i Excel Online, skal du som minimum have læserettigheder til den pågældende projektmappe. Ellers åbnes projektmappen ikke i Excel Online, hvis du vælger feltet.
* Lad os sige, at du opretter et felt direkte på dashboardet ved hjælp af **Tilføj felt** og angiver et brugerdefineret hyperlink for det. Derefter åbnes den pågældende URL-adresse, hvis du vælger titlen, undertitlen eller feltet. Ellers sker der som standard ingenting, når du vælger et felt, der er oprettet direkte på dashboardet for et billede, en webkode eller et tekstfelt.
* Hvis du ikke har tilladelse til rapporten i Reporting Services, vil valget af et felt, der er oprettet på baggrund af en Reporting Services-rapport, føre dig til en side, hvor det angives, at du ikke har adgang (rsAccessDenied).
* Hvis du ikke har adgang til netværket, hvor Reporting Services-serveren er placeret, vil valget af et felt, der er oprettet på baggrund af Reporting Services, føre dig til en side, hvor det angives, at serveren ikke blev fundet (HTTP 404). Enheden skal have netværksadgang til rapportserveren, for at du kan få vist rapporten.
* Hvis den oprindelige visualisering, der blev brugt til at oprette feltet, ændres, er det ikke tilfældet med feltet.  Hvis du f.eks. fastgør et kurvediagram fra en rapport og derefter ændrer kurvediagrammet til et søjlediagram, fortsætter dashboardfeltet med at vise et kurvediagram. Dataene opdateres, men visualiseringstypen bliver ikke.

## <a name="next-steps"></a>Næste trin
[Opret et kort (felt med stort tal) til dit dashboard](power-bi-visualization-card.md)

[Dashboards i Power BI](service-dashboards.md)  

[Opdatering af data](refresh-data.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

[Eksportér et felt til Power Point](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Fastgør Reporting Services-elementer til Power BI-dashboards](https://msdn.microsoft.com/library/mt604784.aspx)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

