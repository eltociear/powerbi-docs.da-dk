---
title: Dashboardfelter i Power BI-tjenesten til forbrugere
description: Alt om dashboardfelter i Power BI til forbrugere. Det omfatter felter, der er oprettet fra SQL Server Reporting Services (SSRS).
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/18/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 92c473b5df6c21509ba32e41d88dd43c265fa3a0
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73861424"
---
# <a name="dashboard-tiles-in-power-bi"></a>Dashboardfelter i Power BI

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Et felt er et snapshot af dine data, der er fastgjort til dashboardet af en *designer*. *Designere* kan oprette felter ud fra en rapport, et datasæt, et dashboard, feltet Spørgsmål og svar, Excel og SQL Server Reporting Services (SSRS) med flere.  Dette skærmbillede viser mange forskellige felter, der er fastgjort til et dashboard.

![Power BI-dashboard](./media/end-user-tiles/power-bi-dash.png)


Udover felter, der er fastgjort fra rapporter, kan *designere* føje separate felter direkte til dashboardet ved hjælp af **Tilføj felt**. Separate felter omfatter: tekstfelter, billeder, videoer, streamingdata og webindhold.

Har du brug for hjælp til at forstå de komponenter, der udgør Power BI?  Se [Power BI – Grundlæggende begreber](end-user-basic-concepts.md).


## <a name="interacting-with-tiles-on-a-dashboard"></a>Interager med felter på et dashboard

1. Peg på feltet for at vise ellipsen.
   
    ![feltellipse](./media/end-user-tiles/ellipses_new.png)
2. Vælg ellipsen for at åbne menuen med felthandlinger. De tilgængelige indstillinger varierer afhængigt af visualiseringstypen og den metode, der bruges til at oprette feltet. Her er nogle eksempler på, hvad du kan se.

    - felt, der er oprettet ved hjælp af Spørgsmål og svar
   
        ![ellipseikon](./media/end-user-tiles/power-bi-options-1.png)

    - felt, der oprettet ud fra en projektmappe
   
        ![ellipseikon](./media/end-user-tiles/power-bi-options-2.png)

    - felt, der oprettet ud fra en rapport
   
        ![ellipseikon](./media/end-user-tiles/power-bi-options-3.png)
   
    Herfra kan du:
   
   * [Åbne den rapport, der blev brugt til at oprette dette felt ](end-user-reports.md) ![rapportikon](./media/end-user-tiles/chart-icon.jpg)  
   
   * [Åbn det spørgsmål under Spørgsmål og svar, som blev brugt til at oprette feltet ](end-user-reports.md) ![ikon for Spørgsmål og svar](./media/end-user-tiles/qna-icon.png)  
   

   * [Åbn den projektmappe, der blev brugt til at oprette dette felt ](end-user-reports.md) ![regnearksikon](./media/end-user-tiles/power-bi-open-worksheet.png)  
   * [Få vist feltet i fokustilstand ](end-user-focus.md) ![fokusikon](./media/end-user-tiles/fullscreen-icon.jpg)  
   * [Vis indsigt](end-user-insights.md) ![ikonet for indsigt](./media/end-user-tiles/power-bi-insights.png)
   * [Tilføj en kommentar, og start en diskussion](end-user-comment.md) ![kommentarikon](./media/end-user-tiles/comment-icons.png)
   * [Administrer vigtige beskeder, der er angivet på et dashboardfelt](end-user-alerts.md) ![ikon for vigtig besked](./media/end-user-tiles/power-bi-alert-icon.png)
   * [Åbn dataene i Excel](end-user-export.md) ![ikonet for eksport](./media/end-user-tiles/power-bi-export-icon.png)


3. Vælg et tomt område på canvasset for at lukke handlingsmenuen.

### <a name="select-click-a-tile"></a>Vælg (klik på) et felt
Når du vælger et felt, afhænger næste handling af, hvordan feltet blev oprettet, og om det har et [brugerdefineret link](../service-dashboard-edit-tile.md). Hvis det har et brugerdefineret link, føres du til linket ved at vælge feltet. Ellers føres du til rapporten, Excel Online-projektmappen, SSRS-rapporten, der er i det lokale miljø, eller spørgsmål i Spørgsmål og svar, der blev brugt til at oprette feltet.

> [!NOTE]
> Undtagelsen til dette er videofelter, der er oprettet direkte på dashboardet ved hjælp af **Tilføj felt**. Hvis du vælger et videofelt (der blev oprettet på denne måde), afspilles videoen direkte på dashboardet.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Hvis den rapport, der blev brugt til at oprette visualiseringen, ikke blev gemt, sker der ikke noget, når feltet vælges.
* Hvis feltet blev oprettet fra en projektmappe i Excel Online, og du ikke som minimum har læserettigheder til denne projektmappe, åbnes projektmappen ikke i Excel Online, når du vælger feltet.
* For felter, der er oprettet direkte på dashboardet ved hjælp af **Tilføj felt**, og hvis et brugerdefineret hyperlink er angivet, åbnes denne URL-adresse, når titlen, undertitlen eller feltet vælges.  Ellers medfører det som standard ingen handling at vælge et af disse felter oprettet direkte på dashboardet for et billede, en webkode eller et tekstfelt.
* Hvis du ikke har tilladelse til rapporten i SSRS, vil valget af et felt oprettet ud fra SSRS producere en side, der angiver, at du ikke har adgang (rsAccessDenied).
* Hvis du ikke har adgang til netværket, hvor SSRS-serveren er placeret, vil valget af et felt oprettet ud fra SSRS producere en side, der angiver, at serveren ikke blev fundet (HTTP 404). Enheden skal have netværksadgang til rapportserveren for at få vist rapporten.
* Hvis den oprindelige visualisering, der blev brugt til at oprette feltet, ændres, er det ikke tilfældet med feltet.  Hvis *designeren* f.eks. har fastgjort et kurvediagram fra en rapport og derefter har ændret kurvediagrammet til et søjlediagram, vises der fortsat et kurvediagram på dashboardfeltet. Dataene opdateres, men visualiseringstypen bliver ikke.

## <a name="next-steps"></a>Næste trin
[Opdatering af data](../refresh-data.md)

[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)
