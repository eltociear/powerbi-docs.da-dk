---
title: Ruden Analytics i Power BI-tjenesten
description: Opret dynamiske referencelinjer til visuelle effekter i Power BI-tjenesten
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
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: 3750d733967301f952fd092d2d1d0a2b9d1b2238
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/21/2017
---
# <a name="analytics-pane-in-power-bi-service"></a>Ruden Analytics i Power BI-tjenesten
Med ruden **Analytics** i **Power BI-tjenesten** kan du tilføje dynamiske *referencelinjer* for visuelle effekter og angive fokus for vigtige tendenser eller indsigt.

![](media/service-analytics-pane/power-bi-analytics-pane.png)

> [!NOTE]
> Ruden **Analytics** vises kun, når du vælger en visuel effekt på rapportlærredet.
> 
> 

## <a name="using-the-analytics-pane"></a>Sådan bruges ruden Analytics
Med ruden **Analytics** kan du oprette følgende typer dynamiske referencelinjer (ikke alle linjer er tilgængelige for alle typer visuelle effekter):

* Konstantlinje for X-akse
* Konstantlinje for Y-akse
* Minimumlinje
* Maksimumlinje
* Gennemsnitslinje
* Medianlinje
* Fraktillinje


Få vist de tilgængelige dynamiske referencelinjer for en visuel effekt ved at følge disse trin:

1. Vælg eller opret en visuel effekt, og vælg derefter ikonet **Analytics** ![](media/service-analytics-pane/power-bi-analytics-icon.png) i ruden **Visuelle effekter**.

2. Vælg pil ned til den linjetype, du vil oprette, for at åbne dens indstillinger. I dette tilfælde vælger vi **Gennemsnitslinje**.
   
   ![tilføj gennemsnitslinje](media/service-analytics-pane/power-bi-add.png)

3. Du opretter en ny linje ved at vælge **+ Tilføj** og beslutte dig for, hvilken måling der skal bruges til at oprette linjen.  Rullelisten **Måling** udfyldes automatisk med tilgængelige data fra den valgte visualisering. Nu skal du bruge **Open store count**.

5. Du har en række forskellige indstillinger for linjen, f.eks. farve, gennemsigtighed, typografi og position (i forhold til den visuelle effekts dataelementer). Hvis du vil navngive linjen, kan du give den en titel og derefter flytte skyderen **Datanavn** til **Til**.  I dette tilfælde kalder vi linjen *Avg # Open Stores* og tilpasser nogle af de andre indstillinger, som vist nedenfor.
   
   ![tilpas analyse for gennemsnitslinje](media/service-analytics-pane/power-bi-average-line2.png)

1. Bemærk tallet, der vises ved siden af elementet **Gennemsnitslinje** i ruden **Analytics**. Det fortæller dig, hvor mange dynamiske linjer, du på nuværende tidspunkt har på dine visuelle effekter og af hvilken type. Hvis vi føjer en **Konstantlinje** som et måltal for butikker på 9, kan du se, at ruden **Analytics** viser, at vi nu også anvender en **Konstantlinje** som referencelinje for den visuelle effekt.
   
   ![](media/service-analytics-pane/power-bi-reference-lines.png)
   

Der er mange typer interessant viden, du kan fremhæve ved at oprette dynamiske referencelinjer med ruden **Analytics**.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

Hvis der ikke kan anvendes dynamiske linjer for den valgte visuelle effekt (i dette tilfælde den visuelle effekt **Kort**), får du vist følgende, når du vælger ruden **Analytics**.
   
![analytics er ikke tilgængelig](media/service-analytics-pane/power-bi-no-lines.png)

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
[Ruden Analytics i Power BI Desktop](desktop-analytics-pane.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

