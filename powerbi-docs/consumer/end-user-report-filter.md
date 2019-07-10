---
title: Få en rundvisning af ruden Rapportfiltre
description: Sådan tilføjer du et filter i en rapport i Power BI-tjenesten for forbrugere
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: ef7e4f556832f1323043a80cf219678a16511c9e
ms.sourcegitcommit: e67bacbfc5638ee97e3d2e0e7f5bd2d9aac78f9c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/02/2019
ms.locfileid: "67532892"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Få en præsentation af ruden Rapportfiltre

I denne artikel ser vi nærmere på ruden **Filtre** i rapporter i Power BI-tjenesten. Brug filtre for at få ny indsigt i dine data.

Der er mange forskellige måder at filtrere data på i Power BI. Du kan få flere oplysninger under [Om filtre og fremhævning i Power BI-rapporter](../power-bi-reports-filters-and-highlighting.md).

![Skærmbillede af en rapport i browseren med en pil, der peger på indstillingen Filtre.](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Arbejde med ruden Filtre i rapporter

Når en kollega deler en rapport med dig, skal du søge efter ruden **Filtre**. Nogle gange er den skjult langs højre kant af rapporten. Vælg den for at udvide den.

![Skærmbillede af rapporten med ruden Filtre udvidet.](media/end-user-report-filter/power-bi-filter-pane.png)

Ruden **Filtre** indeholder filtre, der er tilføjet i rapporten af rapportens *designer*. *Forbrugere* som dig selv kan interagere med de eksisterende filtre og gemme ændringer, men forbrugere kan ikke tilføje nye filtre i rapporten. På skærmbilledet ovenfor har designeren f.eks. tilføjet to filtre på sideniveau: **Segment** og **År**. Du kan interagere og ændre disse filtre, men du kan ikke tilføje et tredje filter på sideniveau.

I Power BI-tjenesten beholder rapporter eventuelle ændringer, du foretager i ruden **Filtre**. Tjenesten overfører også disse ændringer til mobilversionen af rapporten.

Hvis du vil nulstille ruden **Filtre** til designerens standardindstillinger, skal du vælge ![Skærmbillede af indstillingen Nulstil til standard](media/end-user-report-filter/power-bi-reset.png). på den øverste menulinje.

## <a name="view-all-the-filters-for-a-report-page"></a>Vis alle filtrene for en rapportside

I ruden **Filtre** vises alle de filtre, der er tilføjet af rapportens designer. Ruden **Filtre** er også det område, hvor du kan få vist oplysninger om filtrene og interagere med dem. Du kan gemme ændringer, du foretager, eller bruge **Nulstil til standard** for at vende tilbage til de oprindelige filterindstillinger.

Hvis der er ændringer, du vil gemme, kan du også oprette et personligt bogmærke.  Du kan finde flere oplysninger under [Hvad er bogmærker?](end-user-bookmarks.md).

Ruden **Filtre** viser og administrerer flere typer rapportfiltre. De kan anvendes på en visualisering, på en rapportside og på hele rapporten.

I dette eksempel har vi valgt en visualisering, der indeholder to filtre. Der er også filtre på rapportsiden. De er angivet under overskriften **Filtre på denne side**. Hele rapporten har desuden et filter for **Dato**.

![Skærmbillede af en rapport med en visualisering og dens relaterede filtre fremhævet.](media/end-user-report-filter/power-bi-all-filters2.png)

Ud for nogle af filtrene vises teksten **(Alle)** . **(Alle)** betyder, at alle værdier er inkluderet i filteret. På skærmbilledet ovenfor viser **Segment (Alle)** , at denne rapportside indeholder data om alle produktsegmenterne. Hvis du vælger filteret **Område er Vest** på sideniveau, indeholder rapportsiden kun data for det vestlige område.

Alle, der får vist denne rapport, kan arbejde med disse filtre.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Vis kun de filtre, der anvendes på en visualisering

Hvis du vil se nærmere på de filtre, der anvendes på en bestemt visualisering, skal du holde markøren over visualiseringen for at få vist filterikonet ![Skærmbillede af filterikonet](media/end-user-report-filter/power-bi-filter-icon.png). Vælg filterikonet for at se et pop op-vindue med alle de filtre, udsnitsværktøjer m.m., der påvirker den pågældende visualisering. Filtrene i pop op-vinduet er de samme filtre, som vises i ruden **Filtre**.

![Skærmbillede af en liste over filtre med pile, der peger på de steder, hvor filtrene vises i ruden Filtre.](media/end-user-report-filter/power-bi-hover-visual-filter.png)

Her er de filtertyper, der kan vises i denne visning:

- Grundlæggende filtre

- Udsnit

- Tværgående fremhævning

- Tværgående filtrering

- Avancerede filtre

- Top N-filtre

- Filtre for Relativ dato

- Udsnitsværktøjer til synkronisering

- Filtre for Inkluder/Ekskluder

- Filtre sendt via en URL-adresse

I eksemplet kan vi følgende:

1. Søjlediagrammet har tværgående filtrering.

1. **Inkluderet** fortæller os, at den tværgående filtrering gælder for **Segment**, og at der er tre inkluderet.

1. Der er anvendt et udsnit på **Kvartal**.

1. **Område** er et filter, der er anvendt på denne rapportside, og

1. **isVanArsdel** og **År** er filtre, der anvendes på denne visualisering.

![Skærmbillede af en rapport og dens filtre, hvor listen over filtre er nummereret, så de matcher ovenstående nummererede liste.](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Søg i et filter

Et filter kan nogle gange have en lang liste over værdier. Brug søgefeltet til at søge efter og vælge den ønskede værdi.

![Skærmbillede af, hvordan du kan søge i et filter.](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Vis filteroplysninger

Hvis du vil forstå et filter, kan du se nærmere på de tilgængelige værdier og antal.  Få vist oplysninger om filteret ved at holde markøren over det og vælge pilen ud for filterets navn.
  
![Skærmbillede af et filter, der viser det vestlige område som valgt.](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Rediger filtervalg

En metode til at søge efter dataindsigt er at interagere med filtrene. Du kan ændre filtervalg ved hjælp af rullepilen ud for feltets navn.  Afhængigt af det filter og den datatype, der filtreres i Power BI, vil dine muligheder variere fra enkle valg på en liste til at angive dato- eller talområder. I det avancerede filter nedenfor har vi ændret filteret **Antal enheder i alt ÅTD** på træstrukturen til at være mellem 2.000 og 3.000. Bemærk, at denne ændring fjerner Prirum fra træstrukturen.
  
![Skærmbillede af en rapport og dens filtre, der viser Fashions Direct som valgt.](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Hvis du vil vælge mere end én filterværdi ad gangen, skal du holde CTRL-tasten nede. De fleste filtre understøtter valg af flere værdier.

### <a name="reset-filter-to-default"></a>Nulstil filter til standard

Hvis du vil annullere alle ændringer du har foretaget i filtrene, skal du vælge **Nulstil til standard** fra den øverste menulinje.  Med dette valg vender filtrene tilbage til deres oprindelige tilstand, som var angivet af rapportens designer.

![Skærmbillede af indstillingen Nulstil til standard.](media/end-user-report-filter/power-bi-reset.png)

### <a name="clear-a-filter"></a>Ryd et filter

Hvis der kun er ét filter, du vil angive til **(Alle)** , kan du rydde det ved at vælge viskelæderikonet ![Skærmbillede af viskelæderikonet](media/end-user-report-filter/power-bi-eraser-icon.png). ud for filterets navn.
  
<!--  too much detail for consumers

## Types of filters: text field filters
### List mode
Ticking a checkbox either selects or deselects the value. The **All** checkbox can be used to toggle the state of all checkboxes on or off. The checkboxes represent all the available values for that field.  As you adjust the filter, the restatement updates to reflect your choices. 

![list mode filter](media/end-user-report-filter/power-bi-restatement-new.png)

Note how the restatement now says "is Mar, Apr or May".

### Advanced mode
Select **Advanced Filtering** to switch to advanced mode. Use the dropdown controls and text boxes to identify which fields to include. By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.  

![advanced mode](media/end-user-report-filter/power-bi-advanced.png)

## Types of filters: numeric field filters
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the values are infinite or represent a range, selecting the field name opens the advanced filter mode. Use the dropdown and text boxes to specify a range of values that you want to see. 

![advanced filter](media/end-user-report-filter/power-bi-dropdown-and-text.png)

By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.

## Types of filters: date and time
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the field values represent date or time, you can specify a start/end time when using Date/Time filters.  

![datetime filter](media/end-user-report-filter/pbi_date-time-filters.png)

-->

## <a name="next-steps"></a>Næste trin

Få mere at vide om, hvordan og hvorfor [visualiseringer krydsfiltrerer og krydsfremhæver hinanden på en rapportside](end-user-interactions.md)