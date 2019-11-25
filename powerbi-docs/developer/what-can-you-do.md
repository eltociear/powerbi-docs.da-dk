---
title: Hvad kan udviklere bruge Power BI til?
description: Power BI tilbyder en bred vifte af muligheder for udviklere. Det går fra integration til brugerdefinerede visualiseringer og streaming af datasæt.
author: KesemSharabi
ms.author: kesharab
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: mvc
ms.date: 03/15/2019
ms.openlocfilehash: 9f9383e5cdb4b4690ef75294f7ff8c17fb643d9a
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265018"
---
# <a name="what-can-developers-do-with-power-bi"></a>Hvad kan udviklere bruge Power BI til?

Udviklere har forskellige muligheder, når de forsøger at inkludere Power BI-indhold i programmer. Som udvikler kan du bruge disse indstillinger, herunder **integrering med Power BI**, **brugerdefinerede visualiseringer** og **pushoverførsel af data i Power BI**.

## <a name="embedding-power-bi-content"></a>Integrer Power BI-indhold

Power BI-tjenesten (SaaS) og tjenesten Power BI Embedded i Azure (PaaS) har API'er, du kan bruge til at integrere dine dashboards og rapporter. Med denne funktion kan du få adgang til de nyeste funktioner i Power BI, f.eks. dashboards, gateways og arbejdsområder, når du integrerer indhold.

Du kan gennemgå [Embedding-konfigurationsværktøjet](https://aka.ms/embedsetup) for hurtigt at komme i gang og downloade en eksempelapp.

Vælg den løsning, der er den rette for dig:

* Med [Embedding for your customers](embedding.md#embedding-for-your-customers) kan du integrere dashboards og rapporter for de brugere, der ikke har en konto til Power BI. Kør løsningen [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData).

* Med [Embedding for your organization](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Kør løsningen [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData).

![PBIE-eksempel](media/what-can-you-do/what-can-you-do-02.png)

Hvis du vil have mere at vide om integration med Power BI, kan du se [Integration med Power BI](embedding.md).

## <a name="developing-custom-visuals"></a>Udvikling af brugerdefinerede visualiseringer

Du kan bruge brugerdefinerede visualiseringer i Power BI til at oprette unikke visualiseringer, som er skræddersyet til dig eller din virksomhed. Disse brugerdefinerede visualiseringer er ofte oprettet af udviklere. De bygges, når mængden af visualiseringer, der er inkluderet i Power BI, ikke opfylder dine behov.

Med brugerdefinerede visualiseringer kan du oprette dine egne visualiseringer, som du kan bruge i Power BI-rapporter. Brugerdefinerede visualiseringer skrives i TypeScript, der er en udvidelse af JavaScript. TypeScript understøtter visse avancerede funktioner og tidlig adgang til ES6/ES7-funktioner. Formatering af visualiseringer håndteres ved hjælp af overlappende typografiark (CSS). For nemheds skyld bruger vi præcompileren Less, der understøtter nogle avancerede funktioner, f.eks. indlejring, variabler, betingelser, løkker og andre funktioner. Hvis du ikke vil bruge nogen af disse funktioner, kan du bare skrive almindelige overlappende CSS i Less-filen.

![CV-eksempel](media/what-can-you-do/powerbi-custom-visual-store.png)

Hvis du vil have mere at vide om udvikling af brugerdefinerede visualiseringer, kan du se under [Udvikling af en brugerdefineret visualisering i Power BI](visuals/custom-visual-develop-tutorial.md).

## <a name="using-api-automation"></a>Brug af API-automatisering

Power BI viser dashboards, der er interaktive, og som kan oprettes og opdateres fra mange forskellige datakilder i realtid. Du kan bruge alle programmeringssprog, der understøtter REST-kald, til at oprette apps, der kan integreres med et Power BI-dashboard i realtid. Du kan også integrere Power BI-felter og -rapporter i apps.

Udviklere kan også oprette deres egne datavisualiseringer, der kan bruges i interaktive rapporter og på dashboards.

![Eksempel på pushdata](media/what-can-you-do/powerbi-push-data.png)

Du kan se nogle af de ting, du kan gøre med Power BI-API'erne, i [Hvad kan udviklere bruge Power BI-API'en til](overview-of-power-bi-rest-api.md)?

## <a name="next-steps"></a>Næste trin

[Integrer med Power BI](embedding.md)  

[Udvikling af en brugerdefineret visualisering i Power BI](https://microsoft.github.io/PowerBI-visuals/docs/step-by-step-lab/developing-a-power-bi-custom-visual/)

[Hvad kan udviklere bruge Power BI-API'en til?](overview-of-power-bi-rest-api.md)

[Power BI Developer Center](https://powerbi.microsoft.com/developers/)