---
title: Rediger, hvordan et diagram sorteres i en rapport i Power BI
description: Rediger, hvordan et diagram sorteres i en rapport i Power BI
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 13da4602306b1218baee81909d37897524f6dfc9
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/21/2017
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Rediger, hvordan et diagram sorteres i en rapport i Power BI
I en Power BI-rapport kan du sortere de fleste visualiseringer alfabetisk efter navnene på kategorierne i diagrammet eller efter de numeriske værdier for hver kategori. Dette diagram er f.eks. sorteret efter lagernavn.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Det er nemt at ændre sorteringen fra en kategori (gem navn) til en værdi (salg pr. kvadratfod) i stedet.

1. Vælg ellipserne (...), og vælg at **sortere efter salg pr. kvadratfod**.
2. Du kan evt. vælge sorteringsikonet ![](media/power-bi-report-change-sort/sorticon.png) for at skifte til **Faldende**.
   
   ![](media/power-bi-report-change-sort/sortby.gif)
   
   **BEMÆRK!** Det er ikke alle visuelle elementer, der kan sorteres.  Følgende visuelle elementer kan f.eks. ikke sorteres: Træstruktur, Kort (Map), Kartogram, Punkt, Måler, Kort (Card), Kort med flere rækker, Vandfald.

## <a name="sorting-using-other-criteria"></a>Sortering ved hjælp af andre kriterier
Der kan nogle gange være behov for at sortere visuelle elementer med brug af et andet felt eller andre kriterier.  Det kan f.eks. være, at du vil sortere efter måned (og ikke i alfabetisk rækkefølge), eller at du vil sortere efter hele tal i stedet for cifre (f.eks. 0, 1, 9, 20 og ikke 0, 1, 20, 9).  

I nogle tilfælde kan du muligvis sortere det visuelle element på den måde, du ønsker, f.eks. efter måned.  Men er det ikke muligt, kan det være fordi, datasættet bag rapporten skal tilpasses. Her er nogle løsninger:

* I Power BI Desktop [skal du bruge fanen til modellering af dataværktøj til at sortere efter en anden kolonne](desktop-sort-by-column.md).
* Hvis du arbejder med Excel og ejer datasættet, kan du tilføje en ny kolonne, der sammenkæder månedens navn og nummer. Opdater derefter datasættet, eller importér det igen, for at få vist den nye kolonne i området Felter.
* I Excel skal du sørge for, at numeriske kolonner er mærket som "heltal" eller "decimal" og ikke som "tekst".

## <a name="next-steps"></a>Næste trin
Få mere at vide om [Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md).

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

