---
title: Integreret analyse med Power BI
description: Power BI tilbyder API'er, så du kan bruge integreret analyse af dine dashboards og rapporter i programmer. Få mere at vide om integration med Power BI både i et PaaS-miljø og et SaaS-miljø ved hjælp af software til integreret analyse, integrerede analyseværktøjer eller integrerede business intelligence-værktøjer.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
ms.custom: seodec18
ms.date: 02/05/2019
ms.openlocfilehash: ca159fb8cea26f4c707aabc99d9fa2c308a32e1a
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762438"
---
# <a name="embedded-analytics-with-power-bi"></a>Integreret analyse med Power BI

Power BI-tjenesten (SaaS) og tjenesten Power BI Embedded i Azure (PaaS) har API'er, du kan bruge til at integrere dine dashboards og rapporter. Denne funktion betyder, at du har en række funktioner og adgang til de nyeste funktioner i Power BI, f.eks. dashboards, gateways og programarbejdsområder, når du integrerer indhold.

Du kan gennemgå [Embedding-konfigurationsværktøjet](https://aka.ms/embedsetup) for hurtigt at komme i gang og downloade et eksempelprogram.

Vælg den løsning, der er den rette for dig:

* Med [Integrering for din organisation](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Kør løsningen [Integrer for din organisation](https://aka.ms/embedsetup/UserOwnsData).
* Med [Integrering for dine kunder](embedding.md#embedding-for-your-customers) kan du integrere dashboards og rapporter for de brugere, der ikke har en konto til Power BI. Kør løsningen [Integrer for dine kunder](https://aka.ms/embedsetup/AppOwnsData).

![PBIE-eksempel](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>Brug af API'er

Der er to hovedscenarier, når du integrerer Power BI-indhold. Integrering for brugere i din organisation (der har licenser til Power BI) og integrering for dine brugere og kunder, uden at det kræves, at de har Power BI-licenser. Power BI REST-API'en gør begge scenarier mulige.

For kunder og brugere uden Power BI-licenser kan du integrere dashboards og rapporter i dit brugerdefinerede program ved hjælp af den samme API for enten at betjene din organisation eller dine kunder. Dine kunder ser de data, der administreres af programmet. Power BI-brugere i din organisation har desuden yderligere indstillinger, som de kan bruge til at få vist *deres data* direkte i Power BI eller i konteksten af det integrerede program. Du kan fuldt ud benytte JavaScript- og REST-API'erne til dine integreringsbehov.

Du kan få vist et eksempel på, hvordan integrering fungerer under [Eksempel på integrering af JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Integrer for din organisation

Med **Integrering for din organisation** kan du udvide Power BI-tjenesten. Integrering for din organisationen kræver, at brugerne af dit program logger på Power BI-tjenesten, når de vil have vist indholdet. Når en person i din organisation logger på, har vedkommende kun adgang til dashboards og rapporter, som de ejer, eller som er delt med vedkommende i Power BI-tjenesten.

*Eksempler på integrering i forbindelse med din organisation omfatter interne programmer, f.eks. [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Integrering med Microsoft Teams (du skal have administratorrettigheder)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) og [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).*

Se nedenfor vedrørende integrering i forbindelse med din organisation:

* [Integrer en rapport i et program](embed-sample-for-your-organization.md)

Funktionaliteten i selvbetjeningsportalen, f.eks. rediger, gem og meget mere, er tilgængelig via [JavaScript-API'en](https://github.com/Microsoft/PowerBI-JavaScript) ved integrering i forbindelse med Power BI-brugere.

Du kan gennemgå [værktøjet til konfiguration af integrering](https://aka.ms/embedsetup/UserOwnsData) for at integrere for din organisation, så du kan komme i gang og downloade et eksempelprogram, hvor du kan se, hvordan du integrerer en rapport for din organisation.

## <a name="embedding-for-your-customers"></a>Integrer for dine kunder

Med **Embedding for your customers** kan du integrere dashboards og rapporter for de brugere, der ikke har en konto til Power BI. Integrering for dine kunder kaldes også **Power BI Embedded**.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) er en **Microsoft Azure**-tjeneste, der gør det muligt for uafhængige softwareleverandører (ISV'er) og udviklere hurtigt at integrere visualiseringer, rapporter og dashboards i et program via en kapacitetsbaseret model, der afregnes på timebasis.

![Integreringsflow for integrering i forbindelse med dine kunder](media/embedding/powerbi-embed-flow.png)

Power BI Embedded giver fordele til ISV'er, udviklere og kunder. En ISV kan f.eks. begynde at oprette visualiseringer gratis vha. Power BI Desktop. ISV'er kan opnå hurtigere lancering ved at minimere det analytiske udviklingsarbejde med visualiseringer, hvilket betyder, at du kan skille dig ud fra konkurrenterne ved at give differentierede dataoplevelser. ISV'er kan også vælge at opkræve et premiumgebyr for den ekstra værdi, der tilføres vha. den integrerede analyse.

Med Power BI Embedded behøver dine kunder ikke at have kendskab til Power BI. Du kan bruge to forskellige metoder til at oprette et integreret program. Den ene mulighed er at bruge en Power BI Pro-konto. Den anden mulighed er at bruge en tjenesteprincipal. 

Power BI Pro-kontoen fungerer som en masterkonto for dit program (du kan opfatte denne masterkonto som en proxykonto). Power BI Pro-kontoen giver dig mulighed for at generere integreringstokens, der giver adgang til dashboards og rapporter i Power BI-tjenesten, som ejes og administreres af dit program.

En [tjenesteprincipal](embed-service-principal.md) kan integrere Power BI-indhold i et program ved hjælp af et **kun program**-token. En tjenesteprincipal giver dig mulighed for at generere integreringstokens, der giver adgang til dashboards og rapporter i Power BI-tjenesten, som ejes og administreres af dit program.

Udviklere, der bruger Power BI Embedded, kan fokusere på opbygningen af kernekompetencen i deres program i stedet for at bruge tid på at udvikle visualiseringer og analyse. Udviklere kan hurtigt imødekomme kundebehov for rapporter og dashboards, og de kan nemt integrere med fuldt dokumenterede API'er og SDK'er. ISV'er kan give kunder mulighed for at træffe hurtige databaserede beslutninger i kontekst fra enhver enhed ved at muliggøre intuitiv udforskning af data i deres programmer.

> [!IMPORTANT]
> Integrering er afhængig af Power BI-tjenesten, men dine kunder er ikke afhængige af Power Bi. De behøver ikke at tilmelde sig Power BI for at få vist det integrerede indhold i dit program.

Når du er klar til at overgå til produktion, skal programarbejdsområdet tildeles en dedikeret kapacitet. Power BI Embedded i Microsoft Azure tilbyder [dedikeret kapacitet](azure-pbie-create-capacity.md), som du kan bruge til dine programmer.

Du kan finde flere oplysninger om, hvordan du integrerer, under [Sådan integrerer du Power BI-indhold](embed-sample-for-customers.md).

## <a name="next-steps"></a>Næste trin

Nu kan du prøve at integrere Power BI-indhold i et program, eller du kan prøve at integrere Power BI-indhold for dine kunder.

> [!div class="nextstepaction"]
> [Integrer til din organisation](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Hvad er Power BI Embedded?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Integrer indhold for dine kunder](embed-sample-for-customers.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)