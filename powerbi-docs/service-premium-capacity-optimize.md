---
title: Optimer Microsoft Power BI Premium-kapaciteter
description: I denne artikel beskrives optimering strategier til Power BI Premium-kapaciteter.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 06712b6bcf57ca84ec03d2c7b99b32ea61ad8c71
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565358"
---
# <a name="optimizing-premium-capacities"></a>Optimering af Premium-kapaciteter

Når der opstår problemer med ydeevnen i Premium-kapacitet, er en fælles første tilgang til at optimere eller indstille dine løsninger for at gendanne acceptable svartider. Det er at undgå at købe ekstra Premium-kapacitet, medmindre berettiget begrundelse.

Når der kræves yderligere Premium-kapacitet, der er to muligheder, der er beskrevet i denne artikel:

- Skalering af en eksisterende Premium-kapacitet
- Tilføjelse af en ny Premium-kapacitet

Endelig test tilgange og Premium-kapacitet størrelse indgå i denne artikel.

## <a name="best-practices"></a>Bedste praksis

Når du forsøger at få den bedste udnyttelse og ydeevne, er der nogle anbefalede bedste fremgangsmåder, herunder:

- Ved hjælp af app-arbejdsområder i stedet for personlige arbejdsområder.
- Adskille forretningskritisk og Self-Service BI (SSBI) i forskellige kapaciteter.

  ![Adskillelse af forretningskritisk og SSBI (Self-Service BI) i forskellige kapaciteter](media/service-premium-capacity-optimize/separate-capacities.png)

- Hvis du deler indhold kun med Power BI Pro-brugere, kan der være behøver ikke at gemme indholdet i en dedikeret kapacitet.
- Brug dedikeret kapacitet, når du ønsker for at opnå et bestemt opdateringstidspunkt, eller når specifikke funktioner er påkrævet. For eksempel med store datasæt eller sideinddelte reporting.

### <a name="addressing-common-questions"></a>Adresser til ofte stillede spørgsmål

Optimering af udrulninger af Power BI Premium er et komplekse emne, der involverer en forståelse af krav til arbejdsbelastningen, tilgængelige ressourcer og deres effektiv udnyttelse.

I denne artikel omhandler syv almindelige supportspørgsmål, der beskriver mulige problemer og forklaringer og oplysninger om, hvordan du kan identificere og løse problemerne.

### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Hvorfor er kapaciteten langsom, og hvad kan jeg gøre?

Der kan være mange årsager til en langsom Premium-kapacitet. Dette spørgsmål kræver yderligere oplysninger for at forstå, hvad der menes med langsom. Tager det for lang tid at indlæse rapporter? Eller kan de slet ikke indlæses? Tager det for lang tid at indlæse eller opdatere visualiseringerne, når brugerne interagerer med rapporten? De opdateres tager længere tid at fuldføre end forventet eller tidligere oplevede?

Når du har fået en forståelse af årsagen, kan du begynde at foretage en undersøgelse. Svar på seks følgende spørgsmål kan hjælpe dig med at håndtere mere specifikke problemer.

### <a name="what-content-is-using-up-my-capacity"></a>Hvilket indhold bruger al kapaciteten?

Du kan bruge appen **Power BI Premium Capacity Metrics** til at filtrere efter kapacitet og gennemse metrikværdier for arbejdsområdeindholdets ydeevne. Det er muligt at gennemse brugen af ydeevne målepunkter og ressource ved time for de seneste syv dage for alt indhold, der er lagret i en Premium-kapacitet. Overvågning er ofte første trin skal udføres, når fejlfinding i forbindelse med en generelle bekymringer om Premium-kapacitet ydeevne.

Vigtige målepunkter, der bør overvåges:

- Gennemsnitlig CPU og høj udnyttelse count.
- Gennemsnitlig hukommelse og høj udnyttelse, antal og forbruget af hukommelse for bestemte datasæt, dataflows og sideinddelte rapporter.
- Aktive datasæt, der er indlæst i hukommelsen.
- Forespørgslen gennemsnitlige og maksimale varighed.
- Gennemsnitlig forespørgsel ventetider.
- Gennemsnitlig datasæt og dataflowet opdateres gange.

I Power BI Premium-kapacitet målepunkter appen viser aktiv hukommelse den samlede mængde hukommelse, der er angivet til en rapport, der ikke kan fjernes, fordi det er i brug i de sidste tre minutter. En stor stigning i ventetiden for opdateringer kan skyldes et stort/eller aktivt datasæt.

Den **Top 5 efter gennemsnitlige varighed** diagram fremhæver de de fem datasæt, sideinddelte rapporter og dataflows forbruger kapacitet ressourcer. Indhold i de fem lister er kandidater til undersøgelsesformål og mulige optimering.

### <a name="why-are-reports-slow"></a>Hvorfor er rapporterne langsomme?

I følgende tabel vises mulige problemer og måder at identificere og håndtere dem på.

#### <a name="insufficient-capacity-resources"></a>Utilstrækkelige kapacitetsressourcer

| Mulige forklaringer | Sådan identificeres problemet | Sådan løses problemet |
| --- | --- | --- |
| Samlet antal aktive HIMEM (model kan ikke fjernes, fordi den er i brug i de sidste tre minutter).<br><br> Flere høj stigninger i forespørgsel venter gange.<br><br> Flere høj stigninger i opdatering Vent gange. | Overvåg hukommelse målepunkter \[ [1](#endnote-1)\], og antallet af hård \[ [2](#endnote-2)\]. | Formindsk størrelsen på den model, eller konvertere til DirectQuery-tilstand. Se de [optimering af modeller](#optimizing-models) afsnit i denne artikel.<br><br> Op-kapacitet.<br><br> Du kan tildele indholdet til en anden kapacitet. |

#### <a name="inefficient-report-designs"></a>Ineffektive rapportdesign

| Mulige forklaringer | Sådan identificeres problemet | Sådan løses problemet |
| --- | --- | --- |
| Rapportsider indeholder for mange visualiseringer (interaktive filtrering kan udløse mindst én forespørgsel pr. visualisering).<br><br> Visuelle elementer, hentes flere data end nødvendigt. | Gennemse rapporten design.<br><br> Interview rapportbrugere for at forstå, hvordan de interagerer med rapporter.<br><br> Overvåg datasæt forespørgsel målepunkter \[ [3](#endnote-3)\]. | Omdesign rapporter med færre visuelle elementer pr. side. |

#### <a name="dataset-is-slow-especially-when-reports-have-previously-performed-well"></a>Datasættet er langsom, især når rapporter har tidligere udført godt

| Mulige forklaringer | Sådan identificeres problemet | Sådan løses problemet |
| --- | --- | --- |
| Stadig større datamængder import.<br><br> Beregning af komplekse eller ineffektiv logik, herunder RLS-roller.<br><br> Model, der ikke er fuldt optimeret.<br><br> (DQ/LC) Gateway ventetid.<br><br> Langsom DQ kilde forespørgselssvartider. | Gennemse model design.<br><br> Overvåg gateway ydelsestællere. | Se de [optimering af modeller](#optimizing-models) afsnit i denne artikel. |

#### <a name="high-concurrent-report-usage"></a>Højt samtidigt forbrug af rapporter

| Mulige forklaringer | Sådan identificeres problemet | Sådan løses problemet |
| --- | --- | --- |
| Høj forespørgsel ventetider.<br><br> CPU-mætning.<br><br> DQ/LC forbindelse er overskredet. | Overvåg CPU-forbruget \[ [4](#endnote-4)\], forespørgsel ventetider og udnyttelse af DQ/LC \[ [5](#endnote-5) \] målepunkter + varigheder forespørgsel. Hvis svingende tal, du kan angive samtidighed problemer. | Op-kapacitet, eller tildele indhold til en anden kapacitet.<br><br> Omdesign rapporter med færre visuelle elementer pr. side. |

**Noter:**    
<a name="endnote-1"></a>\[1\] gennemsnitlig brug af hukommelse (GB) og højeste hukommelsesforbrug (GB).   
<a name="endnote-2"></a>\[2\] evictions datasæt.   
<a name="endnote-3"></a>\[3\] vente datasæt forespørgsler, datasæt gennemsnitlige varighed af forespørgsel (ms), datasæt, antal og datasæt gennemsnitlige ventetid (ms).   
<a name="endnote-4"></a>\[4\] CPU høj udnyttelse antal og CPU-tid af højeste udnyttelse (de seneste syv dage).   
<a name="endnote-5"></a>\[5\] DQ/LC høj udnyttelse antal og DQ/LC tidspunktet for højeste udnyttelse (de seneste syv dage).   

### <a name="why-are-reports-not-loading"></a>Hvorfor indlæses rapporter ikke?

Når der opstår fejl i rapporter til at indlæse, er det en sikker på, at logge kapaciteten, der ikke har tilstrækkelig hukommelse og er overløbsfejl opvarmet. Dette kan ske, når alle indlæste modeller bliver forespurgt aktivt og derfor ikke kan fjernes, og hvis opdateringshandlinger er blevet sat på pause eller forsinket. Power BI-tjenesten forsøger at indlæse datasættet i 30 sekunder, og brugeren får besked om fejlen med et forslag til at prøve igen om et øjeblik.

Der er i øjeblikket ingen metrikværdier til at overvåge fejl i forbindelse med rapportindlæsninger. Du kan identificere risikoen for dette problem ved at overvåge systemhukommelsen, især den højeste udnyttelse og tidspunktet for den højeste udnyttelse. Mange fjernelser af datasæt og en lang gennemsnitlig ventetid kan tyde på, at dette problem er ved at opstå.

Hvis det sker sjældent, betragtes det muligvis ikke som en prioritet. Rapportbrugere bliver informeret om, at tjenesten er optaget, og at de skal prøve igen efter et øjeblik. Hvis det sker for ofte, kan problemet løses ved at skalere Premium-kapaciteten op eller ved at tildele indholdet til en anden kapacitet.

Kapacitetsadministratorer (og administratorer af Power BI-tjenesten) kan overvåge metrikværdien **forespørgselsfejl** for at bestemme, hvornår dette sker. De kan også genstarte kapaciteten for at nulstille alle handlinger i tilfælde af, at systemet overbelastes.

### <a name="why-are-refreshes-not-starting-on-schedule"></a>Hvorfor starter opdateringer ikke efter planen?

Der er ikke garanti for starttidspunkterne for planlagte opdateringer. Husk, at Power BI-tjenesten altid prioriterer interaktive handlinger over handlinger i baggrunden. Opdatering er en handling i baggrunden, der kan opstå, når to betingelser er opfyldt:

- Der er tilstrækkelig hukommelse
- Antallet af understøttede samtidige opdateringer for Premium-kapaciteten ikke er overskredet

Hvis betingelserne ikke opfydes, sættes opdateringen i kø, indtil betingelserne er opfyldt.

Husk, at der for en fuld opdatering kræves mindst det dobbelte af den aktuelle hukommelsesstørrelse for datasættet. Hvis der ikke er tilstrækkelig hukommelse tilgængelig, kan opdateringen ikke påbegyndes, før modelfjernelse frigør hukommelse – det betyder forsinkelser, indtil et eller flere datasæt bliver inaktive og kan fjernes.

Husk, at det maksimale antal samtidige opdateringer, der understøttes, er angivet til 1,5 gange backend-v-kernerne, rundet op.

En planlagt opdatering mislykkes, når den ikke kan påbegyndes, før den næste planlagte opdatering skal påbegyndes. En opdatering efter behov, der er udløst manuelt fra brugergrænsefladen, vil forsøge at køre op til tre gange, før der opstår en fejl.

Kapacitetsadministratorer (og administratorer af Power BI-tjenesten) kan overvåge metrikværdien **den gennemsnitlig opdateringsventetid (minutter)** for at bestemme den gennemsnitlige forsinkelse mellem det planlagte tidspunkt og begyndelsen af handlingen.

Selvom det normalt ikke er en administrativ prioritet, kan påvirkningen af rettidige dataopdateringer sikre, at der er tilstrækkelig tilgængelig hukommelse. Dette kan gøres ved at isolere datasæt til kapaciteter, man ved har tilstrækkeligt med ressourcer. Det er også muligt, at administratorer kan koordinere med datasætejere til at hjælpe Forskyd eller reducere planlagte opdatering gange for at minimere kollisioner. Bemærk, at det ikke er muligt for en administrator til at få vist opdatering køen eller til at hente datasættet tidsplaner.

### <a name="why-are-refreshes-slow"></a>Hvorfor kører opdateringerne langsomt?

Opdateringer kan være langsomme – eller opfattes som langsomme (som de forrige almindelige spørgsmål omhandler).

Når opdateringen rent faktisk er langsom, kan det skyldes flere årsager:

- Utilstrækkelige CPU (opdatering kan være meget CPU-intensive).
- Utilstrækkelig hukommelse, hvilket resulterer i opdatering afbryder (som kræver, at opdateringen til at starte forfra, når betingelser er positiv starte forfra).
- Ikke-kapacitet årsager, herunder datasource system reaktionsevne, netværksventetid, ugyldige tilladelser eller gateway gennemløb.
- Datamængde – en god grund til at konfigurere trinvis opdatering, som beskrevet nedenfor.

Kapacitetsadministratorer (og administratorer af Power BI-tjenesten) kan overvåge metrikværdien **den gennemsnitlige opdateringsvarighed (minutter)** for at have en benchmark til sammenligning over tid og metrikværdien **gennemsnitlig opdateringsventetid (minutter)** for at fastsætte den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og den faktiske start af handlingen.

Trinvise opdateringer kan reducere dataopdateringsvarigheden væsentligt, især for store modeltabeller. Der er fire fordele, der er forbundet med trinvis opdatering:

- **Opdateringer er hurtigere** – kun et undersæt af en tabel skal indlæse, nedbringe CPU og hukommelse forbrug, og parallelitet kan være højere ved opdatering af flere partitioner.
- **Opdaterer sker kun, når der kræves** -politikker for trinvis opdatering kan konfigureres til at indlæse kun, når data er ændret.
- **Opdateringer, der er mere pålidelig** -kortere kørende forbindelser til svingende datasource systemer er mindre sårbar over for afbrydelse.
- **Modeller forbliver trim** -politikker for trinvis opdatering kan konfigureres til automatisk for at fjerne historik ud over et glidende tidsrum.

Hvis du vil vide mere, kan du se [trinvis opdatering i Power BI Premium](service-premium-incremental-refresh.md).

### <a name="why-are-data-refreshes-not-completing"></a>Hvorfor fuldføres dataopdateringer ikke?

Når dataopdateringen påbegyndes, men ikke fuldføres, kan det skyldes flere årsager:

- Utilstrækkelig hukommelse, selvom der er kun én model i Premium-kapacitet, dvs. modellen størrelsen er meget store.
- Årsager til ikke-kapacitet, herunder datasource system afbrydelse, ugyldige tilladelser eller gateway-fejl.

Kapacitetsadministratorer (og administratorer af Power BI-tjenesten) kan overvåge metrikværdien **opdateringsfejl pga. manglende hukommelse**.

## <a name="optimizing-models"></a>Optimering af modeller

Et optimalt modeldesign er afgørende for leveringen af en effektiv og skalerbar løsning. Det er dog ikke inden for rammerne af denne artikel til at levere en komplet diskussion. I stedet indeholder dette afsnit vigtige områder, som bør overvejes ve doptimering f modeller.

### <a name="optimizing-power-bi-hosted-models"></a>Optimere Power BI hostet modeller

Optimering af modeller, der hostes i en Premium-kapacitet kan gennemføres på lag datasource(s) og modellen.

Overvej optimeringsmulighederne for en importmodel:

![Optimeringsmuligheder for en importmodel](media/service-premium-capacity-optimize/import-model-optimizations.png)

På datasource lag:

- Relationelle datakilder kan optimeres for at sikre, at opdateringen hurtigst muligt ved forhånd integration af data, anvendelse af relevante indekser, definition af tabellen partitioner, Juster til perioder med trinvis opdatering og oprettelse af beregninger (i stedet for beregnet model, tabeller og kolonner) eller tilføjelse af beregningen logik til visninger.
- Ikke-relationelle datakilder kan være forudintegreret med relationelle butikker.
- Sikre, gateways, har tilstrækkelige ressourcer, helst på dedikerede maskiner, med de nødvendige netværksbåndbredde og i nærheden af datakilderne.

På modellaget:

- Design af Power-forespørgsler kan minimere eller fjerne komplekse transformationer og især dem, der fletter forskellige datakilder (datalagre opnår dette i fasen Udtræk-Transformer-Indlæs). Også sikre, at den relevante datasource niveauer for beskyttelse af personlige oplysninger er angivet, og dette kan undgå kræver Power BI til at indlæse komplette resultater for at generere resultatet kombinerede på tværs af forespørgsler.
- Modelstrukturen bestemmer de data, der skal indlæses, og har en direkte indvirkning på modelstørrelsen. Det kan designes til at undgå at indlæse unødvendige data ved at fjerne kolonner, fjerne rækker (især historiske data) eller ved at indlæse opsummerede data (i stedet for at indlæse detaljerede data). En væsentlig reduktion af størrelsen kan opnås ved at fjerne kolonner med høj kardinalitet (især tekstkolonner), som hverken kan gemmes eller komprimeres særligt effektivt.
- Ydeevnen for modelforespørgsler kan forbedres ved at konfigurere relationer i én retning, medmindre der er en meget god grund til at tillade tovejsfiltrering. Du kan eventuelt også bruge den [CROSSFILTER](https://docs.microsoft.com/dax/crossfilter-function) funktion i stedet for tovejsfiltrering.
- Med akkumuleringstabeller kan du opnå hurtige forespørgsler ved at indlæse data, der er opsummerede på forhånd, men dette vil forøge størrelsen af modellen og resulterer i længere opdateringstider. Akkumuleringstabeller bør generelt benyttes til design med meget store modeller eller sammensatte modeller.
- Beregnede tabeller og kolonner forøger størrelsen på modellen og resulterer i længere opdateringstider. En mindre lagerstørrelse og hurtigere opdateringstidspunkt kan generelt opnås, når dataene er indtruffet eller beregnet i datakilden. Hvis dette ikke er muligt, kan brug af brugerdefinerede kolonner i Power-forespørglser forbedre lagerkomprimeringen.
- Det kan være muligt at optimere DAX-udtryk for målinger og RLS-regler og måske omskrive logik for at undgå dyre formler.
- Trinvis opdatering reducerer opdateringstiden væsentligt og sparer hukommelse og CPU. Den trinvise opdatering kan også være konfigureret til at fjerne historiske data ved at holde modelstørrelserne trimmede.
- En model kan ændres til to modeller, når der er forskellige og modstridende forespørgselsmønstre. Nogle rapporter rummer f.eks. aggregeringer på højt niveau over al historik og kan tolerere ventetid for 24 timer. Andre rapporter beskæftiger sig med dagens data og har brug for detaljeret adgang til individuelle transaktioner. Du kan også oprette to modeller, der er optimeret til ethvert behov, i stedet for at designe en enkelt model, der opfylder alle rapportbehov.

Overvej optimeringsmulighederne for en DirectQuery-model. Som modellen udsteder forespørgselsanmodninger til den underliggende datakilde, er datasource optimering er afgørende for leveringen af dynamisk model forespørgsler.

 ![Optimeringsmuligheder for en DirectQuery-model](media/service-premium-capacity-optimize/direct-query-model-optimizations.png)

På datasource lag:

- Datakilden kan optimeres for at sikre den hurtigst muligt forespørgsler ved at integrere forhånd data (der ikke er muligt på laget model), anvender de relevante indekser, definition af tabelpartitioner, oprettelse opsummerede data (med indekserede visninger), og minimere mængden beregning. Den bedste oplevelse opnås, når pass-through-forespørgsler skal kun filtrere og udføre indvendige joinforbindelser mellem indekserede tabeller eller visninger.
- Sikre, gateways, har tilstrækkelige ressourcer, helst på dedikerede maskiner, med de nødvendige netværksbåndbredde og tæt på datakilden.

På modellaget:

- Power-forespørgsel design helst skal anvende transformeringer – ellers forsøge at holde transformationer på et absolut minimum.
- Ydeevnen for modelforespørgsler kan forbedres ved at konfigurere relationer i én retning, medmindre der er en meget god grund til at tillade tovejsfiltrering. Desuden relationer i modellen skal konfigureres til at antage referentiel integritet gennemtvinges (når det er tilfældet) og medfører datasource forespørgsler ved hjælp af mere effektiv indre joinforbindelser (i stedet for ydre joinforbindelser).
- Undgå at oprette brugerdefinerede kolonner i Power-forespørgsel forespørgsel eller model beregnet kolonne - materialisere dem i datakilden, når det er muligt.
- Der kan være mulighed for at optimere DAX-udtryk for målinger og RLS-regler, der måske skrive logik for at undgå dyre formler.

Overvej optimeringsmulighederne for en sammensat model: Husk, at en sammensat model gør det muligt at blande import- og DirectQuery-tabeller.

![Optimering af muligheder for en sammensat model](media/service-premium-capacity-optimize/composite-model-optimizations.png)

- Optimering af Import og DirectQuery-modeller gælder generelt sammensatte modeltabeller, der anvender disse storage-tilstande.
- Du skal bestræbe dig op at opnå et balanceret design ved at konfigurere tabeller af dimensionstypen (repræsenterer forretningsobjekter) som tabeller med dobbelt lagringstilstand og tabeller af oplysningstypen (ofte store tabeller, der repræsenterer driftsmæssige fakta) som lagringstilstanden DirectQuery. Dual lagringstilstand betyder, at både Import og DirectQuery storage-tilstand, og det gør det muligt for Power BI-tjenesten til at bestemme den mest effektive lagringstilstand, der skal bruges til at generere en oprindelig forespørgsel for gennemgående.
- Sørg for, at gateways har tilstrækkelige ressourcer, helst på dedikerede maskiner, med den nødvendige netværksbåndbredde og i nærheden af datakilderne.
- Akkumuleringstabeller, der er konfigureret som importlagringstilstand kan resultere i en væsentlig forbedring af forespørgselsydeevnen, når de bruges til at opsummere tabeller af faktatypen i DirectQuery-lagringstilstand. I dette tilfælde øger akkumuleringstabeller størrelsen af modellen og øger opdateringstiden, hvilket ofte er et acceptabelt kompromis for at opnå hurtigere forespørgsler.

### <a name="optimizing-externally-hosted-models"></a>Optimering af eksternt hostet modeller

Mange optimering muligheder, der er beskrevet i den [optimering af Power BI hostet modeller](#optimizing-power-bi-hosted-models) sektion gælder også for modeller, der er udviklet med Azure Analysis Services og SQL Server Analysis Services. Der er dog undtagelser i form af bestemt funktioner, der ikke understøttes i øjeblikket, bl.a. sammensatte modeller og akkumuleringstabeller.

I forbindelse med eksternt hostede datasæt bør du tage databasehostingen i forhold til Power BI-tjenesten med i dine overvejelser. For Azure Analysis Services betyder det, at Azure-ressourcen skal oprettes i samme område som Power BI-lejeren (det lokale område). I forbindelse med IaaS i SQL Server Analysis Services betyder det, at den virtuelle maskine skal hostes i samme område, og hvis der er tale om det lokale miljø, skal der sørges for en effektiv gatewaykonfiguration.

Det skal også nævnes, at Azure Analysis Services-databaser og SQL Server Analysis Services-tabeldatabaser kræver, at deres modeller indlæses fuldt ud i hukommelsen, og at de forbliver der hele tiden for at understøtte forespørgsler. På samme måde som Power BI-tjenesten skal der være tilstrækkelig hukommelse til opdatering, hvis modellen skal forblive online under opdateringen. I modsætning til Power BI-tjenesten er der ikke noget behov for, at modellerne tilføjes og fjernes fra hukommelsen i henhold til forbrug. Power BI Premium tilbyder derfor en mere effektiv tilgang til maksimering af modelforespørgsler med et lavere hukommelsesforbrug.

## <a name="capacity-planning"></a>Kapacitetsplanlægning

Størrelsen af en Premium-kapacitet bestemmer den hukommelse og de processorressourcer, der er tilgængelige, og de grænser, der er gælder for kapaciteten. Antallet af Premium-kapaciteter bør også overvejes, da oprettelsen af flere Premium kapaciteter kan hjælpe med at isolere arbejdsbelastninger fra hinanden. Bemærk, at lagring er 100 TB pr. kapacitetsnode, og at det sandsynligvis er mere end rigeligt for en hvilken som helst arbejdsbelastning.

Det kan være udfordrende at fastlægge størrelsen på og antallet af Premium-kapaciteter, især for de første kapaciteter, som du opretter. Det første trin, når du vælger kapacitetstørrelse er at forstå den gennemsnitlige arbejdsbelastning, der repræsenterer det forventede daglige forbrug. Det er vigtigt at forstå, at ikke alle arbejdsbelastninger er ens. I den ene ende af spektret kan du f.eks. have 100 samtidige brugere, der får adgang til en enkelt rapportside, der indeholder en enkelt visualisering, hvilket nemt kan opnås. I den anden ende af spektret kan du have 100 samtidige brugere, der får adgang til 100 forskellige rapporter, der hver har 100 visualiseringer på rapportsiden, hvilket belaster behovet for kapacitetsressourcer på forskellig vis.

Kapacitetsadministratorer skal derfor overveje flere forskellige faktorer, der er specifikke for jeres miljø, indhold og forventet brug. Det overordnede mål er at maksimere udnyttelsen af kapaciteter, samtidig med at der leveres ensartede forespørgselstider samt acceptable ventetider og fjernelsesrater. Følgende faktorer bør overvejes:

- **Model, størrelse og data** -Import modeller skal være fuldt indlæses i hukommelsen for at tillade forespørgsel eller opdateres. Datasæt med liveforbindelse eller DQ-datasæt kan kræve betydelig processortid og muligvis også meget hukommelse for at evaluere komplekse målinger eller RLS-regler. Hukommelses- og processorstørrelse og gennemløb for forespørgsler med liveforbindelse eller DQ-forespørgsler er begrænset af kapacitetsstørrelsen.
- **Samtidige aktive modeller** – den samtidige forespørgsler til forskellige import modeller giver bedste svartid og ydeevne, når de forbliver i hukommelsen. Der skal være tilstrækkelig hukommelse til at hoste alle modeller, der forespørges meget, med ekstra hukommelse for at muliggøre opdateringen af disse modeller.
- **Importér model opdatering** -opdateringstype (fuld eller trinvise), varighed og kompleksiteten ved forespørgsler fra Power-forespørgsel og beregnede tabelkolonne logik, kan have indflydelse på hukommelse og især processor forbrug. Samtidige opdateringer er begrænset af kapacitetsstørrelsen (1,5 x backend v-kerner, rundet op).
- **Samtidige forespørgsler** – mange samtidige forespørgsler kan resultere i svarer ikke rapporterer når processor eller LC/DQ forbindelser overskrider kapacitetsgrænsen for. Dette er især tilfældet for rapportsider, der indeholder mange visualiseringer.
- **Dataflows og sideinddelte rapporter** -kapaciteten kan konfigureres til at understøtte dataflows og sideinddelte rapporter med kræver en konfigurerbar maksimale procentdel af kapacitet hukommelse. Hukommelsen allokeres dynamisk at dataflows, men statisk er allokeret til sideinddelte rapporter.

Ud over disse faktorer kan kapacitetsadministratorer overveje at oprette flere kapaciteter. Flere kapaciteter gør det muligt at isolere arbejdsbelastninger og kan konfigureres til at sikre, at prioriterede arbejdsbelastninger har garanterede ressourcer. To kapaciteter kan f.eks. oprettes for at adskille forretningskritiske arbejdsbelastninger fra arbejdsbelastninger i BI-selvbetjeningsportalen (SSBI). Den forretningskritiske kapacitet kan bruges til at isolere store virksomhedsmodeller, der giver dem garanterede ressourcer, hvor det kun er it-afdelingen, der har oprettelesadgang. SSBI-kapaciteten kan bruges til at hoste et stigende antal mindre modeller, som forretningsanalytikere har adgang til. SSBI-kapaciteten kan nogle gange opleve ventetider på forespørgsler eller opdateringer, der er acceptable.

Med tiden kan kapacitetsadministratorer balancere arbejdsområder på tværs af kapaciteter ved at flytte indhold mellem arbejdsområder eller arbejdsområder mellem kapaciteter og ved at skalere kapaciteter op eller ned. Generelt udskalere til værten større modeller du op- og højere samtidighed du.

Husk, at køb af en licens giver lejeren v-kerner. Køb af et **P3-** abonnement kan bruges til at oprette en eller op til fire Premium-kapaciteter, dvs. 1 x P3 eller 2 x P2 eller 4 x P1. Før du konverterer en P2-kapacitet til en P3-kapacitet, kan du også overveje at opdele v-kernerne for at oprette to P1-kapaciteter.

## <a name="testing-approaches"></a>Test tilgange

Når du har valgt en kapacitetsstørrelse, kan test udføres ved at oprette et kontrolleret miljø. En praktisk og økonomisk mulighed er at oprette en Azure-kapacitet (A-SKU'er), hvor en P1-kapacitet har den samme størrelse som en A4-kapacitet, og P2- og P3-kapaciteterne har den samme størrelse som henholdsvis A5- og A6-kapaciteterne. Det er hurtigt at oprette Azure-kapaciteter, og de faktureres på timebasis. Når testen er fuldført, kan de nemt slettes, så du ikke længere faktureres for disse Azure-kapaciteter.

Testindholdet kan føjes til de arbejdsområder, der er oprettet på Azure-kapaciteten, og en enkelt bruger kan derefter køre rapporter for at generere en realistisk og repræsentativ arbejdsbelastning af forespørgsler. Hvis der er importmodeller, skal der også udføres en opdatering af hver model. Overvågningsværktøjer kan derefter bruges til at gennemse alle målepunkter for at forstå ressourceudnyttelsen.

Det er vigtigt, at de er gentages. Testene skal køres flere gange, og de skal levere ca. det samme resultat hver gang. Et gennemsnit af disse resultater kan bruges til at ekstrapolere og estimere arbejdsbelastning under ægte produktionsbetingelser.

I forbindelse med en belastningstest bør du overveje at udvikle et program til belastningstest for at simulere en realistisk arbejdsbelastning. Hvordan kan du gøre konkrete er ikke omfattet af denne artikel. Få yderligere oplysninger herunder et kodeeksempel ved at referere til den [indlæse test Power BI-programmer med Visual Studio belastningstest](https://blogs.msdn.microsoft.com/charles_sterling/2018/04/04/webinar-load-testing-power-bi-applications-with-visual-studio-load-test/) webinar.

## <a name="acknowledgements"></a>Godkendelser

I denne artikel er skrevet af Peter Myers, Data Platform MVP og uafhængige BI-ekspert med [bitvis løsninger](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Næste trin

> [!div class="nextstepaction"]
> [Premium-kapacitet scenarier](service-premium-capacity-scenarios.md)   
  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

||||||