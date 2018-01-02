---
title: Kransediagrammer i Power BI (selvstudium)
description: 'Selvstudium: Kransediagrammer i Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Kransediagrammer i Power BI (selvstudium)
Et kransediagram ligner meget et cirkeldiagram og viser relationen mellem dele af en helhed. Den eneste forskel er, at centreret i det er tomt og giver plads til en etiket eller et ikon.

## <a name="create-a-doughnut-chart"></a>Opret et kransediagram
Log på Power BI for at følge fremgangsmåden, og vælg **Hent Data** \> **Eksempler**  \>  **Eksempel på detailhandelsanalyse** \> **Opret forbindelse**. 

1. Fra dashboardet skal du markere feltet **Total stores** (Butikker i alt) for at åbne rapporten "Eksempel på detailhandelsanalyse".
2. Vælg **Rediger rapport** for at åbne rapporten i Redigeringsvisning.
3. [Tilføj en ny rapportside](power-bi-report-add-page.md).
4. Opret et kransediagram, der viser dette års salg efter kategori.
   
   * I ruden **Felter** skal du markere **Sales** \> **Last Year Sales** (Salg/Sidste års salg).
   * Konvertér til et kransediagram. Hvis sidste års salg ikke findes i området **Værdier**, skal du trække det derhen.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * Vælg **Element** \> **Kategori** for at føje det til området **Forklaring**. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Summen af kransediagrammets værdier skal give 100 %.
* Er der for mange kategorier, er det svært at læse og fortolke diagrammet.
* Kransediagrammer er bedst egnet til at sammenligne en bestemt del med helheden og ikke sammenligne de enkelte dele med hinanden. 

## <a name="next-steps"></a>Næste trin
[Rapporter i Power BI](service-reports.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

