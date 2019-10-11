---
title: Brug bånddiagrammer i Power BI
description: Opret og brug bånddiagrammer i Power BI Desktop
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e6044f3a2cfdbfc40d0497ebde25780336dc1dc4
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715489"
---
# <a name="use-ribbon-charts-in-power-bi"></a>Brug bånddiagrammer i Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Du kan bruge bånddiagrammer til at visualisere data og hurtigt finde ud af, hvilken kategori af data der har den højeste placering (største værdi). Bånddiagrammer er effektive til at vise ændringer af placeringer, hvor den højeste placering (værdi) altid vises øverst for hver tidsperiode. 

![bånddiagram](media/desktop-ribbon-charts/ribbon-charts-01.png)

## <a name="prerequisites"></a>Forudsætninger

I dette selvstudium bruges [PBIX-filen med eksemplet Detailhandelsanalyse](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Vælg **Fil** > **Åbn** i øverste venstre afsnit af menulinjen
   
2. Find din kopi af **PBIX-filen med eksemplet Detailhandelsanalyse**

1. Åbn **PBIX-filen med eksemplet Detailhandelsanalyse** i rapportvisning ![ikon for skærmbillede af rapportvisning.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Markér ![Skærmbillede af den gule fane.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) for at tilføje en ny side.

## <a name="create-a-ribbon-chart"></a>Opret et bånddiagram

1. Du opretter et bånddiagram ved at vælge **bånddiagram** på panelet **Visualiseringer**.

    ![visualiseringsskabeloner](media/desktop-ribbon-charts/power-bi-template.png)

    Med bånddiagrammer tilknyttes en kategori af data for den visualiserede tidsperiode ved hjælp af bånd, hvilket gør det muligt at se, hvordan en bestemt kategori placeres over hele diagrammets x-akse (normalt tidslinjen).

2. Vælg felter for **Akse**, **Forklaring** og **Værdi**.  I dette eksempel har vi valgt: **Butik** > **OpenDate**, **Vare** > **Kategori** og **Salg** > **Dette års salg** > **Værdi**.  

    ![valgte felter](media/desktop-ribbon-charts/power-bi-ribbon-values.png)

    Eftersom datasættet kun indeholder data for ét år, har vi også fjernet feltet **År** og **Kvartal** fra kategorien **Akse**.

3. I bånddiagrammet kan du se placeringen for hver måned. Bemærk, hvordan placering ændres over tid. Kategorien Hjem rykker for eksempel fra anden til femte fra februar til marts.

    ![bånddiagram](media/desktop-ribbon-charts/power-bi-ribbon.png)

## <a name="format-a-ribbon-chart"></a>Formatér et bånddiagram
Når du opretter et bånddiagram, er der formateringsindstillinger tilgængelige under afsnittet **Format** i ruden **Visualiseringer**. Formateringsindstillingerne for bånddiagrammer ligner indstillingerne for et stablet søjlediagram, men byder på yderligere formateringsindstillinger, som er specifikke for båndene.

![båndskabelon i ruden Visualisering](media/desktop-ribbon-charts/power-bi-format-ribbon.png)

Ved hjælp af disse formateringsindstillinger for bånddiagrammer kan du foretage følgende justeringer.

* **Afstand** gør det muligt at justere, hvor meget plads der vises mellem båndene. Tallet er procentdelen af kolonnens maksimumhøjde.
* **Match seriens farve** gør det muligt at matche farven på båndene med seriens farve. Når den er slået **fra**, er båndene grå.
* **Gennemsigtighed** angiver, hvor gennemsigtige båndene er. Standardværdien er angivet til 30.
* **Kant** gør det muligt at placere en mørk kant øverst og nederst på båndene. Kanter er som standard slået fra.

Da bånddiagrammet ikke har mærkater for y-aksen, kan det være en god idé at tilføje datamærkater. I ruden Formatering skal du vælge **Datamærkater**. 

![formateringsindstillinger for datamærkater](media/desktop-ribbon-charts/power-bi-labels.png)

Angiv formateringsindstillingerne for dine datamærkater. I dette eksempel har vi sat tekstfarven til hvid og visningsenheder til tusinde.

![båndskabelon i ruden Visualisering](media/desktop-ribbon-charts/power-bi-data-labels.png)

## <a name="next-steps"></a>Næste trin

[Punktdiagrammer og boblediagrammer i Power BI](power-bi-visualization-scatter.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
