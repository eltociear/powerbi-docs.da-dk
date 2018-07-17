---
title: Integrering med Power BI
description: Power BI tilbyder API'er til integrering af dine dashboards og rapporter i applikationer.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 06/22/2018
ms.author: maghan
ms.openlocfilehash: 82a4c9c58567f5ace943363b7bed59fa744e85a5
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "36944094"
---
# <a name="embedding-with-power-bi"></a>Integrering med Power BI
Power BI tilbyder API'er til integrering af dine dashboards og rapporter i applikationer. Power BI-API'erne tilbyder en ensartet række egenskaber og adgang til de nyeste funktioner i Power BI, som f.eks. dashboards, gateways og apparbejdsområder, når du integrerer indhold.

## <a name="a-single-api"></a>En enkelt API
Der er to hovedscenarier, når du integrerer Power BI-indhold.  Integrering for brugere i din organisation (der har licenser til Power BI) og integrering for dine brugere og kunder, uden at det er et krav, at de har Power BI-licenser. Power BI REST-API'en gør begge scenarier mulige. 

For kunder og brugere uden Power BI-licenser kan du integrere dashboards og rapporter i dit brugerdefinerede program ved hjælp af den samme API for enten at betjene din organisation eller dine kunder. Dine kunder ser de data, der administreres af programmet. Og Power BI-brugere i din organisation får de yderligere indstillinger til at få vist *deres egne data* direkte i Power BI eller i konteksten af det program, der er integreret. Du kan fuldt ud benytte JavaScript- og REST-API'erne til dine integreringsbehov.

Du kan få vist et eksempel på, hvordan integrering fungerer under [Eksempel på integrering af JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Integrering i forbindelse med din organisation
Med integrering i forbindelse med din organisation har du mulighed for at udvide Power BI-tjenesten. Dette kræver, at brugerne af dit program logger på Power BI-tjenesten, når de vil have vist deres indhold. Når en person i din organisation logger på, har vedkommende kun adgang til dashboards og rapporter, der er delt med ham eller hende i Power BI-tjenesten. 

*Eksempler på integrering i forbindelse med din organisation omfatter intern webapplikationer, SharePoint Online-webdelen og integrering med [Microsoft Teams (du skal have administratorrettigheder)](https://powerbi.microsoft.com/en-us/blog/power-bi-teams-up-with-microsoft-teams/).*

Se følgende for integrering i forbindelse med din organisation:

* [Integrer en rapport i en app](integrate-report.md)
* [Integrer et dashboard i en app](integrate-dashboard.md)
* [Integrer et felt i en app](integrate-tile.md)

Funktionaliteten i selvbetjeningsportalen, f.eks. rediger, gem og meget mere, er tilgængelig via [JavaScript-API'en](https://github.com/Microsoft/PowerBI-JavaScript) ved integrering i forbindelse med Power BI-brugere.

Du kan gennemgå [Onboarding Experience Tool for at integrere for din organisation](https://aka.ms/embedsetup/UserOwnsData) og hurtigt komme i gang med og downloade en eksempelapp, hvor du kan se, hvordan du integrerer en rapport for din organisation.

## <a name="embedding-for-your-customers"></a>Integrer for dine kunder
Integrering for dine kunder giver mulighed for at integrere dashboards og rapporter for brugere, der ikke har en Power BI-konto. Dine kunder behøver ikke at have kendskab til Power BI. Der skal bruges mindst én Power BI-konto til at oprette et integreret program. Power BI Pro-kontoen fungerer som en masterkonto for dit program. Tænk på denne konto som en proxykonto. Power BI Pro-kontoen giver dig også mulighed for at generere integreringstokens, der giver adgang til dashboards og rapporter i Power BI-tjenesten, som ejes/administreres af dit program. 

*Et eksempel på integrering i forbindelse med din kunder er en ISV-applikation, der sælges til andre firmaer.*

![Integreringsflow for integrering i forbindelse med dine kunder](media/embedding/powerbi-embed-flow.png)

Hvis du vil integrere dashboards, rapporter og felter, kan du bruge de samme API'er, som du vil bruge til integrering i forbindelse med din organisation.

> [!IMPORTANT]
> Integrering er afhængig af Power BI-tjenesten, men dine kunder er ikke afhængige af Power Bi. De behøver ikke at tilmelde sig Power BI for at få vist det integrerede indhold i din app.
> 

Når du er klar til at overgå til produktion, skal apparbejdsområdet tildeles en kapacitet. Power BI Embedded i Microsoft Azure tilbyder kapacitet, som du kan bruge til dine applikationer.

Du kan finde oplysninger om, hvordan du integrerer under [Sådan integrerer du Power BI-dashboards, -rapporter og -felter](embedding-content.md).

Du kan gennemgå [Onboarding Experience Tool for at integrere for dine kunder](https://aka.ms/embedsetup/AppOwnsData) og hurtigt komme i gang med og downloade en eksempelapp, hvor du kan se, hvordan du integrerer en rapport for dine kunder.

Hvis du bruger tjenesten Power BI Workspace Collections i Azure, kan du finde oplysninger om, hvordan du overfører indhold under [Overfør indhold fra tjenesten Power BI Workspace Collections i Azure](migrate-from-powerbi-embedded.md).

## <a name="next-steps"></a>Næste trin
[Sådan integrerer du Power BI-dashboards, -rapporter og -felter](embedding-content.md)  
[Sådan overfører du indhold fra arbejdsområdesamlinger i Power BI Embedded til Power BI](migrate-from-powerbi-embedded.md)  
[Power BI Premium – hvad er det?](../service-premium.md)  
[Git-lager til JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript)  
[Git-lager til Power BI C#](https://github.com/Microsoft/PowerBI-CSharp)  
[Integreringseksempel til JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Hvidbog om planlægning af analysekapacitet til Embedded](https://aka.ms/pbiewhitepaper)  
[Hvidbog om Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

Flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

