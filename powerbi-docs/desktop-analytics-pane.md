---
title: Brug af ruden Analytics i Power BI Desktop
description: Opret dynamiske referencelinjer til visuelle effekter i Power BI Desktop
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: add95532f645c143aea0f58200f9e3b1467320d0
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="using-the-analytics-pane-in-power-bi-desktop"></a>Brug af ruden Analytics i Power BI Desktop
Med ruden **Analytics** i **Power BI Desktop** kan du tilføje dynamiske *referencelinjer* for visuelle elementer og give vigtige tendenser eller indsigt fokus. Ruden **Analytics** findes i området **Visualiseringer** i Power BI Desktop med start fra august 2016-versionen (version 2.37.4464.321 eller nyere) eller som vist nedenfor.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> Ruden **Analytics** vises kun, når du vælger en visuel effekt på Power BI Desktop-lærredet.
> 
> 

## <a name="enable-forecasting-preview"></a>Aktivér Prognose (prøveversion)
Derudover kan du med september 2016-versionen af **Power BI Desktop** (version 2.39.4526.362 eller nyere) også udføre *prognoser* fra ruden **Analytics**. Du skal aktivere denne prøveversionsfunktion ved at gå til **Filer > Indstillinger > Indstillinger** og derefter vælge **Funktioner i prøveversion** i venstre rude. Markér afkrydsningsfeltet ud for **Prognose** for at aktivere funktionen som vist i følgende billede. Du skal genstarte **Power BI Desktop**, før ændringerne kan træde i kraft.

![](media/desktop-analytics-pane/analytics-pane_1b.png)

## <a name="using-the-analytics-pane"></a>Sådan bruges ruden Analytics
Med ruden **Analytics** kan du oprette følgende typer dynamiske referencelinjer (ikke alle linjer er tilgængelige for alle typer visuelle effekter):

* Konstantlinje for X-akse
* Konstantlinje for Y-akse
* Minimumlinje
* Maksimumlinje
* Gennemsnitslinje
* Medianlinje
* Fraktillinje

Følgende afsnit viser, hvordan du kan bruge ruden **Analytics** og dynamiske referencelinjer i dine visuelle effekter.

Få vist de tilgængelige dynamiske referencelinjer for en visuel effekt ved at følge disse trin:

1. Vælg eller opret en visuel effekt, og vælg derefter ikonet **Analytics** i ruden **Visualiseringer**.
   
   ![](media/desktop-analytics-pane/analytics-pane_2.png)
2. Vælg pil ned til den linjetype, du vil oprette, for at udvide dens indstillinger. I dette tilfælde vælger vi **Gennemsnitslinje**.
   
   ![](media/desktop-analytics-pane/analytics-pane_3.png)
3. Vælg **+ Tilføj** for at oprette en ny linje. Du kan derefter angive et navn på linjen ved at dobbeltklikke på tekstfeltet og derefter skrive navnet.
   
   Du har en række forskellige indstillinger for linjen. Du kan f.eks. vælge dens *farve*, *gennemsigtighed*, *typografi* og *position* (forhold til den visuelle effekts dataelementer), og om du vil medtage etiketten. Og som det vigtigste kan du vælge, hvilken **Måling** i den visuelle effekt, du ønsker, at linjen skal være baseret på, ved at vælge rullemenuen **Måling**, som automatisk er udfyldt med dataelementer fra den visuelle effekt. I dette tilfælde vælger vi *Weather* (Vejr) som målingen, mærker den *Average Weather* (Gennemsnitligt vejr) og tilpasser nogle af de andre indstillinger, som vist nedenfor.
   
   ![](media/desktop-analytics-pane/analytics-pane_4.png)
4. Hvis du vil have vist et datanavn, skal du slå skyderen **Datanavn** til. Når du gør dette, får du mange yderligere indstillinger for dit datanavn som vist i følgende billede.
   
   ![](media/desktop-analytics-pane/analytics-pane_5.png)
5. Bemærk tallet, der vises ved siden af elementet **Gennemsnitslinje** i ruden **Analytics**. Det fortæller dig, hvor mange dynamiske linjer du på nuværende tidspunkt har på dine visuelle effekter og af hvilken type. Hvis vi tilføjer en **Maksimumlinje** for *Cost of Living* (Leveomkostninger), kan du se, at ruden **Analytics** viser, at vi nu har også anvender en **Maksimumlinje** som dynamisk referencelinje for den visuelle effekt.
   
   ![](media/desktop-analytics-pane/analytics-pane_6.png)

Hvis der ikke kan anvendes dynamiske linjer for den valgte visuelle effekt (i dette tilfælde den visuelle effekt **Kort**), får du vist følgende, når du vælger ruden **Analytics**.

![](media/desktop-analytics-pane/analytics-pane_7.png)

Der er mange typer interessant viden, du kan fremhæve ved at oprette dynamiske referencelinjer med ruden **Analytics**.

Vi planlægger flere funktioner og egenskaber herunder at udvide, hvilke visuelle effekter dynamiske referencelinjer kan anvendes til, så vend tilbage ofte for at se nyheder.

## <a name="apply-forecasting"></a>Anvend Prognose
Du kan bruge funktionen **Prognose** ved at vælge et visuelt element og derefter udvide afsnittet **Prognose** i ruden **Analytics**. Du kan angive mange input for at redigere prognosen, f.eks. *Budgetteret længde*, *Konfidensinterval* og andet. Det følgende billede viser en grundlæggende linjevisualisering med anvendte prognose, men du kan bruge din fantasi (og afprøve funktionen *prognose* på forskellige måder) for at se, hvordan den kan anvendes til din modeller.

![](media/desktop-analytics-pane/analytics-pane_8.png)

## <a name="limitations"></a>Begrænsninger
Muligheden for at bruge dynamiske referencelinjer er baseret på typen af visuel effekt, der bruges. Følgende liste viser, hvilke dynamiske linjer der i øjeblikket er tilgængelig for de visuelle effekter:

Fuld brug af dynamiske linjer er tilgængelig på følgende visuelle effekter:

* Områdediagram
* Kurvediagram
* Punktdiagram
* Grupperet søjlediagram
* Grupperet liggende søjlediagram

Følgende visuelle effekter kan kun bruge en *konstantlinje* fra ruden **Analytics**:

* Stablet område
* Stablet liggende søjle
* Stablet søjle
* 100 % stablet liggende søjle
* 100 % stablet søjle

For følgende visuelle effekter er en *tendenslinje* i øjeblikket den eneste mulighed:

* Ikke-stablet linje
* Grupperet søjlediagram

Slutteligt kan ikke-kartesianske visuelle effekter i øjeblikket ikke anvende dynamiske linjer fra ruden **Analytics**, f.eks.:

* Matrix
* Cirkeldiagram
* Krans
* Tabel

## <a name="next-steps"></a>Næste trin
Der er mange forskellige ting, du kan gøre med Power BI Desktop. Du kan finde flere oplysninger om funktionerne i følgende ressourcer:

* [Nyheder i Power BI Desktop](desktop-latest-update.md)
* [Download Power BI Desktop](desktop-get-the-desktop.md)
* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datatyper i Power BI Desktop](desktop-data-types.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)    

