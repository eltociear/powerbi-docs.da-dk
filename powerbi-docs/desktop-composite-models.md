---
title: Brug Sammensatte modeller i Power BI Desktop (Preview)
description: Opret datamodeller med flere dataforbindelser og mange-til-mange-relationer i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/31/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: ddfe0c7ad116a74fa6887491ee41e544096de0f9
ms.sourcegitcommit: 06f59902105c93700e71e913dff8453e221e4f82
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/01/2018
ms.locfileid: "39388841"
---
# <a name="composite-models-in-power-bi-desktop-preview"></a>Sammensatte modeller i Power BI Desktop (Preview)

Tidligere i **Power BI Desktop** når du brugte en DirectQuery i en rapport, var ingen andre dataforbindelser, hverken DirectQuery eller Import, tilladt for den pågældende rapport. Denne begrænsning er nu fjernet med **sammensatte modeller**, og en rapport kan uden problemer indeholde dataforbindelser fra mere end én DirectQuery eller importdataforbindelse i en hvilken som helst kombination, du vælger.

![sammensatte modeller i Power BI Desktop](media/desktop-composite-models/composite-models_01.png)

**Sammensatte modeller**-funktionaliteten i **Power BI Desktop** består af tre relaterede funktioner:

* **Sammensatte modeller** – gør det muligt for en rapport at have flere dataforbindelser, herunder DirectQuery-forbindelser eller import, i en vilkårlig kombination af disse.
* **Mange til mange-relationer** – med **sammensatte modeller** kan du oprette **mange til mange-relationer** mellem tabeller, fjerne kravene om entydige værdier i tabeller og fjerne tidligere løsninger som f.eks at introducere nye tabeller kun for at oprette relationer. 
* **Lagringstilstand** – du kan nu angive, hvilke visuelle elementer der kræver en forespørgsel til backend-datakilder, og dem, hvor det ikke kræves, importeres, selvom de er baseret på DirectQuery, hvilket forbedrer kvaliteten og reducerer belastningen af backenden. Tidligere ville selv enkle visuelle elementer som udsnit igangsætte forespørgsler, der blev sendt til backend-kilderne. 

Denne samling af tre relaterede funktioner for **sammensatte modeller** er beskrevet i særskilte artikler:

* **Sammensatte modeller** er beskrevet nærmere i denne artikel.
* **Mange-til-mange-relationer** er beskrevet i deres egen artikel [mange-til-mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md).
* **Lagringstilstand** er beskrevet i sin egen artikel: [Lagringstilstand i Power BI Desktop (Preview)](desktop-storage-mode.md).

## <a name="enabling-the-composite-models-preview-feature"></a>Aktivering af prøveversionsfunktionen i sammensatte modeller

Funktionen **sammensatte modeller** fås i prøveversion og skal aktiveres i **Power BI Desktop**. Du kan aktivere **sammensatte modeller** ved at vælge **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning** og derefter vælge afkrydsningsfeltet **Sammensatte modeller**. 

![aktivering af prøveversionsfunktioner](media/desktop-composite-models/composite-models_02.png)

Du skal genstarte **Power BI Desktop**, før funktionen kan bruges.

![genstart er nødvendig for, at ændringerne kan træde i kraft](media/desktop-composite-models/composite-models_03.png)


## <a name="using-composite-models"></a>Brug af sammensatte modeller

Du kan bruge **sammensatte modeller** til at oprette forbindelse til alle mulige forskellige datakilder, når du bruger **Power BI Desktop** eller **Power BI-tjenesten**, og du kan oprette disse dataforbindelser på forskellige måder. Du kan importere data til Power BI, hvilket er den mest almindelige måde at hente data på, eller du kan oprette forbindelse direkte til dataene i det oprindelige kildelager ved hjælp af DirectQuery. Du kan få mere at vide om DirectQuery-oplysninger i artiklen [sådan bruges DirectQuery i Power BI](desktop-directquery-about.md).

Når du bruger DirectQuery med **sammensatte modeller**, er det muligt at oprette en Power BI-model (f.eks. en enkelt .pbix Power BI Desktop-fil), der gør følgende:

* kombinerer data fra en eller flere DirectQuery-kilder, og/eller
* kombinerer data fra DirectQuery-kilder og importdata

Eksempelvis er det med **sammensatte modeller** muligt at oprette en model, der kombinerer salgsdata fra en professionel datawarehouse-database, med data vedr. salgsmål, der findes i en afdelings SQL Server-database, sammen med nogle data, der er importeret fra et regneark. En model, der kombinerer data fra mere end én DirectQuery-kilde, eller kombinerer DirectQuery med importerede data, kaldes en *sammensat model*.

> [!NOTE]
> Mens sammensatte modeller er i prøveversion, er det ikke muligt at udgive sammensatte modeller til Power BI-tjenesten. 

Du kan oprette relationer mellem tabeller, som du altid har gjort, selv når disse tabeller kommer fra forskellige kilder, med følgende begrænsninger: alle relationer, der er etableret på tværs af kilder, skal være defineret som havende en kardinalitet på **mange-til-mange** , uanset deres faktiske kardinalitet. Disse relationer fungerer som normalt for **mange-til-mange**-relationer, som beskrevet i [mange-til-mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md). Bemærk, at inden for rammerne af sammensatte modeller er alle importerede tabeller reelt en enkelt kilde uanset den faktiske underliggende datakilde, som de faktisk er importeret fra.   

## <a name="example-of-using-composite-models"></a>Eksempel på brugen af sammensatte modeller

Som et eksempel på en **sammensatte model** kan du bruge en rapport, der er forbundet til en virksomheds datawarehouse-database (i SQL Server) via DirectQuery, hvor datawarehouse-databasen indeholder data knyttet til *Salg efter land*, *Kvartal* og *Cykel (produkt)*, som vist i det følgende billede.

![relationsvisning for sammensatte modeller](media/desktop-composite-models/composite-models_04.png)

På dette tidspunkt kan du oprette simple visuelle elementer ved hjælp af felter fra denne kilde. Følgende visuelle element viser f.eks. det samlede salgsbeløb efter *ProduktNavn*, for et valgt kvartal. 

![visuelt element baseret på data](media/desktop-composite-models/composite-models_05.png)

Men hvad nu, hvis du har nogle oplysninger om ProduktChef, der er tildelt hvert produkt, sammen med marketingprioriteten, hvor dataene administreres i et Excel-regneark? Du kan få vist *Salgsbeløb* efter *Produktchef*, men det vil sandsynligvis være upraktisk at føje disse data til virksomhedens datawarehouse-database, eller det vil i bedste fald tage mange måneder. Mens det kan være muligt at importere disse salgsdata fra data warehouse-databasen (i stedet for at bruge DirectQuery), hvorved de kunne kombineres med data importeret fra regnearket, er denne fremgangsmåde urimelig set i forhold til motivationen for overhovedet at bruge DirectQuery – som f.eks. en relevant kombination af sikkerhedsreglerne, der gennemtvinges i den underliggende kilde, behovet for at kunne se de seneste data, og selve dataenes størrelse. 

Det er her, **sammensatte data** finder anvendelse. Sammensatte modeller giver dig mulighed for at oprette forbindelse til datawarehouse-databasen ved hjælp af DirectQuery, og derefter også bruge GetData for yderligere datakilder. I dette tilfælde opretter vi DirectQuery-forbindelse til virksomhedens datawarehouse-database, derefter bruger vi GetData og vælger Excel, navigerer til regnearket med dine lokale data, og kan importere arket med *Produktnavne*, den tildelte *Salgschef* og *Prioritet*.  

![Vinduet Navigator](media/desktop-composite-models/composite-models_06.png)

Nu kan vi på listen **Felter** se den oprindelige *Cykel*-tabel (fra SQL Server) og en ny *Produktchef*-tabel (med data importeret fra Excel). 

![Feltvisning i tabeller](media/desktop-composite-models/composite-models_07.png)

På samme måde ser vi nu i **Relationsvisning** i **Power BI Desktop** en yderligere tabel kaldet *Produktchefer*. 

![relationsvisning i tabeller](media/desktop-composite-models/composite-models_08.png)

Vi skal nu relatere disse til andre tabeller i modellen, som vi altid har gjort, nemlig ved at oprette en relation mellem tabellen *Cykel* (i SQL Server) og tabellen *Produktchefer* (der er importeret), såsom mellem *Cykel [Produktnavn]* og *Produktchefer [Produktnavn]*. Som beskrevet tidligere i denne artikel skal alle relationer, der går på tværs af kilder, have kardinaliteten **mange-til-mange**, og derfor er det standardkardinaliteten, der er valgt. 

![opret dialogboksen relation](media/desktop-composite-models/composite-models_09.png)

Når denne relation er oprettet, vises relationen i **Relationsvisning** i **Power BI Desktop** helt som forventet.

![ny relationsvisning](media/desktop-composite-models/composite-models_10.png)

Når disse tabelrelationer er etableret, kan vi oprette visuelle elementer ved hjælp af felterne på listen **Felter**, der problemfrit blander data fra flere kilder. Nedenstående visuelle element viser f.eks. det samlede *Salgsbeløb* for hver *Produktchef*. 

![visuelt element med visning af ruden Felter](media/desktop-composite-models/composite-models_11.png)

Eksemplet her viser en almindeligt forekommende *dimension*-tabel (f.eks. *Produkt* eller *Kunde*), der udvides med nogle ekstra data importeret fra et andet sted, det er også muligt at etablere DirectQuery-forbindelse fra tabeller til forskellige kilder. I forlængelse af vores eksempel antager vi nu, at *Salgsmål* pr. *Land* og *Periode* er lagret i en separat afdelingsdatabase. Du kan bruge **GetData** til at oprette forbindelse til disse data som normalt, som vist på det følgende billede. 

![Dialogboksen Navigator](media/desktop-composite-models/composite-models_12.png)

Derefter kan vi på samme måde som tidligere i dette kapitel, oprette relationer mellem den nye tabel og andre tabeller i modellen, og oprette visuelle elementer, der kombinerer deres data. Lad os igen se på **Relationsvisningen**, hvor vi har etableret nye relationer i vores udvidede eksempelscenarie.

![relationsvisning med mange tabeller](media/desktop-composite-models/composite-models_13.png)

Som det fremgår af det følgende billede, som er baseret på de nye data og relationer, vi lige har oprettet, viser det visuelle element nederst i venstre hjørne det samlede *Salgsbeløb* versus *Mål* med beregningen af afvigelsen visende forskellen, hvor *Salgsbeløb*  og *Mål* kommer fra to forskellige SQL Server-databaser. 

![visuelt element visende flere data](media/desktop-composite-models/composite-models_14.png)

## <a name="setting-storage-mode"></a>Indstilling af lagringstilstand

Hver tabel i en **sammensat model** har en **lagringstilstand**, der angiver, om tabellen er baseret på DirectQuery eller import. **Lagringstilstand** kan vises og redigeres i ruden **Egenskab**. For at komme dertil skal du vælge **Egenskaber** på listen **Felter** i genvejsmenuen ved at højreklikke. På følgende billede vises **lagringstilstanden** (forkortet til **Lagrings...**  på billedet på grund af rudens bredde).

![Indstilling af lagringstilstand](media/desktop-composite-models/composite-models_15.png)

**Lagringstilstanden** kan også ses på værktøjstippet for hver tabel.

![værktøjstip med lagringstilstand](media/desktop-composite-models/composite-models_16.png)

For alle **Power BI Desktop**-filer (.pbix-filer), der indeholder nogle tabeller fra DirectQuery og nogle importtabeller, viser statuslinjen **lagringstilstanden** **Blandet**. Du kan klikke på elementet på statuslinjen og let skifte alle tabeller til import.

Detaljer om **lagringstilstand** er beskrevet fuldt ud i artiklen [Lagringstilstand i Power BI Desktop (Preview)](desktop-storage-mode.md).  

## <a name="calculated-tables"></a>Beregnede tabeller

Beregnede tabeller kan føjes til en model, der bruger DirectQuery, og DAX-formlen med definition af den beregnede tabel kan referere til enten importerede eller DirectQuery-tabeller, eller en kombination af begge. 

Beregnede tabeller importeres altid, og dataene i disse tabeller opdateres, når tabellen opdateres. Hvis en beregnet tabel således refererer til en DirectQuery-tabel, så viser de visuelle elementer, der refererer til DirectQuery-tabellen, altid de nyeste værdier i den underliggende kilde, men visuelle elementer, der refererer til den beregnede tabel, viser værdierne på det tidspunkt, hvor den beregnede tabel sidst blev opdateret.

## <a name="security-implications"></a>Sikkerhedsmæssige konsekvenser 

Sammensatte modeller har nogle sikkerhedsmæssige konsekvenser. En forespørgsel, der sendes til en datakilde, kan indeholde dataværdier, der er blevet hentet fra en anden anderledes kilde. Eksempelvis, som beskrevet tidligere i denne artikel, så vil det visuelle element, der viser *Salgsbeløb* efter *Produktchef*, resultere i en SQL-forespørgsel, der sendes til relationsdatabasen **Salg**, hvor denne SQL-forespørgsel kan indeholde navnene på *Produktchefer* og deres tilknyttede *Produkter*. 

![script visende sikkerhedsmæssige konsekvenser](media/desktop-composite-models/composite-models_17.png)

Dette resulterer i, at oplysninger, der er lagret i regnearket, nu bliver inkluderet i en forespørgsel, der sendes til relationsdatabasen. Hvis disse oplysninger er fortrolige, så bør man være opmærksom på de sikkerhedsmæssige konsekvenser, dette kan have. Du skal især være opmærksom på de følgende konsekvenser:

* En hvilken som helst administrator af databasen, der kan se sporinger eller overvågningslogge, vil kunne se disse oplysninger, selvom de ikke har tilladelser til at tilgå dataene i den oprindelige kilde (i dette tilfælde adgangstilladelse til Excel-filen).

* Krypteringsindstillingerne for hver kilde bør tages i betragtning for at undgå, at oplysninger hentes fra en kilde via krypteret forbindelse, men som derefter utilsigtet inkluderes i en forespørgsel, der sendes til en anden kilde via en ukrypteret forbindelse. 

**Power BI Desktop** viser en advarsel, når der udføres en handling med henblik på at oprette en sammensat model, så man kan bekræfte, at alle sikkerhedsmæssige konsekvenser er taget i betragtning.  

Af tilsvarende grunde skal man udvise forsigtighed, når man åbner en **Power BI Desktop**-fil sendt fra en kilde, der ikke er tillid til. Hvis filen indeholder sammensatte modeller, betyder det, at oplysninger, der hentes fra én kilde (ved at bruge legitimationsoplysningerne for brugeren, der åbner filen) sendes til en anden datakilde som en del af forespørgslen (hvor de muligvis kan ses af en potentielt ondsindet forfatter af Power BI Desktop-filen). Derfor vises en advarsel, når du første gang åbner en Power BI Desktop-fil, hvis den indeholder flere kilder. Denne advarsel svarer til advarslen, der vises, når du åbner en fil med oprindelige SQL-forespørgsler.  

## <a name="performance-implications"></a>Konsekvenserne for kvaliteten  

Når DirectQuery bruges, skal man altid være opmærksom på kvaliteten, primært for at sikre, at backend-kilden har tilstrækkelige ressourcer til at give brugerne en god oplevelse. En god oplevelse betyder, at visuelle elementer opdateres på fem sekunder eller mindre. Du skal også rette dig efter kvalitetsrådene nævnt i artiklen [brug af DirectQuery i Power BI](desktop-directquery-about.md). Brugen af sammensatte modeller tilføjer yderligere kvalitetsmæssige overvejelser, idet et enkelt visuelt element kan resultere i, at forespørgsler sendes til adskillige kilder, hvorved resultater sendes videre fra en forespørgsel til en anden kilde. Denne situation kan føre til de følgende potentielle former for udførelse:

* **En SQL-forespørgsel der indeholder et stort antal konstantværdier** – f.eks. et visuelt element, der anmoder om samlede *Salgsbeløb* (fra SQL-databasen) for et sæt af udvalgte *Produktchefer* (fra den relaterede tabel, der er blevet importeret fra et regneark) skal først finde ud af, hvilke *Produkter*, der blev administreret af disse Produktchefer, før der sendes en SQL-forespørgsel, herunder alle produkt-id’erne i en *WHERE*-delsætningen.

* **En SQL-forespørgsel, der forespørger på et lavere niveau af granularitet, hvorefter dataene aggregeres lokalt** – kan det samme eksempel bruges som i det forrige punkttegn på denne liste, idet antallet af *Produkter*, der opfylder filterets betingelser til *Produktchef*, bliver meget stort, på et bestemt tidspunkt bliver det ineffektivt eller upraktisk at inkludere dem alle i *WHERE*-delsætningen. Det er i stedet nødvendigt at forespørge relationskilden på det lavere niveau for *Produkt* og derefter lokalt aggregere resultaterne. Hvis kardinaliteten for *Produkter* overskrider en grænse på 1 mio., så mislykkes forespørgslen.

* **Flere SQL-forespørgsler, én pr. gruppér efter værdi** – når aggregeringen bruger **DistinctCount** grupperet efter en relevant kolonne fra en anden kilde, så er det nødvendigt at sende én SQL-forespørgsel pr. gruppér efter værdi, hvis den eksterne kilde ikke understøtter effektiv overførsel af mange konstantværdier, der definerer grupperingen. Eksempelvis skal et visuelt element, der anmoder om et distinkt antal af *Kundekontonummer* (fra SQL Server-tabellen) efter *Produktchef* (fra den relaterede tabel importeret fra et regneark) overføre detaljer fra tabellen *Produktchefer* i forespørgslen sendt til SQL Server. Over andre kilder, f.eks. Redshift, er dette ikke praktisk, og i stedet vil der blive sendt én SQL-forespørgsel pr. *Salgschef* (op til en given praktisk grænse, hvorefter forespørgslen mislykkes). 

Hver af disse scenarier har konsekvenser for kvaliteten, hvor de præcise detaljer varierer for hver datakilde. En god tommelfingerregel er, at mens kardinaliteten for de kolonner, der bruges i relationen, der forbinder de to kilder, forbliver lav (nogle få tusind), så bør kvaliteten ikke blive væsentlig påvirket. Jo mere kardinaliteten øges, jo større skal opmærksomheden rettes mod konsekvenserne for den endelige kvalitet. 

Desuden betyder brugen af **mange-til-mange**-relationer, at særskilte forespørgsler skal sendes til den underliggende kilde for hvert totale/subtotale niveau fremfor at aggregere de detaljerede værdier lokalt. Således vil et simpelt visuelt element i en tabel med samlede værdier sende to SQL-forespørgsler fremfor ét. 

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Der er nogle få begrænsninger ved denne udgave af **sammensatte modeller**.

Følgende flerdimensionelle kilder kan ikke bruges med **sammensatte modeller**:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI-datasæt

Når du opretter forbindelse til disse flerdimensionelle datakilder ved hjælp af DirectQuery, kan du ikke også oprette forbindelse til en anden DirectQuery-kilde eller kombinere med importerede data.

De eksisterende begrænsningerne ved at bruge DirectQuery gælder stadig, når du bruger **sammensatte modeller**. Mange af disse begrænsninger er nu pr. tabel afhængigt af tabellens **lagringstilstand**. En beregnet kolonne i en importeret tabel kan f.eks. referere til andre tabeller, men en beregnet kolonne i en DirectQuery-tabel er stadig begrænset til kun at referere til kolonner i den samme tabel. Andre begrænsninger gælder for modellen som helhed, hvis nogle af tabellerne i modellen er DirectQuery. For eksempel er funktionerne **QuickInsights** og **Q&A** ikke tilgængelige for en model, hvis nogen af tabellerne i den har en **lagringstilstand** for DirectQuery. 

## <a name="next-steps"></a>Næste trin

I følgende artikler beskrives sammensatte modeller yderligere, og du finder også en detaljeret beskrivelse af DirectQuery.

* [Mange til mange-relationer i Power BI Desktop (Preview)](desktop-many-to-many-relationships.md)
* [Lagringstilstand i Power BI Desktop (Preview)](desktop-storage-mode.md)

Artikler om DirectQuery:

* [Brug af DirectQuery in Power BI](desktop-directquery-about.md)
* [Understøttede datakilder i forbindelse med DirectQuery i Power BI](desktop-directquery-data-sources.md)

