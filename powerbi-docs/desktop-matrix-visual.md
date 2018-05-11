---
title: Brug matrixvisualisering i Power BI Desktop
description: Få mere at vide, hvordan matrixvisualisering giver mulighed for trinvist layout og findelt fremhævning i Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: c1c7eeeb1592b6a043dd25c5664ecd505e7975fc
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2018
---
# <a name="use-the-matrix-visual-in-power-bi-desktop"></a>Brug matrixvisualisering i Power BI Desktop
Når du bruger visualiseringen **Matrix**, kan du oprette matrixvisualiseringer (også kaldet *tabeller*) i rapporter i **Power BI Desktop** og få tværgående fremhævning af elementer i matrixen med andre visualiseringer. Derudover kan du vælge rækker, kolonner og endda individuelle celler og tværgående fremhævning. Endelig kan du udnytte pladsen i layoutet bedre, fordi matrixvisualisering understøtter et trinvist layout.

![](media/desktop-matrix-visual/matrix-visual_2a.png)

Der er mange funktioner knyttet til matrixen, og vi vil gennemgå dem i følgende afsnit i denne artikel.

> [!NOTE]
> Fra og med udgivelsen i juli 2017 af **Power BI Desktop** afspejler matrix- og tabelvisualiseringer formatering (herunder farver) fra det anvendte **rapporttema**. Det er måske ikke de farver, du forventer til din matrixvisualisering, og du kan ændre dem i konfigurationen **Rapporttema**. Se [**Use Report Themes in Power BI Desktop**](desktop-report-themes.md) (Brug rapporttemaer i Power BI Desktop), hvor du kan finde flere oplysninger om temaer.
> 
> 

## <a name="understanding-how-power-bi-calculates-totals"></a>Sådan beregner Power BI totaler

Før du begynder at læse om, hvordan du bruger **Matrix**-visualiseringen, er det vigtigt at forstå, hvordan Power BI beregner værdierne for total og subtotal i tabeller og matrixer. I rækker med total og subtotal evalueres målingen henover alle rækker i de underliggende data – det er *ikke* kun en simpel addition af værdierne i de synlige og viste rækker. Det betyder, at du kan ende med at have en anden værdi i rækken Total, end hvad du regnede med. 

Se følgende **Matrix**-visualiseringer. 

![](media/desktop-matrix-visual/matrix-visual_3.png)

I dette eksempel vises *Beløb* for hver sælger/dato-kombination i hver række i **Matrix**-visualiseringen længst til højre. Men da en sælger vises for flere datoer, kan tallene forekomme mere end én gang. Den nøjagtige total fra de underliggende data og en simpel addition af de synlige værdier kan derfor ikke sidestilles. Dette er et almindeligt mønster, når den værdi, du regner på, er på den "ene" side i en en til mange-relation.

Når du arbejder med totaler og subtotaler, skal du huske på, at disse værdier er baseret på de underliggende data og ikke kun på de synlige værdier. 


## <a name="using-drill-down-with-the-matrix-visual"></a>Brug detailudledning til matrixvisualiseringen
Med **Matrix**-visualiseringen kan du foretage en mængde interessante aktiviteter til detailudledning, der ikke var tilgængelig før. Dette omfatter mulighed for at foretage detailudledning ved hjælp af rækker, kolonner og endda til individuelle afsnit og celler. Lad os se på, hvordan hver enkelt af disse fungerer.

### <a name="drill-down-on-row-headers"></a>Detailudledning på rækkeoverskrifter
Når du i ruden **Visualiseringer** føjer flere felter til sektionen **Rækker** i området **Felter**, aktiverer du detailudledning på rækkerne i matrixvisualiseringen. Dette minder om oprettelse af et hierarki, hvor du derefter kan foretage detailudledning (og så sikkerhedskopiering) via hierarkiet og analysere dataene på hvert niveau.

I det følgende billede indeholder sektionen **Rækker** *Kategori* og *Underkategori* og opretter en gruppering (eller et hierarki) i rækkerne, som vi kan foretage detailudledning af.

![](media/desktop-matrix-visual/matrix-visual_4.png)

Når der er oprettet gruppering for visualiseringen i sektionen **Rækker**, viser selve visualiseringen *detailudledningen* og *udvider* ikonerne i øverste venstre hjørne i visualiseringen.

![](media/desktop-matrix-visual/matrix-visual_5.png)

Som der er tilfældet med funktionsmåden til detailudledning og udvidelse i andre visualiseringer kan vi ved at vælge disse knapper bruge detailudledning (eller sikkerhedskopiering) gennem hierarkiet. I dette tilfælde kan vi foretage detailudledning fra *Kategori* til *Underkategori* som vist på følgende billede, hvor ikonet for vis detaljer for ét niveau (fork) er valgt.

![](media/desktop-matrix-visual/matrix-visual_6.png)

Ud over at bruge disse ikoner kan du højreklikke på en af rækkeoverskrifterne og foretage detailudledning ved at foretage et valg i den menu, der vises.

![](media/desktop-matrix-visual/matrix-visual_7.png)

Bemærk, at der er nogle indstillinger i den viste menu, der udløser forskellige resultater:

Valg af **Foretag detailudledning** udvider matrixen for *det pågældende* rækkeniveau og *udelader* alle andre rækkeoverskrifter bortset fra den rækkeoverskrift, der blev højreklikket på. I det følgende billede blev der højreklikket på *Computers*, og der blev valgt **Foretag detailudledning**. Bemærk, at andre rækker på øverste niveau ikke længere vises i matrixen. Det er en nyttig funktion, og den er specielt god, når vi når til afsnittet om **tværgående fremhævning**.

![](media/desktop-matrix-visual/matrix-visual_8.png)

Du kan også klikke på ikonet for **færre detaljer** for at komme tilbage til den forrige visning af øverste niveau. Hvis du derefter vælger **Vis næste niveau** i genvejsmenuen, får du vist en alfabetiske liste over alle elementer på næste niveau (i dette tilfælde feltet *Underkategori*) uden den hierarkiske kategorisering på højere niveau.

![](media/desktop-matrix-visual/matrix-visual_8a.png)

Når du klikker på ikonet for **færre detaljer** i øverste venstre hjørne for at få matrixen til at vise alle kategorier på øverste niveau og derefter højreklikker igen og vælger **Udvid til næste niveau**, får du vist følgende:

![](media/desktop-matrix-visual/matrix-visual_9.png)

Du kan også bruge menupunkterne **Include** (Medtag) og **Exclude** (Udelad) til at bevare (eller hhv. fjerne) den række, der blev højreklikket på (og evt. underkategorier) fra matrixen.

### <a name="drill-down-on-column-headers"></a>Detailudledning på kolonneoverskrifter
Du kan også foretage detailudledning på **kolonner**, hvilket minder meget om detailudledning på rækker. I det følgende billede kan du se, at der er to felter i feltområdet **Kolonner**, hvilket opretter et hierarki, der minder om det, der blev brugt til rækkerne tidligere i denne artikel. I feltområdet **Kolonner** har vi *Klasse* og *Farve*.

![](media/desktop-matrix-visual/matrix-visual_10.png)

Når vi i **Matrix**-visualiseringen højreklikker på en kolonne, får vi mulighed for at foretage detailudledning. I det følgende billede skal du højreklikke på *Deluxe* og vælge **Foretag detailudledning**.

![](media/desktop-matrix-visual/matrix-visual_11.png)

Når du vælger **Foretag detailudledning**, vises næste niveau i kolonnehierarkiet for *Deluxe*, hvilket i dette tilfælde er *Farve*.

![](media/desktop-matrix-visual/matrix-visual_12.png)

Resten af punkterne i genvejsmenuen fungerer i kolonner på samme måde, som de gør i rækker (se forrige afsnit, **Detailudledning på rækkeoverskrifter**). Du kan vælge **Vis næste niveau**, **Udvid til næste niveau** og **Include** (Medtag) eller **Exclude** (Udelad) på samme måde, som du kan med rækker.

> [!NOTE]
> Ikonerne for detailudledning og færre detaljer øverst til venstre i matrixvisualiseringen gælder kun for rækker. Hvis du vil foretage detailudledning for kolonner, skal du bruge genvejsmenuen.
> 
> 

## <a name="stepped-layout-with-matrix-visuals"></a>Trinvist layout med matrixvisualisering
**Matrix**-visualiseringen indrykker automatisk underkategorier i et hierarki under hvert overordnet element, hvilket kaldes et **trinvist layout**.

I den *oprindelige* version af matrixvisualiseringen blev underkategorier vist i en helt anden kolonne, der optager meget mere plads i visualiseringen. Billedet herunder viser tabellen i den oprindelige **matrix**-visualisering. Bemærk, at underkategorier er i en fuldstændig separat kolonne.

![](media/desktop-matrix-visual/matrix-visual_14.png)

På det følgende billede kan du se en rigtig **matrix**-visualisering med **trinvist layout**. Bemærk, at kategorien *Computers* har underkategorier (Computers Accessories (Computertilbehør), Desktops (Stationære computere), Laptops (Bærbare computere), Monitors (Skærme) og osv.) let indrykket, hvilket visuelt giver et meget renere og mere komprimeret indtryk.

![](media/desktop-matrix-visual/matrix-visual_13.png)

Du kan nemt justere indstillingerne for det trinvise layout. Når visualiseringen **Matrix** er valgt i sektionen **Format** (malerrulleikonet) i ruden **Visualiseringer**, kan du udvide sektionen **Rækkeoverskrifter**. Du har to muligheder: Til/fra-knappen til **trinvist layout** (som slår det til eller fra) og **indrykningen af det trinvise layout** (angiver mængden af indrykning i pixel).

![](media/desktop-matrix-visual/matrix-visual_15.png)

Hvis du deaktiverer **det trinvise layout**, vises underkategorier i en anden kolonne og ikke indrykket under den overordnede kategori.

## <a name="subtotals-with-matrix-visuals"></a>Subtotaler med matrixvisualiseringer
Du kan slå subtotaler til eller fra i matrixvisualiseringer både for rækker og kolonner. I det følgende billede kan du se, at rækkesubtotaler er slået **til**.

![](media/desktop-matrix-visual/matrix-visual_20.png)

I sektionen **Format** i ruden **Visualiseringer** kan du udvide kortet **Subtotaler** og sætte skyderen **Rækkesubtotaler**  til **Fra**. Når du gør det, vises subtotaler ikke.

![](media/desktop-matrix-visual/matrix-visual_21.png)

Den samme proces gælder for kolonnesubtotaler.

## <a name="cross-highlighting-with-matrix-visuals"></a>Tværgående fremhævning med matrixvisualiseringer
Med **matrix**-visualiseringen kan du vælge alle elementer i matrixen som basis for tværgående fremhævning. Når du markerer en kolonne i en **Matrix**, fremhæves kolonnen, og det samme gør andre visuelle elementer på rapportsiden. Dette har været en almindelig funktion i andre visuals og markeringer af et datapunkt, og nu kan **matrix**-visualiseringen få del i den.

Derudover fungerer Ctrl+klik også for tværgående fremhævning. I eksemplet herunder er en samling underkategorier f.eks. markeret i **Matrix**-visualiseringen. Bemærk, hvordan elementer, der ikke er valgt i visualiseringen, er nedtonet, og hvordan de andre visualiseringer på siden afspejler de valg, der er foretaget i **Matrix**-visualiseringen.

![](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Skygge og skrifttypefarver med matrixvisualiseringer
Når du bruger **matrix**-visualiseringen kan du anvende **betinget formatering** (farver og skygge) til baggrunden af celler i matrixen, og du kan anvende betinget formatering til selve teksten og værdierne.

Hvis du vil anvende betinget formatering, kan du gøre et af følgende, når en matrixvisualisering er valgt:

* Højreklik på feltet i ruden **Felter**, og vælg **Betinget formatering** i menuen.
  
  ![](media/desktop-matrix-visual/matrix-visual_17.png)
* Du kan også udvide kortet **Betinget formatering** i ruden **Format** og indstille skyderen til **Til** for enten **Baggrundsfarveskalaer** eller **Skriftfarveskalaer**. Når du aktiverer en af indstillingerne, vises et link til *avancerede kontrolelementer*, så du kan tilpasse farver og værdier for farveformateringen.
  
  ![](media/desktop-matrix-visual/matrix-visual_18.png)

Begge fremgangsmåde giver samme resultat. Hvis du vælger *Avancerede kontrolelementer* vises følgende dialogboks, hvor du kan foretage justeringer:

![](media/desktop-matrix-visual/matrix-visual_19.png)

## <a name="next-steps"></a>Næste trin

Du vil måske også være interesseret i følgende artikler:

* [Brug gitterlinjer og fastgørelse til gitter i Power BI Desktop-rapporter](desktop-gridlines-snap-to-grid.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Datatyper i Power BI Desktop](desktop-data-types.md)

 