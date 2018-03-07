---
title: "Brug gitterlinjer og fastgørelse til gitter i Power BI Desktop-rapporter"
description: "Brug gitterlinjer, fastgørelse til gitter, z-rækkefølge, justering og fordeling i Power BI Desktop-rapporter"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1b6b1a3ecda7d3f827975da8fcfec5d9d5b67023
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="use-gridlines-and-snap-to-grid-in-power-bi-desktop-reports"></a>Brug gitterlinjer og fastgørelse til gitter i Power BI Desktop-rapporter
**Power BI Desktop**-rapportlærredet indeholder gitterlinjer, som du kan bruge til at justere visuelle elementer på en rapportside, så det ser pænt ud, og det indeholder også funktionen for fastgørelse til gitter, så dine visuelle elementer i dine rapporter ser jævne ud, er justeret og har lige stor afstand.

I **Power BI Desktop** kan du også tilpasse z-rækkefølgen (flytte fremad eller bagud) for objekter i en rapport samt justere eller fordele valgte visuelle elementer på lærredet på en jævn måde.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_0.png)

### <a name="enabling-gridlines-and-snap-to-grid"></a>Aktivér gitterlinjer og fastgørelse til gitter
Hvis du vil aktivere gitterlinjer og fastgørelse til gitter, skal du vælge båndet **Vis** og derefter markere afkrydsningsfeltet for **Vis gitterlinjer** og **Fastgør objekter til gitter**. Du kan vælge et eller begge felter. De fungerer uafhængigt af hinanden.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_1.png)

> [!NOTE]
> Hvis **Vis gitterlinjer** og **Fastgør objekter til gitter** er deaktiveret, kan du oprette forbindelse til en datakilde for at aktivere dem.
> 
> 

### <a name="using-gridlines"></a>Brug af gitterlinjer
Gitterlinjer er visuelle hjælpelinjer, som viser dig, om to eller flere visuelle elementer er justeret korrekt. Når du forsøger at bestemme, om to (eller flere) visuelle elementer er justeret vandret eller lodret, kan du bruge gitterlinjerne til at se, om kanterne er justeret.

Du kan bruge *Ctrl + klik* til at vælge mere end ét visuelt element ad gangen, hvilket viser alle de valgte visuelle kanter, så du nemt kan se, om de visuelle elementer er justeret korrekt.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_2.png)

#### <a name="using-gridlines-inside-visuals"></a>Brug af gitterlinjer i visuelle elementer
I Power BI er der også gitterlinjer i visuelle elementer, som indeholder visuelle hjælpelinjer til sammenligning af datapunkter og værdier. Fra og med versionen af **Power BI Desktop** fra september 2017 kan du nu administrere gitterlinjerne i visuelle elementer ved hjælp af kortet **X-akse** eller **Y-akse** (afhængigt af typen af visuelt element), der findes i sektionen **Format** i ruden **Visualiseringer**. Du kan administrere følgende gitterlinjeelementer i et visuelt element:

* Slå gitterlinjer til eller fra
* Skift farve på gitterlinjer
* Juster stregen (tykkelsen) i gitterlinjer
* Vælg stregtypen for gitterlinjerne i det visuelle element, f.eks. udfyldt, stiplet eller prikket

Det kan især være en god ide at ændre bestemte elementer i gitterlinjer i rapporter, hvor der bruges en mørk baggrund til visuelle elementer. På følgende billede vises sektionen *Gitterlinjer* på kortet **X-akse**.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_9.png)

### <a name="using-snap-to-grid"></a>Brug fastgørelse til gitter
Når du aktiverer **Fastgør objekter til gitter**, justeres alle visuelle elementer på lærredet i **Power BI Desktop**, som du flytter (eller ændrer størrelsen på), automatisk i forhold til den nærmeste akse i gitteret for at sikre, at to eller flere visuelle elementer justeres i forhold til den samme vandrette eller lodrette placering eller størrelse.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_3.png)

Og det er det eneste, du skal vide om at bruge **gitterlinjer** og **fastgørelse til gitter**, så du nemt kan sikre, at de visuelle elementer i dine rapporter justeres, som de skal.

### <a name="using-z-order-align-and-distribute"></a>Brug z-rækkefølge, justering og fordeling
Du kan også administrere rækkefølgen fra den første til den sidste af de visuelle elementer i en rapport, ofte kaldet *z-rækkefølgen* af elementer. Det giver dig mulighed for at overlappe visuelle elementer, som du ønsker det, og derefter justere rækkefølgen fra første til sidste for de enkelte visuelle elementer. Denne sortering udføres ved hjælp af knapperne **Flyt fremad** og **Flyt bagud**, der findes i sektionen **Arranger** på båndet **Format**, der vises, når du vælger et eller flere visuelle elementer på siden (og den er ikke tilgængelig, hvis der ikke er valgt visuelle elementer).

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_4.png)

På båndet **Format** kan du også justere visuelle elementer på mange forskellige måder. Det giver dig mulighed at sikre, at visuelle elementer vises på siden med den justering, som du synes fungerer og ser bedst ud.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_5.png)

Når der er valgt ét visuelt element og du bruger knappen **Juster**, justeres dette visuelle element til kanten (eller midten) af rapportlærredet, som vist på følgende billede.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_6.png)

Når der er valgt to eller flere visuelle elementer, justeres de sammen og bruger den eksisterende justerede grænse i de visuelle elementer til justering. Hvis der for eksempel er valgt to visuelle elementer, og knappen *Venstrejuster* er valgt, justeres de visuelle elementer i forhold til grænsen længst til venstre for alle de valgte visuelle elementer.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_7.png)

Du kan også fordele dine visuelle elementer jævnt over hele rapportlærredet lodret eller vandret. Du skal bare bruge knappen **Fordel** på båndet **Format**.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_8.png)

Med bare et par indstillinger i disse værktøjer til gitterlinjer, justering og fordeling kommer dine rapporter til at se ud, som du ønsker det.

