---
title: 'Selvstudium: Byg en model til maskinel indlæring med Power BI (prøveversion)'
description: I dette selvstudium skal du bygge en model til maskinel indlæring i Power BI.
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
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61406579"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Selvstudium: Byg en model til maskinel indlæring med Power BI (prøveversion)

I denne artikel i dette selvstudium skal du bruge **automatiseret maskinel indlæring** til at oprette og anvende en binær forudsigelsesmodel i Power BI. Selvstudiet indeholder en vejledning i, hvordan du opretter et dataflow i Power BI og bruger de enheder, der er defineret i dataflowet, til at oplære og validere en model til maskinel indlæring direkte i Power BI. Derefter bruger vi denne model til at tildele point for at generere forudsigelser.

Først skal du oprette en binær forudsigelsesmodel til maskinel indlæring for at forudsige købshensigten hos onlineshoppere på baggrund af attributterne for deres onlinesession. Vi benytter et benchmarkdatasæt til maskinel indlæring til denne øvelse. Når en model er oplært, opretter Power BI automatisk en valideringsrapport, der forklarer resultaterne af modellen. Du kan derefter gennemgå valideringsrapporten og anvende modellen på dine data for at tildele point.

Dette selvstudium består af følgende trin:

> [!div class="checklist"]
> * Opret et dataflow med inputdataene
> * Opret og oplær en model til maskinel indlæring
> * Gennemse modelvalideringsrapporten
> * Anvend modellen på en dataflowenhed
> * Brug af resultatet fra modellen i en Power BI-rapport

## <a name="create-a-dataflow-with-the-input-data"></a>Opret et dataflow med inputdataene

Den første del af dette selvstudium består i at oprette et dataflow med inputdata. Denne proces involverer nogle få trin, som vist i følgende afsnit, og begynder med hentning af data.

### <a name="get-data"></a>Hent data

Det første trin i oprettelsen af et dataflow er at gøre dine datakilder klar. I vores tilfælde bruger vi et datasæt til maskinel indlæring fra et sæt onlinesessioner, hvoraf nogle af dem resulterede i et køb. Datasættet indeholder et sæt attributter om disse sessioner, som vi bruger til oplæring af vores model.

Du kan downloade datasættet fra UC Irvine-webstedet.  Til dette selvstudium har vi også adgang til denne fil fra følgende link: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Opret enhederne

Log på Power BI-tjenesten for at oprette enhederne i dit dataflow, og gå til et arbejdsområde i den dedikerede kapacitet, som AI-prøveversionen er aktiveret for.

Hvis du ikke allerede har et arbejdsområde, kan du oprette et ved at vælge **Arbejdsområder** i menuen til venstre i Power BI-tjenesten og derefter vælge **Opret apparbejdsområde** nederst i det panel, der vises. Herefter åbnes et panel til højre, hvor du kan angive oplysninger om arbejdsområdet. Skriv et navn til arbejdsområdet, og vælg derefter **Avanceret**. Bekræft, at arbejdsområdet bruger dedikeret kapacitet, ved hjælp af alternativknappen, og at det er tildelt til en forekomst af dedikeret kapacitet, hvor AI Preview er slået til. Vælg derefter **Gem**.

![Opret et arbejdsområde](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Når arbejdsområdet er blevet oprettet, kan du vælge **Spring over** nederst til højre på velkomstskærmen, som vist på følgende billede.

![Spring over, hvis du har et arbejdsområde](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

Vælg fanen **Dataflow (forhåndsvisning)** . Vælg knappen **Opret** øverst til højre i arbejdsområdet, og vælg derefter **Dataflow**.

![Opret dataflow](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

Vælg **Tilføj nye enheder**. Dette starter en **Power-forespørgselseditor** i browseren.

![Tilføj ny enhed](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Vælg **Tekst/CSV-fil** som en datakilde, som vist på følgende billede.

![Tekst/CSV-fil er valgt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

I **Opret forbindelse til en datakilde**, der vises herefter, skal du indsætte følgende link til *online_shoppers_intention.csv* i feltet **Filsti eller URL-adresse** og derefter vælge  **Næste**.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Filsti](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

I Power-forespørgselseditor vises et eksempel på dataene fra CSV-filen. Vælg **Transformér tabel** på kommandobåndet, og vælg derefter **Brug den første række som overskrifter** i den menu, der vises. Herefter føjes forespørgselstrinnet _Fremhævede overskrifter_ til afsnittet **Anvendte trin** til højre på skærmen. Du kan omdøbe forespørgslen til et mere brugervenligt navn ved at ændre værdien i feltet **Navn** i ruden til højre. Du kan f.eks. ændre navnet på forespørgslen til _Onlinebesøgende_.

![Skift til et brugervenligt navn](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Nogle af attributdatatyperne i dette datasæt er _numeriske_ eller _booleske_, selvom de kan fortolkes som strenge af **Power Query**. Vælg attributtypeikonet øverst i hver kolonneoverskrift for at ændre de kolonner, der er angivet nedenfor, til følgende typer:

* **Decimaltal:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **Sand/falsk:** Weekend; Revenue

![Skift datatype](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

Den **binære forudsigelsesmodel**, som vi vil oplære, kræver et boolesk felt som et mærkat, der identificerer resultaterne fra de tidligere observationer. I dette datasæt indikerer attributten _Revenue_ køb, og denne attribut er allerede tilgængelig som en boolesk værdi. Vi behøver derfor ikke at tilføje en beregnet kolonne for mærkatet. I andre datasæt kan du blive nødt til at transformere eksisterende mærkatattributter til en boolesk kolonne.

Vælg knappen **Udført** for at lukke Power-forespørgselseditor. Dette viser listen over enheder med de data for _Onlinebesøgende_, som vi har tilføjet. Vælg **Gem** i øverste højre hjørne, angiv et navn til dataflowet, og vælg derefter **Gem** i dialogboksen, som vist på følgende billede.

![Gem dataflowet](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Opdater dataflowet

Hvis du gemmer dataflowet, resulterer det i, at en meddelelse, som angiver, at dataflowet er blevet gemt, vises. Vælg **Opdater nu** for at overføre data fra kilden til dataflowet.

![Opdater nu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Vælg **Luk** i øverste højre hjørne, og vent, indtil opdateringen af dataflowet er blevet fuldført.

Du kan også opdatere dataflowet ved hjælp af kommandoen **Handlinger**. I dataflowet vises et tidsstempel for, hvornår opdateringen blev fuldført.

![Tidsstempel for opdatering](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Opret og oplær en model til maskinel indlæring

Vælg dataflowet, når opdateringen er fuldført. Hvis du vil tilføje en model til maskinel indlæring, skal du bruge knappen **Anvend ML-model** på listen **Handlinger** for den basisenhed, der indeholder dine oplæringsdata og mærkatoplysninger, og derefter vælge **Tilføj en model til maskinel indlæring**.

![Tilføj en model til maskinel indlæring](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Det første trin til oprettelse af vores model til maskinel indlæring er at identificere de historiske data, herunder det mærkatfelt, som du vil forudsige. Modellen vil blive oprettet ved at lære fra disse data.

I forbindelse med det datasæt, som vi benytter, er dette felt **Revenue**. Vælg **Revenue** som værdien for feltet med det historiske resultat, og vælg derefter **Næste**.

![Vælg historiske data](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Derefter skal du vælge den type model til maskinel indlæring, der skal oprettes. Power BI analyserer værdierne i det historiske resultatfelt, som du har identificeret, og foreslår de typer modeller til maskinel indlæring, der kan oprettes for at forudsige dette felt.

Da vi i dette tilfælde forudsiger et binært udfald af, om en bruger vil foretage et køb eller ej, skal du vælge **Binær forudsigelse** som modeltype og derefter vælge Næste.

![Binær forudsigelse er valgt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Derefter foretager Power BI en foreløbig scanning af dataene og foreslår de input, som modellen kan bruge. Du har mulighed for at tilpasse de inputfelter, der bruges til modellen. I vores organiserede datasæt skal du markere afkrydsningsfeltet ud for enhedens navn for at markere alle felterne. Vælg **Næste** for at acceptere inputtene.

![Vælg Næste](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

I det sidste trin skal du give modellen et navn samt brugervenlige mærkater for de resultater, der skal benyttes i den rapport, der automatisk genereres, og som opsummerer resultaterne af modelvalideringen. Derefter skal du navngive modellen _Purchase Intent Prediction_ og mærkaterne for True og False til henholdsvis _Køb_ og _Intet køb_. Vælg derefter **Gem**.

![Gem modellen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Vores model til maskinel indlæring er nu klar til oplæring. Vælg **Opdater nu** for at begynde at oplære modellen.

![Opdater nu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Oplæringsprocessen starter med at indsamle og normalisere dine historiske data og opdele dit datasæt i to nye enheder *Purchase Intent Prediction Training Data* og *Purchase Intent Prediction Testing Data*.

Afhængigt af datasættets størrelse kan oplæringen tage alt fra nogle få minutter til et par timer. På dette tidspunkt kan du se modellen på fanen **Modeller til maskinel indlæring** i dataflowet. Statussen _Klar_ angiver, at modellen er sat i kø til oplæring eller er under oplæring.

![Klar til oplæring](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Mens modellen oplæres, kan du hverken få vist eller redigere dataflowet. Du kan få bekræftet, at modellen oplæres og valideres, gennem dataflowets status. Dette vises som en igangværende dataopdatering på fanen **Dataflows** i arbejdsområdet.

![Igangværende](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Når oplæringen af modellen er fuldført, viser dataflowet et opdateret opdateringstidspunkt. Du kan få bekræftet, at modellen er oplært, ved at gå til fanen **Modeller til maskinel indlæring** i dataflowet. Den model, du har oprettet, bør have status som **Oplært** og tidspunktet for **Senest oplært** bør nu være opdateret.

![Senest oplært den](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Gennemse modelvalideringsrapporten

Hvis du vil gennemse modelvalideringsrapporten skal du i **Modeller til maskinel indlæring** vælge knappen **Vis performance-rapport, og anvend model** i kolonnen **Handlinger** for modellen. I denne rapport beskrives det, hvordan ydeevnen for din model til maskinel indlæring sandsynligvis vil være.

På siden **Ydeevne af modellen** i rapporten skal du vælge **Nøglefaktorer** for at få vist de vigtigste forudsigelser for din model. Du kan vælge en af forudsigelserne for at få vist fordelingen af det resultat, der er knyttet til den pågældende forudsigelse.

![Ydeevne af modellen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Du kan bruge udsnitsværktøjet **Tærskel for sandsynlighed** på siden Ydeevne af modellen til at undersøge dens indflydelse på præcision og genkaldelse for modellen.

![Tærskel for sandsynlighed](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

De øvrige sider i rapporten beskriver de statistiske ydeevnemålepunkter for modellen.

Rapporten indeholder også siden Oplæringsoplysninger, der beskriver de forskellige gentagelser, der er blevet kørt, hvordan funktionerne blev trukket ud fra inputtet, samt hyperparametrene for den endelige model, der blev anvendt.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Anvend modellen på en dataflowenhed

Vælg knappen **Anvend model** øverst i rapporten for at aktivere denne model, når dataflowet opdateres. I dialogboksen **Anvend** skal du angive den destinationsenhed, der har de kildedata, som modellen skal anvendes for.

![Anvend modellen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

Du skal **opdatere** dataflowet for at få vist et eksempel på resultatet af din model, når du bliver bedt om det.

Hvis du anvender modellen, oprettes en ny enhed med suffikset **enriched <model_name>** , der føjes til den enhed, som du anvendte modellen for. I vores tilfælde vil anvendelse af modellen for enheden **OnlineShoppers** oprette **OnlineShoppers enriched Purchase Intent Prediction**, som omfatter det forudsagte output fra modellen.

Hvis du anvender en binær forudsigelsesmodel, tilføjes der tre kolonner med et forudsagt resultat, en sandsynlighedsscore og de vigtigste nøglefaktorer for forudsigelsen, der hver især har det angivne kolonnenavn som præfiks.

![Tre kolonner med resultater](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

På grund af et kendt problem kan du kun få adgang til outputkolonner med tildelte point i den forbedrede enhed, fra Power BI Desktop. Hvis du vil have vist disse kolonner i tjenesten, skal du bruge en særlig eksempelenhed.

Når dataflowet er blevet opdateret, kan du vælge enheden **OnlineShoppers enriched Purchase Intent Prediction Preview** for at få vist resultaterne.

![Se resultaterne](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Brug af resultatet fra modellen i en Power BI-rapport

Hvis du vil bruge resultatet med tildelte point fra din model til maskinel indlæring, kan du oprette forbindelse til dataflowet fra Power BI Desktop ved hjælp af connectoren Dataflows. Enheden **OnlineShoppers enriched Purchase Intent Prediction** kan nu bruges til at inkorporere forudsigelserne fra din model i Power BI-rapporter.

## <a name="next-steps"></a>Næste trin

I dette selvstudium har du oprettet og anvendt en binær forudsigelsesmodel i Power BI ved hjælp af disse trin:

* Opret et dataflow med inputdataene
* Opret og oplær en model til maskinel indlæring
* Gennemse modelvalideringsrapporten
* Anvend modellen på en dataflowenhed
* Brug af resultatet fra modellen i en Power BI-rapport

Du kan få flere oplysninger om automatiseret maskinel indlæring i Power BI i [Automatiseret maskinel indlæring i Power BI (prøveversion)](service-machine-learning-automated.md).
