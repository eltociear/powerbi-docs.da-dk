---
title: Brug Udformningsvisning i Power BI Desktop (prøveversion)
description: Brug Udformningsvisning til at se komplekse datasæt i en visualisering i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 84e2bc663a4e3912608279c7315bc494b3c9844a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296518"
---
# <a name="modeling-view-in-power-bi-desktop-preview"></a>Udformningsvisning i Power BI Desktop (prøveversion)

Med **Udformningsvisning** i **Power BI Desktop** kan du få vist og arbejde med komplekse datasæt, der indeholder mange tabeller. Med Udformningsvisning kan du gøre følgende:


## <a name="enabling-the-modeling-view-preview-feature"></a>Aktivering af prøveversionsfunktionen Udformningsvisning

Funktionen Udformningsvisning er en prøveversion og skal aktiveres i **Power BI Desktop**. For at aktivere Udformningsvisning skal du vælge **Filer > Indstillinger > Indstillinger > Prøveversionsfunktioner** og derefter markere afkrydsningsfeltet **Udformningsvisning**, som vist på følgende billede.

![Aktivér prøveversionsfunktionen Udformningsvisning i Power BI Desktop](media/desktop-modeling-view/modeling-view_01.png)

Du skal genstarte **Power BI Desktop**, før prøveversionsfunktionen bliver aktiveret. 

![Genstart Power BI Desktop for at aktivere prøveversionsfunktionerne](media/desktop-modeling-view/modeling-view_01b.png)

## <a name="using-modeling-view"></a>Brug af Udformningsvisning

Du tilgår Udformningsvisning ved at vælge ikonet Udformningsvisning, som du finder i venstre side af **Power BI Desktop**, som vist på følgende billede.

![Ikonet Udformningsvisning i Power BI Desktop](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>Oprettelse af separate diagrammer

Med Udformningsvisning kan du oprette diagrammer over din model, der kun indeholder et undersæt af tabellerne i modellen. Dette kan hjælpe med at give et tydeligere overblik over tabeller, du vil arbejde med, og gør det lettere at arbejde med komplekse datasæt. Hvis du vil oprette et nyt diagram kun med et undersæt af tabellerne, skal du klikke på tegnet **+** ud for fanen **Alle tabeller** i bunden af Power BI Desktop-vinduet.

![Opret et nyt diagram ved at klikke på plustegnet (+) i afsnittet faner](media/desktop-modeling-view/modeling-view_03.png)

Du kan derefter trække en tabel fra listen **Felter** til diagramoverfladen. Højreklik på tabellen, og vælg derefter **Tilføj relaterede tabeller** i den menu, der vises.

![Højreklik på en tabel, og vælg Tilføj relaterede tabeller](media/desktop-modeling-view/modeling-view_04.png)

Når du gør det, vises tabeller, der er relateret til den oprindelige tabel, i det nye diagram. På følgende billede kan du se, hvordan relaterede tabeller vises, når du har valgt menupunktet **Tilføj relaterede tabeller**.

![Viser relaterede tabeller](media/desktop-modeling-view/modeling-view_05.png)

## <a name="setting-common-properties"></a>Angivelse af fælles egenskaber

Du kan vælge flere objekter på én gang i Udformningsvisning ved at holde **CTRL**-tasten nede og klikke på flere tabeller. Når du vælger flere tabeller, fremhæves de i Udformningsvisning. Når flere tabeller er fremhævet, gælder ændringer, der er anvendt i ruden **Egenskaber**, for alle valgte tabeller.

Du kan f.eks. ændre [lagringstilstanden](desktop-storage-mode.md) for flere tabeller i diagramvisningen ved at holde **CTRL**-tasten nede, vælge tabeller og derefter ændre indstillingen for lagringstilstand i ruden **Egenskaber**.

![Vælg flere tabeller ved at holde CTRL nede, og angiv derefter fælles egenskaber på tværs af alle valgte tabeller](media/desktop-modeling-view/modeling-view_06.png)


## <a name="next-steps"></a>Næste trin

I følgende artikler beskrives flere detaljer om datamodeller og DirectQuery.

* [Sammenlægninger i Power BI Desktop (prøveversion)](desktop-aggregations.md)
* [Sammensatte modeller i Power BI Desktop (Preview)](desktop-composite-models.md)
* [Lagringstilstand i Power BI Desktop (Preview)](desktop-storage-mode.md)
* [Mange til mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md)


Artikler om DirectQuery:

* [Brug af DirectQuery in Power BI](desktop-directquery-about.md)
* [Understøttede datakilder i forbindelse med DirectQuery i Power BI](desktop-directquery-data-sources.md)
