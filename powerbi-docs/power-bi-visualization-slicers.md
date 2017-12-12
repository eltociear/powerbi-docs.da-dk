---
title: Udsnit i Power BI (selvstudium)
description: 'Selvstudium: Udsnit i Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
ms.openlocfilehash: b6ce0c396f4a189489b97fe5cd86ab5cd8dbcc35
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Udsnit i Power BI-tjeneste (selvstudium)
Din vicedirektør ønsker at kunne se på en række målepunkter for hele divisionen og for hver enkelt distriktschef. Hun kunne oprette en separat rapportside for hver chef, eller hun kunne bruge et udsnit. Et udsnit begrænser delen af datasættet, der vises i andre visualiseringer på siden.  Udsnit er en alternativ måde at filtrere på.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Hvornår bruger man et udsnit
Udsnit er et fantastisk valg i følgende situationer.

* For at vise ofte brugte eller vigtige filtre på rapportcanvasset af hensyn til lettere adgang.
* For at gøre det nemmere at se den aktuelle filtrerede tilstand uden at skulle åbne en rulleliste for at finde filtreringsoplysningerne.
* Når du ønsker at skjule kolonner, du ikke har brug for, men stadig vil kunne bruge dem til at filtrere – det giver smallere, mere strømlinede tabeller.
* For at oprette mere fokuserede rapporter – eftersom udsnit er flydende objekter, kan du anbringe dem ved siden af den interessante del af rapporten, som du vil have dine brugere til at fokusere på.

## <a name="create-a-slicer"></a>Opret et udsnit
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. Åbn [Retail Analysis Sample](sample-retail-analysis.md) i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md), og [tilføj en ny rapportside](power-bi-report-add-page.md).
2. Vælg **District > District Manager** i ruden Felter.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. Konverter visualiseringen til et udsnit. Vælg udsnitsikonet i ruden Visualiseringer.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>Formatér udsnittet
1. Vælg malerrulleikonet ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) i ruden Visualiseringer, mens udsnittet er markeret, for at få vist formateringsindstillingerne.
2. Vælg **Generelt > Konturfarve**, og vælg mørkeblå, og skift **tykkelsen** til **6**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. Under **Kontrolelementer til markering** er **Markér alt** som standard **Fra**, og **Vælg én** er **Til**. Det betyder, at jeg skal bruge CTRL-tasten til at markere mere end ét navn ad gangen. Sæt **Markér alt** til **Til** og **Vælg én** til **Fra**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * Bemærk, at udsnittet nu har indstillingen **Markér alt** øverst på listen. Slå **Markér alt** til eller fra for at markere alle navnene eller for ikke at markere nogen af navnene.
   * Og du kan nu markere mere end ét navn uden at bruge CTRL-tasten.
4. Forøg tekststørrelsen til 14 pkt. under **Elementer**.  Vi vil gerne sikre, at vores kollegaer lægger mærke til dette udsnit.
5. Indstil til sidst **Skriftfarve** til mørkerød.  På denne måde skelnes der mellem de markerede navne og de ikke-markerede navne i vores udsnit.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. Mor dig med at udforske de andre indstillinger, der er tilgængelige for udsnit.

## <a name="use-the-slicer-in-a-report"></a>Brug udsnittet i en rapport
1. Føj nogle flere visualiseringer til rapportsiden, eller åbn rapporten [Retail Analysis sample report](sample-retail-analysis.md), og vælg fanen **District Monthly Sales**.
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Opdel rapportsiden for Carlos. Læg mærke til, hvordan de andre visualiseringer opdateres for at afspejle valgene.
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. Sortér udsnittet alfabetisk efter distriktschefens efternavn.  Vælg ellipsen (...) i øverste højre hjørne af udsnittet, og vælg **District Manager**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>Kontrollér, hvilken effekt udsnittet har på andre visuelle elementer på siden
Skal udsnittet kun filtrere nogle af de visuelle elementer på rapportsiden?  Brug kontrolelementet **Visuelle interaktioner** til at konfigurere det.

**BEMÆRK**! Hvis du ikke kan se **Visuelle interaktioner**, skal du kigge efter dets ikon i stedet ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png). Hvis du ikke ser nogen af dem, skal du kontrollere, at du befinder dig i rapportens [redigeringsvisning](service-reading-view-and-editing-view.md).

1. Markér udsnittet for at aktivere det, og vælg **Visuelle interaktioner** på menulinjen.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. Filterkontrolelementer vises over alle de andre visuelle elementer på siden. Hvis udsnittet skal filtrere et visuelt element, skal du vælge ikonet **Filter**.  Hvis udsnittet ikke skal have nogen effekt på det visuelle element, skal du vælge ikonet **Ingen**.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

Du kan finde flere oplysninger i [Visuelle interaktioner i en Power BI-rapport](service-reports-visual-interactions.md).

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Overvejelser og fejlfinding i forbindelse med udsnit i Power BI
Der er nogle få begrænsninger, hvad angår brugen af udsnit i Power BI, og de er følgende:

1. Udsnit understøtter ikke inputfelter.
2. Et enkelt udsnit kan ikke bruges på tværs af en hel rapport. Et udsnit påvirker kun den aktuelle side.
3. Udsnit kan ikke fastgøres til et dashboard.
4. Detaljeret visning understøttes ikke for udsnit.    
5. Udsnit understøtter ikke filtre på visualiseringsniveau.

Har du ideer til at forbedre Power BI? [Send en ide](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

## <a name="next-steps"></a>Næste trin
 [Føj en visualisering til en rapport](power-bi-report-add-visualizations-i.md)

 [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI – Grundlæggende begreber](service-basic-concepts.md)

[Prøv det – det er gratis!](https://powerbi.com/)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

