---
title: Brug af målinger i Power BI Desktop
description: Målinger i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 43c103dcef6caad7e9aa36ab0f1c32939ee2dda6
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2018
ms.locfileid: "39328574"
---
# <a name="measures-in-power-bi-desktop"></a>Målinger i Power BI Desktop
Du kan få hjælp af **Power BI Desktop** til at oprette indsigt i dine data med nogle få klik. Men nogle gange indeholder disse data bare ikke alt det, du skal bruge for at få svar på nogle af dine vigtigste spørgsmål. Det kan målinger hjælpe dig med.

Målinger bruges i nogle af de mest almindelige dataanalyser, f.eks. sum, gennemsnit, minimum- og maksimumværdier, optællinger eller mere avancerede beregninger, som du selv opretter vha. en DAX-formel. De beregnede resultater fra målinger ændres altid som reaktion på din interaktion med dine rapporter. Det giver mulighed hurtig og dynamisk dataudforskning ad hoc. Lad os se nærmere på det.

## <a name="understanding-measures"></a>Om målinger
I **Power BI Desktop** oprettes og bruges målinger i **Rapportvisning** eller **Datavisning**. Målinger, som du selv har oprettet, vises på listen Felter med et lommeregnerikon. Du kan navngive målinger, som du ønsker det, og føje dem til en ny eller eksisterende visualisering på samme måde som alle andre felter.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> Du er måske også interesseret i **hurtig målinger**, som er færdige målinger, som du kan vælge fra dialogbokse. De er velegnet, hvis du hurtigt vil oprette målinger, og hvis du vil have mere at vide om DAX-syntaks, da de automatisk oprettede DAX-formler er tilgængelige til gennemsyn. Tjek artiklen: [Hurtige målinger](desktop-quick-measures.md).
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions
Målinger beregner et resultat af en udtryksformel. Når du opretter dine egne målinger, skal du bruge formelsproget [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX). DAX inkluderer et bibliotek med mere end 200 funktioner, operatorer og konstruktioner, hvilket giver stor fleksibilitet, når du opretter målinger til beregning af resultater for stort alle dataanalyser.

DAX-formler ligner Excel-formler meget. DAX har oven i købet mange af de samme funktioner som DATO, SUM og TILBAGE. Men funktionerne i DAX er beregnet til at arbejde med relationsdata, som vi har i Power BI Desktop.

## <a name="lets-look-at-an-example"></a>Lad os se på et eksempel
Jane er salgschef hos Contoso. Hun er blevet bedt om at angive projektioner for forhandlersalg for det kommende regnskabsår. Hun beslutter sig for at basere sine estimater på sidste års salgsbeløb med en årlig stigning på 6 % som følge af forskellige kampagner, der er planlagt for de næste seks måneder.

For at rapportere estimaterne importerer hun sidste års salgsdata i Power BI Desktop. Hun finder feltet Salgsbeløb i tabellen Forhandlersalg. Da de importerede data kun indeholder beløb for sidste år, omdøber hun feltet Salgsbeløb til Sidste års salg. Hun trækker derefter Sidste års salg til rapportcanvassen. I en diagramvisualisering ser det ud som en enkelt værdi, der er summen af alle forhandlersalg fra sidste år.

Hun bemærker, at selvom hun ikke selv har angivet en beregning, er der angivet en automatisk. I Power BI Desktop er der automatisk blevet oprettet en måling, der summerer alle værdierne i Sidste års salg.

Men Jane har brug for en måling til at beregne salgsprojektioner for det kommende år, som er baseret på sidste års salg ganget med 1,06 for at indregne den forventede stigning på 6 %. Hun opretter sin egen måling til denne beregning. Ved hjælp af funktionen Ny måling opretter hun en ny måling og angiver derefter følgende DAX-formel:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

Derefter trækker Jane den ny måling Projekteret salg til diagrammet.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Jane har nu hurtigt og med en minimal indsats en måling til at beregne det projekterede salg. Hun kan analysere sine projektioner yderligere ved at filtrere efter bestemte forhandlere eller ved at føje andre felter til sin rapport.

## <a name="learn-more"></a>Få mere at vide
Vi har kun givet en hurtig introduktion til målinger her, men der er mange flere oplysninger, der kan hjælpe dig med at få mere at vide om, hvordan du opretter dine egne målinger. Husk at se [Selvstudium: Opret dine egne målinger i Power BI Desktop](desktop-tutorial-create-measures.md), hvor du kan downloade en eksempelfil og få trinvise vejledninger i, hvordan du opretter flere målinger.  

Hvis du vil gå mere i dybden med DAX, skal du tjekke [Grundlæggende oplysninger om DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md). [Data Analysis Expressions-referencen](https://msdn.microsoft.com/library/gg413422.aspx) indeholder detaljerede artikler om hver enkelt funktion, syntaks, operatorer og navngivningskonventioner. DAX er blevet brugt i flere år i Power Pivot i Excel og SQL Server Analysis Services, så der er også mange andre fantastiske ressourcer tilgængelig. Sørg for at se i [DAX Resource Center Wiki](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx), hvor vigtige medlemmer af BI-community'et deler deres viden om DAX.



