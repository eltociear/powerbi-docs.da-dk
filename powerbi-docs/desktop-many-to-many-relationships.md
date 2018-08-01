---
title: Mange til mange-relationer i Power BI Desktop (Preview)
description: Brug mange til mange-relationer i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 1105de002f6461589d61c6f0077cceeedaada471
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2018
ms.locfileid: "39210890"
---
# <a name="many-to-many-relationships-in-power-bi-desktop-preview"></a>Mange til mange-relationer i Power BI Desktop (Preview)

Med funktionen **Mange til mange-relationer**  i **Power BI Desktop** kan du joinforbinde tabeller ved hjælp af en kardinalitet af **Mange til mange**, og du kan nemmere og mere intuitivt oprette datamodeller, der indeholder flere datakilder. Funktionen **mange til mange-relation** er en del af de større funktioner til **sammensatte modeller**  i **Power BI Desktop**.

![mange til mange i dialogboksen Rediger relation](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Funktionen med **mange til mange-relationer** i **Power BI Desktop** er en del af en samling med tre relaterede funktioner:

* **Sammensatte modeller** – gør det muligt for en rapport at have flere dataforbindelser, herunder DirectQuery-forbindelser eller import, i en vilkårlig kombination af disse.
* **Mange til mange-relationer** – med **sammensatte modeller** kan du oprette **mange til mange-relationer** mellem tabeller, fjerne kravene om entydige værdier i tabeller og undgå tidligere løsninger som f.eks at introducere nye tabeller kun for at oprette relationer. 
* **Lagringstilstand** – du kan nu angive, hvilke visualiseringer der kræver en forespørgsel til backend-datakilder, og dem, hvor det ikke kræves, importeres, selvom de er baseret på DirectQuery, hvilket forbedrer ydeevnen og reducerer belastningen af backenden. Tidligere ville selv enkle visualiseringer som udsnit igangsætte forespørgsler, der blev sendt til backend-kilderne. 

Denne samling af tre relaterede funktioner for **sammensatte modeller** er beskrevet i særskilte artikler:

* **Sammensatte modeller** er beskrevet i detaljer i artiklen [sammensatte modeller i Power BI Desktop (Preview)](desktop-composite-models.md).
* **Mange til mange-relationer** beskrives i denne artikel.
* **Lagringstilstand** beskrives i sin egen artikel, [lagringstilstand i Power BI Desktop (Preview)](desktop-storage-mode.md).

## <a name="enabling-the-many-to-many-relationships-preview-feature"></a>Sådan aktiveres prøveversionen af mange til mange-relationer

Funktionen med **mange til mange-relationer** er en del af funktionerne til **sammensatte modeller**. Den er i prøveversion og skal aktiveres i **Power BI Desktop**. Du kan aktivere **sammensatte modeller** ved at vælge **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning** og derefter vælge afkrydsningsfeltet **Sammensatte modeller**.

![aktivering af funktioner til eksempelvisning](media/desktop-composite-models/composite-models_02.png)

Du skal genstarte **Power BI Desktop**, før funktionen kan bruges.

![genstart er nødvendig for at ændringerne kan træde i kraft](media/desktop-composite-models/composite-models_03.png)


## <a name="what-many-to-many-relationships-solves"></a>Formålet med mange til mange-relationer

Før funktionen til **mange til mange-relationer** blev introduceret, var det lidt mere vanskeligt at definere en relation mellem to tabeller i Power BI, da mindst én af de involverede kolonner i relationen skulle have entydige værdier. I mange tilfælde vil tabeller dog ikke have en kolonne med entydige værdier. 

To tabeller kan f.eks. have en kolonne, der indeholder *Land*, men værdierne for *Land* var ikke entydige i nogen af tabellerne. Inden det var muligt at joinforbinde sådanne tabeller, var det nødvendigt med en løsning, hvor der blev tilføjet ekstra tabeller med de nødvendige entydige værdier i modellen. Funktionen **mange til mange-relationer** giver en alternativ metode, der gør det muligt for sådanne tabeller at blive joinforbundet direkte ved hjælp af en relation med en kardinalitet af **Mange til mange**.  

## <a name="using-many-to-many-relationships"></a>Brug af mange til mange-relationer

Når du definerer en relation mellem to tabeller i Power BI, skal du definere kardinalitet for relationen. Eksempelvis kan relationen mellem *ProductSales* og *Product* (med kolonnerne *ProductSales[ProductCode]* og *Product[ProductCode]*) være defineret som **Mange til 1**, da der er mange salg for hvert produkt, og tabellen *Product* *(ProductCode)* er entydig. Når du definerer en relationskardinalitet som **Mange-1**, **1-mange** eller **1-1**, vil Power BI udføre en validering for at sikre, at den valgte kardinalitet stemmer overens med de faktiske data.

Se f.eks. nærmere på den enkle model i følgende billede.

![relationsvisning](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

Forestil dig, at tabellen *Product* kun indeholder to rækker.

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

Forestil dig også, at tabellen *Sales* kun indeholder fire rækker, herunder *Sales* for produktet **C**, som ikke findes i tabellen *Product* (pga. en fejl i refererenceintegriteten).

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

En visualisering, der viser *ProductName* og *Price* (fra tabellen *Product*) sammen med totalen *Qty* for hvert produkt (fra tabellen *ProductSales*) ville blive vist som i følgende billede: 

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

Som du kan se i det forrige billede, er der en række i visualiseringen, hvor *ProductName* er tom, og den er knyttet til salget af produktet *C*. Den tomme række står for følgende:

* Alle de rækker i tabellen *ProductSales*, hvor der ikke findes en tilsvarende række i tabellen *Product*. Der er problemer med referenceintegriteten, som det kan ses for produkt *C* i dette eksempel.

* Alle de rækker i tabellen *ProductSales*, hvor kolonnen med den fremmede nøgle er Null. 

I begge tilfælde vil den tomme række stå for de salg, hvor *ProductName* og *Price* er ukendt.

Det kan nogle gange skyldes, at tabellerne er joinforbundne via to kolonner, men at ingen af kolonnerne er entydige. Du kan f.eks. overveje følgende to tabeller:

* Tabellen *Sales* indeholder salgsdata efter *State*, hvor hver række indeholder salgsbeløbet for den type salg i den stat (inklusive staterne CA, WA og TX) 

    ![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* Tabellen *CityData* indeholder data om byer, herunder indbyggertal og stat (inklusive staterne CA, WA og New York)

    ![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

Selvom kolonnen *State* findes i begge tabeller, og det er almindeligt at ville rapportere om det samlede salg (*Sales*) efter stat (*State*) sammen med befolkningstallet i hver stat, opstår der et problem: kolonnen *State* er ikke entydig i nogen af kolonnerne. 

## <a name="the-prior-workaround"></a>Den tidligere løsning

I versioner af **Power BI Desktop** fra før udgivelsen i juli 2018 var det ikke muligt at oprette en relation direkte mellem disse tabeller. En almindelig løsning på problemet var at gøre følgende:

* Opret en tredje tabel, der indeholder kun de entydige id'er for *State*. Det kunne være en beregnet tabel (defineret med DAX), eller det kunne være en tabel, der var defineret med en forespørgsel, som var defineret i **Query Editor**, og som indeholdt de entydige id'er fra en af tabellerne eller det samlede forende sæt.

* Relater de to oprindelige tabeller til den nye tabel ved hjælp af almindelige **Mange-1*-relationer.

Den ekstra tabel kunne enten være synlig, eller den kunne være skjult, så den ikke blev vist på feltlisten. Hvis det sidste var tilfældet, ville **Mange-1**-relationen som regel være indstillet til at filtrere i begge retninger, f.eks. så feltet *State* fra en af tabellerne kunne bruges, med efterfølgende krydsfiltrering til at udfylde den anden tabel. Den løsning vises i følgende billede af **relationsvisningen**.

![relationsvisning](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

En visualisering, der viser *State* (fra tabellen *CityData*) sammen med totalen af *Population* og totalen af *Sales*, vil se ud som følgende.

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

Vær opmærksom på, at da denne løsning bruger staten fra tabellen *CityData*, vises der kun de *stater*, som findes i den tabel (derfor vises staten TX ikke). Selvom rækken med totalen indeholder alle **Sales** (inklusive dem for TX), vil detaljerne til forskel fra *Mange-1*-relationen ikke indeholde en tom række for de fejlbehæftede rækker. Der vil heller ikke være en tom række for *Sales*, hvor der var en null-værdi for *State*.

Hvis *City* også blev føjet til visualiseringen, vil indbyggertallet pr. *City* være kendt, og *Sales* for *City* vil være en gentagelse af *Sales* for den tilsvarende *State* (som det normalt er tilfældet, når du grupperer en kolonne, der ikke relaterer til en aggregeret måling), som det kan ses i det følgende billede.

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

Hvis den nye tabel *salg* blev defineret til at være foreningen af alle *States* i denne løsning, og tabellen blev gjort synlig på feltlisten, ville den samme visualisering vise *State* (i den nye tabel) sammen med totalen for *Population*, og totalen for *Sales* vil derefter være som følger.

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

I det tilfælde vil *TX* (med *Sales*, men med ukendt Population) blive vist i visualiseringen, og *New York* (med en kendt Population, men ingen *Sales*) vil være inkluderet. 

Som du kan se, var denne løsning ikke optimal, og den medførte mange problemer. Med oprettelsen af **mange til mange-relationen** bliver problemerne løst, som det er beskrevet i følgende afsnit.

## <a name="using-many-to-many-relationships-instead-of-the-workaround"></a>Brug af mange til mange-relationer i stedet for løsningen

I versioner af **Power BI Desktop** fra og med udgivelsen i juli 2018 kan du direkte relatere sådanne tabeller, som er beskrevet i forrige afsnit, uden at du skal bruge en løsning. Det er nu muligt at indstille kardinaliteten af en relation til **Mange til mange** for at angive, at ingen af tabellerne indeholder entydige værdier. For disse relationer kan du stadig styre, hvilke tabeller der filtrerer andre tabeller, eller du kan have tovejsfiltrering, hvor begge tabeller filtrerer hinanden.  

> [!NOTE]
> Muligheden for at oprette **Mange til mange**-relationer findes i prøveversion, men det er ikke muligt at publicere modeller med **Mange til mange**-relationer til Power BI-tjenesten i prøveversionen. 

I **Power BI Desktop** vil kardinalitet som standard være **Mange til mange**, når det er fastslået, at ingen af tabellerne indeholder entydige værdier for kolonnerne i relationen. Når det er tilfældet, vises der en advarsel, hvor du skal bekræfte, at denne relationsindstilling er bevidst, så det ikke risikeres, at det er en utilsigtet effekt af et dataproblem. 

Hvis du f.eks. opretter en relation direkte mellem *CityData* og *Sales*, hvor filtre skal gå fra *CityData* til *Sales*, vil dialogboksen med relationer blive vist som i følgende billede.

![Dialogboksen Rediger relation](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Den resulterende **relationsvisning** vil indeholde den direkte **Mange til mange**-relation mellem de to tabeller. Udseendet af **feltlisten** og den efterfølgende funktionalitet, når visualiseringerne oprettes, vil derefter være den samme som at bruge den løsning, der blev beskrevet i det forrige afsnit, hvor den ekstra tabel (med distinkt *States*) ikke er synlig. Som i det tidligere afsnit, hvor løsningen beskrives, vil en visualisering med *States* sammen med den samlede befolkning og det samlede salg se ud på følgende måde.

![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

Den primære forskel mellem **Mange til mange**-relationer og de mere almindelige **Mange-1**-relationer er følgende.

* De værdier, der vises, omfatter ikke en tom række, som viser fejlbehæftede rækker i en af tabellerne, og de omfatter ikke de rækker, hvor den kolonne, der bruges i relationen i den anden tabel, er null.
* Det er ikke muligt at bruge funktionen *RELATED()* (da mere end én række kan være relateret)
* Hvis du bruger funktionen *ALL()* på en tabel, fjerner det ikke de filtre, som er anvendt på andre tabeller, der er relateret til den via en **Mange til mange**-relation. Hvis en måling f.eks. er defineret som følgende i det forrige eksempel, vil det ikke fjerne filtrene på kolonnerne i den relaterede tabel *CityData*:

    ![scripteksempel](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    Det vil medføre, at en visualisering, der viser *State*, *Sales* og *Sales total*, vises på følgende måde:

    ![tabelvisualisering](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

Derfor skal man være omhyggelig med at sikre, om de beregninger, der bruger *ALL(\<Table>)*, f.eks. *% of grand total*, returnerer de forventede resultater. 


## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Der er nogle få begrænsninger for denne frigivelse af **mange til mange-relationer** og **sammensatte modeller**.

Følgende flerdimensionelle kilder kan ikke bruges med **sammensatte modeller**:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI-datasæt

Når du opretter forbindelse til disse flerdimensionelle datakilder ved hjælp af DirectQuery, kan du ikke også oprette forbindelse til en anden DirectQuery-kilde eller kombinere med importerede data.

De eksisterende begrænsningerne ved at bruge DirectQuery gælder stadig, når du bruger **mange til mange-relationer**. Mange af disse begrænsninger er nu pr. tabel afhængigt af tabellens **lagringstilstand**. En beregnet kolonne i en importeret tabel kan f.eks. referere til andre tabeller, men en beregnet kolonne i en DirectQuery-tabel er stadig begrænset til kun at referere til kolonner i den samme tabel. Andre begrænsninger gælder for modellen som helhed, hvis nogen af tabellerne i modellen er DirectQuery. For eksempel er funktionerne **QuickInsights** og **Q&A** ikke tilgængelige for en model, hvis nogen af tabellerne i den har en **lagringstilstand** for DirectQuery. 

## <a name="next-steps"></a>Næste trin

I følgende artikler beskrives sammensatte modeller yderligere, og du finder også en detaljeret beskrivelse af DirectQuery.

* [Sammensatte modeller i Power BI Desktop (Preview)](desktop-composite-models.md)
* [Lagringstilstand i Power BI Desktop (Preview)](desktop-storage-mode.md)

Artikler om DirectQuery:

* [Brug af DirectQuery in Power BI](desktop-directquery-about.md)
* [Understøttede datakilder i forbindelse med DirectQuery i Power BI](desktop-directquery-data-sources.md)

