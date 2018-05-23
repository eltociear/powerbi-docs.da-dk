---
title: Om filtre og fremhævning i Power BI-rapporter
description: Om filtre og fremhævning i Power BI-rapporter
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/13/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 855ed26172fa0f157787ba4cfdc3e7e6ab4ff4ba
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Om filtre og fremhævning i Power BI-rapporter
***Filtre*** fjerner alt andet end de data, du vil fokusere på.  ***Fremhævning*** er ikke filtrering, da det ikke fjerner data, men i stedet fremhæver et undersæt af de synlige data – ikke fremhævede data forbliver synlige, men nedtonede.

Du kan filtrere og fremhæve rapporter i Power BI på mange forskellige måder. Hvis vi havde inkluderet alle oplysningerne i én artikel, ville det være forvirrende, så vi har opdelt dem som følger:

* Introduktion til filtre og fremhævning (artiklen, du er ved at læse nu)
* De måder, hvorpå du kan [oprette og bruge filtre og fremhævning i redigeringsvisning/rapporter, som du ejer](power-bi-report-add-filter.md). Når du har redigeringsrettigheder til en rapport, kan du oprette, ændre og slette filtre og fremhævning i rapporter.
* De måder, hvorpå du kan [oprette filtre og fremhævning i en rapport, der deles med dig eller i redigeringsvisning for rapporter](service-reading-view-and-editing-view.md). Her har du færre valgmuligheder, men Power BI giver dig stadig en lang række muligheder for filtrering og fremhævning.  
* [En detaljeret præsentation af de filter- og fremhævningsmuligheder, der er tilgængelige i redigeringsvisning](power-bi-how-to-report-filter.md), herunder et detaljeret indblik i filtertyperne (f.eks. dato og klokkeslæt, numerisk og tekst) og forskellen mellem grundlæggende og avancerede indstillinger.
* Nu hvor du ved, hvordan filtre og fremhævning fungerer som standard, [kan du lære, hvordan du ændrer, hvordan visualiseringer på en side filtrerer og fremhæver hinanden](service-reports-visual-interactions.md)

> [!TIP]
> Hvordan ved Power BI, hvordan data er knyttet til hinanden?  Programmet bruger relationerne imellem de forskellige tabeller og felter i den underliggende [datamodel](https://support.office.com/article/Create-a-Data-Model-in-Excel-87e7a54c-87dc-488e-9410-5c75dbcb0f7b?ui=en-US&rs=en-US&ad=US) til at få elementer på en rapportside til at interagere med hinanden.
> 
> 

## <a name="introduction-to-filters-and-highlighting-in-reports-using-the-filters-pane"></a>Introduktion til filtre og fremhævning i rapporter ved hjælp af ruden Filtre
 I denne artikel beskrives, hvordan du anvender filtre og fremhævning i Power BI-tjenesten.  Men brugeroplevelsen er stort den samme i Power BI Desktop.  

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Filtre og fremhævning kan anvendes ved hjælp af ruden **Filtre** eller ved at lave fremhævninger direkte på selve rapporten (ad hoc, se nederst på siden). Ruden Filtre viser de tabeller og felter, der bruges i rapporten, og eventuelle filtre, der anvendes. Filtrene er opdelt i **sideniveau**, **rapportniveau**, **detaljeadgang** og **visualiseringsniveau**.  Du kan kun se filtre på visualiseringsniveau, hvis du har valgt en visualisering på rapportlærredet.

> [!TIP]
> Hvis der står **Alle** ud for filteret, betyder det, at hele feltet inkluderes som et filter.  **Kæde(Alle)** på skærmbilledet nedenfor viser f.eks., at denne rapportside inkluderer data om alle butikskæderne.  På den anden side viser filteret på rapportniveau for **Regnskabsåret er 2013 eller 2014**, at rapporten kun indeholder data for regnskabsårene 2013 og 2014.
> 
> 

## <a name="filters-in-reading-view-versus-editing-view"></a>Filtre i læsevisning sammenlignet med redigeringsvisning
Du kan interagere med rapporter i to forskellige tilstande: [Læsevisning og Redigeringsvisning](service-reading-view-and-editing-view.md).  Og de filterfunktioner, der er tilgængelige, afhænger af hvilken tilstand du arbejder i.

* Du kan tilføje rapport- og sidefiltre samt detaljeadgangs- og visualiseringsfiltre i redigeringsvisning. Filtrene gemmes sammen med rapporten, når du gemmer den, også selvom rapporten er åbnet i en mobilapp. Personer, der åbner rapporten i Læsevisning, kan arbejde med de filtre, du har tilføjet, men kan ikke tilføje nye filtre.
* I Læsevisning kan du anvende de eventuelle filtre, som allerede findes i rapporten, og gemme dine valg.  Du kan dog ikke tilføje nye filtre.

### <a name="the-filters-pane-in-reading-view"></a>Ruden Filtre i læsevisning
Hvis du kun har adgang til en rapport i læsevisning, ser ruden Filtre cirka sådan ud:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Denne side i rapporten har 6 filtre på sideniveau og 1 filter på rapportniveau.

Vælg en visual for at se, om der eksisterer filtre på visualiseringsniveau. På billedet nedenfor anvendes der 6 filtre på boblediagrammet.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Udforsk data ved at ændre eksisterende filtre i læsevisning. De ændringer, du foretager, gemmes sammen med rapporten, også selvom rapporten er åbnet i en mobilapp. Læs mere i artiklen [Læsevisning og Redigeringsvisning i Power BI-tjenesten](service-reading-view-and-editing-view.md).

### <a name="the-filters-pane-in-editing-view"></a>Ruden Filtre i redigeringsvisning
Når du har ejerrettigheder til en rapport og åbner den i redigeringsvisning, kan du se, at **Filtre** bare er ét ud af flere felter, du kan bruge til redigering.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Som i læsevisning (ovenfor) kan vi se, at denne side i rapporten har 6 filtre på sideniveau og 1 filter på rapportniveau. Og ved at vælge boblediagrammet ser vi, at der anvendes 6 filtre på visualiseringsniveau.

Men i redigeringsvisning kan vi gøre meget mere med filtre og fremhævning. Den vigtigste forskel er, at vi kan tilføje nye filtre. Få mere at vide om, hvordan du gør dette og meget andet i artiklen [Føj et filter til en rapport](power-bi-report-add-filter.md)

## <a name="ad-hoc-filtering-and-highlighting"></a>Ad hoc-filtrering og -fremhævning
Vælg et felt på rapportlærredet for at filtrere og fremhæve resten af siden. Vælg et tomt område i den samme visual for at fjerne det. Denne type filtrering og fremhævning er en sjov og hurtig måde til at udforske dataeffekter. Hvis du vil finjustere funktionsmåden for denne type krydsfiltrering og krydsfremhævning, kan du se mere under [Visuelle interaktioner](service-reports-visual-interactions.md).

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)

Dine ændringer gemmes, når du lukker rapporten. Du kan fortryde en filtrering ved at vælge **Nulstil til standard** på den øverste menulinje.

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

## <a name="next-steps"></a>Næste trin
[Arbejde med filtre og fremhævning (i læsevisning)](service-reading-view-and-editing-view.md)

[Føj et filter til en rapport (i redigeringsvisning)](power-bi-report-add-filter.md)

[Få en præsentation af rapportfiltre](power-bi-how-to-report-filter.md)

[Rediger, hvordan visuals i rapporter krydsfiltrerer og krydsfremhæver hinanden](service-reports-visual-interactions.md)

Få mere at vide om [rapporter i Power BI](service-reports.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

