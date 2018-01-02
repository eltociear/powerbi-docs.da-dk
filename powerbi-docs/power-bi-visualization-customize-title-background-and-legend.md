---
title: Introduktion til formatering af Power BI-visualiseringer (selvstudium)
description: 'Selvstudium: Tilpas visualiseringstitel, -baggrund og -forklaring'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
featuredvideoid: IkJda4O7oGs
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
ms.openlocfilehash: 424e96c5315bd41fc79999555097602f629a1285
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="customize-visualization-titles-legends-and-backgrounds-tutorial"></a>Tilpas visualiseringstitler, -forklaringer og baggrunde (selvstudium)
I dette selvstudium lærer du et par forskellige måder, hvorpå du kan tilpasse dine visualiseringer.   Der findes mange muligheder for at tilpasse dine visualiseringer. Den bedste måde at lære dem at kende på, er ved at prøve sig frem med indstillingerne under fanen Formatering (vælg ikonet med malerullen).  I denne artikel kan du se, hvordan du tilpasser en visualiserings titel, forklaring og baggrund.  

Det er ikke alle visualiseringer, der kan tilpasses. [Se en komplet oversigt](#list).  

Se Amanda tilpasse visualiseringerne i hendes rapport (spol frem til 4:50 i videoen). Følg derefter instruktionerne nedenfor for selv at prøve det med dine egne data.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="customize-visualization-titles-in-reports"></a>Tilpas titler på visualiseringer i rapporter
Hvis du vil følge med, skal du logge på app.powerbi og [åbne rapporten Retail Analysis Sample](sample-datasets.md) i [redigeringsvisning](service-interact-with-a-report-in-editing-view.md).

> [!NOTE]
> Når du fastgør en visualisering på et dashboard, bliver den til et dashboardfelt.  Selve felterne kan også tilpasses med [nye titler og undertitler, links og tilpasning af størrelsen](service-dashboard-edit-tile.md).
> 
> 

1. Gå til siden "New Stores" i rapporten, og vælg søjlediagrammet "Open Store Count by Open Month".
2. I ruden Visualiseringer kan du vælge ikonet med malerullen for at få vist formateringsindstillingerne.  og vælg **Titel** for at udvide den sektion.  
   
   ![](media/power-bi-visualization-customize-title-background-and-legend/power-bi-formatting-menu.png)
3. Slå **Titel** til eller fra ved at vælge skyderen Til (eller Fra). Lad den stå på **Til**.  
   
   ![](media/power-bi-visualization-customize-title-background-and-legend/onoffslider.png)
4. Jeg retter **Titeltekst** ved at skrive **Store count by month opened** i tekstfeltet.  
5. Ret **Skriftfarve** til orange og **Baggrundsfarve** til gul.
   
   * Vælg rullelisten, og vælg en farve fra **Temafarver**, **Seneste farver** eller **Brugerdefineret farve**.
   * Vælg rullelisten for at lukke farvevinduet.  
     ![](media/power-bi-visualization-customize-title-background-and-legend/customizecolorpicker.png)
   
   Du kan til enhver tid gendanne de oprindelige farver ved at vælge **Vend tilbage til standard** i farvevinduet.
6. Øg tekststørrelsen til 12.
7. Den sidste tilpasning af diagramtitlen er at justere placeringen, så den står midt i visualiseringen. Som standard er titlen venstrejusteret.  
   ![](media/power-bi-visualization-customize-title-background-and-legend/customizealign.png)
   
    På dette punkt i selvstudiet skulle **titlen** i dit søjlediagram se nogenlunde sådan ud:  
    ![](media/power-bi-visualization-customize-title-background-and-legend/tutorialprogress1.png)
   
    Hvis du vil fjerne alle tilpasningerne af titlen, skal du vælge **Vend tilbage til standard** nederst i ruden **Titel**.  
    ![](media/power-bi-visualization-customize-title-background-and-legend/revertall.png)

## <a name="customize-visualization-backgrounds"></a>Tilpas baggrunden i en visualisering
Udvid indstillingerne under Baggrund i det samme søjlediagram.

1. Du kan slå baggrunden til og fra ved at angive skyderen til Til (eller Fra). Lad den stå på **Til**.
2. Skift baggrundsfarve til 74 % grå.
   
   * Vælg rullelisten, og vælg en grå farve fra **Temafarver**, **Seneste farver** eller **Brugerdefineret farve**.
   * Ret Gennemsigtighed til 74 %.   
     ![](media/power-bi-visualization-customize-title-background-and-legend/power-bi-customize-background.png)
   
   Hvis du vil fjerne alle tilpasningerne af baggrunden, skal du vælge **Vend tilbage til standard** nederst i ruden **Baggrund**.

## <a name="customize-visualization-legends"></a>Tilpas forklaringer i en visualisering
1. Åbn rapportsiden **Overview**, og vælg diagrammet "Total Sales Variance by FiscalMonth and District Manager".
2. Under fanen Visualiseringer skal du vælge ikonet med malerullen for at åbne ruden Formatering.  
3. Udvid indstillingerne under **Forklaring**.
   
      ![](media/power-bi-visualization-customize-title-background-and-legend/legend.png)
4. Du kan slå forklaringen til og fra ved at angive skyderen til Til (eller Fra). Lad den stå på **Til**.
5. Flyt forklaringen til venstre side af visualiseringen.    
6. Føj en titel til forklaringen ved at slå **Titel** **Til**, og skriv **Chefer** i feltet **Navn på forklaring**.
   ![](media/power-bi-visualization-customize-title-background-and-legend/legend-move.png)
   
   Hvis du vil fjerne alle tilpasningerne af forklaringen, skal du vælge **Vend tilbage til standard** nederst i ruden **Forklaring**.

<a name="list"></a>

## <a name="visualization-types-that-can-be-customized"></a>Visualiseringstyper, der kan tilpasses
| Visualisering | Titel | Baggrund | Forklaring |
|:--- |:--- |:--- |:--- |
| Områdediagram |ja |ja |ja |
| Liggende søjlediagram |ja |ja |ja |
| Kort |ja |ja |i/t |
| Kort med flere rækker |ja |ja |i/t |
| Søjlediagram |ja |ja |ja |
| Kombinationsdiagram |ja |ja |ja |
| Kransediagram |ja |ja |ja |
| Kartogram |ja |ja |ja |
| Tragt |ja |ja |i/t |
| Måler |ja |ja |i/t |
| KPI |ja |ja |i/t |
| Kurvediagram |ja |ja |ja |
| Kort |ja |ja |ja |
| Matrix |ja |ja |i/t |
| Cirkeldiagram |ja |ja |ja |
| Punktdiagram |ja |ja |ja |
| Udsnit |ja |ja |i/t |
| Tabel |ja |ja |i/t |
| Tekstfelt |nej |ja |i/t |
| Træstruktur |ja |ja |ja |
| Vandfaldsdiagram |ja |ja |ja |

## <a name="next-steps"></a>Næste trin
Få mere at vide om [Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)  
[Tilpas X- og Y-aksen](power-bi-visualization-customize-x-axis-and-y-axis.md)  
[Tilpas farver og akseegenskaber](service-getting-started-with-color-formatting-and-axis-properties.md)  
[Power BI – Grundlæggende begreber](service-basic-concepts.md)  
Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

