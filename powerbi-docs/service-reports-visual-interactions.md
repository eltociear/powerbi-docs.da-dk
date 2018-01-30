---
title: Rediger, hvordan visualiseringer interagerer i en rapport
description: Dokumentation til, hvordan visuelle interaktioner indstilles i en rapport i Microsoft Power BI-tjenesten og i en Power BI Desktop-rapport.
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/10/2018
ms.author: mihart
ms.openlocfilehash: a7c4db0044772c28a3cb7a62649de3001945246c
ms.sourcegitcommit: afd6e9e6f8b192b26486cd04d2cbc9de046911b3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/11/2018
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Visuelle interaktioner i en Power BI-rapport
Hvis du har redigeringsrettigheder til en rapport, kan du bruge **Visuelle interaktioner** til at ændre, hvor visualiseringer på en rapportside påvirker hinanden. 

Som standard kan visualiseringer på en rapportside bruges til tværgående filtrering og tværgående fremhævning af de andre visualiseringer på siden.
Hvis der for eksempel vælges en delstat på en kortvisualisering, fremhæves søjlediagrammet, og kurvediagrammet filtreres for kun at vise data, som gælder for denne ene delstat.
Se [Om filtrering og fremhævning](power-bi-reports-filters-and-highlighting.md). Og hvis du har visuelle effekter, der understøtter [detailudledning](power-bi-visualization-drill-down.md) som standard, har det ingen indvirkning på andre visualiseringer på rapportsiden, at du foretager detailudledning i én visualisering. Men begge disse standardfunktionsmåder kan tilsidesættes, og interaktioner indstilles for den enkelte visualisering.

Denne artikel viser, hvordan du kan bruge **visuelle interaktioner** i Power BI-tjenestens [redigeringstilstand](service-interact-with-a-report-in-editing-view.md) og i Power BI Desktop. Hvis en rapport er blevet delt med dig, kan du ikke ændre indstillingerne for de visuelle interaktioner.

> [!NOTE]
> Begreberne *tværgående filter* og *tværgående fremhævning* bruges til at skelne mellem den funktionsmåde, der er beskrevet her, og hvad der sker, når du bruger ruden **Filtre** til at filtrere og fremhæve visualiseringer.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Vælg en visualisering for at aktivere den.  
2. Vis indstillingerne for **visuelle interaktioner**.
    - Vælg på rullelisten for menulinjen Rapport i Power BI-tjenesten.

       ![](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - Vælg **Format > Interaktioner** under Desktop.

        ![](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. Hvis du vil aktivere interaktionskontrolelementerne for visualisering, skal du vælge **Rediger interaktioner**. Power BI tilføjes ikoner for tværgående filter og tværgående fremhævning til alle de andre visualiseringer på rapportsiden.
   
    ![](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. Find ud af, hvilke indvirkning den valgte visualisering skal have på de andre.  Og gentag eventuelt for alle andre visualiseringer på rapportsiden.
   
   * Hvis den skal filtrere visualiseringen i tværgående retning, skal du vælge **filterikonet** ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Hvis den skal fremhæve visualiseringen i tværgående retning, skal du vælge **fremhævningsikonet** ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Hvis den ikke skal have nogen indvirkning, kan du vælge ikonet for **ingen indvirkning** ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).

4. Hvis du vil aktivere kontrolelementer til detailudledning, skal du vælge **Boring filtrerer andre visuelle elementer**.  Når du analyserer ned (og op) i en visualisering, ændres de andre visualiseringer på rapportsiden for at afspejle det aktuelle valg af detailudledning. 

   ![](media/service-reports-visual-interactions/drill2.gif)

### <a name="next-steps"></a>Næste trin
[Sådan bruger du rapportfiltre](power-bi-how-to-report-filter.md)

[Filtre og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
