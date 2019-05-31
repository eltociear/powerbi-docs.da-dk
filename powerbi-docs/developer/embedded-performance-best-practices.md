---
title: Bedste praksis for ydeevnen i Power BI Embedded
description: Denne artikel indeholder en vejledning til bedste praksis for integreret analyse
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: ac8052b78e452f5da1f3db8988a180923c08e0b6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61343162"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Bedste praksis for ydeevnen i Power BI Embedded

Denne artikel indeholder anbefalinger til hurtigere gengivelse af rapporter, dashboards og felter i dit program

## <a name="embed-parameters"></a>Integrer parametre

Metoden Powerbi.embed() modtager nogle få parametre til at integrere en rapport, et dashboard eller et felt. Disse parametre har indflydelse på ydeevnen.

### <a name="embed-url"></a>Integreret URL-adresse

Undgå at generere den integrerede URL-adresse selv. Sørg i stedet for at få den integrerede URL-adresse ved at kalde API'en for [Hent rapporter](/rest/api/power-bi/reports/getreportsingroup), [Hent dashboards](/rest/api/power-bi/dashboards/getdashboardsingroup) eller [Hent felter](/rest/api/power-bi/dashboards/gettilesingroup). Vi har føjet en ny parameter til URL-adressen kaldet **_config_** , som bruges til forbedringer af ydeevnen.

### <a name="permissions"></a>Tilladelser

Angiv tilladelsen **Vis**, hvis du ikke har til hensigt at integrere en rapport i **Redigeringstilstand**. På den måde initialiserer integreringskode ikke komponenter, der bruges til Redigeringstilstand.

### <a name="filters-bookmarks-and-slicers"></a>Filtre, bogmærker og udsnit

Visualiseringer i rapporter gemmes ofte med cachelagrede data. De cachelagrede data bruges til at levere den opfattede ydeevne. Rapporter gengiver cachelagrede data, mens forespørgslerne udføres. Hvis der er angivet filtre, bogmærker eller udsnit, er cachelagrede data ikke relevante. Visualiseringerne gengives i så fald kun, efter forespørgslen om visualiseringen er kørt.

Hvis du integrerer rapporter med de samme filtre, skal du gemme rapporten med filtrerene anvendt for at undgå at viderebringe en liste over filtre til indlæsningskonfigurationen.

## <a name="preload"></a>Forudindlæs

Brug JavaScript API'en *forudindlæs* for at forbedre ydeevnen for slutbrugeren.
Med Powerbi.preload() downloades javascript, css-filer og andre artefakter, som bruges senere til integration i en rapport.

Kald forudindlæs, hvis du ikke integrerer rapporten med det samme. Hvis du f.eks. integrerer en rapport ved et klik på en knap, er det bedre at kalde forudindlæs, når den forrige side indlæses. Når brugeren af programmet derefter klikker på knappen, er gengivelsen hurtigere.

## <a name="measure-performance"></a>Mål ydeevne

Hvis du vil måle ydeevnen, skal du bruge følgende:

1. Indlæst: tiden, indtil rapporten initialiseres (brugeren ser ingen spinny).
2. Gengivet: tiden, indtil den fulde rapport er gengivet med faktiske data. Den gengivne hændelse vises, hver gang rapporten gengives igen, dvs. når der anvendes filtre. Hvis du vil starte med at måle en rapport, skal du sørge for at foretage beregningerne i den første fremhævede hændelse.

Cachelagrede data gengives, når de er tilgængelige, men vi har endnu ikke en hændelse for disse data.

## <a name="update-tools-and-sdk-packages"></a>Opdater værktøjer og SDK-pakker

Hold værktøjer og SDK-pakker opdateret.

* Brug altid den nyeste version af [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

* Installér den nyeste version af [klient-SDK'en til Power BI](https://github.com/Microsoft/PowerBI-JavaScript). Vi fortsætter med at udgive flere forbedringer, så kig forbi regelmæssigt.

* Pakker, der skal installeres:
    * Npm-pakke: powerbi-client
    * NuGet-pakke: Microsoft.PowerBI.JavaScript

> [!Note]
> Husk, at indlæsningstiden hovedsageligt afhænger af elementer, der er relevante for rapporten og selve dataene. Det kan f.eks være antallet af visualiseringer, størrelsen af data og kompleksiteten af forespørgslerne og beregnede målinger. Følg [bedste praksis](../power-bi-reports-performance.md) for at forbedre indlæsningstiden for rapporten.

## <a name="next-steps"></a>Næste trin

* [Power BI-rapportydeevne – bedste praksis](../power-bi-reports-performance.md)
* [Sådan foretager du fejlfinding af problemer med Power BI Embedded](embedded-troubleshoot.md)
* [Ofte stillede spørgsmål om Power BI Embedded](embedded-faq.md)
