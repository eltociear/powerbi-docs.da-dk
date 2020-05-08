---
title: Brug af dataflow med datakilder i det lokale miljø
description: Få mere at vide om, hvordan du bruger data i det lokale miljø i dataflow
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: efd110ad73b1bd72813d418a1f641613c88dc0d5
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "75762571"
---
# <a name="using-dataflows-with-on-premises-data-sources"></a>Brug af dataflow med datakilder i det lokale miljø

Ved hjælp af **dataflow** kan du oprette en samling af data fra forskellige kilder, rense dataene, transformere dem og derefter indlæse dem i Power BI-lageret. Når du opretter et dataflow, kan du bruge datakilder i det lokale miljø. I denne artikel afklare de krav, der er forbundet med oprettelse af dataflow, og hvordan din **Enterprise Gateway** skal konfigureres for at aktivere disse forbindelser.

![Dataflow og gateways](media/service-dataflows-onpremises-gateways/onpremises-gateways_01.png)

## <a name="configuring-an-enterprise-gateway-for-use-with-dataflows"></a>Konfiguration af en Enterprise Gateway til brug med dataflow

Hvis du vil oprette et dataflow ved hjælp af en gateway, skal brugeren være virksomhedens gatewayadministrator, eller administratoren skal have delt den datakilde, der planlægges at bruges sammen med brugeren. 


> [!NOTE]
> Dataflow understøttes kun ved hjælp af Enterprise Gateways.

## <a name="using-an-on-premises-data-source-in-a-dataflow"></a>Brug af en datakilde i det lokale miljø i et dataflow

Når du opretter et dataflow, skal du vælge en datakilde i det lokale miljø på listen over datakilder, som vist på følgende billede.

![Vælg en datakilde i det lokale miljø](media/service-dataflows-onpremises-gateways/onpremises-gateways_02a.png)

Når du har foretaget dit valg, bliver du bedt om at angive forbindelsesoplysningerne for den Enterprise Gateway, der skal bruges til at få adgang til dataene i det lokale miljø. Du skal vælge selve gatewayen og angive legitimationsoplysninger for den valgte gateway.

![Angiv forbindelsesoplysninger](media/service-dataflows-onpremises-gateways/onpremises-gateways_03.png)

## <a name="monitoring-your-gateway"></a>Overvågning af din gateway

Du kan overvåge din Enterprise-Gateway for et dataflow på samme måde, som du overvåger gateways for et datasæt.

På skærmen med indstillinger for dataflowet i Power BI kan du overvåge gatewaystatus for et dataflow og tildele en gateway til dataflowet, som vist på følgende billede.

![Overvågning af gatewayen](media/service-dataflows-onpremises-gateways/onpremises-gateways_01.png)

## <a name="changing-a-gateway"></a>Ændring af en gateway

Du kan ændre Enterprise Gateway, der bruges til et givet dataflow, på to måder:

1. **Fra oprettelsesværktøjet** – du kan ændre den gateway, der er tildelt til alle dine forespørgsler ved hjælp af værktøjet til oprettelse af dataflowet.

    > [!NOTE]
    > Dataflowet prøver at finde eller oprette de påkrævede datakilder ved hjælp af den nye gateway. Hvis det ikke kan lade sig gøre, kan du ikke kan ændre gatewayen, før alle nødvendige dataflow er tilgængelige fra den valgte gateway.

2. **Fra skærmbilledet med indstillinger** – du kan ændre den tildelte gateway ved hjælp af skærmen med indstillinger for dataflowet i Power BI-tjenesten.

Du kan få mere at vide om Enterprise Gateways under [Datagateway i det lokale miljø](service-gateway-onprem.md).

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Der er nogle få kendte begrænsninger i forbindelse med brugen af Enterprise Gateways og dataflow:

* Hvert enkelt dataflow bruger muligvis kun én gateway. Derfor skal alle forespørgsler konfigureres vha. den samme gateway.
* Ændring af gatewayen påvirker hele dataflowet.
* Hvis der er brug for flere gateways, er den bedste fremgangsmåde at oprette flere dataflow (ét for hver enkelt gateway) og bruge funktionerne til compute eller enhedsreference til at samle dataene.
* Dataflow understøttes kun vha. Enterprise Gateways. Personlige gateways kan ikke vælges på rullelisten, lister og på skærme med indstillinger.


## <a name="next-steps"></a>Næste trin

Denne artikel indeholder oplysninger om brug af datakilder i det lokale miljø til dataflow, og hvordan du bruger og konfigurerer gateways for at få adgang til disse data. Følgende artikler kan også være nyttige

* [Selvbetjent dataforberedelse med dataflow](service-dataflows-overview.md)
* [Opret og brug dataflow i Power BI](service-dataflows-create-use.md)
* [Brug af beregnede objekter i Power BI Premium](service-dataflows-computed-entities-premium.md)
* [Udviklerressourcer til Power BI-dataflow](service-dataflows-developer-resources.md)

Du kan finde flere oplysninger om Power-forespørgsel og planlagt opdatering i disse artikler:
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Konfiguration af planlagt opdatering](refresh-scheduled-refresh.md)

Du kan finde flere oplysninger om Common Data Model i denne oversigtsartikel:
* [Common Data Model – oversigt](https://docs.microsoft.com/powerapps/common-data-model/overview)

