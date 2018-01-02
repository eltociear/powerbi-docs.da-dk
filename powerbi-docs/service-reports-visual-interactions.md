---
title: Rediger, hvordan visualiseringer interagerer i en rapport
description: Dokumentation til, hvordan visuelle interaktioner indstilles i en Microsoft Power BI-rapport.
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
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Visuelle interaktioner i en Power BI-rapport
Som standard kan visualiseringer på en rapportside bruges til tværgående filtrering og tværgående fremhævning af de andre visualiseringer på siden.
Hvis der for eksempel vælges en delstat på en kortvisualisering, fremhæves søjlediagrammet, og kurvediagrammet filtreres for kun at vise data, som gælder for denne ene delstat.
Se [Om filtrering og fremhævning](power-bi-reports-filters-and-highlighting.md).

Hvis du vil ændre denne standardfunktionsmåde, skal du bruge kontrolelementet **Visuel interaktion**. Visuelle interaktioner er kun tilgængelige i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md). Hvis en rapport er blevet delt med dig, har du ikke adgang til visuelle interaktioner.

> [!NOTE]
> Begreberne *tværgående filter* og *tværgående fremhævning* bruges til at skelne mellem den funktionsmåde, der er beskrevet her, og hvad der sker, når du bruger ruden **Filtre** til at filtrere og fremhæve visualiseringer.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Vælg en visualisering for at aktivere den.  
2. Slå **Visuelle interaktioner** til ved at vælge det på den øverste menulinje. Læg mærke til filter- og fremhævningsikonerne, der vises, når du peger på andre visualiseringer på rapportsiden.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. Find ud af, hvilke indvirkning den valgte visualisering skal have på de andre.  
   
   * Hvis den skal filtrere den anden visualisering i tværgående retning, skal du vælge **filterikonet** ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Hvis den skal fremhæve den pågældende visualisering i tværgående retning, skal du vælge **fremhævningsikonet** ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Hvis den ikke skal have nogen indvirkning, kan du vælge ikonet for **ingen indvirkning** ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).
4. Gentag eventuelt for alle andre visualiseringer på rapportsiden.

### <a name="next-steps"></a>Næste trin
[Sådan bruger du rapportfiltre](power-bi-how-to-report-filter.md)

[Filtre og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

