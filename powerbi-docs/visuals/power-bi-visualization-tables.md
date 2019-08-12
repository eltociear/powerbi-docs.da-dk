---
title: Tabelvisualiseringer i Power BI-rapporter og -dashboards
description: Selvstudium til at arbejde med tabelvisualiseringer i Power BI-rapporter og dashboards, herunder, hvordan du tilpasser kolonnebredder.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 857db3240385e9bf1b4e0416cc1200d1a029d73e
ms.sourcegitcommit: cc4b18d55b2dca8fdb1bef00f53a0a808c41432a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/09/2019
ms.locfileid: "68867199"
---
# <a name="tables-in-power-bi-reports-and-dashboards"></a>Tabeller i Power BI-rapporter og -dashboards

En tabel er et gitter, der indeholder relaterede data i logiske serier af rækker og kolonner. Den kan også indeholde overskrifter og en række til totaler. Tabeller fungerer godt med kvantitative sammenligninger, hvor du får vist mange værdier for en enkelt kategori. I denne tabel vises f.eks. fem forskellige målinger for **Kategori**.

![Skærmbillede af en tabel, der viser fem forskellige målinger for Kategori.](media/power-bi-visualization-tables/table.png)

Opret tabeller i rapporter, og udfør tværgående fremhævning af elementer i tabellen med andre visualiseringer på samme rapportside. Du kan vælge rækker, kolonner og endda individuelle celler og tværgående fremhævning. Du kan også kopiere og indsætte de enkelte celler og markeringer med flere celler i andre programmer.

## <a name="when-to-use-a-table"></a>Du skal bruge en tabel, til at

Tabeller er et godt valg til at:

* se og sammenligne detaljerede data og nøjagtige værdier (i stedet for visuelle repræsentationer).

* se data i tabelformat.

* se numeriske data efter kategori.

## <a name="prerequisites"></a>Forudsætninger

* Power BI-tjenesten eller Power BI Desktop

* Rapporten Retail Analysis Sample

## <a name="get-the-retail-analysis-sample-report"></a>Hent rapporten Retail Analysis Sample

I denne vejledning bruges Retail Analysis Sample (Eksempel på detailhandelsanalyse). Oprettelse af en visualisering kræver redigeringsrettigheder til datasættet og rapporten. Heldigvis kan alle Power BI-eksemplerne redigeres. Hvis en person deler en rapport med dig, kan du ikke oprette visualiseringer i rapporter. Hvis du vil følge med, skal du hente [rapporten Retail Analysis Sample](../sample-datasets.md).

Når du har hentet datasættet for **Retail Analysis Sample**, kan du komme i gang.

## <a name="create-a-table"></a>Opret en tabel

Du opretter den tabel, der vises i starten af artiklen, for at få vist salgsværdierne efter varekategori.

1. Vælg **Datasæt** > **Opret en rapport** fra **Mit arbejdsområde**.

    ![Skærmbillede af Datasæt > Opret en rapport.](media/power-bi-visualization-tables/power-bi-create-a-report.png)

1. Vælg **Element** > **Kategori** i ruden **Felter**.

    Power BI opretter automatisk en tabel over alle kategorierne.

    ![resultat af tilføjelse af kategori](media/power-bi-visualization-tables/power-bi-table1.png)

1. Vælg **Sales > Average Unit Price** og **Sales > Last Year Sales**

1. Vælg derefter **Sales > This Year Sales**, og vælg alle tre indstillinger: **Værdi**, **Mål** og **Status**.

1. Find **Værdier** i ruden **Visualiseringer**, og træk værdierne, indtil rækkefølgen af diagramkolonnerne stemmer overens med det første billede på denne side. Du kan nu se følgende under **Værdier**:

    ![Værdibrønd](media/power-bi-visualization-tables/power-bi-table2.png)

1. Fastgør tabellen til dashboardet ved at vælge ikonet med tavlenålen ![thumbtack](media/power-bi-visualization-tables/pbi_pintile.png) i øverste højre hjørne af visualiseringen.

## <a name="format-the-table"></a>Formatér tabellen

Du kan formatere en tabel på mange måder. Kun et par af dem beskrives her. Hvis du vil vide mere om andre formateringsindstillinger, kan du åbne ruden **Formatér** (ikonet med malerrullen ![malerrulle](media/power-bi-visualization-tables/power-bi-format.png)) og prøve dig frem.

* Prøv at formatere tabelgitteret. Her tilføjer du et blåt lodret gitter, du tilføjer mellemrum mellem rækkerne og forstørrer kanten og tekststørrelsen en smule.

    ![Gitterkort](media/power-bi-visualization-tables/power-bi-table-gridnew.png)

    ![tabel, der viser resultater](media/power-bi-visualization-tables/power-bi-table-grid3.png)

* I kolonneoverskrifterne skal du ændre baggrundsfarven, tilføje en kant og øge skriftstørrelsen.

    ![Kolonneoverskriftskort](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

    ![overskriftsformatering i tabel](media/power-bi-visualization-tables/power-bi-table-column2.png)

* Du kan også formatere enkelte kolonner og kolonneoverskrifter. Start ved at udvide **feltformateringen**, og vælg den kolonne, der skal formateres, på rullelisten. Afhængigt af kolonneværdierne kan du bruge **feltformatering** til at angive oplysninger som: visningsenheder, skriftfarve, antal decimaler, baggrund, justering med mere. Når du har valgt de ønskede indstillinger, kan du beslutte, om du også vil anvende disse indstillinger til sidehovedet og rækken Totaler.

    ![Feltformatering for This year sales](media/power-bi-visualization-tables/power-bi-field-formatting.png)

    ![Feltformatering for This year sales i tabellen](media/power-bi-visualization-tables/power-bi-field-formatting-1.png)

* Efter lidt yderligere formatering ser den endelige tabel sådan ud.

    ![tabel med al formatering indtil videre](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Betinget formatering

*Betinget formatering* er en type formatering. Power BI anvender betinget formatering på felter i området **Værdier** i ruden **Visualiseringer**.

Med betinget formatering af tabeller kan du angive brugerdefinerede baggrundsfarver og skriftfarver for celler baseret på celleværdier, bl.a. ved hjælp af gradueringsfarver.

1. Vælg ikonet **Felter** ![feltikonet](media/power-bi-visualization-tables/power-bi-fields-icon.png) i ruden **Visualiseringer**.

1. Vælg pil ned ud for den værdi under **Værdier**, du vil formatere (eller højreklik på feltet).

    > [!NOTE]
    > Du kan kun administrere betinget formatering for felter i området **Værdier** under **Felter**.

    ![sti til baggrundsfarveskalaer](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)

1. Vælg **Baggrundsfarve**.

1. Du kan konfigurere farven og **Minimum**-værdien og **Maksimum**-værdien i den dialogboks, der vises. Hvis du vælger indstillingen **Divergerende**, kan du også konfigurere en valgfri værdi af typen **Centreret**.

    ![skærmen Baggrundsfarveskalaer](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)

    Jeg vil prøve at anvende brugerdefineret formatering til Average Unit Price-værdierne. Vælg **Divergerende**, tilføj nogle farver, og vælg **OK**.

    ![tabel, der viser divergerende farver](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
1. Tilføj et nyt felt i tabellen, der har både positive og negative værdier. Vælg **Sales > Total Sales Variance**.

    ![viser et nyt felt længst til højre](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)

1. Tilføj betinget formatering for datalinjen ved at vælge den nedadvendte pil ud for **Total Sales Variance** og vælge **Betinget formatering > Datalinjer**.

    ![sti til udvalgte datalinjer](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)

1. I den viste dialogboks kan du angive farver for **Positiv streg** og **Negativ streg**, markere afkrydsningsfeltet **Vis kun streg** og foretage eventuelle andre ændringer.

    ![afkrydsning af Vis kun streg](media/power-bi-visualization-tables/power-bi-data-bars.png)

1. Vælg **OK**.

    Datalinjerne erstatter de numeriske værdier i tabellen, så det er nemmere at skimme den.

    ![samme tabel, men med søjler i sidste kolonne](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)

Hvis du vil fjerne betinget formatering fra en visualisering, skal du højreklikke på feltet igen og vælge **Fjern betinget formatering**.

> [!TIP]
> Du kan også angive betinget formatering i ruden **Formatér**. Vælg den værdi, du vil formatere, og angiv derefter **Farveskalaer** eller **Datalinjer** til **Til** for at anvende standardindstillingerne. Hvis du vil tilpasse indstillingerne, skal du vælge **Avancerede kontrolelementer**.

## <a name="copy-values-from-power-bi-tables-for-use-in-other-applications"></a>Kopiér værdier fra Power BI-tabeller til brug i andre programmer

Din tabel eller matrix kan have indhold, som du ønsker at bruge i andre programmer, f.eks. Dynamics CRM, Excel og endda andre Power BI-rapporter. Når du højreklikker i en celle i Power BI, kan du kopiere dataene i en enkelt celle eller en markering med flere celler til udklipsholder og indsætte dem i det andet program.

Sådan kopierer du værdien af en enkelt celle:

1. Markér den celle, du vil kopiere.

1. Højreklik i cellen.

1. Vælg **Kopiér** > **Kopiér værdi**.

    ![kopieringsindstillinger](media/power-bi-visualization-tables/power-bi-copy-value.png)

    Den ikke-formaterede celleværdi er nu i din udklipsholder, og du kan indsætte den i et andet program.

Sådan kopierer du mere end en enkelt celle:

1. Markér et celleområde, eller brug **Ctrl** til at markere en eller flere celler.

1. Højreklik i en af de celler, du har markeret.

1. Vælg **Kopiér** > **Kopiér markering**.

    ![kopieringsindstillinger](media/power-bi-visualization-tables/power-bi-copy-selection.png)

    Kopien inkluderer kolonne- og rækkeoverskrifterne.

    ![indsætte i Excel](media/power-bi-visualization-tables/power-bi-paste-selection.png)

## <a name="adjust-the-column-width-of-a-table"></a>Tilpas kolonnebredden i en tabel

Nogle gange kan Power BI afskære en kolonneoverskrift i en rapport og på et dashboard. Hvis du vil kunne se hele kolonnenavnet, skal du pege på mellemrummet til højre for overskriften for at få vist dobbeltpilene og klikke og trække.

![videocloseup af ændring af kolonnestørrelse](media/power-bi-visualization-tables/resizetable.gif)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

Når du anvender kolonneformatering, kan du kun vælge én indstilling for justering pr. kolonne: **Automatisk**, **Venstre**, **Centreret**, **Højre**. En kolonne indeholder som regel enten tekst eller tal og ikke en blanding. Hvis en kolonne indeholder både tal og tekst, vil indstillingen **Automatisk** venstrejustere tekst og højrejustere tal. Denne funktionalitet understøtter de sprog, der læses fra venstre mod højre.

## <a name="next-steps"></a>Næste trin

* [Trækort i Power BI](power-bi-visualization-treemaps.md)

* [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
