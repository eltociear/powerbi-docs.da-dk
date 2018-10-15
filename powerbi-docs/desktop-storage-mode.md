---
title: Brug Lagringstilstand i Power BI Desktop (Preview)
description: Brug Lagringstilstand til at kontrollere, om data cachelagres i hukommelsen for rapporter i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/17/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: ce4aab1a477485a30a4166d86d166a4ac289108f
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/17/2018
ms.locfileid: "45974224"
---
# <a name="storage-mode-in-power-bi-desktop-preview"></a>Lagringstilstand i Power BI Desktop (Preview)

I **Power BI Desktop** kan du angive tabellers **lagringstilstand**, hvilket giver dig kontrol over, om tabeldata cachelagres i hukommelsen for rapporter. 

![Lagringstilstand i Power BI Desktop](media/desktop-storage-mode/storage-mode_01.png)

Indstilling af **lagringstilstand** giver mange fordele. Du kan angive **lagringstilstand** for hver enkelt tabel i din model, hvilket gør det muligt for et enkelt datasæt at drage fordel af en eller flere af følgende fordele:

* **Forespørgselsydeevne** – når brugere interagerer med visuelle elementer i Power BI-rapporter, sendes DAX-forespørgsler til datasættet. Cachelagring af data til hukommelsen ved korrekt at angive **lagringstilstand** kan øge forespørgslens kvalitet og dine rapporters interaktivitet.
* **Store datasæt** – tabeller, der ikke cachelagres, forbruger ikke hukommelse beregnet til cachelagring. Du kan aktivere interaktive analyser over store datasæt, der er for store eller dyre til helt at cachelagre i hukommelsen. Du kan vælge, hvilke tabeller, der er værd at cachelagre, og hvilke der ikke er.
* **Optimering af dataopdatering** – tabeller, der ikke er cachelagret, skal ikke opdateres. Du kan reducere opdateringstider ved kun at cachelagre de nødvendige data for at opfylde dine serviceniveauaftaler og virksomhedens behov.
* **Tidskrav i nærheden af realtid** – tabeller med tidskrav i nærheden af realtid kan drage fordel af ikke at blive cachelagret for at mindske dataventetiden.
* **Tilbageførsel** – tilbageførsel gør det muligt for virksomheder at granske mulige scenarier ved at ændre celleværdier. Brugerdefinerede programmer kan foretage ændringer af datakilden. Tabeller, der ikke er cachelagret, kan straks afspejle ændringer og dermed tillade umiddelbar analyse af konsekvenserne.

Indstillingen **lagringstilstand** i **Power BI Desktop** er én af tre relaterede funktioner:

* **Sammensatte modeller** – gør det muligt for en rapport at have flere dataforbindelser, herunder DirectQuery-forbindelser eller import, i en vilkårlig kombination af disse.
* **Mange til mange-relationer** – med **sammensatte modeller** kan du oprette **mange til mange-relationer** mellem tabeller, fjerne kravene om entydige værdier i tabeller og fjerne tidligere løsninger som f.eks at introducere nye tabeller kun for at oprette relationer. 
* **Lagringstilstand** – du kan nu angive, hvilke visuelle elementer der kræver en forespørgsel til backend-datakilder, og dem, hvor det ikke kræves, importeres, selvom de er baseret på DirectQuery, hvilket forbedrer kvaliteten og reducerer belastningen af backenden. Tidligere ville selv enkle visuelle elementer som udsnit igangsætte forespørgsler, der blev sendt til backend-kilderne. 

Denne samling af tre relaterede funktioner knyttet til **sammensatte modeller** er hver beskrevet i særskilte artikler:

* **Sammensatte modeller** er beskrevet i detaljer i deres egen artikel: [Sammensatte modeller i Power BI Desktop (Preview)](desktop-composite-models.md).
* **Mange-til-mange-relationer** er beskrevet i deres egen artikel [mange-til-mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md).
* **Lagringstilstand** er beskrevet nærmere i denne artikel.

## <a name="enabling-the-storage-mode-preview-feature"></a>Aktivering af lagringstilstandens prøveversionsfunktion

Funktionen **Lagringstilstand** fås i prøveversion og skal aktiveres i **Power BI Desktop**. Du aktiverer **lagringstilstand** ved at vælge **Filer > Indstillinger > Indstillinger > Prøveversionsfunktioner** og derefter ved at markere afkrydsningsfeltet **Sammensatte modeller**. 

![aktivering af prøveversionsfunktioner](media/desktop-composite-models/composite-models_02.png)

Du skal genstarte **Power BI Desktop**, før funktionen kan bruges.

![genstart påkrævet, for at ændringerne kan træde i kraft](media/desktop-composite-models/composite-models_03.png)


## <a name="using-the-storage-mode-property"></a>Korrekt brug af lagringstilstand

**Lagringstilstand** er en egenskab, du kan angive på hver tabel i din model. For at angive **lagringstilstanden** skal du vælge tabellen i ruden **Felter** og derefter højreklikke for at få vist genvejsmenuen. Vælg **Egenskaber** i genvejsmenuen.

![Vælg Egenskaber i genvejsmenuen](media/desktop-storage-mode/storage-mode_02.png)

Valgmuligheden **lagringstilstand** vises i ruden **Feltegenskaber** for tabellen. Derfra kan du få vist den aktuelle **lagringstilstand** eller ændre den.

![Angiv lagringstilstand for en tabel](media/desktop-storage-mode/storage-mode_03.png)

Der er tre værdier for **lagringstilstand**:

* **Import** – importerede tabeller cachelagres, når **Import** er angivet. Forespørgsler sendt til Power BI-datasættet, der returnerer data fra importtabeller, kan kun opfyldes fra cachelagrede data.
* **DirectQuery** – med denne indstilling cachelagres DirectQuery-tabeller ikke. Forespørgsler sendt til Power BI-datasættet (f.eks. DAX-forespørgsler), der returnerer data fra DirectQuery-tabeller, kan kun opfyldes ved at udføre forespørgsler efter behov til datakilden. Forespørgsler, der er sendt til datakilden, bruger forespørgselssproget for denne datakilde (f.eks. SQL).
* **Dual** – Dual-tabeller kan enten fungere som cachelagrede eller ikke-cachelagrede, afhængigt af i hvilken kontekst forespørgslen blev sendt til Power BI-datasættet. I nogle tilfælde opfyldes forespørgsler fra cachelagrede data, i andre tilfælde opfyldes forespørgsler ved at udføre en forespørgsel efter behov til datakilden.

Ændring af en tabel til Import kan *ikke fortrydes*; handlingen kan ikke føres tilbage til DirectQuery, eller tilbage til Dual.

## <a name="constraints-on-directquery-and-dual-tables"></a>Begrænsninger af DirectQuery- og Dual-tabeller

Dual-tabeller er underlagt de samme begrænsninger som DirectQuery-tabeller. Disse omfatter begrænsede M-transformationer og begrænsede DAX-funktioner i beregnede kolonner. Se [Konsekvenser ved brugen af DirectQuery](desktop-directquery-about.md#implications-of-using-directquery) for at få flere oplysninger.

## <a name="relationship-rules-on-tables-with-different-storage-modes"></a>Relationsregler for tabeller med forskellige lagringstilstande

Relationer skal overholde regler, baseret på de relaterede tabellers **lagringstilstand**. I dette afsnit kan du se eksempler på gyldige kombinationer. Se [mange til mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md) for komplette oplysninger.

På et datasæt med en enkelt datakilde er følgende **1-til-mange**-relationskombinationer gyldige:

| Tabellen på siden **mange** | Tabellen på siden **1** |
| ------------- |----------------------| 
| Dual          | Dual                 | 
| Importér        | Import eller Dual       | 
| DirectQuery   | DirectQuery eller Dual  | 

## <a name="propagation-of-dual"></a>Overførsel af Dual
Lad os tage et kig på et eksempel. Se den følgende simple model, hvor alle tabellerne er fra en enkelt kilde, der understøtter Import og DirectQuery.

![Eksempel på Relationsvisning for lagringstilstand](media/desktop-storage-mode/storage-mode_04.png)

Lad os sige, at alle tabeller i denne model er DirectQuery til at starte med. Hvis vi derefter ændrer **lagringstilstanden** for tabellen *SurveyResponse* til Import, så vises nedenstående meddelelse:

![Dialogboks med advarsel om lagringstilstand](media/desktop-storage-mode/storage-mode_05.png)

Dimensionstabellerne (*Kunde*, *Dato* og *Geografi*) skal være angivet som **Dual** for at overholde de tidligere beskrevne relationsregler. I stedet for at kræve, at disse tabeller angives som **Dual** i forvejen, kan de angives med en enkelt handling.

Overførselslogikken er designet til at hjælpe med modeller, der indeholder mange tabeller. Lad os antage, at du har en model med 50 tabeller, og kun visse faktatabeller (transaktionstabeller) skal cachelagres. Logikken i **Power BI Desktop** regner ud, hvad det mindste antal sæt af dimensionstabeller er, der skal angives som **Dual**, så du ikke behøver at gøre det.

Overførselslogikken gennemgår kun den ene side af **1-til-mange**-relationer.

* Ændring af tabellen *Kunde* til **Import** (i stedet for at ændre *SurveyResponse*) er ikke tilladt på grund af dens relationer til DirectQuery-tabellerne *Salg* og *SurveyResponse*.
* Ændring af tabellen *Kunde* til **Dual** (i stedet for at ændre *SurveyResponse*) er tilladt. Overførselslogikken angiver tabellen *Geografi* til også at være **Dual**.

## <a name="storage-mode-usage-example"></a>Eksempel på brugen af lagringstilstand
Lad os fortsætte med eksemplet fra det forrige afsnit og antage, at vi anvender de følgende indstillinger for tilstanden **lagringstilstand**:

| Tabel                   | Lagringstilstand         |
| ----------------------- |----------------------| 
| *Salg*                 | DirectQuery          | 
| *SurveyResponse*        | Importér               | 
| *Dato*                  | Dual                 | 
| *Kunde*              | Dual                 | 
| *Geografi*             | Dual                 | 


Når du angiver disse egenskabsindstillinger for lagringstilstand, sker der følgende under forudsætning af, at tabellen *Salg* har en betydelig datamængde.
* Dimensionstabeller (*Dato*, *Kunde* og *Geografi*) cachelagres, så de indledende rapportindlæsningstider bør være hurtige, når der hentes udsnitsværktøjsværdier til visning.
* De følgende resultater opnås ved ikke at cachelagre tabellen *Salg*:
    * Tiderne for dataopdateringer forkortes, og hukommelsesforbrug mindskes
    * Rapportforespørgsler baseret på tabellen *Salg* kører i tilstanden DirectQuery, som kan tage længere tid, men er tættere på i realtid, fordi der ikke introduceres nogen ventetid knyttet til cachelagring

* Rapportforespørgsler baseret på tabellen *SurveyResponse* returneres fra cachelagring i hukommelsen og bør derfor foregå relativt hurtigt.

## <a name="queries-that-hit-or-miss-the-cache"></a>Forespørgsler, der findes eller ikke findes i cachen

Ved at forbinde **SQL Profiler** til porten til diagnosticering for **Power BI** kan du se, hvilke forespørgsler der findes eller ikke findes i cachelageret i hukommelsen ved at udføre en sporing baseret på de følgende hændelser:

* Forespørgsler Hændelser\Forespørgsel start
* Forespørgsel Behandler\Vertipaq SE-forespørgsel start
* Forespørgsel Behandler\DirectQuery start

For hver *Forespørgsel start*-hændelse skal du kontrollere andre hændelser med samme *ActivityID*. Hvis der f.eks. ikke er en *DirectQuery start*-hændelse, men der er en *Vertipaq SE-forespørgsel start*-hændelse, så blev forespørgslen besvaret af cachen.

Forespørgsler, der refererer til tabeller i **Dual**-tilstanden, returnerer data fra cachen, hvis det er muligt, ellers vender de tilbage til DirectQuery.

I forlængelse af det forrige eksempel henviser den følgende forespørgsel kun til en kolonne fra tabellen *Dato*, som er i **Dual**-tilstand. Derfor bør den finde indhold i cachen.

![Script til diagnosticering af lagringstilstand](media/desktop-storage-mode/storage-mode_06.png)

Følgende forespørgsel henviser kun til en kolonne fra tabellen *Salg*, som er i tilstanden **DirectQuery**. Derfor bør den *ikke* finde indhold i cachen.

![Script til diagnosticering af lagringstilstand](media/desktop-storage-mode/storage-mode_07.png)

Følgende forespørgsel er interessant, fordi den kombinerer begge kolonner. Denne forespørgsel finder ikke noget indhold i cachen. Indledningsvist forventer du nok, at den henter *CalendarYear*-værdier fra cachen og *SalesAmount*-værdier fra kilden og derefter kombinerer resultaterne, men det vil være mindre effektivt end at sende SUMMÉR/GRUPPÉR EFTER-handlingen til kildesystemet. Hvis handlingen skubbes ned til kilden, vil antallet af returnerede rækker sandsynligvis være langt færre. 

![Script til diagnosticering af lagringstilstand](media/desktop-storage-mode/storage-mode_08.png)

> [!NOTE]
> Denne funktionsmåde er anderledes end [mange-til-mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md), når du kombinerer cachelagrede og ikke-cachelagret tabeller.

## <a name="caches-should-be-kept-in-sync"></a>Cacher bør holdes synkroniserede

Forespørgslerne fra det forrige afsnit viser, at **Dual**-tabeller nogle gange finder indhold i cachen og andre gange ikke. Dette kan resultere i, at forskellige værdier returneres, hvis cachen er forældet. Udførelse af forespørgsler vil ikke forsøge at maskere dataproblemer ved f.eks. at filtrere DirectQuery-resultater for at matche cachelagrede værdier. Det er dit ansvar at kende dine dataflows, og du bør designe i henhold hertil. Der er fastlagt teknikker til at håndtere sådanne tilfælde ved kilden, hvis det er nødvendigt.

**Dual**-lagringsmodellen er en ydeevneoptimering. Den må kun bruges på måder, der ikke kompromitterer evnen til at opfylde forretningsbehov. For alternativ funktionalitet bør du overveje at bruge teknikkerne, der er beskrevet i artiklen [Mange-til-mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md).

## <a name="data-view"></a>Datavisning
Hvis mindst én tabel i datasættet har angivet **lagringstilstanden** som enten Import eller Dual, så vises fanen **Datavisning**.

![Datavisning i Power BI Desktop](media/desktop-storage-mode/storage-mode_09.png)

Når de vælges i *Datavisning** viser **Dual**- og **Import**-tabeller cachelagrede data. DirectQuery-tabeller viser ikke data, og du får vist en meddelelse om, at DirectQuery-tabeller ikke kan vises.


## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Der er nogle få begrænsninger af denne udgave af **lagringstilstand** og dens korrelation med **sammensatte modeller**.

Følgende Live Connect-kilder (flerdimensionelle) kan ikke bruges sammen med **sammensatte modeller**:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI-datasæt
* Azure Analysis Services

Når du opretter forbindelse til disse flerdimensionelle datakilder ved hjælp af DirectQuery, kan du ikke også oprette forbindelse til en anden DirectQuery-kilde eller kombinere med importerede data.

De eksisterende begrænsningerne ved at bruge DirectQuery gælder stadig, når du bruger **sammensatte modeller**. Mange af disse begrænsninger er nu pr. tabel afhængigt af tabellens **lagringstilstand**. En beregnet kolonne i en importeret tabel kan f.eks. referere til andre tabeller, men en beregnet kolonne i en DirectQuery-tabel er stadig begrænset til kun at referere til kolonner i den samme tabel. Andre begrænsninger gælder for modellen som helhed, hvis nogle af tabellerne i modellen er DirectQuery. For eksempel er funktionerne **QuickInsights** og **Q&A** ikke tilgængelige for en model, hvis nogen af tabellerne i den har en **lagringstilstand** for DirectQuery. 

## <a name="next-steps"></a>Næste trin

I følgende artikler beskrives sammensatte modeller yderligere, og du finder også en detaljeret beskrivelse af DirectQuery.

* [Sammensatte modeller i Power BI Desktop (Preview)](desktop-composite-models.md)
* [Mange til mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md)

Artikler om DirectQuery:

* [Brug af DirectQuery in Power BI](desktop-directquery-about.md)
* [Understøttede datakilder i forbindelse med DirectQuery i Power BI](desktop-directquery-data-sources.md)

