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
ms.date: 10/09/2018
LocalizationGroup: Premium
ms.openlocfilehash: b2627950ea51239acb19972fde3244f3bd158255
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/10/2018
ms.locfileid: "48909216"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Overvåg kapaciteter i Power BI Premium og Power BI Embedded

Denne artikel indeholder en oversigt over overvågning af målepunkter for dine Power BI Premium-kapaciteter. Ved at overvåge kapacitetsforbrug kan du træffe mere velovervejede beslutninger, når du administrerer dine kapaciteter.

Du kan overvåge kapacitet med Power BI Premium-appen Capacity Metrics eller i administrationsportalen. Vi anbefaler appen, fordi den giver mange flere detaljer, men i denne artikel beskrives begge muligheder.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UgsjMbhi_Bk?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="install-the-premium-capacity-metrics-app"></a>Installér Premium-appen Capacity Metrics

Du kan gå direkte til [Premium-appen Capacity Metrics](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) eller installere den, som du plejer med andre apps i Power BI.

1. I Power BI skal du klikke på **Apps**.

    ![Gå til Apps](media/service-admin-premium-monitor-capacity/apps.png)

2. I højre side skal du klikke på **Hent apps**.

3. I kategorien **Apps** skal du søge efter **Power BI-appen Capacity Metrics**.

4. Abonner for at installere appen.

Nu, hvor du har installeret appen, kan du se målepunkter for kapaciteterne i din organisation. Lad os se nærmere på nogle af de vigtigste målepunkter, der er tilgængelige.

## <a name="use-the-metrics-app"></a>Brug målepunktsappen

Når du åbner appen, viser den først et dashboard med en oversigt over alle de kapaciteter, som du har administratorrettigheder til.

![Appdashboardet Målepunkter](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Rapporten indeholder tre faner, der beskrives mere detaljeret i følgende afsnit.

* **Filters applied to all pages (Filtre anvendt på alle sider)**: Gør det muligt at filtrere de andre sider i rapporten til en bestemt kapacitet.
* **Datasæt**: Giver detaljeret målepunkter for tilstanden for datasættene i dine kapaciteter.
* **System**: Giver overordnede kapacitetsmålepunkter, herunder hukommelse og højt CPU-forbrug. 

### <a name="filters-applied-to-all-pages-tab"></a>Fanen Filters applied to all pages (Filtre anvendt på alle sider)

Under fanen **Filtre, der anvendes på alle sider** kan du vælge en kapacitet, et datasæt og et datointerval inden for de seneste syv dage. Filtrene anvendes derefter på alle de relevante sider og felter i rapporten. Hvis der ikke er markeret nogen filtre, viser rapporten som standard målepunkter for den seneste uge for hver kapacitet, du ejer.

![Fanen Filtre](media/service-admin-premium-monitor-capacity/filters-tab.png)

### <a name="datasets-tab"></a>Fanen Datasæt

Under fanen **Datasæt** vises størstedelen af målepunkterne i appen. Brug de fire knapper øverst under fanen til at navigere til forskellige områder: **Oversigt**, **Opdateringer**, **Forespørgsler** og **Datasæt**.

![Fanen Datasæt](media/service-admin-premium-monitor-capacity/datasets-tab.png)

#### <a name="summary-area"></a>Området Oversigt

![Knappen Oversigt](media/service-admin-premium-monitor-capacity/summary-button.png)

I området **Oversigt** kan du få et overblik over dine kapaciteter på basis af entiteter, systemressourcer og arbejdsbelastninger for datasæt.

| | **Målepunkter** |
| --- | --- |
| **Objekter** | * Antallet af kapaciteter, som du ejer<br> * Det specifikke antal datasæt i din kapacitet<br> * Det specifikke antal arbejdsområder i din kapacitet |
| **System** | * Det gennemsnitlige hukommelsesforbrug i GB over de seneste syv dage<br> * Højeste hukommelsesforbrug i GB i løbet af de seneste syv dage og den lokale tid, forbruget opstod<br> * Det antal gange, CPU'en har overskredet 80 % af tærsklerne i løbet af de seneste syv dage opdelt i buckets på tre minutter<br> * De fleste gange, CPU'en har overskredet 80 % i løbet af de seneste syv dage opdelt i buckets på én time og den lokale tid, det opstod<br> * Det antal gange, forbindelser via direkte forespørgsler/direkte forbindelser har overskredet 80 % af tærsklerne i løbet af de seneste syv dage opdelt i buckets på tre minutter<br> * De fleste gange, forbindelser via direkte forespørgsler/direkte forbindelser har overskredet 80 % i løbet af de seneste syv dage opdelt i buckets på én time og den lokale tid, det opstod |
| **Arbejdsbelastninger for datasæt** | * Det samlede antal opdateringer i løbet af de seneste syv dage<br> * Det samlede antal vellykkede opdateringer i løbet af de seneste syv dage<br> * Det samlede antal mislykkede opdateringer i løbet af de seneste syv dage<br> * Det samlede antal mislykkede opdateringer, der skyldes manglende hukommelse<br> * Den gennemsnitlige varighed af opdateringer måles i minutter – den tid, det tager at udføre handlingen<br> * Den gennemsnitlige ventetid for opdateringer måles i minutter – den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starten af handlingen<br> * Det samlede antal forespørgsler, der er kørt i løbet af de seneste syv dage<br> * Det samlede antal vellykkede forespørgsler i løbet af de seneste syv dage<br> * Det samlede antal mislykkede forespørgsler i løbet af de seneste syv dage<br> * Den gennemsnitlige varighed af forespørgsler måles i minutter – den tid, det tager at udføre handlingen<br> * Det samlede antal modeller, der fjernes på grund af for stort hukommelsesforbrug |
|  |  |

#### <a name="refreshes-area"></a>Området Opdateringer

![Knappen Opdateringer](media/service-admin-premium-monitor-capacity/refreshes-button.png)

I området **Opdateringer** vises de fuldførte opdateringer, målinger af vellykkede opdateringer, den gennemsnitlige/maksimale ventetid for opdateringer og den gennemsnitlige/maksimale varighed af opdateringer opdelt efter datasæt i løbet af de seneste syv dage. I de to diagrammer nederst vises opdateringer i forhold til hukommelsesforbrug i GB og de gennemsnitlige ventetider opdelt i buckets på én time og rapporteret i lokaltid. I de øverste søjlediagrammer vises de fem øverste datasæt efter den gennemsnitlige tid, det tog at fuldføre det datasæt, der skulle opdateres (opdateringens varighed), og den gennemsnitlige ventetid for opdateringen. Hvis der er flere høje ventetider for opdateringer, kan det være tegn på, at kapaciteten snart er brugt op.

#### <a name="queries-area"></a>Området Forespørgsler

![Knappen Forespørgsler](media/service-admin-premium-monitor-capacity/queries-button.png)

I området **Forespørgsler** kan du set det samlede antal kørte forespørgsler, det samlede antal ventende forespørgsler for dynamiske forespørgsler/direkte forespørgsler, gennemsnitlig/maks. varighed, gennemsnitlig/maks. ventetid rapporteret i millisekunder opdelt efter datasæt, arbejdsområde og buckets pr. time i de seneste syv dage. I diagrammerne nederst vises antallet af forespørgsler, gennemsnitlig varighed (i millisekunder) og gennemsnitlig ventetid (i millisekunder) vs. hukommelsesforbrug i GB, opdelt i buckets på én time rapporteret i lokaltid. I de to diagrammer øverst til højre kan du se de øverste fem datasæt angivet efter den gennemsnitlige forespørgselsvarighed og ventetiden, inden forespørgslerne var udført. Lange forespørgselsvarigheder og lange ventetider betyder, at kapaciteten er overbelastet. Det kan også betyde, at et enkelt datasæt forårsager problemer, og at der er behov for yderligere undersøgelser.

#### <a name="datasets-area"></a>Området Datasæt

![Knappen Datasæt](media/service-admin-premium-monitor-capacity/datasets-button.png)

I området **Datasæt** vises fuldførte datasæt, der er fjernet på grund af et stort hukommelsesforbrug pr. time.

### <a name="system-tab"></a>Fanen System

Under fanen **System** vises antal gange med høj CPU-udnyttelse (det antal gange, udnyttelsen på 80 % er overskredet), høj udnyttelse af forbindelser via direkte forespørgsler/dynamiske forbindelser og hukommelsesforbrug.

![Premium System-rapport](media/service-admin-premium-monitor-capacity/system-tab.png)

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
