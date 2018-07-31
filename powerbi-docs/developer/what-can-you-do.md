---
title: Hvad kan udviklere bruge Power BI til?
description: Power BI tilbyder en bred vifte af muligheder for udviklere. Det går fra integration til brugerdefinerede visualiseringer og streaming af datasæt.
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 07fb8d365a6fe4a874b057a71a90a99fc8a9e5fa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34564690"
---
# <a name="what-can-developers-do-with-power-bi"></a>Hvad kan udviklere bruge Power BI til?

Udviklere har forskellige muligheder, når de forsøger at inkludere Power BI-indhold i programmer. Disse indstillinger omfatter **integrering med Power BI**, **brugerdefinerede visuelle elementer** og **pushoverførsel af data i Power BI**.

## <a name="embedding"></a>Integration
Power BI-tjenesten (SaaS) og tjenesten Power BI Embedded i Azure (PaaS) har API'er, du kan bruge til at integrere dine dashboards og rapporter. Det betyder, at du har en række funktioner og adgang til de nyeste funktioner i Power BI, f.eks. dashboards, gateways og apparbejdsområder, når du integrerer indhold.

Du kan gennemgå [Onboarding lbudExperience Tool](https://aka.ms/embedsetup) for hurtigt at komme i gang og downloade en eksempelapp.

Vælg den løsning, der er den rette for dig:
* Med [Embedding for your customers](embedding.md#embedding-for-your-customers) kan du integrere dashboards og rapporter for de brugere, der ikke har en konto til Power BI. Kør løsningen [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData).
* Med [Embedding for your organization](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Kør løsningen [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData).

![PBIE-eksempel](media/what-can-you-do/what-can-you-do-02.png)

## <a name="develop-custom-visuals"></a>Opret brugerdefinerede visuelle elementer
Med brugerdefinerede visualiseringer kan du oprette dine egne visualiseringer, som du kan bruge i Power BI-rapporter. Brugerdefinerede visuelle elementer skrives i TypeScript, der er en udvidelse af JavaScript. TypeScript understøtter visse avancerede funktioner og tidlig adgang til ES6/ES7-funktioner. Formatering af visualiseringer håndteres ved hjælp af overlappende typografiark. For nemheds skyld bruger vi præcompileren Less, der understøtter nogle avancerede funktioner, f.eks. indlejring, variabler, betingelser, løkker osv. Hvis du ikke vil bruge nogen af disse funktioner, kan du bare skrive almindelige overlappende typografiark i Less-filen.

![CV-eksempel](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Overfør data til Power BI
Du kan bruge Power BI-API til at overføre data til et datasæt. Det giver dig mulighed at føje en række til en tabel i et datasæt. De nye data kan derefter afspejles på felter på et dashboard og i visualiseringer i rapporten.

![Eksempel på pushdata](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Næste trin
[Integrer med Power BI](embedding.md)  
[Publicer brugerdefinerede visuals i Office Store](office-store.md)  
[Overfør data til et dashboard](walkthrough-push-data.md)
