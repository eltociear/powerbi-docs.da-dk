---
title: Kom i gang vha. spørgsmål og svar om Power BI
description: Kom i gang med Spørgsmål og svar i Power BI-tjenesten ved hjælp af eksemplet på detailhandelsanalyse
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 87783b928fdec1cadf5318ae184858c37daa4acc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279245"
---
# <a name="get-started-with-power-bi-qa"></a>Kom i gang vha. spørgsmål og svar om Power BI

Den hurtigste måde at få svar ud af dine data på er nogle gange at stille et spørgsmål på et naturligt sprog.  I denne hurtige introduktion ser vi på to forskellige måder at lave den samme visualisering på: først ved at integrere den i en rapport og derefter ved at stille et spørgsmål i forbindelse med Spørgsmål og svar. Vi vil bruge Power BI-tjenesten, men processen er næsten identisk med Power BI Desktop.

For at følge med skal du bruge en rapport, som du kan redigere, så vi vil bruge et eksempel, der fås med Power BI.

## <a name="create-a-visual-in-the-report-editor"></a>Opret en visualisering i rapporteditoren

1. Fra dit Power BI-arbejdsområde skal du vælge **Hent data** \> **Eksempler** \> **Eksempel på detailhandelsanalyse** > **Tilslut**.
   
2. Dashboardet har et områdediagramfelt, der hedder "Sidste års salg og dette års salg."  Vælg dette felt. Hvis dette felt blev oprettet med Spørgsmål og svar, åbnes Spørgsmål og svar, hvis du vælger feltet. Men dette felt blev oprettet i en rapport, så rapporten åbnes til siden, der indeholder denne visualisering.

    ![Dashboard med eksempel på detailhandelsanalyse](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Vælg **Rediger rapport** for at åbne rapporten i Redigeringsvisning.  Hvis du ikke er ejer af en rapport, har du ikke mulighed for at åbne rapporten i Redigeringsvisning.
   
    ![Knappen Rediger rapport](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Vælg områdediagrammet, og gennemse indstillingerne i ruden **Felter**.  Rapportopretteren byggede dette diagram ved at vælge disse tre værdier (**Tid > Regnskabsmåned**, **Salg > Dette års salg**, **Salg >Sidste års salg >Værdi**) og placere dem i beholderne **Akse** og **Værdier**.
   
    ![Ruden Visualiseringer](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="create-the-same-visual-with-qa"></a>Opret den samme visualisering med Spørgsmål og svar

Hvordan kunne vi oprette dette samme kurvediagram ved hjælp af Spørgsmål og svar?

![Feltet Stil et spørgsmål](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Naviger tilbage til dashboardet med eksemplet på detailhandelsanalyse.
2. Skriv noget i stil med dette spørgsmål i naturligt sprog i spørgsmålsfeltet:
   
   **Hvordan så dette års salg og sidste års salg per måned ud som områdediagram**
   
   Imens du skriver dette spørgsmål, vælger Spørgsmål og svar den bedste visualisering til at vise dit svar, og visualiseringen ændres automatisk, når du ændrer spørgsmålet. Desuden hjælper Spørgsmål og svar dig med at formulere dit spørgsmål med forslag, automatisk færdiggørelse og rettelse af stavefejl.
   
   Når du er færdig med at skrive dit spørgsmål, er resultatet præcis det samme diagram, som vi så i rapporten.  Men det er meget hurtigere at lave det sådan her!
   
   ![Eksempel på spørgsmål](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. På samme måde som når du arbejder med rapporter, har du i Spørgsmål og svar adgang til ruderne Visualiseringer, Filtre og Felter.  Åbn disse ruder for at finde ud af mere og ændre din visual.
4. Hvis du vil fastgøre diagrammet til dit dashboard, skal du vælge tegnestiftikonet ![Tegnestiftikon](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Næste trin
[Spørgsmål og svar i Power BI](consumer/end-user-q-and-a.md)

[Få dine data til at fungere godt med Spørgsmål og svar i Power BI](service-prepare-data-for-q-and-a.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

