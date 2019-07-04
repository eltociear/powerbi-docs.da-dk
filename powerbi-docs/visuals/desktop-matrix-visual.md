---
title: Brug matrixvisualiseringen i Power BI
description: Få mere at vide om, hvordan matrixvisualisering giver dig mulighed for trinvist layout og findelt fremhævning i Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/25/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 2f50a6fc9fccc35333257caaf3efeb8185c8caff
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390380"
---
# <a name="use-the-matrix-visual-in-power-bi"></a>Brug matrixvisualiseringen i Power BI
**Matrix**visualiseringen svarer til en **tabel**.  En tabel understøtter to dimensioner, og dataene er flade, hvilket vil sige, at dublerede værdier vises og samles ikke. En matrix gør det lettere at få vist data på tværs af flere dimensioner på en meningsfuld måde – det understøtter et trinvist layout. Matricen samler automatisk dataene og gør det muligt at foretage detailudledning. 

Du kan oprette matrixvisualiseringer i rapporter i **Power BI Desktop** og **Power BI-tjenesten** og få tværgående fremhævning af elementer i matricen med andre visualiseringer på den pågældende rapportside. Du kan f.eks. vælge rækker, kolonner og endda individuelle celler og tværgående fremhævning. Og enkelte celler og markeringer med flere celler kan kopieres og indsættes i andre programmer. 

![matrix med tværgående fremhævning og kransediagram](media/desktop-matrix-visual/matrix-visual_2a.png)

Der er mange funktioner knyttet til matrixen, og vi vil gennemgå dem i følgende afsnit i denne artikel.


## <a name="understanding-how-power-bi-calculates-totals"></a>Sådan beregner Power BI totaler

Før du begynder at læse om, hvordan du bruger **matrix**visualiseringen, er det vigtigt at forstå, hvordan Power BI beregner værdierne for total og subtotal i tabeller og matricer. I rækker med total og subtotal evaluerer Power BI målingen hen over alle rækker i de underliggende data – det er ikke kun en simpel addition af værdierne i de synlige og viste rækker. Det betyder, at du kan ende med at have en anden værdi i rækken Total, end hvad du regnede med.

Se følgende matrixvisualiseringer. 

![sammenligner tabel og matrix](media/desktop-matrix-visual/matrix-visual_3.png)

I dette eksempel vises *Amount* for alle kombinationer af sælger/dato i hver række i matrixvisualiseringen længst til højre. Men da en sælger vises for flere datoer, kan tallene forekomme mere end én gang. Den nøjagtige total fra de underliggende data og en simpel addition af de synlige værdier kan derfor ikke sidestilles. Dette er et almindeligt mønster, når den værdi, du regner på, er på den "ene" side i en en til mange-relation.

Når du ser på totaler og subtotaler, skal du huske, at disse værdier er baseret på de underliggende data. De er ikke udelukkende baseret på de synlige værdier.

<!-- use Nov blog post video

## Expanding and collapsing row headers
There are two ways you can expand row headers. The first is through the right-click menu. You’ll see options to expand the specific row header you clicked on, the entire level or everything down to the very last level of the hierarchy. You have similar options for collapsing row headers as well.

![](media/desktop-matrix-visual/power-bi-expand1.png)

You can also add +/- buttons to the row headers through the formatting pane under the row headers card. By default, the icons will match the formatting of the row header, but you can customize the icons’ color and size separately if you want. 
Once the icons are turned on, they work similarly to the icons from PivotTables in Excel.

![](media/desktop-matrix-visual/power-bi-expand2.png)

The expansion state of the matrix will save with your report. It can be pinned to dashboards as well, but consumers will need to open up the report to change the state. Conditional formatting will only apply to the inner most visible level of the hierarchy. Note that this expand/collapse experience is not currently supported when connecting to AS servers older than 2016 or MD servers.

![](media/desktop-matrix-visual/power-bi-expand3.png)

Watch the following video to learn more about expand/collapse in the matrix:

-->
## <a name="using-drill-down-with-the-matrix-visual"></a>Brug detailudledning til matrixvisualiseringen
Med matrixvisualiseringen kan du foretage en mængde interessante aktiviteter for detailudledning, der ikke var tilgængelige før. Du kan f.eks. foretage detailudledning ved hjælp af rækker, kolonner og endda til individuelle afsnit og celler. Lad os se på, hvordan hver enkelt af disse fungerer.

### <a name="drill-down-on-row-headers"></a>Detailudledning på rækkeoverskrifter

Når du føjer flere felter til sektionen **Rækker** i området **Felter** i ruden Visualiseringer, aktiverer du detailudledning på rækkerne i matrixvisualiseringen. Dette minder om oprettelse af et hierarki, hvor du derefter kan foretage detailudledning (og så sikkerhedskopiering) via hierarkiet og analysere dataene på hvert niveau.

I det følgende billede indeholder sektionen **Rækker** *Sales stage* og *Opportunity size* og opretter en gruppering (eller et hierarki) i rækkerne, som vi kan foretage detailudledning af.

![Filtrerer kort, der viser, hvilke rækker der er valgt](media/desktop-matrix-visual/power-bi-rows-matrix.png)

Når der er oprettet gruppering for visualiseringen i sektionen **Rækker**, viser selve visualiseringen *detailudledningen* og *udvider* ikonerne i øverste venstre hjørne i visualiseringen.

![matrix med viste kontrolelementer til detailudledning](media/desktop-matrix-visual/power-bi-matrix-drilldown.png)

Som det er tilfældet med funktionsmåden til detailudledning og udvidelse i andre visualiseringer kan vi ved at vælge disse knapper bruge detailudledning (eller sikkerhedskopiering) gennem hierarkiet. I dette tilfælde kan vi foretage detailudledning fra *Sales stage* til *Opportunity size* som vist på følgende billede, hvor ikonet for detailudledning ét niveau ned (fork) er valgt.

![matrix med vist fork](media/desktop-matrix-visual/power-bi-matrix-drill3.png)

Ud over at bruge disse ikoner kan du vælge en af rækkeoverskrifterne og foretage detailudledning ved at foretage et valg i den menu, der vises.

![menuindstillinger for rækker i matrix](media/desktop-matrix-visual/power-bi-matrix-menu.png)

Bemærk, at der er nogle indstillinger i den viste menu, der udløser forskellige resultater:

Hvis du vælger **Foretag detailudledning**, udvides matricen for *det pågældende* rækkeniveau, og alle andre rækkeoverskrifter *udelades* bortset fra den rækkeoverskrift, der blev valgt. På følgende billede er **Forslag** > **Detailudledning** valgt. Bemærk, at andre rækker på øverste niveau ikke længere vises i matrixen. Funktionen til detailudledning er nyttig, og den er specielt god, når vi kommer til afsnittet om **tværgående fremhævning**.

![matrix med detailudledning ét niveau ned](media/desktop-matrix-visual/power-bi-drill-down-matrix.png)

Vælg ikonet **Færre detaljer** for at komme tilbage til den forrige visning af øverste niveau. Hvis du derefter vælger **Forslag** > **Vis næste niveau**, får du vist en liste i stigende rækkefølge over alle elementer på næste niveau (i dette tilfælde feltet *Opportunity size*) uden den hierarkiske kategorisering på højere niveau.

![matrix, der bruger Vis næste niveau](media/desktop-matrix-visual/power-bi-next-level-matrix.png)

Vælg ikonet **Færre detaljer** i øverste venstre hjørne for at få matricen til at vise alle kategorier på øverste niveau, og vælg derefter **Forslag** > **Udvid til næste niveau** for at se alle værdierne for begge niveauer i hierarkiet – *Sales stage* og *Opportunity size*.

![matrix, der bruger Udvid næste niveau](media/desktop-matrix-visual/power-bi-matrix-expand-next.png)

Du kan også bruge menupunktet **Udvid** til at styre visningen yderligere.  Vælg f.eks. **Forslag** > **Udvid** > **Markering**. Power BI viser én totalrække for hver enkelt *Sales stage* og alle indstillinger for *Opportunity size* for *Forslag*.

![Matrix, efter at Udvid er anvendt på Forslag](media/desktop-matrix-visual/power-bi-matrix-expand.png)

### <a name="drill-down-on-column-headers"></a>Detailudledning på kolonneoverskrifter
Du kan også foretage detailudledning på **kolonner**, hvilket minder meget om detailudledning på rækker. I det følgende billede er der to felter i feltområdet **Kolonner**, hvilket opretter et hierarki, der minder om det, der blev brugt til rækkerne tidligere i denne artikel. I feltområdet **Kolonner** har vi *Område* og *Segment*. Så snart det andet felt blev føjet til **Kolonner**, blev der vist en ny rullemenu i visualiseringen. Den viser i øjeblikket **Rækker**.

![Matrix, efter at endnu en kolonneværdi blev tilføjet](media/desktop-matrix-visual/power-bi-matrix-row.png)

Hvis du vil foretage detailudledning for kolonner, skal du vælge **Kolonner** i menuen *Fortsæt analyse*, der findes i øverste venstre hjørne af matricen. Vælg området *East*, og vælg **Detailudledning**.

![menu til detailudledning for kolonner](media/desktop-matrix-visual/power-bi-matrix-column.png)

Når du vælger **Detailudledning**, vises næste niveau i kolonnehierarkiet for *Område > East*, hvilket i dette tilfælde er *Opportunity count*. Det andet område vises, men er nedtonet.

![matrix med detailudledning ét niveau ned for kolonner](media/desktop-matrix-visual/power-bi-matrix-column-drill.png)

Resten af punkterne i menuen fungerer i kolonner på samme måde, som de gør i rækker (se forrige afsnit, **Detailudledning på rækkeoverskrifter**). Du kan vælge **Vis næste niveau** og **Udvid til næste niveau** med kolonner, som du kan med rækker.

> [!NOTE]
> Ikonerne for detailudledning og færre detaljer øverst til venstre i matrixvisualiseringen gælder kun for rækker. Hvis du vil foretage detailudledning for kolonner, skal du bruge genvejsmenuen.

## <a name="stepped-layout-with-matrix-visuals"></a>Trinvist layout med matrixvisualisering

**Matrix**visualiseringen indrykker automatisk underkategorier i et hierarki under hvert overordnet element, hvilket kaldes et **trinvist layout**.

I den oprindelige version af matrixvisualiseringen blev underkategorier vist i en helt anden kolonne, der optager meget mere plads i visualiseringen. Billedet herunder viser tabellen i den oprindelige **matrixvisualisering**. Bemærk, at underkategorierne er i en separat kolonne.

![Skærmbillede af den gamle matrixvisualisering, der viser, at underkategorierne er i en separat kolonne.](media/desktop-matrix-visual/matrix-visual_14.png)

På det følgende billede kan du se en rigtig **matrix**-visualisering med **trinvist layout**. Bemærk, at kategorien *Computers* har underkategorier (Computers Accessories (Computertilbehør), Desktops (Stationære computere), Laptops (Bærbare computere), Monitors (Skærme) og osv.) let indrykket, hvilket visuelt giver et meget renere og mere komprimeret indtryk.

![den måde, en matrix i øjeblikket formaterer data på](media/desktop-matrix-visual/matrix-visual_13.png)

Du kan nemt justere indstillingerne for det trinvise layout. Når visualiseringen **Matrix** er valgt i sektionen **Format** (malerrulleikonet) i ruden **Visualiseringer**, kan du udvide sektionen **Rækkeoverskrifter**. Du har to muligheder: Til/fra-knappen til **trinvist layout** (som slår det til eller fra) og **indrykningen af det trinvise layout** (angiver mængden af indrykning i pixel).

![Rækkeoverskriftskortet, der viser kontrolelementet Trinvist layout](media/desktop-matrix-visual/power-bi-stepped-matrix.png)

Hvis du deaktiverer **Trinvist layout**, viser Power BI underkategorier i en anden kolonne og ikke indrykket under den overordnede kategori.

## <a name="subtotals-with-matrix-visuals"></a>Subtotaler med matrixvisualiseringer

Du kan slå subtotaler til eller fra i matrixvisualiseringer både for rækker og kolonner. I det følgende billede kan du se, at rækkesubtotaler er slået **til**.

![matrix, der viser totaler og subtotaler](media/desktop-matrix-visual/matrix-visual_20.png)

I sektionen **Format** i ruden **Visualiseringer** kan du udvide kortet **Subtotaler** og sætte skyderen **Rækkesubtotaler**  til **Fra**. Når du gør det, vises subtotaler ikke.

![matrix med subtotaler slået fra](media/desktop-matrix-visual/matrix-visual_21.png)

Den samme proces gælder for kolonnesubtotaler.

## <a name="cross-highlighting-with-matrix-visuals"></a>Tværgående fremhævning med matrixvisualiseringer

Med **matrix**-visualiseringen kan du vælge alle elementer i matrixen som basis for tværgående fremhævning. Når du markerer en kolonne i en **matrix**, fremhæves kolonnen i Power BI, og det samme gør andre visualiseringer på rapportsiden. Denne form for tværgående fremhævning har været en almindelig funktion i andre visualiseringer og markeringer af datapunkter, og nu kan **matrixvisualiseringen** få del i den.

Derudover fungerer Ctrl+klik også for tværgående fremhævning. I eksemplet herunder er en samling underkategorier f.eks. markeret i **Matrix**-visualiseringen. Bemærk, hvordan elementer, der ikke er valgt i visualiseringen, er nedtonet, og hvordan de andre visualiseringer på siden afspejler de valg, der er foretaget i **Matrix**-visualiseringen.

![Skærmbillede af matrixvisualiseringen sammen med to andre visualiseringer, der demonstrerer Ctrl + klik-funktionen for tværgående fremhævning.](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="copying-values-from-power-bi-for-use-in-other-applications"></a>Kopiering af værdier fra Power BI til brug i andre programmer

Din matrix eller tabel kan have indhold, som du gerne vil bruge i andre programmer: Dynamics CRM, Excel og andre Power BI-rapporter. Ved at højreklikke i Power BI kan du kopiere en enkelt celle eller en markering med flere celler til udklipsholder. Derefter kan du indsætte det i andet program.



* Hvis du vil kopiere værdien af en enkelt celle, skal du markere cellen, højreklikke og vælge **Kopiér værdi**. Med den ikke-formaterede celleværdi i din udklipsholder kan du nu indsætte det i et andet program.

    ![Skærmbillede af matrixvisualiseringen med en pil, der peger på en værdi, og genvejsmenuen udvidet, så indstillingerne Kopiér værdi og Kopiér markering vises.](media/desktop-matrix-visual/power-bi-cell-copy.png)



* Hvis du vil kopiere mere end en enkelt celle, skal du vælge et celleområde eller bruge Ctrl til at markere en eller flere celler. 

    ![Skærmbillede af matrixvisualiseringen med en pil, der fra tre fremhævede værdier peger på den udvidede genvejsmenu, så indstillingerne Kopiér værdi og Kopiér markering er fremhævet.](media/desktop-matrix-visual/power-bi-copy.png)

* Kopien inkluderer kolonne- og rækkeoverskrifterne.

    ![Skærmbillede, der viser Excel-rækker og -kolonner med de værdier, der er indsat i dem.](media/desktop-matrix-visual/power-bi-copy-selection.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Skygge og skrifttypefarver med matrixvisualiseringer
Når du bruger matrixvisualiseringen, kan du anvende **betinget formatering** (farver og skygge og datalinjer) på baggrunden af celler i matricen, og du kan anvende betinget formatering på selve teksten og værdierne.

Hvis du vil anvende betinget formatering, skal du vælge matrixvisualiseringen og åbne ruden **Formatér**. Udvid kortet **Betinget formatering**, og indstil skyderen til **Til** for **Baggrundsfarve** eller **Skriftfarve** eller **Datalinjer**. Når du aktiverer en af indstillingerne, vises et link til *avancerede kontrolelementer*, så du kan tilpasse farver og værdier for farveformateringen.
  
  ![Ruden Formatér, der viser kontrolelementet Datalinjer](media/desktop-matrix-visual/power-bi-matrix-data-bars.png)

Vælg *Avancerede kontrolelementer* for at få vist en dialogboks, hvor du kan foretage justeringer. I dette eksempel vises dialogboksen for **datalinjer**.

![Ruden Datalinjer](media/desktop-matrix-visual/power-bi-data-bars.png)

## <a name="next-steps"></a>Næste trin

[Punkt- og boblediagrammer i Power BI](power-bi-visualization-scatter.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)