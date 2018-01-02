---
title: "Træstrukturer i Power BI (selvstudium)"
description: "Selvstudium: Træstrukturer i Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: IkJda4O7oGs
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 5e5bc8eaa4e710e6564ee6f1d3ea1bfcf7f28127
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="treemaps-in-power-bi-tutorial"></a>Træstrukturer i Power BI (selvstudium)
Træstrukturer viser hierarkiske data som et sæt af indlejrede rektangler.  Hvert niveau i hierarkiet er repræsenteret af et farvet rektangel (ofte kaldte en "gren"), der indeholder andre rektangler ("blade").  Pladsen inde i hvert rektangel allokeres ud fra den kvantitative værdi, der måles, hvor rektanglerne er arrangeret efter størrelse fra øverste til venstre (størst) til nederst til højre (mindst).

![](media/power-bi-visualization-treemaps/pbi-nancy_viz_treemap.png)

Hvis jeg f.eks. analyserer mit salg, så kunne jeg have nogle rektangler (grene) på øverste niveau for tøjkategorierne: **Urban**, **Rural**, **Youth** og **Mix**.  Min rektangel med kategorier indeholder mindre rektangler (blade) for tøjproducenterne inden for den pågældende kategori, og disse mindre rektangler får størrelse og skygge baseret på det antal, der er solgt.  I grenen **Urban** ovenfor er der blevet solgt meget tøj fra Maximus og mindre fra Natura og Fama og meget lidt fra Leo.  Så grenen **Urban** i min træstruktur har det største rektangel for Maximus (i øverste venstre hjørne), lidt mindre rektangler for Natura og Fama og mange andre rektangler, der repræsenterer alt det andet tøj, der er blevet solgt, og et lillebitte rektangel for Leo.  Og jeg kan sammenligne antallet af varer, der er solgt på tværs af de andre tøjkategorier, ved at sammenligne størrelse og skygge på hver bladnode – jo større rektangel og jo mørkere skygge, desto højere værdi.

## <a name="when-to-use-a-treemap"></a>Hvornår bruger man en træstruktur?
Træstrukturer er et godt valg:

* til at vise store mængder hierarkiske data
* når et liggende søjlediagram ikke effektivt kan håndtere det store antal værdier
* til at vise proportionerne mellem de enkelte dele og et hele
* til at vise fordelingsmønsteret for målingen på tværs af hvert niveau af kategorier i hierarkiet
* til at vise attributter ved hjælp af størrelse og farvekodning
* til at identificere mønstre, udenforliggende værdier, de vigtigste bidragsydere samt undtagelser.

## <a name="create-a-basic-treemap"></a>Opret en grundlæggende træstruktur
Vil du gerne se en anden oprette en træstruktur først?  Gå til 2:10 i denne video for at se Amanda oprette en træstruktur.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Eller opret din egen træstruktur. I denne vejledning bruges Retail Analysis Sample (Eksempel på detailhandelsanalyse). For at kunne følge med skal du [downloade eksemplet](sample-datasets.md), logge på Power BI og vælge **Hent data \> Excel-projektmappe \> Opret forbindelse \> Retail Analysis Sample**.**xlsx**.

1. Start i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md), og vælg målingen **Sales** > **Last Years Sales**.   
   ![](media/power-bi-visualization-treemaps/treemapfirstvalue_new.png)
2. Konvertér diagrammet til en træstruktur.  
   ![](media/power-bi-visualization-treemaps/treemapconvertto_new.png)
3. Træk **Item** > **Category** til feltet **Group**. Power BI opretter en træstruktur, hvor størrelsen af rektanglerne afspejler det samlede salg, og farven repræsenterer kategorien.  Egentlig har du oprettet et hierarki, som visuelt beskriver den relative størrelse af det samlede salg efter kategori.  Kategorien **Mens** har det højeste salg, og kategorien **Hosiery** har det laveste.
   ![](media/power-bi-visualization-treemaps/treemapcomplete_new.png)
4. Træk **Store** > **Chain** til feltet **Detaljer** for at fuldende din træstruktur. Nu kan du sammenligne sidste års salg efter kategori og kæde.   
   ![](media/power-bi-visualization-treemaps/treemap_addgroup_new.png)
   
   > [!NOTE]
   > Farvemætning og Detaljer kan ikke bruges samtidig.
   > 
   > 
5. Hold markøren over **Chain** for at få vist værktøjstippet til den del af **Category**.  Hvis du f.eks. holder markøren over **Lindseys** i rektanglet **040 Juniors**, vises værktøjstippet for Lindsey's del af kategorien Juniors.  
   ![](media/power-bi-visualization-treemaps/treemaphoverdetail_new.png)
6. [Tilføj træstrukturen som et dashboardfelt (fastgør det visuelle element)](service-dashboard-tiles.md). 
7. [Gem rapporten](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Fremhævning og krydsfiltrering
Du kan få mere at vide om brug af ruden Filtre under [Føj et filter til en rapport](power-bi-report-add-filter.md).

Fremhævning af en kategori eller detaljer i en træstruktur krydsfremhæver og krydsfiltrerer de andre visuelle elementer på rapportsiden ... og vice versa. For at følge med skal du enten tilføje nogle visuelle elementer på den samme side eller kopiere/indsætte træstrukturen på en rapportside, hvor der allerede er andre visuelle elementer.

1. Vælg enten Category eller Chain i en kategori på træstrukturen.  Dette krydsfremhæver de andre visualiseringer på siden. Hvis du f.eks. vælger **050 Shoes**, kan du se, at sidste års salg af sko var 3.640.471 USD, hvoraf 2.174.185 USD kom fra Fashions Direct.  
   ![](media/power-bi-visualization-treemaps/treemaphiliting.png)
2. I cirkeldiagrammet **Last Year Sales by Chain** skal du vælge udsnittet **Fashions Direct**.  
   ![](media/power-bi-visualization-treemaps/treemapnoowl.gif)
3. Hvis du vil administrere, hvordan diagrammer krydsfremhæver og krydsfiltrerer hinanden, skal du se [Interaktioner mellem visuelle elementer i en Power BI-rapport](service-reports-visual-interactions.md)

## <a name="next-steps"></a>Næste trin
[Rapporter i Power BI](service-reports.md)  
[Føj et visuelt element til en rapport](power-bi-report-add-visualizations-i.md)  
[Typer af visuelle elementer i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
[ Fastgør et visuelt element til et dashboard](service-dashboard-pin-tile-from-report.md)  
[Power BI – Grundlæggende begreber](service-basic-concepts.md)  
[Prøv det – det er gratis!](https://powerbi.com/)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)  

