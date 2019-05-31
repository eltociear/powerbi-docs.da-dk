---
title: 'Selvstudium: Byg en model til Maskinindlæring i Power BI (prøveversion)'
description: I dette selvstudium kan du oprette en model til Maskinindlæring i Power BI.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/29/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 611d6f6c923e6cb68af94840c4266a0b6dee7651
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61406579"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Selvstudium: Byg en model til Maskinindlæring i Power BI (prøveversion)

I dette selvstudium artikel kan du bruge **automatiseret Machine Learning** til at oprette og anvende en binær forudsigelsesmodel i Power BI. Selvstudiet indeholder vejledning til oprettelse af en Power BI dataflowet og ved hjælp af enhederne, der er defineret i dataflowet til at træne og validere en model til maskinel indlæring direkte i Power BI. Vi bruger derefter denne model for pointsystem til at generere forudsigelser.

Først skal opretter du en binær forudsigelse model til maskinel indlæring, for at forudsige formålet køb med online kunder, der er baseret på et sæt af deres online session attributter. Et benchmark machine learning-datasæt, der bruges i denne opgave. Når en model er oplært, vil Power BI automatisk generere en valideringsrapport, der forklarer model resultaterne. Du kan derefter gennemse Valideringsrapporten og anvende modellen til dine data for scoring.

I dette selvstudium, består af følgende trin:

> [!div class="checklist"]
> * Opret en dataflow med inputdata
> * Opret og træne en model til maskinel indlæring
> * Gennemse rapporten model validering
> * Anvende modellen til en dataflowet enhed
> * Ved hjælp af outputtet fra modellen score i en Power BI-rapport

## <a name="create-a-dataflow-with-the-input-data"></a>Opret en dataflow med inputdata

Den første del af dette selvstudium er at oprette en dataflow med inputdata. Denne proces tager nogle få trin, som vist i følgende afsnit, starter med at hente data.

### <a name="get-data"></a>Hent data

Det første trin i oprettelsen af en dataflowet er at have dine datakilder, der er klar. I dette tilfælde kan vi bruge et machine learning datasæt fra et sæt online-sessioner, hvoraf nogle culminated i et køb. Datasættet indeholder et sæt af attributter om disse sessioner, som vi bruger til oplæring af vores model.

Du kan downloade datasættet fra Irvine UC-webstedet.  Vi har også det tilgængeligt med henblik på dette selvstudium, fra følgende link: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Opret enheder

Log på Power BI-tjenesten for at oprette enhederne i dit dataflow, og gå til et arbejdsområde i den dedikerede kapacitet, som AI-prøveversionen er aktiveret for.

Hvis du ikke allerede har et arbejdsområde, kan du oprette en ved at vælge **arbejdsområder** i navigationsmenuen til venstre i Power BI-tjenesten, og vælg **Opret apparbejdsområde** nederst på panelet, der vises. Dette åbner et panel til højre for at angive oplysninger om arbejdsområde. Angiv et navn til arbejdsområdet, og vælg **Avanceret**. Bekræft, at arbejdsområdet bruger dedikeret kapacitet ved hjælp af knappen radio, og at den er tildelt til en forekomst af dedikeret kapacitet, der har aktiveret prøveversionen AI. Vælg derefter **Gem**.

![Opret et arbejdsområde](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Når arbejdsområdet er oprettet, kan du vælge **Skip** nederst til højre på velkomstskærmen, som vist på følgende billede.

![Spring over, hvis du har et arbejdsområde](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

Vælg den **Dataflows (prøveversion)** fanen. Vælg den **Opret** knappen øverst til højre på arbejdsområdet, og derefter vælge **dataflowet**.

![Opret dataflow](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

Vælg **Tilføj nye enheder**. Dette starter en **Power-forespørgsel** -editoren i browseren.

![Tilføj ny enhed](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Vælg **tekst/CSV-fil** som en datakilde, vist på følgende billede.

![Tekst/CSF-fil, der er valgt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

I den **Opret forbindelse til en datakilde** , der vises, næste, skal du indsætte følgende link til den *online_shoppers_intention.csv* i den **filsti eller URL-adresse** , og vælg derefter  **Næste**.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Filsti](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Power-Forespørgselseditor kan du se en eksempelvisning af data fra csv-filen. Vælg **transformere tabellen** i kommandoen båndet og derefter vælge **Brug den første række som overskrifter** i den menu, der vises. Dette tilføjer den _Promoveres overskrifter_ forespørgselstrin i den **anvendte trin** afsnit i højre side af skærmen. Du kan omdøbe forespørgslen til et pift navn ved at ændre værdien i den **navn** box, der blev fundet i ruden til højre. Du kan f.eks. ændre navnet på forespørgslen til _Online besøgende_.

![Skift til et brugervenligt navn](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Nogle af attributtyperne i data i dette datasæt er _numerisk_ eller _boolesk_, selvom disse kan fortolkes som strenge ved **Power-forespørgsel**. Vælg ikonet attribut type øverst på hver kolonneoverskrift for at ændre de kolonner, der er anført nedenfor til følgende typer:

* **Decimaltal:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **Sand/falsk:** Weekend; Indtægt

![Skift datatype](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

Den **binære forudsigelse** model, vi vil træne kræver et boolesk felt som en etiket, der identificerer resultater fra de tidligere observationer. I dette datasæt, den _indtægt_ attribut angiver køb, og denne attribut er allerede tilgængelig som en boolesk værdi. Så behøver vi ikke at tilføje en beregnet kolonne til etiketten. I andre datasæt, skal du muligvis at transformere eksisterende etiketattributterne til en boolesk kolonne.

Vælg den **udført** knap til at lukke Forespørgselseditor. Dette viser listen over enheder med den _Online besøgende_ data, vi har tilføjet. Vælg **Gem** i øverste højre hjørne, og Angiv et navn til dataflowet, og vælg derefter **Gem** i dialogboksen, som vist på følgende billede.

![Gem dataflowet](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Opdater dataflowet

Lagring af dataflowet resultaterne i en meddelelse, der vises, angiver, at din dataflowet er blevet gemt. Vælg **Opdater nu** til at overføre data fra kilden i dataflowet.

![Opdater nu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Vælg **Luk** i øverste højre hjørne, og vent, indtil opdateringen af dataflowet er blevet fuldført.

Du kan også opdatere din dataflowet ved hjælp af den **handlinger** kommandoer. Tidsstemplet viser dataflowet, når opdateringen er fuldført.

![Tidsstempel for opdatering](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Opret og træne en model til maskinel indlæring

Vælg dataflowet, når opdateringen er fuldført. For at tilføje en machine learning-modellen, skal du vælge den **gælder ML-model** knappen i den **handlinger** listen for den grundlæggende enhed, der indeholder dine data og etiket undervisningsoplysninger, og vælg derefter **Tilføj en Machine learning-modellen**.

![Tilføj en model til maskinel indlæring](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Det første trin til oprettelse af vores machine learning-modellen er at identificere de historiske data, herunder feltet etiket, der skal til at forudsige. Modellen oprettes ved at lære på baggrund af disse data.

Hvis vi bruger datasættet, dette er den **indtægt** felt. Vælg **indtægt** som ' historiske resultatet ' feltværdien og derefter vælge **næste**.

![Vælg historiske data](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Derefter skal vi vælge typen af machine learning-modellen til at oprette. Powerbi analyserer værdierne i feltet historiske resultatet, som du har identificeret og foreslår, hvilke typer af modeller til maskinel indlæring, der kan oprettes for at forudsige dette felt.

I dette tilfælde, da vi er ved at forudsige en binær resultatet af om en bruger vil gøre et køb eller ej, vælger **binære forudsigelse** for modeltype og derefter vælge Næste.

![Binær forudsigelse, der er valgt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Derefter skal Power BI har en foreløbig scanning af dataene og foreslår input, som kunne bruge modellen. Du har mulighed for at tilpasse felterne input, der bruges til modellen. I vores organiserede datasæt, for at vælge felterne, markere afkrydsningsfeltet ud for enhedsnavnet på. Vælg **næste** til at acceptere input.

![Skal du markere afkrydsningsfeltet Næste](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

Vi skal angive et navn til vores model samt brugervenlige etiketterne til de resultater, der skal bruges i den automatisk oprettede rapport, der opsummerer resultaterne af valideringen modellen i det sidste trin. Næste vi nødt til at navngive modellen _køb hensigt forudsigelse_, og de etiketter, true og false som _køb_ og _Nej-køb_. Vælg derefter **Gem**.

![Gem modellen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Vores machine learning-modellen er nu klar til undervisning. Vælg **Opdater nu** til at starte oplæring af modellen.

![Opdater nu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Starter uddannelsesprocessen af med høj tæthed og normalisering af dine historiske data og opdele dit datasæt i to nye enheder *køb hensigt forudsigelse Træningsdata* og *køb hensigt forudsigelse test Data*.

Afhængigt af størrelsen på datasættet, kan uddannelsesprocessen tage alt fra nogle få minutter til et par timer. På dette tidspunkt kan du se modellen i det **modeller til maskinel indlæring** fanen i dataflowet. Den _klar_ status, der angiver, at modellen er sat i kø til uddannelse eller er under uddannelse.

![Klar til uddannelse](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Mens modellen er uddannelse, kan du ikke kan få vist eller redigere dataflowet. Du kan bekræfte, at modellen er ved at blive oplært og godkendt via status for dataflowet. Det ser ud som en opdatering af data i gang i den **Dataflows** fane i arbejdsområdet.

![Igangværende](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Når modelundervisning er fuldført, viser dataflowet en opdaterede opdateringstidspunkt. Du kan bekræfte, at modellen er oplært ved at navigere til den **modeller til maskinel indlæring** fane i dataflowet. Du har oprettet modellen skal vise status som **Trained** og **sidste uddannet** tid nu skal opdateres.

![Sidst trænet i](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Gennemse rapporten model validering

Til at gennemse model validering af rapporten, i den **modeller til maskinel indlæring, s** vælger den **Vis rapport resultater og anvende modellen** knappen i den **handlinger** kolonne til modellen . Denne rapport beskriver, hvordan din machine learning-modellen er sandsynligvis til at udføre.

I den **Modelydeevnen** side i rapporten, vælge **nøgle Lobbyister** til at få vist de øverste indikatorer data til din model. Du kan vælge en af indikatorer data for at se, hvordan resultatet fordelingen er knyttet til denne indikator.

![Model-ydeevne](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Du kan bruge den **sandsynlighed tærskel** udsnit på siden Modelydeevnen for at undersøge dens indflydelse på præcision og tilbagekaldelse til modellen.

![Tærskel for sandsynlighed](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

Andre sider i rapporten beskrive den statistiske præstation til modellen.

Rapporten indeholder også en siden med oplysninger om træning, som beskriver de forskellige gentagelser, der blev kørt, hvordan funktioner blev hentet fra input og hyperparameters for den endelige model, der bruges.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Anvende modellen til en dataflowet enhed

Vælg den **Anvend model** knappen øverst i rapporten for at aktivere denne model, når dataflowet opdateres. I den **Anvend** dialogboksen, kan du angive målenheden, der har som modellen skal anvendes i kildedataene.

![Anvend modellen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

Når du bliver spurgt, skal du **Opdater** dataflowet til at få vist resultaterne af din model.

Anvendelse af modellen opretter en ny enhed med suffikset **beriget < modelnavn >** føjes til den enhed, hvor du har anvendt modellen. Anvendelse af modellen til i dette tilfælde den **OnlineShoppers** enhed opretter **OnlineShoppers beriget køb hensigt forudsigelse**, som indeholder de forudsagte output fra modellen.

Anvendelse af en binær forudsigelsesmodel føjer tre kolonner med forudsagt resultatet, sandsynlighedsscore og de øverste post-specifikke lobbyister for forudsigelse, hver indledes med det angivne kolonnenavn.

![Tre kolonner i resultatet](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

På grund af et kendt problem der score output kolonnerne i den enhed, der er beriget kun kan tilgås fra Power BI Desktop. Hvis du vil se dem i tjenesten, skal du bruge et særlig forhåndsvisning objekt.

Når dataflowet opdateringen er fuldført, kan du vælge den **OnlineShoppers beriget køb hensigt forudsigelse prøveversion** enheden for at få vist resultaterne.

![Få vist resultaterne](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Ved hjælp af outputtet fra modellen score i en Power BI-rapport

Hvis du vil bruge score outputtet fra din model til maskinel indlæring, du kan oprette forbindelse til din dataflowet fra Power BI desktop, ved hjælp af Dataflows connector. Den **OnlineShoppers beriget køb hensigt forudsigelse** enhed kan nu bruges til at inkorporere til forudsigelse af din model i Power BI-rapporter.

## <a name="next-steps"></a>Næste trin

I dette selvstudium kan du har oprettet og anvendes en binær forudsigelsesmodel i Power BI ved hjælp af disse trin:

* Opret en dataflow med inputdata
* Opret og træne en model til maskinel indlæring
* Gennemse rapporten model validering
* Anvende modellen til en dataflowet enhed
* Ved hjælp af outputtet fra modellen score i en Power BI-rapport

Du kan finde flere oplysninger om Machine Learning automation i Power BI i [automatiseret Machine Learning i Power BI (prøveversion)](service-machine-learning-automated.md).
