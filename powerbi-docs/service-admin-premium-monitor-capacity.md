---
title: Overvåg Power BI Premium-kapaciteter i din organisation
description: Brug Power BI-administrationsportalen og Power BI Premium-appen Capacity Metrics
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/06/2018
LocalizationGroup: Premium
ms.openlocfilehash: 4fc036bf9191d0ed56be11e69152e579cfc5102d
ms.sourcegitcommit: 883d7e76816f2696e88ae391744ac6c7b1cb59c7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2018
ms.locfileid: "51688390"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Overvåg kapaciteter i Power BI Premium og Power BI Embedded

Denne artikel indeholder en oversigt over overvågning af målepunkter for dine Power BI Premium-kapaciteter. Ved at overvåge kapacitetsforbrug kan du træffe mere velovervejede beslutninger, når du administrerer dine kapaciteter.

Du kan overvåge kapacitet med Power BI Premium-appen Capacity Metrics eller i administrationsportalen. Vi anbefaler appen, fordi den giver mange flere detaljer, men i denne artikel beskrives begge muligheder.

**Den aktuelle version af appen er 1.9 (udgivet den 14. november 2018).**

.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UgsjMbhi_Bk?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="install-the-premium-capacity-metrics-app"></a>Installér Premium-appen Capacity Metrics

Du kan gå direkte til [Premium-appen Capacity Metrics](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) eller installere den, som du plejer med andre apps i Power BI.

1. I Power BI skal du klikke på **Apps**.

    ![Gå til Apps](media/service-admin-premium-monitor-capacity/apps.png)

1. I højre side skal du klikke på **Hent apps**.

1. I kategorien **Apps** skal du søge efter **Power BI-appen Capacity Metrics**.

1. Abonner for at installere appen.

Nu, hvor du har installeret appen, kan du se målepunkter for kapaciteterne i din organisation. Lad os se nærmere på nogle af de vigtigste målepunkter, der er tilgængelige.

## <a name="use-the-metrics-app"></a>Brug målepunktsappen

Når du åbner appen, viser den først et dashboard med en oversigt over alle de kapaciteter, som du har administratorrettigheder til.

![Appdashboardet Målepunkter](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Klik på dashboardet for at gå til den underliggende rapport. Rapporten indeholder seks faner, der beskrives mere detaljeret i følgende afsnit.

* **Filtre**: Gør det muligt at filtrere de andre sider i rapporten til en bestemt kapacitet.

* **Datasæt**: Giver detaljerede målepunkter for tilstanden for Power BI-datasættene i dine kapaciteter.

* **Sideinddelte rapporter**: Giver detaljerede målepunkter for tilstanden for sideinddelte rapporter i dine kapaciteter.

* **Dataflow**: Giver detaljerede opdateringsmålepunkter for dataflow i dine kapaciteter.

* **System**: Giver overordnede kapacitetsmålepunkter, herunder hukommelse og højt CPU-forbrug.

* **Viste navne og id'er**: Giver navne, id'er og ejere for kapaciteter, arbejdsområder og arbejdsbelastninger.

### <a name="filters-tab"></a>Fanen Filtre

Fanen **Filtre** gør det muligt at vælge en kapacitet, et datointerval og andre indstillinger. Filtrene anvendes derefter på alle de relevante sider og felter i rapporten. Hvis der ikke er markeret nogen filtre, viser rapporten som standard målepunkter for den seneste uge for hver kapacitet, du ejer.

![Fanen Filtre](media/service-admin-premium-monitor-capacity/filters-tab.png)

* **(A)**  Vælg **Datasæt**, **Sideinddelte rapporter** eller **Dataflow** for at angive filtre for hver enkelt arbejdsbelastning.

* **(B)**  Navn og **(C)** oplysninger opdateres baseret på det, du vælger i **(A)**, så du kan filtrere på en arbejdsbelastning efter navn. På billedet ovenfor, er **Dataflow** f.eks. valgt, og **Dataflownavn** og **Dataflowoplysninger** vises.

* **(D)** Kapacitetsoplysninger, der indikerer, om datasæt, sideinddelte rapporter eller dataflow er aktiveret for en kapacitet.

### <a name="datasets-tab"></a>Fanen Datasæt

Brug knapperne øverst på fanen **Datasæt** til at gå til forskellige områder: **Oversigt**, **Opdateringer**, **Forespørgselsvarigheder**, **Forespørgselsventetider** og **Datasæt**.

![Fanen Datasæt](media/service-admin-premium-monitor-capacity/datasets-tab.png)

#### <a name="summary-area"></a>Området Oversigt

I området **Oversigt** kan du få et overblik over dine kapaciteter på basis af entiteter, systemressourcer og arbejdsbelastninger for datasæt. Det viser følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Objekter** | * Antallet af kapaciteter, som du ejer<br> * Det specifikke antal datasæt i din kapacitet<br> * Det specifikke antal arbejdsområder i din kapacitet |
| **System** | * Det gennemsnitlige hukommelsesforbrug i GB over de seneste syv dage<br> * Højeste hukommelsesforbrug i GB i løbet af de seneste syv dage og den lokale tid, forbruget opstod<br> * Det antal gange, CPU'en har overskredet 80 % af tærsklerne i løbet af de seneste syv dage opdelt i buckets på tre minutter<br> * De fleste gange, CPU'en har overskredet 80 % i løbet af de seneste syv dage opdelt i buckets på én time og den lokale tid, det opstod<br> * Det antal gange, forbindelser via direkte forespørgsler/direkte forbindelser har overskredet 80 % af tærsklerne i løbet af de seneste syv dage opdelt i buckets på tre minutter<br> * De fleste gange, forbindelser via direkte forespørgsler/direkte forbindelser har overskredet 80 % i løbet af de seneste syv dage opdelt i buckets på én time og den lokale tid, det opstod |
| **Arbejdsbelastninger for datasæt** | * Det samlede antal opdateringer i løbet af de seneste syv dage<br> * Det samlede antal vellykkede opdateringer i løbet af de seneste syv dage<br> * Det samlede antal mislykkede opdateringer i løbet af de seneste syv dage<br> * Det samlede antal mislykkede opdateringer, der skyldes manglende hukommelse<br> * Den gennemsnitlige opdateringsvarighed er den tid, det tager at udføre handlingen i minutter<br> * Den gennemsnitlige opdateringsventetid er den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starten af handlingen i minutter<br> * Det samlede antal forespørgsler, der er kørt i løbet af de seneste syv dage<br> * Det samlede antal vellykkede forespørgsler i løbet af de seneste syv dage<br> * Det samlede antal mislykkede forespørgsler i løbet af de seneste syv dage<br> * Den gennemsnitlige forespørgselsvarighed er den tid, det tager at udføre handlingen i minutter<br> * Det samlede antal modeller, der fjernes på grund af for stort hukommelsesforbrug<br> * Den gennemsnitlige størrelse af datasæt <br> * Det gennemsnitlige antal datasæt, der indlæses i hukommelsen |
|  |  |

#### <a name="refreshes-area"></a>Området Opdateringer

Området **Opdateringer** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Opdateringspålidelighed** | * Samlet antal: Det samlede opdateringer for hvert datasæt<br> * Pålidelighed: Den fuldførte opdateringsandel for hvert enkelt datasæt i procent<br> * Gennemsnitlig ventetid: Den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starten af en opdatering af datasættet i minutter<br> * Maksimal ventetid: Den maksimale ventetid for datasættet i minutter <br> * Gennemsnitlig varighed: Den gennemsnitlige opdateringsvarighed for datasættet i minutter<br> * Maksimal varighed: Varigheden af den længstvarende opdatering af datasættet i minutter |
| **Top 5-datasæt efter Gennemsnitlig opdateringsvarighed** | * De fem datasæt med den længstvarende gennemsnitlige opdateringsvarighed i minutter |
| **Top 5 datasæt efter Gennemsnitlig ventetid** | * De fem datasæt med den længstvarende gennemsnitlige opdateringsventetid i minutter |
| **Gennemsnitlige opdateringsventetider pr. time** | * Den gennemsnitlige opdateringsventetid opdelt i 1-times buckets, rapporteret i lokaltid. Flere tilfælde af høje opdateringsventetider kan være tegn på, at kapaciteten snart er brugt op. |
| **Opdateringsantal og hukommelsesforbrug pr. time** | * Succeser, fejl og hukommelsesforbrug opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

#### <a name="query-durations-area"></a>Område for forespørgselsvarigheder

Området **Forespørgselsvarigheder** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Forespørgselsvarigheder** | * Data i dette afsnit er opdelt i udsnit efter datasæt, arbejdsområde og buckets pr. time for de seneste syv dage<br> * I alt: Det samlede antal forespørgsler, der er kørt i forbindelse med datasættet<br> * Gennemsnit: Den gennemsnitlige forespørgselsvarighed for datasættet i millisekunder<br> * Maksimum: Varigheden af den længstkørende forespørgsel i datasættet i millisekunder|
| **Distribution af forespørgselsvarighed** | * Histogrammet med forespørgselsvarighed er inddelt i buckets efter forespørgselsvarigheder (i millisekunder) i følgende kategorier: intervaller af < = 30 ms, 30-100 ms, 100-300 ms, 300 ms-1 sek., 1-3 sek., 3-10 sek., 10-30 sek. og > 30 sek. Lange forespørgselsvarigheder og lange ventetider betyder, at kapaciteten er overbelastet. Det kan også betyde, at et enkelt datasæt forårsager problemer, og at der er behov for yderligere undersøgelser. |
| **Top 5-datasæt efter Gennemsnitlig varighed** | * De fem datasæt med den længstvarende gennemsnitlige forespørgselsvarighed i millisekunder |
| **Direkte forespørgsel/liveforbindelser (> 80 % udnyttelse)** | * De gange, en direkte forespørgsel eller liveforbindelse har overskredet CPU-udnyttelsen på 80 % opdelt i 1-times buckets, rapporteret i lokaltid |
| **Distributioner af forespørgselsvarighed pr. time** | * Antallet af forespørgsler og gennemsnitlig varighed (i millisekunder) vs. hukommelsesforbrug i GB opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

#### <a name="query-waits-area"></a>Område for ventetider for forespørgsler

Området **Forespørgselsventetider** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Forespørgselsventetider** | * Data i dette afsnit er opdelt i udsnit efter datasæt, arbejdsområde og buckets pr. time for de seneste syv dage<br> * I alt: Det samlede antal forespørgsler, der er kørt i forbindelse med datasættet<br> * Antal forespørgselsventetider: Antallet af forespørgsler i datasættet, der har ventet på systemressourcer, inden de blev udført <br> * Gennemsnit: Den gennemsnitlige forespørgselsventetid for datasættet i millisekunder<br> * Maksimum: Varigheden af den længstventende forespørgsel i datasættet i millisekunder|
| **Distribution af ventetid** | * Histogrammet med forespørgselsvarighed er inddelt i buckets efter forespørgselsvarigheder (i millisekunder) i følgende kategorier: intervaller af <= 50 ms, 50-100 ms, 100-200 ms, 200-400 ms, 400 ms-1 sek., 1-5 sek. og > 5 sek. |
| **Top 5 datasæt efter Gennemsnitlig ventetid** | * De fem datasæt med den længste gennemsnitlige ventetid inden udførelsen af en forespørgsel i millisekunder |
| **Antal forespørgselsventetider og tidspunkter pr. time** | * Antal forespørgsler og den gennemsnitlige ventetid (i millisekunder) vs. hukommelsesforbrug i GB, opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

#### <a name="datasets-area"></a>Området Datasæt

Området **Datasæt** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Antal datasætfjernelser** | * I alt: Det samlede antal datasæt*fjernelser* for hver enkelt kapacitet. Når en kapacitet står over for øget hukommelsesforbrug, fjerner noden et eller flere datasæt fra hukommelsen. Datasæt, der er inaktive (uden forespørgsels-/opdateringshandlinger, der udføres i øjeblikket), ryddes først. Derefter er fjernelsesrækkefølgen baseret på en måling af 'mindst brugt for nylig'.|
| **Datasætfjernelser og hukommelsesforbrug pr. time** | * Datasætfjernelser i forhold til hukommelsesforbrug i GB opdelt i 1-times buckets, rapporteret i lokaltid |
| **Antal indlæste datasæt pr. time** | * Antal datasæt, der er indlæst i hukommelsen i forhold til hukommelsesforbrug i GB opdelt i 1-times buckets, rapporteret i lokaltid |
| **Datastørrelser**  | * Maksimumstørrelse: den maksimale størrelse på datasættet i MB for den viste periode |
|  |  |

### <a name="paginated-reports-tab"></a>Fanen Sideinddelte rapporter

Fanen **Sideinddelte rapporter** viser detaljerede målepunkter for tilstanden for sideinddelte rapporter i dine kapaciteter.

![Fanen Sideinddelte rapporter](media/service-admin-premium-monitor-capacity/paginated-reports-tab.png)

Fanen **Sideinddelte rapporter** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Samlet forbrug** | * Samlet antal visninger: Antallet af gange, som rapporten er blevet set af en bruger<br> * Rækkeantal: Antallet af rækker med data i rapporten<br> * Hentning (gns.): Den gennemsnitlige mængde tid, det tager for at hente data til rapporten i millisekunder. Lange varigheder kan være et tegn på langsomme forespørgsler eller andre datakildeproblemer. <br> * Behandling (gns.): Den gennemsnitlige mængde tid, det tager at behandle dataene til en rapport i millisekunder<br>* Gengivelse (gns.): Den gennemsnitlige mængde tid, det tager at gengive en rapport i en browser i millisekunder<br> * Tid i alt: Den mængde tid, det tager at gennemgå alle faserne i rapporten i millisekunder|
| **Top 5-rapporter efter Gennemsnitlig datahentningstid** | * De fem rapporter med den længste gennemsnitlige datahentningstid i millisekunder |
| **Top 5-rapporter efter Gennemsnitlig rapportbehandlingstid** | * De fem rapporter med den længste gennemsnitlige rapportbehandlingstid i millisekunder |
| **Varigheder pr. time** | * Datahentning i forhold til behandlings- og gengivelsestid opdelt i 1-times buckets, rapporteret i lokaltid |
| **Resultater pr. time** | * Succeser, fejl og hukommelsesforbrug opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

### <a name="dataflows-tab"></a>Fanen Dataflow

Fanen **Dataflow** viser detaljerede opdateringsmålepunkter for dataflow i dine kapaciteter.

![Fanen Dataflow](media/service-admin-premium-monitor-capacity/dataflows-tab.png)

Fanen **Dataflow** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Opdatering** | * I alt: Det samlede antal opdateringer for hvert dataflow<br> * Pålidelighed: Den fuldførte opdateringsandel for hvert enkelt dataflow i procent<br> * Gennemsnitlig ventetid: Den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starten af en opdatering af dataflowet i minutter<br> * Maksimal ventetid: Den maksimale ventetid for dataflowet i minutter <br> * Gennemsnitlig varighed: Den gennemsnitlige opdateringsvarighed for dataflowet i minutter<br> * Maksimal varighed: Varigheden af den længstvarende opdatering af dataflowet i minutter |
| **Top 5-dataflow efter Gennemsnitlig opdateringsvarighed** | * De fem dataflow med den længstvarende gennemsnitlige opdateringsvarighed i minutter |
| **Top 5-dataflow efter Gennemsnitlig ventetid** | * De fem dataflow med den længstvarende gennemsnitlige opdateringsventetid i minutter |
| **Gennemsnitlige opdateringsventetider pr. time** | * Den gennemsnitlige opdateringsventetid opdelt i 1-times buckets, rapporteret i lokaltid. Flere tilfælde af høje opdateringsventetider kan være tegn på, at kapaciteten snart er brugt op. |
| **Opdateringsantal og hukommelsesforbrug pr. time** | * Succeser, fejl og hukommelsesforbrug opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

### <a name="system-tab"></a>Fanen System

Fanen **System** viser CPU- og hukommelsesforbruget for alle kapaciteter og arbejdsbelastninger.

![Fanen System](media/service-admin-premium-monitor-capacity/system-tab.png)

Fanen **System** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **CPU-målepunkter (> 80 % udnyttelse)** | * Det antal gange, CPU'en har overskredet 80 % af tærsklerne i løbet af de seneste syv dage opdelt i buckets på tre minutter |
| **Hukommelsesforbrug** | * Hukommelsesforbrug i de seneste syv dage opdelt i 3-minutters buckets |
|  |  |

### <a name="display-names-and-ids-tab"></a>Fanen Viste navne og id'er

Fanen **Viste navne og id'er** indeholder navne, id'er og ejere for kapaciteter, arbejdsområder og arbejdsbelastninger.

## <a name="monitor-power-bi-embedded-capacity"></a>Overvåg Power BI Embedded-kapacitet

Du kan også bruge Power BI Premium-appen Capacity Metrics til at overvåge *A SKU*-kapaciteter i Power BI Embedded. Disse kapaciteter vises i rapporten, hvis du er administrator af kapaciteten. Men opdatering af rapporten mislykkes, medmindre du tildeler visse tilladelser til Power BI på dine A SKU'er:

1. Åbn din kapacitet på Azure-portalen.

1. Klik på **Adgangskontrol (IAM)**, og føj appen "Power BI Premium" til læserrollen. Hvis du ikke kan finde appen ved hjælp af navnet, du kan også tilføje den ved hjælp af klient-id'et: cb4dc29f-0bf4-402a-8b30-7511498ed654.

    ![Tilladelser til Power BI Embedded](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Du kan overvåge Power BI Embedded-kapacitetsforbrug i appen eller på Azure-portalen, men ikke på Power BI-administrationsportalen.

## <a name="basic-monitoring-in-the-admin-portal"></a>Grundlæggende overvågning på administrationsportalen

Området **Kapacitetsindstillinger** på administrationsportalen indeholder fire målere, der angiver de placerede belastninger og de ressourcer, der er brugt af din kapacitet i løbet af de seneste syv dage. Disse fire felter arbejder på timebasis og angiver, hvor mange timer i løbet af de seneste syv dage det tilknyttede målepunkt oversteg 80 %. Dette målepunkt angiver en potentiel forringelse af slutbrugerens oplevelse.

![Forbrug i løbet af syv dage](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| CPU |Det antal gange, CPU-forbruget har overskredet 80 %. |
| Hukommelsesudskiftning |Repræsenterer hukommelsesforbrug på backend-kerner. Disse data angiver specifikt, hvor mange gange datasæt ryddes fra hukommelsen pga. hukommelsesforbrug grundet brugen af flere datasæt. |
| Hukommelsesbrug |Gennemsnitligt hukommelsesforbrug vist i GB. |
| DQ/s | Det antal gange, antallet af direkte forespørgsler og direkte forbindelser har overskredet 80 % af grænsen. <br> * Vi begrænser det samlede antal forespørgsler i relation til DirectQuery og direkte forbindelse pr. sekund.* Grænserne er 30/s for P1, 60/s for P2 og 120/s for P3. * Forespørgsler i relation til DirectQuery og direkte forbindelse indgår også i de ovenstående begrænsninger. Hvis du f.eks. har 15 direkte forspørgsler og 15 direkte forbindelser på et sekund, er grænsen nået<br>* Dette gælder ligeligt for forbindelser i det lokale miljø og cloudbaserede forbindelser. |
|  |  |

Målepunkter afspejler udnyttelse i løbet af den seneste uge.  Hvis du vil se en mere detaljeret visning af målepunkter, kan du gøre det ved at klikke på et af oversigtsfelterne.  Derved åbnes detaljerede diagrammer over de enkelte målepunkter for din Premium-kapacitet. I følgende diagram vises der oplysninger om CPU-målepunktet.

![Detaljeret diagram over forbrug, CPU](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Disse diagrammer opsummeres for hver time i løbet af den seneste uge og kan hjælpe med at identificere, hvornår du har haft særlige hændelser relateret til ydeevne i din Premium-kapacitet.

Du kan også eksportere de underliggende data for et eller flere målepunkter til en CSV-fil.  Via denne eksport får du detaljerede oplysninger i tre minutters intervaller for hver dag fra den seneste uge.

## <a name="next-steps"></a>Næste trin

Nu, hvor du har en forståelse af, hvordan du overvåger Power BI Premium-kapaciteter, kan du få mere at vide om optimering af kapaciteter.

> [!div class="nextstepaction"]
> [Administration og optimering af ressourcer med Power BI Premium-kapacitet](service-premium-understand-how-it-works.md)
