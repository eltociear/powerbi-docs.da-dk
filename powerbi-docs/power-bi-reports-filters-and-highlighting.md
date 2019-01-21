---
title: Om filtre og fremhævning i Power BI-rapporter
description: Om filtre og fremhævning i Power BI-rapporter
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/28/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: ace392570dbabc65d128941fc735231622f2c008
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285317"
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Om filtre og fremhævning i Power BI-rapporter
 I denne artikel beskrives, hvordan du anvender filtre og fremhævning i Power BI-tjenesten. Brugeroplevelsen er stort den samme i Power BI Desktop. ***Filtre*** fjerner alt andet end de data, du vil fokusere på. ***Fremhævning*** er ikke filtrering. Det fjerner ikke data, men fremhæver i stedet et undersæt af de synlige data – ikke-fremhævede data forbliver synlige, men nedtonede.

Du kan filtrere og fremhæve rapporter i Power BI på mange forskellige måder. Hvis vi havde inkluderet alle oplysningerne i én artikel, ville det være forvirrende, så vi har opdelt dem i følgende afsnit:

* Introduktion til filtre og fremhævning (artiklen, du er ved at læse nu)
* De måder, du kan[oprette og bruge filtre på i Redigeringsvisning](power-bi-report-add-filter.md) i rapporter. Når du har redigeringsrettigheder til en rapport, kan du oprette, ændre og slette filtre i rapporter.
* De måder, hvorpå du kan [filtre og fremhæve i en rapport, der deles med dig](consumer/end-user-reading-view.md), i redigeringsvisning for rapporter. Her har du færre valgmuligheder, men du har stadig en lang række muligheder for filtrering og fremhævning.  
* [En detaljeret præsentation af de filter- og fremhævningsmuligheder, der er tilgængelige i redigeringsvisning](consumer/end-user-report-filter.md), herunder et detaljeret indblik i filtertyperne (f.eks. dato og klokkeslæt, numerisk og tekst) og forskellen mellem grundlæggende og avancerede indstillinger.
* Nu hvor du ved, hvordan filtre og fremhævning fungerer som standard, [kan du lære, hvordan du ændrer den måde, visualiseringer på en side filtreres og fremhæver hinanden på](consumer/end-user-interactions.md)

## <a name="intro-to-the-filters-pane"></a>Introduktion til ruden Filtre

Du kan anvende filtre i ruden **Filtre** eller ved [at foretage valg i udsnitsværktøj](visuals/power-bi-visualization-slicers.md) direkte på selve rapporten. Ruden Filtre viser de tabeller og felter, der bruges i rapporten, og eventuelle filtre, der anvendes. 

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Der findes fire typer filtre.

- **Sidefilter** gælder for alle visuelle elementer på rapportsiden.     
- **Visuelt filter** gælder for et enkelt visuelt element på rapportsiden. Du kan kun se filtre på visualiseringsniveau, hvis du har valgt en visual på rapportlærredet.    
- **Rapportfilter** gælder for alle sider i rapporten.    
- **Detaljeadgangsfilter** gælder for en bestemt enhed i en rapport.    

Du kan søge i side-, visual- og rapportfiltre, i læse- eller redigeringsvisning, for at finde og vælge den værdi, du ønsker. 

![Søg i et filter](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

Hvis filteret er markeret med ordet **Alle**, betyder det, at alle værdierne i feltet er inkluderet i filteret.  **Kæde(Alle)** på skærmbilledet nedenfor betyder f.eks., at denne rapportside inkluderer data om alle butikskæderne.  På den anden side viser filteret på rapportniveau **Regnskabsåret er 2013 eller 2014**, at rapporten kun indeholder data for regnskabsårene 2013 og 2014.

## <a name="filters-in-reading-or-editing-view"></a>Filtre i læse- eller redigeringsvisning
Du kan interagere med rapporter i to forskellige tilstande: [læsevisning](consumer/end-user-reading-view.md) og redigeringsvisning. Hvilke filterfunktioner der er tilgængelige, afhænger af, hvilken tilstand du arbejder i.

* Du kan tilføje rapport- og sidefiltre samt detaljeadgangs- og visualiseringsfiltre i redigeringsvisning. Filtrene gemmes sammen med rapporten, når du gemmer den, også selv om rapporten er åbnet i en mobilapp. Personer, der åbner rapporten i Læsevisning, kan arbejde med de filtre, du har tilføjet, men kan ikke tilføje nye filtre.
* I læsevisning kan du anvende de eventuelle filtre, som allerede findes i rapporten, og gemme dine valg. Du kan ikke tilføje nye filtre.

### <a name="filters-in-reading-view"></a>Filtre i læsevisning
Hvis du kun har adgang til en rapport i læsevisning, ser ruden Filtre omtrent sådan ud:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Denne side i rapporten har seks filtre på sideniveau og et filter på rapportniveau.

Hver visual kan have filtre til alle felterne, og forfatteren til en rapport kan tilføje flere. På billedet nedenfor er der seks filtre på boblediagrammet.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Udforsk data ved at ændre eksisterende filtre i læsevisning. De ændringer, du foretager, gemmes sammen med rapporten, også selvom rapporten er åbnet i en mobilapp. Se hvordan ved at [få en præsentation af ruden Rapportfiltre](consumer/end-user-report-filter.md)

Dine filtre gemmes, når du lukker rapporten. Hvis du vil fortryde filtreringen og vende tilbage til standarden for filtrering, udsnit, detailudledning og sortering som angivet af rapportens forfatter, skal du vælge **Nulstil til standard** på den øverste menulinje.

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Filtre i redigeringsvisning
Når du har ejerrettigheder til en rapport og åbner den i redigeringsvisning, kan du se, at **Filtre** bare er ét ud af flere felter, du kan bruge til redigering.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Som i læsevisningen kan vi se, at denne side i rapporten har seks filtre på sideniveau og et filter på rapportniveau. Og ved at vælge boblediagrammet ser vi, at der anvendes seks filtre på visualniveau.

Vi kan udrette mere med filtre og fremhævning i læsevisning. Primært kan vi tilføje nye filtre. Se, hvordan du [tilføjer et filter i en rapport](power-bi-report-add-filter.md) og meget mere.

## <a name="ad-hoc-highlighting"></a>Ad hoc-fremhævelse
Vælg et felt på rapportlærredet for at fremhæve de andre visuals på siden. Vælg et tomt område i den samme visual for at fjerne det. Denne type fremhævning er en sjov og hurtig måde at udforske dataeffekter på. Hvis du vil finjustere funktionsmåden for denne type krydsfremhævning, kan du se mere under [Visuelle interaktioner](consumer/end-user-interactions.md).

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>Næste trin
[Føj et filter til en rapport (i redigeringsvisning)](power-bi-report-add-filter.md)

[Få en præsentation af rapportfiltre](consumer/end-user-report-filter.md)

[Rediger, hvordan visuals i rapporter krydsfiltrerer og krydsfremhæver hinanden](consumer/end-user-interactions.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

