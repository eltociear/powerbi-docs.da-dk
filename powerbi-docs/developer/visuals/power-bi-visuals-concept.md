---
title: Konceptet visual i Power BI
description: I denne artikel beskrives det, hvordan et visual kan integreres med Power BI
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 36742917829013a6efca9d74f88b01bc686437a8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700840"
---
# <a name="power-bi-visual-concept"></a>Konceptet visual i Power BI

I artiklen forklares det, hvordan en bruger og et visual interagerer med Power BI, og hvordan en bruger interagerer med et Power BI-visual. I diagrammet kan du se, hvilke handlinger der påvirker det visual'et direkte eller gennem Power BI (f. eks. kan brugeren vælge bogmærker).

![Power BI-visual](./media/visual-concept.svg)

## <a name="the-visual-gets-update-from-power-bi"></a>Visual'et henter en opdatering fra Power BI

Visual'et har metoden `update`, og denne metode indeholder normalt den primære logik for visual'et og er ansvarlig for at gengive diagrammet eller visualisere dataene.

Der kommer flere opdateringer i kald af metoden `update`.

### <a name="user-interacts-with-visual-through-power-bi"></a>Brugeren interagerer med visual'et via Power BI

* Brugeren åbner panelet med egenskaber for visuals.

    Power BI henter understøttede objekter og egenskaber fra visual'et `capabilities.json` og for at modtage faktiske værdier for egenskaber kalder Power BI metoden `enumerateObjectInstances` for visual'et.

    Visual'et skal returnere de faktiske værdier for egenskaber.

    Du kan finde flere oplysninger ved at [læse om egenskaberne for visual'et](capabilities.md).

* [Brugeren ændrer egenskaberne for visual'et](../../visuals/power-bi-visualization-customize-title-background-and-legend.md) i formatpanelet.

    Når du har ændret værdien for en egenskab, kalder Power BI metoden `update` for visual'et og overfører de nye `options` til opdateringsmetoden med objekternes nye værdier.

    Du kan finde flere oplysninger ved at [læse om objekter og egenskaber for visual'et](objects-properties.md).

* Brugeren tilpasser visual'ets størrelse.

    Når en bruger ændrer størrelsen af visual'et, kalder Power BI metoden `update` med et nyt `option`-objekt. Indstillinger har indlejret et `viewport`-objekt med en ny visualbredde og -højde.

* Bruger anvender et filter på rapport-, side- eller visualniveau.

    Power BI filtrerer data i henhold til filterbetingelserne og kalder metoden `update` for visual'et for at overføre nye data til visual'et.

    Visual'et får ny opdatering af `options` med nye data i et af de indlejrede objekter. Det afhænger af konfigurationen af tilknytning af datavisninger for visual'et.

    Du kan finde flere oplysninger ved at [læse om tilknytning af datavisninger](dataview-mappings.md).

* Brugeren vælger datapunkter i et andet visual af rapporten.

    Power BI filtrerer eller fremhæver de valgte datapunkter og kalder metoden `update` for visual'et.

    Visual'et henter nye filtrerede data eller de samme data med en fremhævningsmatrix.

    Du kan finde flere oplysninger ved at [læse om, hvordan du fremhæver data i visuals](highlight.md).

* Brugeren vælger bogmærker i bogmærkepanelet i rapporten.

    Der kan forekomme to handlinger:

    1. Den overførte funktion til Power BI-kald, der blev registreret af metoden `registerOnSelectionCallback`, og tilbagekaldsfunktionen får valgmatrixer for det tilsvarende bogmærke.

    2. Power BI kalder metoden `update` med et tilsvarende filterobjekt i `options`.

    I begge tilfælde skal visual'et ændre visualiseringstilstanden i henhold til modtagne valg eller filterobjektet.

    Du kan finde flere oplysninger om bogmærker ved at [læse, hvordan du håndterer bogmærker](filter-api.md).

    Du kan finde flere oplysninger om filtre ved at [læse om, hvordan Power BI-visuals kan filtrere data i andre visuals](filter-api.md).

### <a name="user-interacts-with-visual-directly"></a>Brugeren interagerer direkte med visual

* Bruger holder musemarkøren over dataelementet

    Visual'et kan vise flere oplysninger om datapunkter via værktøjstip-API'en i Power BI.
    Brugeren holder musemarkøren over visual'et. Visual'et kan håndtere hændelser og vise data på værktøjstipelementet.

    Visual'et kan vise standardværktøjstip eller rapportsideværktøjstip.

    Hvis du vil vide mere, kan du læse vejledningen til [hvordan du tilføjer værktøjstip](add-tooltips.md).

* Brugeren ændrer egenskaber for visual'et (brugeren udvider f.eks. et træ, og visual'et gemmer tilstanden i egenskaberne)

    Visual'et kan gemme egenskabsværdier via Power BI-API'en. F. eks. når en bruger interagerer med det visual'et. Og visual'et skal gemme eller opdatere egenskabsværdier. Visual'et kan kalde metoden `presistProperties` for at gøre det.

* Brugeren klikker på URL-link.

    Visual'et kan som standard ikke åbne URL-adressen. Hvis du vil åbne URL-adressen under den nye fane, skal visual'et kalde metoden `launchURL` metode og overføre URL-adressen som en parameter.

    Du kan finde flere oplysninger om [start af URL-API'en](launch-url.md).

* Brugeren anvender et filter via visual'et

    Visual'et kalder `applyJSONFilter` og overfører filterbetingelser for at filtrere efter filtreringsdata i et andet visual.

    Visual'et kan bruge flere typer filtre, f. eks. filteret Basic, filteret Avanceret og filteret Tupel.

    Du kan finde flere oplysninger om filtre ved at [læse om, hvordan Power BI-visuals kan filtrere data i andre visuals](filter-api.md).

* Bruger klikker/vælger elementer i visual'et.

    Du kan finde flere oplysninger om valg ved at [læse om, hvordan visuals interagerer](selection-api.md).

### <a name="the-visual-interacts-with-power-bi"></a>Visual'et interagerer med Power BI

* Visual'et anmoder om flere data fra Power BI.

    Visual'et kan behandle data del for del. API-metoden FetchMoreData anmoder om det næste fragment af datasæt.

    Du kan finde flere oplysninger om `fetchMoreData` ved at [læse om, hvordan du henter flere data fra Power BI](fetch-more-data.md)

* Hændelsestjeneste

    Power BI kan eksportere rapporter til PDF eller sende dem via mail (kun certificerede visuals understøttes). Hvis du vil give Power BI besked om, at gengivelse er fuldført, og at den er klar til at hente PDF/mail, skal visual'et kalde API'en til gengivelse af hændelser.

    Du kan finde flere oplysninger ved at [læse om eksport af rapporter fra Power BI til PDF](../../consumer/end-user-pdf.md)

    Find flere [oplysninger om hændelsestjenesten](event-service.md)

## <a name="next-steps"></a>Næste trin

Er du webudvikler og interesseret i at oprette dine egne visualiseringer og føje dem til AppSource? Se [Udvikling af et Power BI-visual](./custom-visual-develop-tutorial.md), og få mere at vide om, hvordan du [publicerer Power BI-visuals i AppSource](../office-store.md).
