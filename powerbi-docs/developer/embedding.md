---
title: Integreret analyse med Power BI
description: Power BI tilbyder API'er, så du kan bruge integreret analyse af dine dashboards og rapporter i programmer. Få mere at vide om integrering med Power BI både i et PaaS-miljø og et SaaS-miljø ved hjælp af software til integreret analyse, integrerede analyseværktøjer eller integrerede business intelligence-værktøjer.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 05/15/2019
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051057"
---
# <a name="embedded-analytics-with-power-bi"></a>Integreret analyse med Power BI

Power BI-tjenesten (SaaS) og tjenesten Power BI Embedded i Azure (PaaS) har API'er, du kan bruge til at integrere dine dashboards og rapporter. Når du integrerer indhold, giver det dig adgang til de nyeste Power BI-funktioner, f.eks dashboards, gateways og apparbejdsområder.

Du kan gennemgå [Embedding-konfigurationsværktøjet](https://aka.ms/embedsetup) for hurtigt at komme i gang og downloade en eksempelapp.

Vælg den løsning, der er den rette for dig:

* Med [Embedding for your organization](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Gør du ved at implementere de [Integrer for din organisation](https://aka.ms/embedsetup/UserOwnsData) løsning.
* [Integrerer for dine kunder](embedding.md#embedding-for-your-customers) gør det muligt at integrere dashboards og rapporter for brugere, der ikke har en Power BI-konto. Gør du ved at implementere de [Integrer for dine kunder](https://aka.ms/embedsetup/AppOwnsData) løsning.

![PBIE-eksempel](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>Du kan bruge API'er

Der er to hovedscenarier til at integrere Power BI-indhold:
- Integrering for brugere i din organisation (der har licenser til Power BI). 
 
- Integrering for dine brugere og kunder, der ikke har brug for Power BI-licenser. 

Den [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) gør begge scenarier mulige.

For kunder og brugere uden Power BI-licenser kan du integrere dashboards og rapporter i dit brugerdefinerede program ved hjælp af den samme API for enten at betjene din organisation eller dine kunder. Dine kunder se dataene administrerede program. Power BI-brugere i din organisation har også mulighed for yderligere at få vist *deres data* direkte i Power BI eller i det integrerede program kontekst. Du kan fuldt ud benytte JavaScript- og REST-API'erne til dine integreringsbehov.

For at forstå, hvordan integrering fungerer, kan du se de [integreringseksempel](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Integrer for din organisation

Med **Embedding for your organization** kan du udvide Power BI-tjenesten. Denne integration kræver, at dit programs brugere logge på Power BI-tjenesten til at få vist indholdet. Når en person i din organisation logger på, har vedkommende kun adgang til dashboards og rapporter, som de ejer, eller som er delt med vedkommende i Power BI-tjenesten.

Organisation integrering eksempler omfatter interne programmer, f.eks [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams-integration (du skal have administratorrettigheder)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/), og [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

Hvis du vil integrere for din organisation, kan du se [Selvstudium: Integrer Power BI-indhold i et program til din organisation](embed-sample-for-your-organization.md).

Funktionaliteten i selvbetjeningsportalen, f.eks. rediger, gem og meget mere, er tilgængelig via [JavaScript-API'en](https://github.com/Microsoft/PowerBI-JavaScript) ved integrering i forbindelse med Power BI-brugere.

Du kan gå igennem den [Embedding installationsprogrammet værktøj](https://aka.ms/embedsetup/UserOwnsData) til at komme i gang, og download et eksempelprogram, der viser, hvordan du integrerer en rapport for din organisation.

## <a name="embedding-for-your-customers"></a>Integrer for dine kunder

**Integrerer for dine kunder** gør det muligt at integrere dashboards og rapporter for brugere, der ikke har en Power BI-konto. Denne integration er også kendt som *Power BI Embedded*.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) er en **Microsoft Azure** tjeneste, der giver mulighed for uafhængige softwareleverandører (ISV'er) og udviklere hurtigt Integrer visuelle elementer, rapporter og dashboards i et program. Denne integration gøres via en forbrugsbaseret model kapacitet-baseret, pr. time.

![Integreringsflow for integrering i forbindelse med dine kunder](media/embedding/powerbi-embed-flow.png)

Power BI Embedded giver fordele til ISV'er, udviklere og kunder. En ISV kan f.eks. begynde at oprette visuelle elementer gratis vha. Power BI Desktop. Ved at minimere visual analytisk udviklingsarbejdet, ISV'er kom hurtigere på markedet og skiller sig ud fra konkurrenter med differentierede data oplevelser. ISV'er kan også vælge for at opkræve et premium for den ekstra værdi de oprette med integreret analyse.

Med Power BI Embedded behøver dine kunder ikke at have kendskab til Power BI. Du kan bruge to forskellige metoder til at oprette et integreret program:
- Power BI Pro-konto 
- Tjenesteprincipal 

Power BI Pro-kontoen fungerer som dit programs masterkonto (Tænk på det som en proxykonto). Denne konto gør det muligt at generere integreringstokens, der giver adgang til dit programs Power BI-dashboards og rapporter.

En [tjenesteprincipal](embed-service-principal.md) kan integrere Power BI-indhold i et program ved hjælp af et **kun program**-token. Gør det også muligt at generere integreringstokens, der giver adgang til dit programs Power BI-dashboards og rapporter.

Udviklere, der bruger Power BI Embedded kan bruge tid på at fokusere på at bygge deres programs kernefunktionerne i stedet for forbrugsgrænse tid udvikle visuelle elementer og analyse. De kan hurtigt opfylde kundernes behov for rapporter og dashboards og Integrer nemt med fuldt dokumenteret API'er og SDK'er. ISV'er kan give kunder mulighed for at træffe hurtige databaserede beslutninger i kontekst fra enhver enhed ved at muliggøre intuitiv udforskning af data i deres apps.

> [!IMPORTANT]
> Dine kunder behøver ikke at have en Power BI-konto til at få vist dit programs integreret indhold, mens integrerer kræver, at Power BI-tjenesten. 

Når du er klar til at overgå til produktion, skal apparbejdsområdet tildeles en dedikeret kapacitet. Power BI Embedded i Microsoft Azure tilbyder [dedikeret kapacitet](azure-pbie-create-capacity.md), som du kan bruge til dine apps.

Se for integrering i detaljer [Sådan integrerer du Power BI-indhold](embed-sample-for-customers.md).

## <a name="next-steps"></a>Næste trin

Nu kan du prøve at integrere Power BI-indhold i en app, eller du kan prøve at integrere Power BI-indhold for dine kunder.

> [!div class="nextstepaction"]
> [Integrer til din organisation](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Hvad er Power BI Embedded?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Integrer indhold for dine kunder](embed-sample-for-customers.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
