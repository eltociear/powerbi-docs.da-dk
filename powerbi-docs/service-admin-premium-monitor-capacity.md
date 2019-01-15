---
title: Overvåg Power BI Premium-kapaciteter i din organisation
description: Brug Power BI-administrationsportalen og Power BI Premium-appen Capacity Metrics
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/13/2018
LocalizationGroup: Premium
ms.openlocfilehash: e8e69cdacb9ee54cdf19724c590f994f66c4dff7
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54290612"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Overvåg kapaciteter i Power BI Premium og Power BI Embedded

Denne artikel indeholder en oversigt over overvågning af målepunkter for dine Power BI Premium-kapaciteter. Ved at overvåge kapacitetsforbrug kan du træffe mere velovervejede beslutninger, når du administrerer dine kapaciteter.

Du kan overvåge kapacitet med Power BI Premium-appen Capacity Metrics eller i administrationsportalen. Vi anbefaler appen, fordi den giver mange flere detaljer, men i denne artikel beskrives begge muligheder.

**Den aktuelle version af appen er 1.10 (udgivet d. 13. december 2018).**

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

### <a name="metrics-dashboard"></a>Dashboardet for målepunkter

Når du åbner appen, viser den først et dashboard med en oversigt over alle de kapaciteter, som du har administratorrettigheder til.

![Appdashboardet Målepunkter](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Dashboardet indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Systemoversigt** | * Programmets version<br> * Antallet af kapaciteter, som du er administrator for<br> * Antallet af arbejdsområder i dine kapaciteter, som rapporterer målepunkter<br> * Det gennemsnitlige hukommelsesforbrug i GB inden for de seneste syv dage<br> * Det maksimale hukommelsesforbrug i GB inden for de seneste syv dage<br> * Lokalt tidspunkt, hvor der har været maksimal hukommelsesforbrug<br> * Antallet af gange, hvor CPU'en overskred 80 % af tærsklen inden for de seneste syv dage, opdelt i buckets på tre minutter<br> * De fleste gange, hvor CPU'en overskred 80 % inden for de seneste syv dage, opdelt i buckets på 1 time<br> * Lokalt tidspunkt, hvor CPU'en overskred 80 % flest gange på én time |
| **Oversigt over datasæt** | * Det samlede antal datasæt på tværs af alle arbejdsområder i dine kapaciteter<br> * Antallet af gange, hvor forbindelser via direkte forespørgsler/direkte forbindelser overskred 80 % af tærsklerne inden for de seneste syv dage, opdelt i buckets på tre minutter<br> * De fleste gange, hvor forbindelser via direkte forespørgsler/direkte forbindelser overskred 80 % inden for de seneste syv dage, opdelt i buckets på én time<br> * Lokalt tidspunkt, hvor direkte forespørgsler/direkte forbindelser overskred 80 % flest gange på én time<br> * Det samlede antal opdateringer i løbet af de seneste syv dage<br> * Den gennemsnitlige ventetid for opdateringer – den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og opdateringen i minutter<br> * Den gennemsnitlige varighed af opdateringer – den tid, det tager at fuldføre opdateringen, i minutter<br> * Det samlede antal forespørgsler, der er kørt i løbet af de seneste syv dage<br> * Den gennemsnitlige ventetid for forespørgsler – den tid, en forespørgsel har ventet på systemressourcer, før udførelsen startes, i millisekunder<br> * Den gennemsnitlige varighed af forespørgsler – den tid, det tager at fuldføre forespørgslen, i millisekunder<br> * Det samlede antal modeller, der fjernes på grund af for stort hukommelsesforbrug<br> * Den gennemsnitlige størrelse af datasæt <br> * Det gennemsnitlige antal datasæt, der indlæses i hukommelsen |
| **Oversigt over dataflow** | * Det samlede antal dataflow på tværs af alle arbejdsområder i dine kapaciteter<br> * Det samlede antal opdateringer i løbet af de seneste syv dage<br> * Den gennemsnitlige ventetid for opdateringer – den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og opdateringen i minutter<br> * Den gennemsnitlige varighed af opdateringer – den tid, det tager at fuldføre opdateringen, i minutter |
| **Oversigt over sideinddelt rapport** | * Det samlede antal sideinddelte rapporter på tværs af alle arbejdsområder i dine kapaciteter<br> * Det samlede antal gange, som alle rapporter er blevet set af brugere<br> * Det samlede antal rækker med data i alle rapporter<br> * Den samlede tid, det tager for alle faser (datahentning, -behandling og -gengivelse) i alle rapporter i millisekunder |
|  |  |

### <a name="metrics-report"></a>Rapport over målepunkter

Klik på dashboardet for at gå til den underliggende rapport. Rapporten indeholder fem faner, der beskrives mere detaljeret i følgende afsnit.

* **Datasæt**: Giver detaljerede målepunkter for tilstanden for Power BI-datasættene i dine kapaciteter.

* **Sideinddelte rapporter**: Giver detaljerede målepunkter for tilstanden af sideinddelte rapporter i dine kapaciteter.

* **Dataflow**: Giver detaljerede opdateringsmålepunkter for dataflow i dine kapaciteter.

* **Ressourceforbrug**: Giver overordnede målepunkter for kapacitet, herunder hukommelse og højt CPU-forbrug.

* **Id'er og oplysninger**: Indeholder navne, id'er og ejere for kapaciteter, arbejdsområder og arbejdsbelastninger.

På hver fane kan du filtrere målepunkter efter kapacitet og datointerval. Hvis der ikke er valgt nogen filtre, viser rapporten som standard målepunkter for den seneste uge for alle kapaciteter, der rapporterer målepunkter.

#### <a name="datasets-tab"></a>Fanen Datasæt

Brug knapperne øverst på fanen **Datasæt** for at navigere til forskellige områder: **Oversigt**, **Opdateringer**, **Varighed af forespørgsel**, **Ventetid for forespørgsel** og **Datasæt**.

![Fanen Datasæt](media/service-admin-premium-monitor-capacity/datasets-tab.png)

##### <a name="refreshes-area"></a>Området Opdateringer

Området **Opdateringer** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Opdateringspålidelighed** | * Samlet antal: Det samlede antal opdateringer for hvert datasæt<br> * Pålidelighed: Den fuldførte opdateringsandel for hvert enkelt datasæt i procent<br> * Gennemsnitlig ventetid: Den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starten af en opdatering for datasættet i minutter<br> * Maksimal ventetid: Den maksimale ventetid for datasættet i minutter <br> * Gennemsnitlig varighed: Den gennemsnitlige varighed af opdateringen af datasættet i minutter<br> * Maksimal varighed: Varigheden af den længstvarende opdatering af datasættet i minutter |
| **Top 5-datasæt efter Gennemsnitlig opdateringsvarighed** | * De fem datasæt med den længstvarende gennemsnitlige opdateringsvarighed i minutter |
| **Top 5 datasæt efter Gennemsnitlig ventetid** | * De fem datasæt med den længstvarende gennemsnitlige opdateringsventetid i minutter |
| **Gennemsnitlige opdateringsventetider pr. time** | * Den gennemsnitlige opdateringsventetid opdelt i 1-times buckets, rapporteret i lokaltid. Flere tilfælde af høje opdateringsventetider kan være tegn på, at kapaciteten snart er brugt op. |
| **Opdateringsantal og hukommelsesforbrug pr. time** | * Succeser, fejl og hukommelsesforbrug opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

##### <a name="query-durations-area"></a>Område for forespørgselsvarigheder

Området **Forespørgselsvarigheder** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Forespørgselsvarigheder** | * Data i dette afsnit er opdelt i udsnit efter datasæt, arbejdsområde og buckets pr. time for de seneste syv dage<br> * I alt: Det samlede antal forespørgsler, der er kørt for datasættet<br> * Gennemsnit: Den gennemsnitlige varighed af forespørgsler for datasættet i millisekunder<br> * Maksimum: Varigheden af den længstvarende forespørgsel i datasættet i millisekunder|
| **Distribution af forespørgselsvarighed** | * Histogrammet med forespørgselsvarighed er inddelt i buckets efter forespørgselsvarigheder (i millisekunder) i følgende kategorier: intervaller af < = 30 ms, 30-100 ms, 100-300 ms, 300 ms-1 sek., 1-3 sek., 3-10 sek., 10-30 sek. og > 30 sek. Lange forespørgselsvarigheder og lange ventetider betyder, at kapaciteten er overbelastet. Det kan også betyde, at et enkelt datasæt forårsager problemer, og at der er behov for yderligere undersøgelser. |
| **Top 5-datasæt efter Gennemsnitlig varighed** | * De fem datasæt med den længstvarende gennemsnitlige forespørgselsvarighed i millisekunder |
| **Direkte forespørgsel/liveforbindelser (> 80 % udnyttelse)** | * De gange, en direkte forespørgsel eller liveforbindelse har overskredet CPU-udnyttelsen på 80 % opdelt i 1-times buckets, rapporteret i lokaltid |
| **Distributioner af forespørgselsvarighed pr. time** | * Antallet af forespørgsler og gennemsnitlig varighed (i millisekunder) vs. hukommelsesforbrug i GB opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

##### <a name="query-waits-area"></a>Område for ventetider for forespørgsler

Området **Forespørgselsventetider** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Forespørgselsventetider** | * Data i dette afsnit er opdelt i udsnit efter datasæt, arbejdsområde og buckets pr. time for de seneste syv dage<br> * I alt: Det samlede antal forespørgsler, der er kørt for datasættet<br> * Antal ventende: Antallet af forespørgsler i datasættet, der har ventet på systemressourcer, før udførelsen startes <br> * Gennemsnit: Den gennemsnitlige ventetid for forespørgsler for datasættet i millisekunder<br> * Maksimum: Varigheden af den længstventende forespørgsel i datasættet i millisekunder|
| **Distribution af ventetid** | * Histogrammet med forespørgselsvarighed er inddelt i buckets efter forespørgselsvarigheder (i millisekunder) i følgende kategorier: intervaller af <= 50 ms, 50-100 ms, 100-200 ms, 200-400 ms, 400 ms-1 sek., 1-5 sek. og > 5 sek. |
| **Top 5 datasæt efter Gennemsnitlig ventetid** | * De fem datasæt med den længste gennemsnitlige ventetid inden udførelsen af en forespørgsel i millisekunder |
| **Antal forespørgselsventetider og tidspunkter pr. time** | * Antal forespørgsler og den gennemsnitlige ventetid (i millisekunder) vs. hukommelsesforbrug i GB, opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

##### <a name="datasets-area"></a>Området Datasæt

Området **Datasæt** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Antal datasætfjernelser** | * I alt: Det samlede antal *fjernelser* af datasættet for hver enkelt kapacitet. Når en kapacitet står over for øget hukommelsesforbrug, fjerner noden et eller flere datasæt fra hukommelsen. Datasæt, der er inaktive (uden forespørgsels-/opdateringshandlinger, der udføres i øjeblikket), ryddes først. Derefter er fjernelsesrækkefølgen baseret på en måling af 'mindst brugt for nylig'.|
| **Datasætfjernelser og hukommelsesforbrug pr. time** | * Datasætfjernelser i forhold til hukommelsesforbrug i GB opdelt i 1-times buckets, rapporteret i lokaltid |
| **Antal indlæste datasæt pr. time** | * Antal datasæt, der er indlæst i hukommelsen i forhold til hukommelsesforbrug i GB opdelt i 1-times buckets, rapporteret i lokaltid |
| **Datastørrelser**  | * Maksimumstørrelse: Den maksimale størrelse af datasættet i MB for den viste periode |
|  |  |

#### <a name="paginated-reports-tab"></a>Fanen Sideinddelte rapporter

Fanen **Sideinddelte rapporter** viser detaljerede målepunkter for tilstanden for sideinddelte rapporter i dine kapaciteter.

![Fanen Sideinddelte rapporter](media/service-admin-premium-monitor-capacity/paginated-reports-tab.png)

Fanen **Sideinddelte rapporter** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Samlet forbrug** | * Visninger i alt: Antallet af gange, som rapporten er blevet set af brugere<br> * Rækkeantal: Antallet af rækker med data i rapporten<br> * Hentning (gns.): Den gennemsnitlige mængde tid, det tager at hente data til rapporten, i millisekunder. Lange varigheder kan være et tegn på langsomme forespørgsler eller andre datakildeproblemer. <br> * Behandling (gns.): Den gennemsnitlige mængde tid, det tager at behandle dataene til rapporten, i millisekunder<br>* Gengivelse (gns.): Den gennemsnitlige mængde tid, det tager at gengive en rapport i browseren, i millisekunder<br> * Tid i alt: Den mængde tid, det tager for alle faserne i rapporten, i millisekunder|
| **Top 5-rapporter efter Gennemsnitlig datahentningstid** | * De fem rapporter med den længste gennemsnitlige datahentningstid i millisekunder |
| **Top 5-rapporter efter Gennemsnitlig rapportbehandlingstid** | * De fem rapporter med den længste gennemsnitlige rapportbehandlingstid i millisekunder |
| **Varigheder pr. time** | * Datahentning i forhold til behandlings- og gengivelsestid opdelt i 1-times buckets, rapporteret i lokaltid |
| **Resultater pr. time** | * Succeser, fejl og hukommelsesforbrug opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

#### <a name="dataflows-tab"></a>Fanen Dataflow

Fanen **Dataflow** viser detaljerede opdateringsmålepunkter for dataflow i dine kapaciteter.

![Fanen Dataflow](media/service-admin-premium-monitor-capacity/dataflows-tab.png)

Fanen **Dataflow** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **Opdatering** | * I alt: Det samlede antal opdateringer for hvert dataflow<br> * Pålidelighed: Den fuldførte opdateringsandel for hvert enkelt dataflow i procent<br> * Gennemsnitlig ventetid: Den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starten af en opdatering for dataflowet i minutter<br> * Maksimal ventetid: Den maksimale ventetid for dataflowet i minutter <br> * Gennemsnitlig varighed: Den gennemsnitlige varighed af opdateringen af dataflowet i minutter<br> * Maksimal varighed: Varigheden af den længstvarende opdatering af dataflowet i minutter |
| **Top 5-dataflow efter Gennemsnitlig opdateringsvarighed** | * De fem dataflow med den længstvarende gennemsnitlige opdateringsvarighed i minutter |
| **Top 5-dataflow efter Gennemsnitlig ventetid** | * De fem dataflow med den længstvarende gennemsnitlige opdateringsventetid i minutter |
| **Gennemsnitlige opdateringsventetider pr. time** | * Den gennemsnitlige opdateringsventetid opdelt i 1-times buckets, rapporteret i lokaltid. Flere tilfælde af høje opdateringsventetider kan være tegn på, at kapaciteten snart er brugt op. |
| **Opdateringsantal og hukommelsesforbrug pr. time** | * Succeser, fejl og hukommelsesforbrug opdelt i 1-times buckets, rapporteret i lokaltid |
|  |  |

#### <a name="resource-consumption-tab"></a>Fanen Ressourceforbrug

På fanen **Ressourceforbrug** kan du se CPU- og hukommelsesforbrug på tværs af alle kapaciteter og arbejdsbelastninger.

![Fanen Ressourceforbrug](media/service-admin-premium-monitor-capacity/resource-consumption-tab.png)

Fanen **Ressourceforbrug** indeholder følgende målepunkter.

| **Rapportafsnit** | **Målepunkter** |
| --- | --- |
| **CPU-forbrug** | * Det antal gange, CPU'en har overskredet 80 % af tærsklerne i løbet af de seneste syv dage opdelt i buckets på tre minutter |
| **Hukommelsesforbrug** | * Hukommelsesforbrug i de seneste syv dage opdelt i 3-minutters buckets |
|  |  |

#### <a name="ids-and-info-tab"></a>Fanen Id'er og Oplysninger

Fanen **Id'er og oplysninger** indeholder navne, id'er og ejere for kapaciteter, arbejdsområder og arbejdsbelastninger.

![Fanen Id'er og Oplysninger](media/service-admin-premium-monitor-capacity/info-tab.png)

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
| Hukommelsesforbrug |Gennemsnitligt hukommelsesforbrug vist i GB. |
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
