---
title: Automatiseret maskinel indlæring i Power BI (prøveversion)
description: Lær, hvordan du bruger automatiserede Machine Learning (AutoML) i Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: davidi
LocalizationGroup: conceptual
ms.openlocfilehash: 894e92687a6283ce71b253bd4dc635aca0c4673f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61236267"
---
# <a name="automated-machine-learning-in-power-bi-preview"></a>Automatiseret maskinel indlæring i Power BI (prøveversion)

Automatiseret maskinindlæring (AutoML) for dataflows kan forretningsanalytikere til at træne, validere og aktivere Machine Learning-modeller direkte i Power BI. Det indeholder en enkel oplevelse til oprettelse af en ny ML-model, hvor analytikere kan bruge deres dataflows til at angive inputdata for oplæring af modellen. Tjenesten automatisk udtrækker de mest relevante funktioner, vælger en passende algoritme og gør og validerer ML-model. Når en model er oplært, opretter Power BI automatisk en rapport, der indeholder resultaterne af validering, der forklarer, ydeevnen og resultaterne til analytikere. Modellen kan derefter aktiveres på en hvilken som helst nye eller opdaterede data i dataflowet.

![Machine learning skærm](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Automatiserede machine learning er tilgængelig for dataflows, der er placeret på Power BI Premium og integrerede kapaciteter kun. I denne prøveversion, AutoML giver dig mulighed at oplære machine learning-modeller til Regression, klassificering og binær forudsigelse modeller.

## <a name="working-with-automl"></a>Arbejde med AutoML

[Power BI dataflows](service-dataflows-overview.md) tilbyder selvbetjening dataforberedelse til big data. AutoML giver dig mulighed at udnytte dine data forberedelse indsats for at bygge modeller til maskinel indlæring, direkte i Power BI.

AutoML i Power BI gør det muligt for dataanalytikere kan bruge dataflows til at bygge modeller til maskinel indlæring med en forenklet oplevelse, ved hjælp af blot Power BI-færdigheder. De fleste af datavidenskab bag oprettelse af ML-modeller er automatiseret af Power BI, med guardrails til at sikre, at den model, der er produceret har god kvalitet og synlighed, får du fuld indsigt i den proces, der bruges til at oprette din ML-model.

AutoML understøtter oprettelse af **binære forudsigelse**, **klassificering**, og **Regression** modeller til dataflows. Disse er typer af overvåget machine learning-modeller, hvilket betyder, at de få mere at vide fra de kendte resultater af tidligere observationer til at forudsige resultater af andre observationer. Input datasættet til uddannelse, en AutoML model er et sæt af poster, der er **mærket** med de kendte resultater.

AutoML i Power BI kan integreres [automatiseret ML](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) fra den [Azure Machine Learning-tjenesten](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) til at oprette din ML-modeller. Du kan dog ikke behøver et Azure-abonnement til at bruge AutoML i Power BI. Processen til træning og hosting ML-modeller administreres udelukkende af Power BI-tjenesten.

Når et ML-model er oplært, genererer AutoML automatisk en Power BI-rapport, der forklarer sandsynligvis ydeevnen af din ML-model. AutoML fremhæver explainability, ved at fremhæve de vigtigste lobbyister blandt dine input, der påvirker de forudsigelser, der returneres af din model. Rapporten indeholder også vigtige målepunkter for modellen, afhængigt af typen ML-model.

Andre sider i den genererede rapport viser statistiske oversigten over modellen og træning detaljerne. Oversigten over statistiske er interessante for brugere, der gerne vil se standard data science målingerne af ydeevnen for modellen. Uddannelse detaljerne opsummerer alle de gentagelser, der blev kørt for at oprette din model, med de tilknyttede modellering parametre. Det beskrives også, hvordan hver input blev brugt til at oprette ML-modellen.

Du kan derefter anvende din ML-model til dine data for scoring. Når der opdateres dataflowet til forudsigelse af din ML-model der automatisk skal anvendes til dine data. Powerbi indeholder også et individuelt tilpassede forklaring for hver specifikke forudsigelse score, der producerer ML-model.

## <a name="creating-a-machine-learning-model"></a>Oprettelse af et machine learning-modellen

Dette afsnit beskrives, hvordan du opretter en AutoML learning-modellen. 

### <a name="data-prep-for-creating-an-ml-model"></a>Dataforberedelse til oprettelse af et ML-model

Hvis du vil oprette en machine learning-modellen i Power BI, skal du først oprette en dataflowet for dataene, med resultatet af historiske oplysninger, som bruges til uddannelse, ML-model. Få detaljer om konfiguration af din dataflowet [selvbetjent eksamensforberedende i Power BI](service-dataflows-overview.md).

Power BI bruger data fra en enkelt enhed til at oplære modellen ML i den aktuelle udgave. Så hvis dine historiske data, der består af flere enheder, skal du manuelt joinforbinde data til en enkelt dataflowet enhed. Du skal også tilføje beregnede kolonner til en hvilken som helst forretningsmæssige målepunkter, der kan være en stærk indikatorer data for det udfald, du forsøger at forudsige.

AutoML har særlige krav til uddannelse, en model til maskinel indlæring. Disse krav er beskrevet i afsnittene nedenfor, baseret på de respektive modeltyper.

### <a name="configuring-the-ml-model-inputs"></a>Konfiguration af ML model input

For at oprette en AutoML model, skal du vælge ikonet ML i den **handlinger** kolonne af dataflowet enheden med den historiske data, og vælg **Tilføj en maskinel indlæringsmodel**.

![Tilføj et Machine learning-modellen](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

Forenklet startes, består af en guide, der fører dig gennem processen med at oprette ML-modellen. Guiden indeholder følgende enkle trin.

1. Vælg objektet med resultatet af historiske data og det felt, du vil have en forudsigelse
2. Vælg en modeltype, der er baseret på typen af forudsigelse, som du gerne vil se
3. Vælg den model, der skal bruges som forudsigende signaler input
4. Navngiv din model og gemme din konfiguration

Feltet historiske resultatet identificerer attributten etiket til uddannelse, ML modellen, som vises på følgende billede.

![Vælg resultatet af historiske data](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

Når du angiver feltet historiske resultatet, analyserer dataene for at identificere typerne ML-modeller, der kan tilpasses for disse data label AutoML pris og foreslår den mest sandsynlige ML modeltype, der kan tilpasses. 

> [!NOTE]
> Nogle modeltyper understøttes ikke for de data, du har valgt.

AutoML analyserer også alle felter i den valgte enhed til at foreslå input, der kan bruges til uddannelse, ML-model. Denne proces er omtrentlige og er baseret på statistiske analyser, så bør du gennemgå de input, der bruges. En hvilken som helst input, der er afhængige af feltet historiske resultatet (eller feltet etiket) skal ikke bruges til uddannelse ML-model, da de kan påvirke ydeevnen.

![Tilpas inputfelter](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

I det sidste trin, kan du navngive modellen og gemme dens indstillinger.

I denne fase, du bliver bedt om at opdatere dataflowet, som starter processen undervisning i forbindelse med ML-model.

### <a name="ml-model-training"></a>ML oplæring i dataminingmodeller

Uddannelse af AutoML modeller er en del af opdateringen dataflowet. AutoML først forbereder dine data til undervisning.

AutoML opdeler de historiske data, du angiver i en uddannelse, og test datasæt. Test datasættet er et sæt af testdata, der bruges til validering af ydeevnen modellen efter undervisning. Disse er indså som **uddannelse, og test** objekter i dataflowet. AutoML bruger krydsvalidering til validering af modellen.

Derefter skal hver inputfelt analyseres og fradrag anvendes, der erstatter de manglende værdier med erstattede værdier. Et par forskellige fradrag strategier bruges af AutoML. Derefter anvendes de påkrævede med høj tæthed og normalisering til dine data.

AutoML gælder flere transformationer er hvert felt for valgte input, der er baseret på dens datatype og egenskaberne statistiske. AutoML bruger disse transformationer til at udtrække funktioner til brug i oplæring af din ML-model.

Uddannelsesprocessen for AutoML modeller, der består af op til 50 gentagelser med forskellige modellering algoritmer og modeloplæring indstillinger for at finde modellen med den bedste ydeevne. Ydeevnen for hver af disse modeller er vurderet af validering med testdata test datasættet. I dette trin uddannelse opretter AutoML flere pipelines til oplæring og validering af disse gentagelser. Processen med at vurdere ydeevnen for modellerne, der kan tage tid, hvor som helst fra flere minutter, før et par timer, afhængigt af størrelsen af dit datasæt og de tilgængelige ressourcer i dedikeret kapacitet.

I nogle tilfælde kan må den endelige model, der er genereret bruge ensemble læring, hvor flere modeller, der bruges til at levere bedre forudsigende ydeevne.

### <a name="automl-model-explainability"></a>AutoML model explainability

Når modellen er oplært, analyserer AutoML relationen mellem funktionerne til input og output model. Den vurderer størrelse og retning for ændring af modellen outputtet for datasættet test testdata for hver funktion, som input. Dette er kendt som den *funktion vigtighed*.

![Funktionen vigtighed](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

### <a name="automl-model-report"></a>AutoML model rapport

AutoML genererer en Power BI-rapport, der opsummerer ydeevnen af modellen under valideringen, sammen med den globale funktion betydning. Rapporten opsummerer resultaterne fra anvendelse af ML modellen til test testdata og sammenligning af forudsigelser med kendte resultatet værdier.

Du kan gennemse rapporten model til at forstå dens ydeevne. Du kan også bekræfte, at justere de vigtigste lobbyister af modellen med forretningsmæssig indsigt om de kendte udfald.

Diagrammer og målinger, der bruges til at beskrive modelydeevnen i rapporten afhænger af typen af modellen. Disse diagrammer ydeevne og mål, der er beskrevet i følgende afsnit.

Flere sider i rapporten kan beskrive statistiske målinger om modellen fra et data science perspektiv. For eksempel den **binære forudsigelse** rapporten indeholder et diagram med tab og ROC kurven til modellen.

Rapporterne, der omfatter også en **oplysninger om træning** sider, der indeholder en beskrivelse af, hvordan modellen blev uddannet og indeholder et diagram, der beskriver modelydeevnen over hver af gentagelser kører.

![Oplæringsoplysninger](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

På denne side på et andet afsnit beskriver, hvordan metoden fradrag brugte til at udfylde manglende værdier for inputfelterne, samt hvordan hver inputfelt blev transformeret for at udtrække de funktioner, der bruges i modellen. Den omfatter også de parametre, der bruges af den endelige model.

![Flere oplysninger om modellen](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

Hvis den model, der er produceret bruger ensemble læring, og derefter den **oplysninger om træning** -siden omfatter også et afsnit beskriver vægten af hver aktivering af vælgere model i ensemble samt flowets parametre.

![Vægt i ensemble](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

## <a name="applying-the-automl-model"></a>Anvendelse af AutoML modellen

Hvis du er tilfreds med ydeevne i ML-model, der er oprettet, kan du anvende den til nye eller opdaterede data, når din dataflowet opdateres. Du kan gøre dette fra rapporten model ved at vælge den **Anvend** knap i øverste højre hjørne.

Hvis du vil anvende ML-modellen, skal du angive navnet på den enhed, hvor det skal være anvendt og et præfiks for de kolonner, der skal føjes til denne enhed til modellen output. Standardpræfikset for kolonnenavnene er Modelnavnet. Den *Anvend* funktionen kan omfatte yderligere parametre, der er specifikke for typen af modellen.

Anvendelse af modellen ML opretter en ny enhed dataflow med suffikset **beriget < modelnavn >** . Hvis du anvender den _PurchaseIntent_ modeller til den _OnlineShoppers_ enhed, vil generere output af **OnlineShoppers beriget PurchaseIntent**.

I øjeblikket kan output enheden ikke bruges til at få vist resultaterne ML-model i Power Query editor. Outputkolonner vise altid null som resultat. For at få vist resultaterne, et sekund output-enhed med suffikset **beriget < modelnavn > prøveversion** oprettes, når modellen skal anvendes.

Du skal opdatere dataflowet, for at få vist resultaterne i Forespørgselseditor.

![Forespørgselseditor](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Når du anvender modellen, holder AutoML altid dine forudsigelser opdateret når dataflowet opdateres.

AutoML omfatter også en individuelt tilpassede forklaring for hver række, som det scorer i enheden output.

Hvis du vil bruge den indblik og forudsigelser fra ML modellen i en Power BI-rapport, du kan oprette forbindelse til enheden output fra Power BI Desktop ved hjælp af den **dataflows** connector.

## <a name="binary-prediction-models"></a>Binær Prædiktionsmodeller

Binære prædiktionsmodeller, mere formelt er kendt som **binær klassificering modeller**, der bruges til at klassificere et datasæt i to grupper. De bruges til at forudsige hændelser, der kan en binær udfald, f.eks om konverteres en salgsmulighed, om en konto, vil churn, om en faktura, der skal betales til tiden; Angiver, om en transaktion er falske osv.

Da resultatet er binær, Power BI forventer etiketten til en binær forudsigelsesmodel skal være en boolesk værdi, med kendte resultater, der er mærket **true** eller **false**. I en salgsmulighed konvertering model, salgsmuligheder, der har været vundet hedder true, dem, der er gået tabt hedder false, og, åbne salgsmuligheder er mærket som null.

Resultatet af en binær forudsigelsesmodel er en sandsynlighedsscore, som identificerer sandsynligheden for, at der opnås resultatet svarer til etiket for værdien er true.

### <a name="training-a-binary-prediction-model"></a>Oplæring af en binær forudsigelsesmodel

Hvis du vil oprette en binær forudsigelsesmodel, skal input enheden, der indeholder dine uddannelsesdata have et boolesk felt som feltet historiske resultatet til at identificere de sidste kendte resultater.

Forudsætninger:

* Et boolesk felt, der skal bruges som feltet historiske resultatet
* Der skal angives mindst 50 rækker af historiske data for hver enkelt klasse af resultater

Generelt, hvis de seneste udfald identificeres ved hjælp af felter i en anden datatype, kan du tilføje en beregnet kolonne til at transformere disse i en boolesk værdi ved hjælp af Power-forespørgsel.

Processen til oprettelse af en binær forudsigelsesmodel følger de samme trin andre AutoML modeller, der er beskrevet i afsnittet **konfiguration af ML model input** ovenfor.

### <a name="binary-prediction-model-report"></a>Binær forudsigelse model rapport

Den binære forudsigelsesmodel producerer som output en sandsynligheden for, at en post opnår det resultat, der er defineret af værdien boolesk etiket som True. Rapporten indeholder et udsnitsværktøj til grænsen sandsynlighed, som påvirker, hvordan resultaterne, der er over og under grænsen sandsynlighed fortolkes.

Rapporten beskriver ydeevnen af modellen i form af *True positiver*, *falske positiver*, *True negative* og *False negative*. True positive og negative True er korrekt forudsagte resultater for de to klasser i resultatet dataene. Falske positiver, der er resultater, der havde faktiske boolesk etiketten for værdien False, men var forventet som True. Omvendt, er falsk negative resultater, hvor den faktiske for booleske etiketværdi er True, men var forventet som False.

Målinger, f.eks præcision og tilbagekaldelse, beskriver effekten af sandsynlighed grænsen på de forudsagte resultater. Du kan bruge sandsynlighed tærskel udsnitsværktøjet til at vælge en tærskel, der opnår et balanceret kompromis mellem præcision og tilbagekaldelse.

![Nøjagtigheden prøveversion](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

Den **nøjagtighed rapport** side i rapporten model indeholder den *akkumuleret gevinster* diagrammet, og ROC kurve til modellen. Disse er statistisk målinger af ydeevnen i modellen. Rapporterne, der omfatter beskrivelser af diagrammer, der vises.

![Nøjagtigheden rapport skærm](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

### <a name="applying-a-binary-prediction-model"></a>Anvendelse af en binær forudsigelsesmodel

Hvis du vil anvende en binær forudsigelsesmodel, skal du angive enheden med de data, som du vil anvende til forudsigelse af ML-model. Andre parametre omfatter output navn kolonnepræfikset og sandsynlighed grænsen for klassificering forudsagt resultatet.

![Forudsigelse af input](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

Når der anvendes en binær forudsigelsesmodel, føjer tre outputkolonner på enheden, forbedret output. Disse er de **PredictionScore**, **PredictionOutcome** og **PredictionExplanation**. Kolonnenavnene i enheden har det præfiks, der er angivet, når der anvendes af modellen.

Den **PredictionOutcome** kolonne indeholder den forudsagte resultat etiket. Poster, hvor sandsynligheder overskrider grænsen forventes som muligheder for at opnå resultatet, og dem, herunder forventes som usandsynligt at opnå resultatet.

Den **PredictionExplanation** kolonne indeholder en forklaring med den specifikke indflydelse, havde input funktionerne på den **PredictionScore**. Dette er en JSON-formateret samling af vægten af funktionerne til input til forudsigelse.

## <a name="classification-models"></a>Klassificering modeller

Klassificering af modeller, der bruges til at klassificere et datasæt til flere grupper eller klasser.  De bruges til at forudsige hændelser, der kan have en af flere mulige resultater, f.eks om en kunde er sandsynligt, at du har en meget høj, høj, mellem, eller en lav værdi for levetid; om risikoen for standard er høj, moderat, lav eller meget lav; og så videre.

Resultatet af en klassifikationsmodel er en sandsynlighedsscore, som identificerer sandsynligheden for, at en post vil opnå kriterierne for en given klasse.

### <a name="training-a-classification-model"></a>Oplæring af en klassifikationsmodel

Objektet input, der indeholder dataene træning for en model for klassificering skal have en streng eller et numerisk felt, som feltet historiske resultatet, som identificerer de sidste kendte resultater.

Forudsætninger:

* Der skal angives mindst 50 rækker af historiske data for hver enkelt klasse af resultater

Processen til oprettelse af en klassifikationsmodel følger de samme trin andre AutoML modeller, der er beskrevet i afsnittet **konfiguration af ML model input** ovenfor.

### <a name="classification-model-report"></a>Klassificering model rapport

Klassificeringen model rapporten er produceret ved at anvende testdata ML modellen test data og sammenligne den forudsagte klasse for en post med faktiske kendte klassen.

Modellen rapporten indeholder et diagram, der indeholder opdelingen af de korrekt og forkert klassificerede poster for hver enkelt kendte klasse.

![Model-rapport](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

En yderligere klasse-specifikke detaljeret gør det muligt for en analyse af hvordan distribueres forudsigelserne til en kendt klasse. Dette omfatter andre klasser, er sandsynligvis klassificeret poster af denne klasse er kendt.

![Analyserapport](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Forklaring af modellen i rapporten indeholder også de øverste indikatorer data for hvert fag.

Klassificering model rapporten indeholder også en lignende til siderne for andre typer af modellen, siden med oplysninger om træning, som beskrevet i afsnittet **AutoML model rapport** tidligere i denne artikel.

### <a name="applying-a-classification-model"></a>Anvendelse af en klassifikationsmodel

Hvis du vil anvende en klassificering ML-model, skal du angive enheden med inputdata og præfikset output kolonnen navn.

Når der anvendes en klassifikationsmodel, tilføjer den tre kolonner på enheden, forbedret output-output. Disse er de **PredictionScore**, **PredictionClass** og **PredictionExplanation**. Kolonnenavnene i enheden har det præfiks, der er angivet, når der anvendes af modellen.

Den **PredictionClass** kolonne indeholder sandsynligvis forudsagt klassen for posten. Den **PredictionScore** kolonne indeholder en liste over sandsynlighed resultater for posten for hvert mulige klasse.

Den **PredictionExplanation** kolonne indeholder en forklaring med den specifikke indflydelse, havde input funktionerne på den **PredictionScore**. Dette er en JSON-formateret samling af vægten af funktionerne til input til forudsigelse.

## <a name="regression-models"></a>Regressionsmodeller

Regressionsmodeller, der bruges til at forudsige en værdi, f.eks sandsynligvis, at der opstår i en salg handel, levetidsværdien af en konto, mængden af en indgående faktura, der sandsynligvis skal betales, den dato, hvor en faktura kan være betalt indtægter , og så videre.

Resultatet af en regressionsmodel er den forudsagt værdi.

### <a name="training-a-regression-model"></a>Oplæring af en regressionsmodel

Objektet input, der indeholder træning dataene for en regressionsmodel skal have et numerisk felt, som feltet historiske resultatet, som identificerer de sidste kendte resultatet værdier.

Forudsætninger:

* Der skal angives et minimum på 100 rækker af historiske data for en regressionsmodel

Processen til oprettelse af en regressionsmodel følger de samme trin andre AutoML modeller, der er beskrevet i afsnittet **konfiguration af ML model input** ovenfor.

### <a name="regression-model-report"></a>Regression model rapport

Regression rapporten er baseret på resultaterne fra anvendelse af modellen til test testdata som med andre AutoML model rapporter.

Modellen rapporten indeholder et diagram, der sammenligner de forudsagte værdier, som den faktiske værdi. I dette diagram angiver afstanden fra diagonalt af fejl i forudsigelse.

Resterende fejl diagrammet viser fordelingen af procentdelen af den gennemsnitlige fejl for forskellige værdier i testdata test datasættet. Den vandrette akse repræsenterer middelværdien af den faktiske værdi for gruppen med størrelsen på boblerne viser frekvensen eller antallet af værdier i dette område. Den lodrette akse er den gennemsnitlige resterende fejl.

![Resterende fejl diagram](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

Regression model rapporten indeholder også en side med træning oplysninger som f.eks. rapporter for andre typer af modellen, som beskrevet i afsnittet **AutoML model rapport** ovenfor.

### <a name="applying-a-regression-model"></a>Anvendelse af en regressionsmodel

Hvis du vil anvende en Regression ML-model, skal du angive enheden med inputdata og præfikset output kolonnen navn.

![Anvend en regression](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

Når der anvendes en regressionsmodel, tilføjer to outputkolonner til objektet forbedret output. Disse er de **PredictionValue**, og **PredictionExplanation**. Kolonnenavnene i enheden har det præfiks, der er angivet, når der anvendes af modellen.

Den **PredictionValue** kolonne indeholder den forudsagte værdi for den post, der er baseret på inputfelter. Den **PredictionExplanation** kolonne indeholder en forklaring med den specifikke indflydelse, havde input funktionerne på den **PredictionValue**. Dette er en JSON-formateret samling af vægten af funktionerne til input.

## <a name="next-steps"></a>Næste trin

I denne artikel angivet en oversigt over automatiseret Machine Learning til Dataflows i Power BI-tjenesten. I følgende artikler kan også være nyttige.

* [Selvstudium: Byg en model til Maskinindlæring i Power BI (prøveversion)](service-tutorial-build-machine-learning-model.md)
* [Selvstudium: Brug af Cognitive Services i Power BI](service-tutorial-use-cognitive-services.md)
* [Selvstudium: Aktivér en Machine Learning Studio-model i Power BI (prøveversion)](service-tutorial-invoke-machine-learning-model.md)
* [Cognitive Services i Power BI (prøveversion)](service-cognitive-services.md)
* [Azure Machine Learning-integration i Power BI (prøveversion)](service-machine-learning-integration.md)

Du kan få flere oplysninger om dataflow i disse artikler:
* [Opret og brug dataflow i Power BI](service-dataflows-create-use.md)
* [Ved hjælp af den beregnede enheder på Power BI Premium](service-dataflows-computed-entities-premium.md)
* [Ved hjælp af dataflows med datakilder i det lokale miljø](service-dataflows-on-premises-gateways.md)
* [Udviklerressourcer til Power BI dataflows](service-dataflows-developer-resources.md)
* [Integration af dataflow og Azure Data Lake (prøveversion)](service-dataflows-azure-data-lake-integration.md)


