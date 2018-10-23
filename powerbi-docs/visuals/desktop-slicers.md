---
title: Brug af udsnitsværktøjer i Power BI Desktop
description: Du kan bruge udsnitsværktøjer i Power BI Desktop til at filtrere, fremhæve og tilpasse rapporter
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: df4afe91de955eabfba6eeea9022cc5f9475cc33
ms.sourcegitcommit: b8461c1876bfe47bf71c87c7820266993f82c0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/15/2018
ms.locfileid: "49336846"
---
# <a name="using-slicers-power-bi-desktop"></a>Brug af udsnitsværktøjer i Power BI Desktop

Du kan bruge et **udsnitsværktøj** i **Power BI Desktop** til at filtrere resultaterne i en visualisering på din rapportside. Med udsnitsværktøjer kan du nemt justere det filter, der er anvendt, ved at interagere med selve udsnitsværktøjet. Du kan også angive indstillinger for, hvordan udsnitsværktøjet vises, og hvordan du interagerer med det. På følgende billede vises et udsnitsværktøj med rullelisten *type* synlig. 

![udsnit i Desktop](./media/desktop-slicers/desktop-slicers_01.png)

Du kan få vist et udsnitsværktøj fra en af følgende typer:

* Liste
* Rulleliste
* Mellem
* Mindre end eller lig med
* Større end eller lig med

Du kan føje et udsnitsværktøj til en rapport ved at klikke på visualiseringen **udsnitsværktøj** i ruden **Visualiseringer**.

![typen af udsnitsvisual](./media/desktop-slicers/desktop-slicers_02.png)

Udsnitsværktøjer fungerer på samme måde i både **Power BI Desktop** og **Power BI-tjenesten**. I [udsnitsværktøjer i Power BI-tjenesten](power-bi-visualization-slicers.md) kan du finde en artikel om, hvordan du bruger udsnitsværktøjer.

## <a name="synchronize-slicers-across-report-pages"></a>Synkroniser udsnitsværktøjer på tværs af rapportsider

I **Power BI Desktop** kan du synkronisere udsnitsværktøjer på tværs af flere rapportsider. I ruden **Visning** på båndet skal du vælge **Synkroniser udsnitsværktøjer** for at synkronisere udsnitsværktøjer. Når du synkroniserer udsnitsværktøjer, vises ruden **Synkroniser udsnitsværktøjer**, som vist på følgende billede.

![vise ruden Synkroniser udsnit](./media/desktop-slicers/desktop-slicers_03.png)

I ruden **Synkroniser udsnitsværktøjer** kan du angive, hvordan udsnitsværktøjet skal synkroniseres på tværs af rapportsider. Du kan angive, om hvert udsnitsværktøj skal **anvendes** på hver enkelt rapportside, og om udsnitsværktøjet skal være **synligt** på hver enkelt rapportside.

Du kan f.eks. placere et udsnitsværktøj på **side 2** i rapporten, som vist på følgende billede. Du kan derefter vælge, om dette udsnitsværktøj skal *anvendes* på hver valgt side, og om dette udsnitsværktøj skal være *synligt* på hver valgt side i rapporten. Du kan anvende en hvilken som helst kombination af disse for hvert udsnitsværktøj. 

![synkroniser udsnit](./media/desktop-slicers/desktop-slicers_04.png)

Hvis du bruger linket **Føj til alle** i ruden, anvendes det valgte udsnitsværktøj på alle sider i rapporten.


Bemærk, at de valg, der vises i ruden **Synkroniser udsnitsværktøjer**, kun anvendes for det *valgte udsnitsværktøj*. Du kan anvende flere udsnitsværktøjer på forskellige sider og bruge ruden til at definere, hvordan hvert udsnitsværktøj anvendes på tværs af forskellige sider i rapporten. 

Når du synkroniserer dine valgte udsnitsværktøjer, synkroniseres andre valg såsom formatering, redigering og sletning *ikke*. 

## <a name="advanced-options-for-slicers"></a>Avancerede indstillinger for udsnit

Du kan også anvende et **gruppenavn** på en samling af udsnit i sektionen **Avancerede indstillinger** i ruden **Synkroniser udsnit**, og få udsnit, der deler den samme gruppe, synkroniseret på tværs af sider. 

![gruppenavn for udsnit](./media/desktop-slicers/desktop-slicers_05.png)

Du kan bruge denne funktion til at oprette en brugerdefineret gruppe af udsnit, som skal være synkroniseret. Der angives et standardnavn, men du kan bruge et andet navn, hvis du foretrækker det. 

Gruppenavnet giver yderligere fleksibilitet i forbindelse med udsnit. Du kan oprette separate grupper for at synkronisere udsnit, der bruger det samme felt, eller anbringe udsnit, der bruger forskellige felter, i samme gruppe. 

## <a name="how-filtering-affects-selection-in-slicers"></a>Sådan påvirker filtrering valg i udsnitsværktøj

Hvis du vælger noget i et udsnitsværktøj og derefter anvender et filter, som normalt ville fjerne det valgte element, forbliver den nederst på listen over elementer i udsnitsværktøjet. Hvis filteret fjernes, findes valget stadig i udsnitsværktøjet. Hvis du fjerner valget af elementet fra udsnitsværktøjet, vil du se, at det forsvinder fra listen.

![bevaret valg i udsnitsværktøj](./media/desktop-slicers/retained-selection-in-slicers.gif)


## <a name="next-steps"></a>Næste trin

Du vil måske også være interesseret i følgende artikler:

* [Udsnitsværktøjer i Power BI-tjenesten](power-bi-visualization-slicers.md)
* [Brug udsnitsværktøjet til numerisk område i Power BI Desktop](../desktop-slicer-numeric-range.md)
* [Brug et udsnitsværktøj og filter til relativ dato i Power BI Desktop](desktop-slicer-filter-date-range.md)

