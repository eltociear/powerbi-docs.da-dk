---
title: Brug Ydeevneanalyse for at undersøge rapport element ydeevne i Power BI Desktop
description: Find ud af, hvordan visuelle elementer og elementer i rapporten klarer sig med hensyn til ressourceforbrug og reaktionsevne
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1851e0a55bf01073a6591f64de43830a72eca89b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854407"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>Brug Ydeevneanalyse for at undersøge rapport element ydeevne

I **Power BI Desktop** kan du finde ud af, hvordan hver af dine rapportelementer, f.eks visuelle elementer og DAX-formler, der agerer. Ved hjælp af den **Ydeevneanalyse**, kan du se og post logfører, måle, hvor hver af dine rapportelementer udfører, når brugerne interagerer med dem, og hvilke aspekter af deres ydeevne, er de fleste (eller mindst) ressourcekrævende.

![Ydeevneanalyse](media/desktop-performance-analyzer/performance-analyzer-01.png)

Ydeevneanalyse undersøger og viser den tid, der er nødvendige for at opdatere eller at alle visualiseringer, starte Brugerinteraktioner og indeholder oplysninger, så du kan få vist, analysere ned eller eksportere resultaterne. Ydeevneanalyse kan hjælpe dig med at identificere visualiseringer, der påvirker ydeevnen i dine rapporter, og at identificere årsagen til virkningen.

## <a name="displaying-the-performance-analyzer-pane"></a>Få vist ruden Ydeevneanalyse

I **Power BI Desktop** skal du vælge den **visning** båndet. I den **Vis** område på den **visning** båndet, kan du markere afkrydsningsfeltet ud for **Ydeevneanalyse** at få vist ruden Ydeevneanalyse.

![Vælg Ydeevneanalyse båndet](media/desktop-performance-analyzer/performance-analyzer-02.png)

Når du har valgt, vises Ydeevneanalyse i sit eget ruden til højre for rapportcanvasset.

## <a name="using-performance-analyzer"></a>Ved hjælp af Ydeevneanalyse

Målinger af ydeevnen analyzer behandlingstiden (herunder tid til at oprette eller opdatere en visualisering) kræves for at opdatere elementer i rapporten startet som følge af brugerinput, der resulterer i kørsel af en forespørgsel. Justere et udsnit kræver f.eks, den udsnittet visualisering skal ændres, en forespørgsel sendes til datamodellen, og de berørte visuelle elementer, der skal opdateres på grund af de nye indstillinger. 

Hvis du vil have Ydeevneanalyse starte optagelsen, skal du blot vælge **starte optagelsen**

![Start optagelse](media/desktop-performance-analyzer/performance-analyzer-03.png)

Handlinger, du tager i rapporten vises og logget i ruden Ydeevneanalyse i den rækkefølge, indlæses den visuelle gengivelse af Power BI. F.eks. måske du have en rapport, som brugere har sagt tager lang tid at opdatere. Eller visse visuelle elementer i en rapport tage lang tid der vises, når en skyder er justeret. Ydeevneanalyse kan se, hvilke visualiseringer er det pågældende element, og identificerer, hvilke aspekter af det visuelle element du benytter dig den længste varighed til at behandle. 

Når du starter optagelsen, den **starte optagelsen** knappen er nedtonet out (inaktiv, da du allerede er begyndt at optagelse) og **stoppe** knap er aktiv. 

Ydeevneanalyse indsamler og viser oplysninger om måling af ydeevne i realtid. Så hver gang du klikker på et visuelt element, flytte et udsnit, eller på anden måde interagere, viser Ydeevneanalyse med det samme ydeevne resultaterne i ruden.

Hvis ruden indeholder yderligere oplysninger, end der kan vises, vises et rullepanel til at navigere til yderligere oplysninger.

Hver interaktion har et afsnit id i den rude, der beskriver den handling, der startede logposterne. På følgende billede er interaktionen, brugerne har ændret et udsnit.

![Afsnit, der er baseret på typen af interaktion](media/desktop-performance-analyzer/performance-analyzer-04.png)

Hver enkelt visualisering logoplysninger indeholder den anvendte tid (varighed) for at fuldføre følgende kategorier af opgaver:

* **DAX-forespørgslen** – Hvis en DAX-forespørgsel var påkrævet, er tiden mellem det visuelle element, der sender forespørgslen, og for Analysis Services for at returnere resultaterne.
* **Visuel visning** -tid, det visuelle element til at tegne på skærmen, herunder påkrævede tid til at hente en hvilken som helst webbilleder eller geokodning. 
* **Andre** -tid, der kræves af det visuelle element til klargøring af forespørgsler, venter på andre visuelle elementer at fuldføre eller udføre andre behandling i baggrunden.

![elementer af logoplysninger](media/desktop-performance-analyzer/performance-analyzer-06.png)

Når du har været i forbindelse med elementer i den rapport, du vil måle med Ydeevneanalyse, kan du vælge den **stoppe** knap. Oplysningerne om ydeevne forbliver i ruden, når du har valgt **Stop** for dig at analysere.

Vælg for at rydde ud af oplysningerne i ruden Ydeevneanalyse **Ryd**. Alle oplysninger, der er slettet og gemmes ikke, når du vælger **Ryd**. Se næste afsnit for at se, hvordan du gemmer oplysninger i loggene. 

## <a name="refreshing-visuals"></a>Opdatering af visuelle elementer

Du kan vælge **visualiseringerne** i ruden Ydeevneanalyse at opdatere alle visuelle elementer på den aktuelle side i rapporten, og dermed har Ydeevneanalyse indsamle oplysninger om alle visualiseringer.

Du kan også opdatere enkelte visualiseringer. Når Ydeevneanalyse optagelsen, kan du vælge **Opdater denne visual** blev fundet i øverste højre hjørne af hver enkelt visualisering, for at opdatere Visualiseringen, og hente oplysninger om dets ydeevne.

![Opdater et individuelt visuelt element](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>Lagring af ydeevneoplysninger om

Du kan gemme de oplysninger, der opretter Ydeevneanalyse om en rapport ved at vælge den **Eksportér** knap. Hvis du vælger **Eksportér** opretter en .json fil med oplysninger fra ruden Ydeevneanalyse. 

![Gem logfilen for Ydeevneanalyse](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om **Power BI Desktop**, og hvordan du kommer i gang, i følgende artikler.

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Opret forbindelse til data i Power BI Desktop](desktop-connect-to-data.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)   

