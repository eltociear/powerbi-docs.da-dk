---
title: Eksportér data fra et visuelt Power BI-element
description: Eksportér data fra en rapportvisualisering og en dashboardvisualisering, og få dem vist i Excel.
author: mihart
manager: kvivek
ms.reviewer: cmfinlan
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/11/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 6aec9f569f657c58eb1dc0b807bbceefc62ab01a
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/04/2019
ms.locfileid: "71943864"
---
# <a name="export-data-from-a-visual"></a>Eksportér data fra et visuelt element
Hvis du gerne vil se de data, der bruges til at oprette en visualisering, [kan du få vist disse data i Power BI](end-user-show-data.md) eller eksportere dem til Excel. Indstillingen for eksport af dataene kræver en bestemt type eller en licens samt redigeringstilladelser til indholdet. Hvis du ikke kan eksportere, bedes du kontakte din Power BI-administrator. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Fra en visualisering på et Power BI-dashboard

1. Start på et Power BI-dashboard. Her bruger vi dashboardet fra appen med ***marketing- og salgseksemplet***. Du kan [downloade denne app fra AppSource.com](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![Appdashboard](media/end-user-export/power-bi-dashboards.png)

2. Hold over en visualisering for at se ellipserne (...), og klik for at få vist handlingsmenuen.

    ![Menu, der vises, når du vælger ellipserne](media/end-user-export/power-bi-action-menu.png)

3. Vælg **Eksportér til Excel**.

4. Den næste handling afhænger af, hvilken browser du bruger. Du bliver muligvis bedt om at gemme filen, eller du kan måske se et link til den eksporterede fil nederst i browseren. 

    ![Chrome-browser med link til den eksporterede fil](media/end-user-export/power-bi-dashboard-exports.png)

5. Åbn filen i Excel.  

    ![Enheder i alt ÅTD i Excel](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Fra en visualisering i en rapport
Du kan eksportere data fra en visualisering i en rapport i .csv- eller .xlsx-format (Excel). 

1. Vælg et felt på et dashboard for at åbne den underliggende rapport.  I dette eksempel vælger vi den samme visualisering som ovenfor, *Varians i % for Enheder i alt ÅTD*. 

    ![Fremhævet dashboardfelt](media/end-user-export/power-bi-export-reports.png)

    Da dette felt blev oprettet fra rapporten med *salgs- og marketingeksemplet*, er det denne rapport, der åbnes. Og den åbnes på den side, som indeholder den valgt feltvisualisering. 

2. Vælg feltet i rapporten. Bemærk ruden **Filtre** til højre. Der er anvendt filtre på denne visualisering. Hvis du vil vide mere om filtre, skal du se [Brug filtre i en rapport](end-user-report-filter.md).

    ![Filterrude valgt](media/end-user-export/power-bi-export-filter.png)


3. Vælg ellipsen i visualiseringens øverste højre hjørne. Vælg **Eksportér data**.

    ![Eksportér data, der er valgt på rullelisten](media/end-user-export/power-bi-export-report.png)

4. Du kan se indstillinger for eksport af opsummerede data eller underliggende data. Hvis du bruger appen med *salgs- og marketingeksemplet*, er **underliggende data** deaktiveret. Men du kan støde på rapporter, hvor begge indstillinger er aktiveret. Her er en forklaring på forskellen.

    **Opsummerede data**: Vælg denne indstilling, hvis du vil eksportere data for det, du ser i visualiseringen.  I denne type eksport vises kun de data, der blev brugt til at oprette visualiseringen. Hvis der er anvendt filtre på visualiseringen, vil de data, du eksporterer, også blive filtreret. For denne visualisering indeholder eksporten f.eks. kun data for 2014 og det centrale område og kun data for fire af producenterne: VanArsdel, Natura, Aliqui og Pirum.
  

    **Underliggende data**: Vælg denne indstilling, hvis du vil eksportere data for det, du ser i visualiseringen, **og** yderligere data fra det underliggende datasæt.  Dette kan omfatte data, der findes i datasættet, men som ikke bruges i visualiseringen. 

    ![Menu, hvor du vælger underliggende eller opsummerede data](media/end-user-export/power-bi-export-option.png)

5. Den næste handling afhænger af, hvilken browser du bruger. Du bliver muligvis bedt om at gemme filen, eller du kan måske se et link til den eksporterede fil nederst i browseren. 

    ![Eksporteret fil vist i Microsoft Edge-browseren](media/end-user-export/power-bi-export-edge-browser.png)


6. Åbn filen i Excel. Sammenlign mængden af eksporterede data med de data, vi eksporterede fra den samme visualisering på dashboardet. Forskellen er, at denne eksport omfatter **underliggende data**. 

    ![Excel-eksempel](media/end-user-export/power-bi-underlying.png)

## <a name="next-steps"></a>Næste trin

[Vis de data, der er brugt til oprettelse af en visualisering](end-user-show-data.md)