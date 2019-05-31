---
title: Overvåg Power BI Premium-kapaciteter ved hjælp af administrationsportalen
description: Brug Power BI-administrationsportalen til at overvåge dine Premium-kapaciteter.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 36b03a67e7c02702a70b6486880cc8eabf93e823
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564907"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Overvåg kapaciteter på administrationsportalen

Den **Health** fanen i den **kapacitetsindstillinger** område i administrationsportalen giver en oversigt over, om din kapacitet og aktiveret arbejdsbelastninger målepunkter.  

![Under fanen kapacitet tilstand i portalen](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Hvis du har brug for mere omfattende målepunkter, kan du bruge den [Power BI Premium-kapacitet målepunkter](service-admin-premium-monitor-capacity.md) app. Appen giver detailudledning og filtrering, og de mest detaljerede målepunkter for næsten alle aspekter påvirker ydeevnen kapacitet. Hvis du vil vide mere, kan du se [Monitor Premium-kapaciteter med appen](service-admin-premium-monitor-capacity.md).

## <a name="system-metrics"></a>Forbrugsdata for system

På den **Health** fanen CPU-forbruget på det højeste niveau, og brug af hukommelse, der giver et hurtigt overblik over de vigtigste målepunkter for kapaciteten. Disse metrikværdier er akkumuleret, herunder alle aktiveret arbejdsbelastninger for kapaciteten.

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| CPU-FORBRUG | Gennemsnitlig CPU-forbruget, som en procentdel af samlede tilgængelige CPU. |
| HUKOMMELSESBRUG | Gennemsnitligt hukommelsesforbrug i gigabyte (GB).|

## <a name="workload-metrics"></a>Arbejdsbelastning målepunkter

For hver enkelt arbejdsbelastning, der er aktiveret for kapaciteten. CPU-forbruget og hukommelsesforbrug vises.

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| CPU-FORBRUG | Gennemsnitlig CPU-forbruget, som en procentdel af samlede tilgængelige CPU. |
| HUKOMMELSESBRUG | Gennemsnitligt hukommelsesforbrug i gigabyte (GB).|

### <a name="detailed-workload-metrics"></a>Detaljerede arbejdsbelastning målepunkter

Hver enkelt arbejdsbelastning har flere målepunkter. Typen af målepunkter, der vises, afhænger af arbejdsbelastningen. Hvis du vil se detaljerede målepunkter for en arbejdsbelastning, skal du klikke på Udvid (pil ned).

![Udvid arbejdsbelastning tilstand](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Dataflow

##### <a name="dataflow-operations"></a>Dataflow operationer

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| Antal i alt | Det samlede antal opdateringer for hvert dataflow. |
| Antal succeser | Samlede vellykkede opdateringer for hver dataflowet.|
| Gennemsnitlig varighed (min.) | Den gennemsnitlige varighed af opdateringen af dataflowet i minutter |
| Maks varighed (min.) | Varigheden af den længstvarende opdatering af dataflowet i minutter. |
| Gennemsnitlig ventetid (min.) | Den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starttidspunktet for en opdatering af dataflowet i minutter. |
| Maks ventetiden (min.) | Den maksimale ventetid for dataflowet i minutter.  |

#### <a name="datasets"></a>Datasæt

##### <a name="refresh"></a>Opdater

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| Antal i alt | Det samlede antal opdateringer for hvert datasæt. |
| Antal succeser | Samlede vellykkede opdateringer for hvert datasæt. |
| Antal fejl | Samlet antal mislykkede opdateringer for hvert datasæt. |
| Hyppighed for fuldførte  | Antallet af vellykkede opdateringer divideret med de samlede opdateringer til at måle. pålidelighed. |
| Gennemsnitlig varighed (min.) | Den gennemsnitlige varighed af opdateringen af datasættet i minutter.  |
| Maks varighed (min.) | Varigheden af den længstvarende opdatering af datasættet i minutter. |
| Gennemsnitlig ventetid (min.) | Den gennemsnitlige mellemliggende tid mellem det planlagte tidspunkt og starttidspunktet for en opdatering af datasættet i minutter. |
| Maks ventetiden (min.) | Den maksimale ventetid for datasættet i minutter. |

##### <a name="query"></a>Forespørgsel

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| Antal i alt | Det samlede antal forespørgsler, der er kørt for datasættet. |
| Gennemsnitlig varighed (minutter) |Den gennemsnitlige varighed af forespørgsler for datasættet i millisekunder|
| Maksimal varighed (minutter) |Varigheden af den længstvarende forespørgsel i datasættet i millisekunder. |
| Gennemsnitlig ventetid (minutter) |Den gennemsnitlige ventetid for forespørgsler for datasættet i millisekunder. |
| Maks. antal ventetid (ms) |Varigheden af den længstventende forespørgsel i datasættet i millisekunder. |

##### <a name="eviction"></a>Hård

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| Model-antal | Det samlede antal datasæt evictions for denne kapacitet. Når en kapacitet står over for øget hukommelsesforbrug, fjerner noden et eller flere datasæt fra hukommelsen. Datasæt, der er inaktive (uden forespørgsels-/opdateringshandlinger, der udføres i øjeblikket), ryddes først. Derefter er fjernelsesrækkefølgen baseret på en måling af 'mindst brugt for nylig'. |

#### <a name="paginated-reports"></a>Sideinddelte rapporter

##### <a name="report-execution"></a>Rapporteksekvering

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| Antal udførelser  | Antallet gange, som rapporten blev kørt og overvåget af brugere.|

##### <a name="report-usage"></a>Brug

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| Antal succeser | Antallet gange, som rapporten er blevet vist af en bruger. |
| Antal fejl |Antallet gange, som rapporten er blevet vist af en bruger.|
| Rækkeantal |Antallet af rækker med data i rapporten. |
| Varighed for hentning af data (ms) |Den gennemsnitlige mængde tid, det tager at hente data til rapporten, i millisekunder. Lange varigheder kan være et tegn på langsomme forespørgsler eller andre datakildeproblemer.  |
| Varighed af behandling af (ms) |Den gennemsnitlige mængde tid, det tager at behandle dataene til rapporten, i millisekunder. |
| Gengivelse varighed (ms) |Den gennemsnitlige mængde tid, det tager at gengive en rapport i browseren, i millisekunder. |

> [!NOTE]
> Detaljerede målepunkter for den **AI** arbejdsbelastning er endnu ikke tilgængelige.

## <a name="next-steps"></a>Næste trin

Nu, hvor du har en forståelse af, hvordan du overvåger Power BI Premium-kapaciteter, kan du få mere at vide om optimering af kapaciteter.

> [!div class="nextstepaction"]
> [Optimering af Power BI Premium-kapaciteter](service-premium-capacity-optimize.md)
