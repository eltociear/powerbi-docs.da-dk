---
title: Opret en visualisering med Power BI spørgsmål og svar
description: Lær, hvordan du opretter en visualisering med spørgsmål og svar i Power BI-tjenesten ved hjælp af eksemplet på Detailhandelsanalyse
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 580b387f8c763b0457bd32a71bfbccd90d4040a3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625174"
---
# <a name="create-a-visual-with-power-bi-qa"></a>Opret en visualisering med Power BI spørgsmål og svar

Den hurtigste måde at få svar ud af dine data på er nogle gange at stille et spørgsmål på et naturligt sprog.  I denne artikel ser vi på to forskellige måder at lave den samme visualisering: først at stille et spørgsmål med spørgsmål og svar, og det andet at integrere den i en rapport. Vi bruger Power BI-tjenesten til at oprette det visuelle element i rapporten, men processen er næsten identisk med Power BI Desktop.

![Power BI, der er udfyldt diagram](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-visual.png)

For at følge med skal du bruge en rapport, som du kan redigere, så vi vil bruge et eksempel, der fås med Power BI.

## <a name="create-a-visual-with-qa"></a>Opret en visualisering med spørgsmål og svar

Hvordan vil vi gå om at oprette dette kurvediagram ved hjælp af spørgsmål og svar?

1. Fra dit Power BI-arbejdsområde skal du vælge **Hent data** \> **Eksempler** \> **Eksempel på detailhandelsanalyse** > **Tilslut**.

1. Åbn dashboardet Retail Analysis Sample, og Placer markøren i spørgsmål og svar, **stil et spørgsmål om dine data**.

    ![Placer markøren i spørgsmål og svar](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-cursor-in-qna-box.png)

2. Skriv noget i stil dette spørgsmål i spørgsmål og svar:
   
    **dette års salg og sidste års salg efter måned som områdediagram**
   
    Imens du skriver dette spørgsmål, vælger Spørgsmål og svar den bedste visualisering til at vise dit svar, og visualiseringen ændres automatisk, når du ændrer spørgsmålet. Desuden hjælper Spørgsmål og svar dig med at formulere dit spørgsmål med forslag, automatisk færdiggørelse og rettelse af stavefejl. Spørgsmål og svar anbefaler en lille formulering ændring: "dette års salg og sidste års salg efter *tid måned* som områdediagram".  

    ![Korrigeret formulering, spørgsmål og svar](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-corrected-create-filled-chart.png)

4. Vælg sætningen til at acceptere forslaget. 
   
   Når du er færdig med at skrive dit spørgsmål, er resultatet det samme diagram, som du kan se i dashboardet.
   
   ![Spørgsmål og svar udfyldt områdediagram](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-filled-chart.png)

4. Hvis du vil fastgøre diagrammet til dit dashboard, skal du vælge tegnestiftikonet ![Tegnestiftikon](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) i øverste højre hjørne.

## <a name="create-a-visual-in-the-report-editor"></a>Opret en visualisering i rapporteditoren

1. Naviger tilbage til dashboardet med eksemplet på detailhandelsanalyse.
   
2. Dashboardet indeholder det samme felt med søjlediagrammet område for "Sidste års salg og dette års salg".  Vælg dette felt. Ikke Vælg det felt, du har oprettet med spørgsmål og svar. Hvis du vælger den åbnes spørgsmål og svar. Det oprindelige felt med søjlediagrammet område blev oprettet i en rapport, så rapporten åbnes til siden, der indeholder denne visualisering.

    ![Dashboard med eksempel på detailhandelsanalyse](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Vælg **Rediger rapport** for at åbne rapporten i Redigeringsvisning.  Hvis du ikke er ejer af en rapport, har du ikke mulighed for at åbne rapporten i Redigeringsvisning.
   
    ![Knappen Rediger rapport](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Vælg områdediagrammet, og gennemse indstillingerne i ruden **Felter**.  Report creator byggede dette diagram ved at vælge disse tre værdier (**sidste års salg** og **dette års salg > værdi** fra den **salg** tabel, og  **FiscalMonth** fra den **tid** tabel) og placere dem i den **akse** og **værdier** beholderne.
   
    ![Ruden Visualiseringer](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

    Du kan se de endte op med den samme visualisering. Det ikke var for kompliceret at lave det sådan. Men det er lettere at lave det med spørgsmål og svar!

## <a name="next-steps"></a>Næste trin

- [Brug spørgsmål og svar i dashboards og rapporter](power-bi-tutorial-q-and-a.md)  
- [Spørgsmål og svar til forbrugere](consumer/end-user-q-and-a.md)
- [Få dine data til at fungere godt med Spørgsmål og svar i Power BI](service-prepare-data-for-q-and-a.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

