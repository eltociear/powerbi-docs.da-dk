---
title: Rediger, hvordan visualiseringer interagerer i en rapport
description: Dokumentation til, hvordan visuelle interaktioner indstilles i en rapport i Microsoft Power BI-tjenesten og i en Power BI Desktop-rapport.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/11/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 6f739992ed282ada92b1049df09a8b5d4b3938a9
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61405915"
---
# <a name="change-how-visuals-interact-in-a-power-bi-report"></a>Rediger, hvordan visualiseringer interagerer i en Power BI-rapport
Hvis du har redigeringsrettigheder til en rapport, kan du bruge **Visuelle interaktioner** til at ændre, hvor visualiseringer på en rapportside påvirker hinanden. 

Som standard kan visualiseringer på en rapportside bruges til tværgående filtrering og tværgående fremhævning af de andre visualiseringer på siden.
Hvis der for eksempel vælges en delstat på en kortvisualisering, fremhæves søjlediagrammet, og kurvediagrammet filtreres for kun at vise data, som gælder for denne ene delstat.
Se [Om filtrering og fremhævning](power-bi-reports-filters-and-highlighting.md). Og hvis du har visuelle effekter, der understøtter [detailudledning](consumer/end-user-drill.md) som standard, har det ingen indvirkning på andre visualiseringer på rapportsiden, at du foretager detailudledning i én visualisering. Men begge disse standardfunktionsmåder kan tilsidesættes, og interaktioner indstilles for den enkelte visualisering.

Denne artikel viser, hvordan du kan bruge **visuelle interaktioner** i Power BI-tjenestens [redigeringstilstand](service-interact-with-a-report-in-editing-view.md) og i Power BI Desktop. Hvis en rapport er blevet delt med dig, kan du ikke ændre indstillingerne for de visuelle interaktioner.

> [!NOTE]
> Begreberne *tværgående filter* og *tværgående fremhævning* bruges til at skelne mellem den funktionsmåde, der er beskrevet her, og hvad der sker, når du bruger ruden **Filtre** til at filtrere og fremhæve visualiseringer.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Vælg en visualisering for at aktivere den.  
2. Vis indstillingerne for **visuelle interaktioner**.
    - Vælg på rullelisten for menulinjen Rapport i Power BI-tjenesten.

       ![Rulleliste med visuelle interaktioner](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - Vælg **Format > Interaktioner** under Desktop.

        ![vælg Format og derefter Interaktioner](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. Hvis du vil aktivere interaktionskontrolelementerne for visualisering, skal du vælge **Rediger interaktioner**. Power BI tilføjes ikoner for tværgående filter og tværgående fremhævning til alle de andre visualiseringer på rapportsiden.
   
    ![rapport, hvor Visuelle interaktioner er slået til](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. Find ud af, hvilke indvirkning den valgte visualisering skal have på de andre.  Og gentag eventuelt for alle andre visualiseringer på rapportsiden.
   
   * Hvis den skal filtrere visualiseringen i tværgående retning, skal du vælge ikonet **Filter** ![filterikon](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Hvis den skal fremhæve visualiseringen i tværgående retning, skal du vælge ikonet **Fremhæv** ![fremhævningsikon](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Hvis den ikke skal have nogen indvirkning, kan du vælge ikonet **Ingen indvirkning** ![ingen indvirkning-ikon](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).

4. Hvis du vil aktivere kontrolelementer til detailudledning, skal du vælge **Boring filtrerer andre visuelle elementer**.  Når du analyserer ned (og op) i en visualisering, ændres de andre visualiseringer på rapportsiden for at afspejle det aktuelle valg af detailudledning. 

   ![video om aktivering af analyseringskontrolelementer](media/service-reports-visual-interactions/drill2.gif)

