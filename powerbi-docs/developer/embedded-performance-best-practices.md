---
title: Bedste praksis for ydeevnen i Power BI Embedded
description: Denne artikel indeholder en vejledning til bedste praksis for integreret analyse
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: d0f4ca29e30e5f6e6176f036dc535601eb580471
ms.sourcegitcommit: 298db44200b78b1281b3ae6dfe7cce7a89865ec9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/13/2018
ms.locfileid: "53329872"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Bedste praksis for ydeevnen i Power BI Embedded

Denne artikel indeholder anbefalinger til hurtigere gengivelse af rapporter, dashboards og felter i dit program

## <a name="embed-parameters"></a>Integrer parametre

Metoden Powerbi.embed() modtager nogle få parametre til at integrere en rapport, et dashboard eller et felt. Disse parametre har indflydelse på ydeevnen.

### <a name="embed-url"></a>Integreret URL-adresse

Undgå at generere den integrerede URL-adresse selv. Sørg i stedet for at få den integrerede URL-adresse ved at kalde API'en for [Hent rapporter](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Freports%2Fgetreportsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=22lkqRM2w1MQfrM8dooedaPqqIU8PufTq9TT4VDzRo0%3D&reserved=0), [Hent dashboards](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgetdashboardsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=nfWRgbSoXVF42Rg%2Ba9491u19uksXp%2FAyz%2Fa%2Ba7%2FCtdA%3D&reserved=0) eller [Hent felter](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgettilesingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256178318&sdata=LgZ27TynNpqQJDrb3aHWGQXIS%2FzichAO9De5M2uhF1Q%3D&reserved=0). Vi har føjet en ny parameter til URL-adressen kaldet **_config_**, som bruges til forbedringer af ydeevnen.

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

* Brug altid den nyeste version af [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).

* Installér den nyeste version af [klient-SDK'en til Power BI](https://github.com/Microsoft/PowerBI-JavaScript). Vi fortsætter med at udgive flere forbedringer, så kig forbi regelmæssigt.

* Pakker, der skal installeres:
    * Npm-pakke: powerbi-client
    * NuGet-pakke: Microsoft.PowerBI.JavaScript

> [!Note]
> Husk, at indlæsningstiden hovedsageligt afhænger af elementer, der er relevante for rapporten og selve dataene. Det kan f.eks være antallet af visualiseringer, størrelsen af data og kompleksiteten af forespørgslerne og beregnede målinger. Følg [bedste praksis](../power-bi-reports-performance.md) for at forbedre indlæsningstiden for rapporten.

## <a name="next-steps"></a>Næste trin

* [Rapportens ydeevne](../power-bi-reports-performance.md)
* [Sådan foretager du fejlfinding af problemer med Power BI Embedded](embedded-troubleshoot.md)
* [Ofte stillede spørgsmål om Power BI Embedded](embedded-faq.md)
