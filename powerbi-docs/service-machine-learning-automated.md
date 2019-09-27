---
title: Automatiseret maskinel indlæring i Power BI (prøveversion)
description: Få mere at vide om, hvordan du bruger automatiseret maskinel indlæring (AutoML) i Power BI
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
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61236267"
---
# <a name="automated-machine-learning-in-power-bi-preview"></a>Automatiseret maskinel indlæring i Power BI (prøveversion)

AutoML (automatiseret maskinel indlæring) til dataflows gør det muligt for virksomhedsanalytikere at oplære, validere og aktivere modeller til maskinel indlæring direkte i Power BI. Versionen indeholder en enkel funktion til oprettelse af en ny ML-model, hvor analytikere kan bruge deres dataflows til at angive inputdataene til oplæring af modellen. Tjenesten udtrækker automatisk de mest relevante funktioner, vælger en passende algoritme og finjusterer og validerer ML-modellen. Når en model er oplært, genererer Power BI automatisk en rapport, der indeholder resultaterne af valideringen, som forklarer ydeevnen og resultaterne til analytikere. Modellen kan derefter aktiveres på alle nye eller opdaterede data i dataflowet.

![Skærmen Maskinel indlæring](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Automatiseret maskinel indlæring er kun tilgængelig for de dataflows, der er hostet i Power BI Premium- og Embedded-kapaciteter. I denne prøveversion kan du bruge AutoML til at oplære modeller til maskinel indlæring til binære forudsigelses-, klassificerings- og regressionsmodeller.

## <a name="working-with-automl"></a>Arbejde med AutoML

[Power BI-dataflows](service-dataflows-overview.md) tilbyder selvbetjent dataforberedelse af big data. AutoML gør det muligt at udnytte dine dataforberedelsestiltag til at opbygge modeller til maskinel indlæring direkte i Power BI.

AutoML i Power BI gør det muligt for dataanalytikere at bruge dataflows til at bygge modeller til maskinel indlæring med en forenklet oplevelse udelukkende ved hjælp af Power BI-færdigheder. Størstedelen af datavidenskaben bag oprettelsen af ML-modeller automatiseres af Power BI med retningslinjer, der sikrer, at den model, der produceres, er i en god kvalitet og giver dig fuld indsigt i den proces, der bruges til at oprette din ML-model.

AutoML understøtter oprettelsen af **binære forudsigelses-** , **klassificerings-** og **regressionsmodeller** til dataflows. Dette er overvågede modeltyper til maskinel indlæring, hvilket betyder, at de lærer fra kendte resultater af tidligere observationer til at forudsige resultatet af andre observationer. Inputdatasættet til oplæring af en AutoML-model er et sæt poster, der er **mærket** med de kendte resultater.

AutoML i Power BI integrerer [automatiseret ML](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) fra [Azure Machine Learning-tjenesten](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) for at oprette dine ML-modeller. Du behøver dog ikke et Azure-abonnement for at bruge AutoML i Power BI. Processen til oplæring og hosting af ML-modeller administreres udelukkende af Power BI-tjenesten.

Når en ML-model er oplært, genererer AutoML automatisk en Power BI-rapport, der forklarer den sandsynlige ydeevne for din ML-model. AutoML lægger vægt på forklaringsdelen ved at fremhæve nøglefaktorer blandt inputtet, der har indflydelse på de forudsigelser, der returneres af modellen. Rapporten indeholder også vigtige målepunkter for modellen, afhængigt af ML-modeltypen.

Andre sider i den genererede rapport viser den statistiske oversigt over modellen og detaljer om oplæringen. Den statistiske oversigt er af interesse for de brugere, der ønsker at få vist den datavidenskabelige standardydeevne for modellen. Detaljerne om oplæringen opsummerer alle de gentagelser, der blev kørt for at oprette din model, med de tilknyttede modelparametre. De beskriver også, hvordan hvert enkelt input blev brugt til at oprette ML-modellen.

Du kan derefter anvende din ML-model på dine data for at få et resultat. Når dataflowet opdateres, anvendes forudsigelser fra din ML-model automatisk på dine data. Power BI omfatter også en individuel forklaring til hver bestemt forudsigelsesscore, som ML-modellen producerer.

## <a name="creating-a-machine-learning-model"></a>Oprettelse af en model til maskinel indlæring

I dette afsnit beskrives det, hvordan du opretter en AutoML-læringsmodel. 

### <a name="data-prep-for-creating-an-ml-model"></a>Forberedelse af data til oprettelse af en ML-model

Hvis du vil oprette en model til maskinel indlæring i Power BI, skal du først oprette et dataflow til dataene med de historiske resultatoplysninger, der bruges til oplæring af ML-modellen. Du kan få mere at vide om, hvordan du konfigurerer dit dataflow, i [Selvbetjent dataforberedelse i Power BI](service-dataflows-overview.md).

I den aktuelle version bruger Power BI kun data fra en enkelt enhed til oplæring af ML-modellen. Hvis dine historiske data består af flere enheder, skal du derfor manuelt forbinde dataene til en enkelt dataflowenhed. Du skal også tilføje beregnede kolonner for alle forretningsmålepunkter, der kan være effektive forudsigelser for det resultat, du forsøger at forudsige.

AutoML har specifikke datakrav til oplæring af en model til maskinel indlæring. Disse krav er beskrevet i nedenstående afsnit ud fra de respektive modeltyper.

### <a name="configuring-the-ml-model-inputs"></a>Konfiguration af ML-modelinput

Hvis du vil oprette en AutoML-model, skal du vælge ML-ikonet i kolonnen **Handlinger** i dataflowenheden med de historiske data og vælge **Tilføj en model til maskinel indlæring**.

![Tilføj en model til maskinel indlæring](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

En forenklet proces igangsættes, der består af en guide, som hjælper dig med at oprette en ML-model. Guiden indeholder følgende enkle trin.

1. Vælg enheden med de historiske resultatdata og det felt, du vil have en forudsigelse for.
2. Vælg en modeltype, der er baseret på den type forudsigelse, du vil have vist.
3. Vælg de input, som modellen skal bruge som forudsigende signaler.
4. Navngiv din model, og gem konfigurationen.

Feltet med det historisk resultat identificerer mærkatattributten for oplæring af MD-modellen, som vist på følgende billede.

![Vælg historiske resultatdata](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

Når du angiver feltet med det historiske resultat, analyserer AutoML mærkatdataene for at identificere de typer ML-modeller, der kan oplæres for de pågældende data, og foreslår den mest sandsynlige ML-modeltype, der kan oplæres. 

> [!NOTE]
> Visse modeltyper understøttes muligvis ikke for de valgte data.

AutoML analyserer også alle felterne i den valgte enhed for at komme med forslag til input, der kan bruges til oplæring af ML-modellen. Denne proces er omtrentlig og er baseret på statistiske analyser, og du skal derfor gennemgå det input, der benyttes. Input, der er afhængige af feltet med det historiske resultat (eller mærkatfeltet), må ikke bruges til oplæring af ML-modellen, da de påvirker modellens ydeevne.

![Tilpas inputfelter](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

I det sidste trin kan du navngive modellen og gemme indstillingerne for den.

På dette tidspunkt bliver du bedt om at opdatere dataflowet, hvilket igangsætter oplæringsprocessen for ML-modellen.

### <a name="ml-model-training"></a>Oplæring af ML-model

Oplæring af AutoML-modeller er en del af dataflowopdateringen. AutoML klargør først dine data til oplæring.

AutoML opdeler de historiske data, som du angiver, i et datasæt til oplæring og et datasæt til test. Testdatasættet er et testsæt, der bruges til at validere modellens ydeevne efter oplæringen. Disse vises som enheder til **oplæring og test** i dataflowet. AutoML bruger krydsvalidering til modelvalideringen.

Derefter analyseres hvert inputfelt, og der foretages en sammenligning, hvor manglende værdier erstattes. AutoML benytter et par forskellige metoder til at foretage udledninger. Derefter anvendes stikprøvetagning og normalisering for dataene, hvis det er påkrævet.

AutoML anvender flere transformationer på baggrund af det enkelte valgte inputfelt, afhængigt af feltets datatype og dets statistiske egenskaber. AutoML bruger disse transformationer til at udtrække funktioner, som kan bruges til oplæring af din ML-model.

Oplæringsprocessen for AutoML-modeller består af op til 50 gentagelser med forskellige modelalgoritmer og indstillinger for hyperparametre for at finde modellen med den bedste ydeevne. Ydeevnen for hver af disse modeller vurderes ved hjælp af validering med testdatasættet. I løbet af dette oplæringstrin opretter AutoML flere pipelines til oplæring og validering af disse gentagelser. Processen med at vurdere ydeevnen for modellerne kan tage alt lige fra adskillige minutter til et par timer, afhængigt af størrelsen på datasættet og de dedikerede kapacitetsressourcer, der er tilgængelige.

I nogle tilfælde kan den endelige model, der genereres, bruge Ensemble Learning, hvor der bruges flere modeller til at levere en bedre forudsigelsesydeevne.

### <a name="automl-model-explainability"></a>Forklaringsdelen af AutoML-modellen

Når modellen er blevet oplært, analyserer AutoML relationen mellem inputfunktionerne og modeloutputtet. Størrelsen og retningen af ændringen af modeloutputtet for testdatasættet for de enkelte inputfunktioner vurderes. Dette kaldes *funktionsprioritet*.

![Funktionsprioritet](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

### <a name="automl-model-report"></a>AutoML-modelrapport

AutoML genererer en Power BI-rapport, der opsummerer modellens ydeevne under validering, sammen med den overordnede funktionsprioritet. Rapporten opsummerer resultaterne i forhold til anvendelse af ML-modellen på testdataene og sammenligner forudsigelserne med de kendte resultatværdier.

Du kan gennemse modelrapporten for at forstå dens ydeevne. Du kan også validere, at nøglefaktorerne for modellen passer til den forretningsmæssige indsigt vedrørende de kendte resultater.

De diagrammer og målinger, der bruges til at beskrive modellens ydeevne i rapporten, afhænger af modeltypen. Disse diagrammer og målinger over ydeevne er beskrevet i følgende afsnit.

Yderligere sider i rapporten kan beskrive statistiske målinger om modellen fra et datavidenskabeligt perspektiv. Rapporten med **binære forudsigelser** indeholder f.eks. et resultatdiagram og ROC-kurven for modellen.

Rapporterne omfatter også siden **Oplæringsoplysninger**, der indeholder en beskrivelse af, hvordan modellen er oplært, og inkluderer et diagram, der beskriver modellens ydeevne for hver af de enkelte gentagelser.

![Oplæringsoplysninger](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

Et andet afsnit på denne side beskriver, hvordan den udledningsmetode, der bruges til udfyldning af manglende værdier for inputfelterne, samt hvordan hvert inputfelt blev transformeret for at udtrække de funktioner, der benyttes i modellen. Det indeholder også de parametre, der bruges af den endelige model.

![Flere oplysninger om modellen](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

Hvis den producerede model bruger Ensemble Learning, indeholder siden **Detaljer til oplæring** også et afsnit, der beskriver vægtningen af hver komponentmodel i ensemblet samt de tilhørende parametre.

![Vægtning i ensemble](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

## <a name="applying-the-automl-model"></a>Anvendelse af AutoML-modellen

Hvis du er tilfreds med ydeevnen i den ML-model, der er blevet oprettet, kan du anvende den på nye eller opdaterede data, når dit dataflow opdateres. Du kan gøre dette fra modelrapporten ved at vælge knappen **Anvend** i øverste højre hjørne.

Hvis du vil anvende ML-modellen, skal du angive navnet på den enhed, som modellen skal anvendes for, og et præfiks for de kolonner, der føjes til denne enhed for modeloutputtet. Standardpræfikset for kolonnenavnene er modelnavnet. Funktionen *Anvend* omfatter muligvis yderligere parametre, der er specifikke for modeltypen.

Når du anvender ML-modellen, oprettes et nyt dataflow med suffikset **enriched <model_name>.** Hvis du f.eks. anvender modellen _PurchaseIntent_ for enheden_OnlineShoppers_ , genererer outputtet**OnlineShoppers enriched PurchaseIntent**.

Outputenheden kan i øjeblikket ikke bruges til at få vist resultaterne af ML-modellen på forhånd i Power-forespørgselseditor. Outputkolonnerne viser altid null som resultat. Hvis du vil have vist resultaterne, oprettes der en anden outputenhed med suffikset **enriched <model_name> Preview**, når modellen anvendes.

Du skal opdatere dataflowet for at få vist et eksempel på resultaterne i forespørgselseditoren.

![Forespørgselseditor](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Når du anvender modellen, holder AutoML altid dine forudsigelser ajour, når dataflowet opdateres.

AutoML indeholder også en personlig forklaring for hver række, der er resultatet af outputenheden.

Hvis du vil bruge indsigt og forudsigelser fra ML-modellen i en Power BI-rapport, kan du oprette forbindelse til outputenheden fra Power BI Desktop ved hjælp connectoren **dataflows**.

## <a name="binary-prediction-models"></a>Binære forudsigelsesmodeller

Binære forudsigelsesmodeller, der mere formelt er kendt som **binære klassifikationsmodeller**, bruges til at klassificere et datasæt i to grupper. De bruges til at forudsige hændelser, der kan have et binært resultat, f.eks. om en salgsmulighed vil blive konverteret, om en kunde falder fra, om en faktura betales til tiden, om en transaktion er ulovlig osv.

Eftersom resultatet er binært, forventer Power BI, at mærkatet for en binær forudsigelsesmodel er boolesk, hvor kendte resultater får mærkatet **True** eller **False**. I en konverteringsmodel for salgsmuligheder mærkes salgsmuligheder, der er blevet vundet, f.eks. med true, de, der er blevet tabt, med false, og åbne salgsmuligheder får mærkatet Null.

Outputtet af den binære forudsigelsesmode er en sandsynlighedsscore, som identificerer sandsynligheden for, om resultatet svarer til mærkatværdien true, opnås.

### <a name="training-a-binary-prediction-model"></a>Oplæring af en binær forudsigelsesmodel

Hvis du vil oprette en binær forudsigelsesmodel, skal den inputenhed, der indeholder oplæringsdataene, have et boolesk felt som det historiske resultatfelt for at identificere tidligere kendte resultater.

Forudsætninger:

* Et boolesk felt skal bruges som det historiske resultatfelt.
* Der kræves mindst 50 rækker historiske data for hver klasse af resultater.

Hvis de tidligere resultater identificeres af felter med en anden datatype, kan du generelt tilføje en beregnet kolonne for at omdanne dem til en boolesk værdi ved hjælp af Power-forespørgsel.

Oprettelsesprocessen for en binær forudsigelsesmodel følger de samme trin som andre AutoML-modeller, der er beskrevet i afsnittet **Konfiguration af ML-modelinput** ovenfor.

### <a name="binary-prediction-model-report"></a>Rapport over binær forudsigelsesmodel

Den binære forudsigelsesmodel frembringer som et resultat en sandsynlighed for, at en post vil opnå det resultat, der er defineret af den booleske mærkatværdi True. Rapporten indeholder et udsnit for tærsklen for sandsynlighed, der påvirker, hvordan scorerne over og under tærsklen for sandsynlighed fortolkes.

I rapporten beskrives ydeevnen for modellen i forhold til *ægte positive*, *falske positive*, *ægte negative* og *falske negative*. Ægte positive og ægte negative er korrekt forudsagte resultater for de to klasser i resultatdataene. Falske positive er udfald, der har den faktiske booleske mærkatværdi False, men som blev forudsagt som True. Omvendt er falske negative udfald, hvor den faktiske booleske mærkatværdi var True, men blev forudsagt som False.

Målinger, f.eks. præcision og genkaldelse, beskriver effekten af tærsklen for sandsynlighed for de forudsagte resultater. Du kan bruge udsnitsværktøjet for tærsklen for sandsynlighed til at vælge en tærskel, der opnår et balanceret kompromis mellem præcision og genkaldelse.

![Forhåndsvisning af nøjagtighed](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

Siden **Nøjagtighedsrapport** i modelrapporten omfatter diagrammet *Akkumulerede gevinster* og ROC-kurven for modellen. Dette er statistiske målinger af modellens ydeevne. Rapporterne indeholder beskrivelser af de viste diagrammer.

![Skærm med rapport over nøjagtighed](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

### <a name="applying-a-binary-prediction-model"></a>Anvendelse af en binær forudsigelsesmodel

Hvis du vil anvende en binær forudsigelsesmodel, skal du angive data for den enhed, du vil anvende forudsigelserne fra ML-modellen på. Andre parametre omfatter outputkolonnens navnepræfiks og tærsklen for sandsynlighed til klassificering af det forudsagte udfald.

![Forudsigelsesinput](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

Når der anvendes en binær forudsigelsesmodel, føjes der tre outputkolonner til den forbedrede outputenhed. Det er **PredictionScore**, **PredictionOutcome** og **PredictionExplanation**. Der angives et præfiks for kolonnenavnene i enheden, når modellen anvendes.

Kolonnen **PredictionOutcome** indeholder mærkatet for det forudsagte resultat. Poster med sandsynligheder, der overskrider tærsklen, forudsiges at være sandsynlige for at opnå resultatet, og de, der ligger under tærsklen, forudsiges at være usandsynlige for at opnå resultatet.

Kolonnen **PredictionExplanation** indeholder en forklaring af den bestemte indvirkning, som inputfunktionerne havde på **PredictionScore**. Dette er en JSON-formateret samling af vægtninger for forudsigelsens inputfunktioner.

## <a name="classification-models"></a>Klassificeringsmodeller

Klassificeringsmodeller bruges til at klassificere et datasæt i flere grupper eller klasser.  De bruges til at forudsige hændelser, der kan have et af flere mulige resultater, f.eks. om en kunde sandsynligvis har en meget høj, høj, mellem eller lav levetidsværdi, om risikoen for manglende betaling er høj, moderat, lav eller meget lav. osv.

Outputtet af en klassificeringsmodel er en sandsynlighedsscore, der identificerer sandsynligheden for, at en post opfylder kriterierne for en bestemt klasse.

### <a name="training-a-classification-model"></a>Oplæring af en klassificeringsmodel

Den inputenhed, der indeholder dine oplæringsdata for en klassificeringsmodel, skal have en streng eller et numerisk felt som det historisk resultatfelt, der identificerer de tidligere kendte resultater.

Forudsætninger:

* Der kræves mindst 50 rækker historiske data for hver klasse af resultater.

Oprettelsesprocessen for en klassificeringsmodel følger de samme trin som andre AutoML-modeller, der er beskrevet i afsnittet **Konfiguration af ML-modelinput** ovenfor.

### <a name="classification-model-report"></a>Rapport over klassificeringsmodel

Klassificeringsmodelrapporten oprettes ved at anvende ML-modellen på testdata og sammenligne den forudsagte klasse for en post med den faktiske kendte klasse.

Modelrapporten indeholder et diagram, der indeholder en opdeling af de korrekt og forkert klassificerede poster for de enkelte kendte klasser.

![Modelrapport](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

En yderligere klassespecifik detailudledning gør det muligt at analysere, hvordan forudsigelserne for en kendt klasse distribueres. Dette omfatter de andre klasser, hvor poster for den kendte klasse sandsynligvis klassificeres forkert.

![Analyserapport](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Modelforklaringen i rapporten indeholder også de vigtigste forudsigelser for hver klasse.

Klassificeringsmodelrapporten omfatter også siden Oplæringsoplysninger, der minder om siderne for andre modeltyper, som beskrevet i afsnittet **AutoML-modelrapport** tidligere i denne artikel.

### <a name="applying-a-classification-model"></a>Anvendelse af en klassificeringsmodel

Hvis du vil anvende en klassificerings-ML-model, skal du angive inputdata for enheden og præfikset for outputkolonnens navn.

Når der anvendes en klassificeringsmodel, føjes der tre outputkolonner til den forbedrede outputenhed. Det er **PredictionScore**, **PredictionClass** og **PredictionExplanation**. Der angives et præfiks for kolonnenavnene i enheden, når modellen anvendes.

Kolonnen **PredictionClass** indeholder den mest forudsigende klasse for posten. Kolonnen **PredictionScore** indeholder listen over sandsynlighedsscores for posten for hver af de mulige klasser.

Kolonnen **PredictionExplanation** indeholder en forklaring af den bestemte indvirkning, som inputfunktionerne havde på **PredictionScore**. Dette er en JSON-formateret samling af vægtninger for forudsigelsens inputfunktioner.

## <a name="regression-models"></a>Regressionsmodeller

Regressionsmodeller bruges til at forudsige en værdi, f.eks. den omsætning, der sandsynligvis realiseres fra en salgsaftale, en kundes værdi over tid, beløbet for en faktura, der sandsynligvis bliver betalt, den dato, hvor en faktura muligvis betales osv.

Outputtet for en regressionsmodel er den forudsagte værdi.

### <a name="training-a-regression-model"></a>Oplæring af en regressionsmodel

Den inputenhed, der indeholder dine oplæringsdata for en regressionsmodel, skal have et numerisk felt som det historiske resultatfelt, der identificerer de tidligere kendte værdier.

Forudsætninger:

* Der kræves mindst 100 rækker historiske data for en regressionsmodel.

Oprettelsesprocessen for en regressionsmodel følger de samme trin som andre AutoML-modeller, der er beskrevet i afsnittet **Konfiguration af ML-modelinput** ovenfor.

### <a name="regression-model-report"></a>Regressionsmodelrapport

På samme måde som med andre AutoML-modelrapporter er regressionsrapporten baseret på resultaterne fra anvendelsen af modellen på testdata.

Modelrapporten indeholder et diagram, der sammenligner de forudsagte værdier med den faktiske værdi. I dette diagram angiver afstanden fra diagonalen fejlen i forudsigelsen.

Diagrammet over residualfejl viser fordelingen af procentdelen for gennemsnitlige fejl for forskellige værdier i testdatasættet. Den vandrette akse repræsenterer gennemsnittet af den faktiske værdi for gruppen, hvor størrelsen af boblen viser frekvensen eller antallet af værdier inden for det pågældende område. Den lodrette akse er de gennemsnitlige residualfejl.

![Diagram over residualfejl](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

Regressionsmodelrapporten omfatter også siden Oplæringsdetaljer, der minder om siderne for andre modeltyper, som beskrevet i afsnittet **AutoML-modelrapport** ovenfor.

### <a name="applying-a-regression-model"></a>Anvendelse af en regressionsmodel

Hvis du vil anvende en regressions-ML-model, skal du angive inputdata for enheden og præfikset for outputkolonnens navn.

![Anvend en regression](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

Når der anvendes en regressionsmodel, føjes der to outputkolonner til den forbedrede outputenhed. Nemlig **PredictionValue** og **PredictionExplanation**. Der angives et præfiks for kolonnenavnene i enheden, når modellen anvendes.

Kolonnen **PredictionValue** indeholder den forudsagte værdi for den post, der er baseret på inputfelterne. Kolonnen **PredictionExplanation** indeholder en forklaring af den bestemte indvirkning, som inputfunktionerne havde på **PredictionValue**. Dette er en JSON-formateret samling af vægtninger af inputfunktionerne.

## <a name="next-steps"></a>Næste trin

Denne artikel indeholder en oversigt over automatiseret maskinel indlæring til dataflows i Power BI-tjenesten. Følgende artikler kan også være nyttige.

* [Selvstudium: Byg en model til maskinel indlæring med Power BI (prøveversion)](service-tutorial-build-machine-learning-model.md)
* [Selvstudium: Brug af Cognitive Services i Power BI](service-tutorial-use-cognitive-services.md)
* [Selvstudium: Aktivér en Machine Learning Studio-model i Power BI (prøveversion)](service-tutorial-invoke-machine-learning-model.md)
* [Cognitive Services i Power BI (prøveversion)](service-cognitive-services.md)
* [Azure Machine Learning-integration i Power BI (prøveversion)](service-machine-learning-integration.md)

Du kan få flere oplysninger om dataflow i disse artikler:
* [Opret og brug dataflow i Power BI](service-dataflows-create-use.md)
* [Brug af beregnede objekter i Power BI Premium](service-dataflows-computed-entities-premium.md)
* [Brug af dataflow med datakilder i det lokale miljø](service-dataflows-on-premises-gateways.md)
* [Udviklerressourcer til Power BI-dataflow](service-dataflows-developer-resources.md)
* [Integration af dataflow og Azure Data Lake (prøveversion)](service-dataflows-azure-data-lake-integration.md)


