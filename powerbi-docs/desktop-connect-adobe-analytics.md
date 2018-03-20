---
title: "Opret forbindelse til Adobe Analytics i Power BI Desktop (prøveversion)"
description: Opret nemt forbindelse til og brug Adobe Analytics i Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: efd6d066e2f98f86248730917c2f4aa0c8a39983
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2018
---
# <a name="connect-to-adobe-analytics-in-power-bi-desktop-preview"></a>Opret forbindelse til Adobe Analytics i Power BI Desktop (prøveversion)
I **Power BI Desktop** kan du oprette forbindelse til **Adobe Analytics** og bruge de underliggende data på samme måde som enhver anden datakilde i Power BI Desktop. 

![Hent data fra Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

## <a name="enable-the-adobe-analytics-connector-preview"></a>Aktivér prøveversionen af Adobe Analytics-connector 
Da **Adobe Analytics**-connector i øjeblikket er en prøveversion, skal du aktivere prøveversionsfunktionen, før connectoren er tilgængelig i vinduet **Hent data**. Du aktiverer prøveversionsfunktionen ved at vælge **Filer > Indstillinger > Indstillinger> Funktioner til eksempelvisning** i Power BI Desktop og derefter markere afkrydsningsfeltet ud for **Bogmærker**. 

![Aktivér prøveversionen af Adobe Analytics-connector under Indstillinger](media/desktop-connect-adobe-analytics/connect-adobe-analytics_02.png)

Du skal genstarte **Power BI Desktop**, når du har aktiveret prøveversionen af Adobe Analytics-connectoren.

## <a name="connect-to-adobe-analytics-data"></a>Opret forbindelse til Adobe Analytics-data
Du opretter forbindelse til **Adobe Analytics**-data ved at vælge **Hent data** på båndet **Hjem** i Power BI Desktop. Vælg **Onlinetjenester** under kategorier til venstre, så kan du se **Adobe Analytics-connector**.

![Hent data fra Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

I vinduet **Adobe Analytics**, der vises, skal du vælge knappen **Log på** og angive dine legitimationsoplysninger for at logge på din Adobe Analytics-konto. Vinduet til at logge på Adobe vises, som vist på følgende billede.

![Log på Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_03.png)

Når du bliver bedt om det, skal du angive dit brugernavn og din adgangskode. Når du har oprettet forbindelse, kan du se eksempler på og vælge flere dimensioner og målinger i dialogboksen **Navigator** i Power BI, som du kan bruge til at oprette et enkelt tabellarisk output. Du kan også angive andre nødvendige inputparametre, som kræves for de valgte elementer. 

![Vælg data ved hjælp af Navigator](media/desktop-connect-adobe-analytics/connect-adobe-analytics_04.png)

Du kan **indlæse** den valgte tabel, der fører hele tabellen ind i **Power BI Desktop**, eller du kan **redigere** forespørgslen, der åbner **Forespørgselseditor**, så du kan filtrere og finindstille det datasæt, du vil bruge, og derefter indlæse dette finindstillede datasæt i **Power BI Desktop**.

![Indlæs eller rediger data i Navigator](media/desktop-connect-adobe-analytics/connect-adobe-analytics_05.png)


## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

