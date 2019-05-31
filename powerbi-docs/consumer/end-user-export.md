---
title: Eksportér data fra et visuelt Power BI-element
description: Eksportér data fra en rapportvisualisering og dashboard visual, og få den vist i Excel.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063661"
---
# <a name="export-data-from-visual"></a>Eksport data fra visual
Hvis du gerne vil se de data, der bruges til at oprette en visualisering, [kan du få vist disse data i Power BI](end-user-show-data.md) eller eksportere dataene til Excel. Mulighed for at eksportere data, der kræver en bestemt type eller licens og redigeringstilladelser til indholdet. Hvis du ikke kan eksportere, kontakte Power BI-administratoren. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Fra et visuelt element på en Power BI-dashboard

1. Start på en Power BI-dashboard. Her bruger vi dashboardet fra den ***Marketing- og salgsressourcer eksempel*** app. Du kan [downloade denne app fra AppSource.com](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![](media/end-user-export/power-bi-dashboard.png)

2. Peg på et visuelt element for at vise ellipsen (...), og klik for at få vist handlingsmenuen.

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. Vælg **Eksportér til Excel**.

4. Næste skridt afhænger af, hvilken browser du bruger. Du kan blive bedt om at gemme filen eller din kan se et link til den eksporterede fil nederst i browseren. 

    ![](media/end-user-export/power-bi-export-browser.png)

5. Åbn filen i Excel.  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Fra et visuelt element i en rapport
Du kan eksportere data fra en visualisering i en rapport som .xlsx (Excel) eller en .csv-format. 

1. På et dashboard, skal du vælge et felt for at åbne den underliggende rapport.  I dette eksempel vælger vi den samme visualisering som ovenfor, *samlede enheder ÅTD var. i %* . 

    ![](media/end-user-export/power-bi-export-report.png)

    Da dette felt blev oprettet fra den *salg og Marketing Sample* , der er den rapport, der åbner rapporten. Og det åbner siden, der indeholder det valgte felt visuelle element. 

2. Vælg feltet i rapporten. Bemærk den **filtre** ruden til højre. Dette visuelle element har filtre, der anvendes. Hvis du vil vide mere om filtre, se [brug filtre i en rapport](end-user-report-filter.md).

    ![](media/end-user-export/power-bi-export-filters.png)


3. Vælg ellipsen i visualiseringens øverste højre hjørne. Vælg **Eksportér data**.

    ![](media/end-user-export/power-bi-export-report2.png)

4. Du kan se indstillinger til eksport af data for opsummeret eller underliggende data. Hvis du bruger den *salg og marketing sample* app, **underliggende data** deaktiveres. Men du kan støde på rapporter, hvor begge muligheder er aktiveret. Her er en forklaring på forskellen.

    **Opsummerede data**: Vælg denne indstilling, hvis du vil eksportere dataene til det, du ser i Visualiseringen.  Denne type export kan du kun de data, der blev brugt til at oprette det visuelle element. Hvis det visuelle element har filtre, filtreres den du eksporterer data også. For eksempel for denne visual omfatter din eksport kun data for 2014 og centrale område, og kun data for fire af producenterne: VanArsdel, Natura, Aliqui og Prirum.
  

    **Underliggende data**: Vælg denne indstilling, hvis du vil eksportere dataene til det, du ser i Visualiseringen **plus** yderligere data fra det underliggende datasæt.  Det kan omfatte data, der er indeholdt i datasættet, men ikke bruges i Visualiseringen. 

    ![](media/end-user-export/power-bi-export-report3.png)

5. Næste skridt afhænger af, hvilken browser du bruger. Du kan blive bedt om at gemme filen eller din kan se et link til den eksporterede fil nederst i browseren. 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Åbn filen i Excel. Sammenlign mængden data, der eksporteres til de data, vi har eksporteret fra den samme visualisering på dashboardet. Forskellen er, at denne eksport omfatter **underliggende data**. 

    ![](media/end-user-export/power-bi-underlying.png)

