---
title: Hvad kan jeg bruge Power BI-API'en til?
description: Hvad kan jeg bruge Power BI-API'en til?
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 3b19740616e7b9a390a883fde2fd96320de7b94a
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/17/2018
ms.locfileid: "45973580"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Hvad kan udviklere bruge Power BI-API'en til?

Power BI viser dashboards, der er interaktive, og som kan oprettes og opdateres fra mange forskellige datakilder i realtid. Du kan bruge alle programmeringssprog, der understøtter REST-kald, til at oprette apps, der kan integreres med et Power BI-dashboard i realtid. Du kan også integrere Power BI-felter og -rapporter i apps.

Udviklere kan også oprette deres egne datavisualiseringer, der kan bruges i interaktive rapporter og på dashboards.

Her er nogle af de ting, du kan bruge Power BI-API'erne til.

| **Hvis du vil** | **Skal du gå hertil** |
| --- | --- |
| Integrer dashboards, rapporter og felter til brugere af Power BI og brugere, der ikke anvender Power BI (appen ejer dataene) |[Sådan integrerer du Power BI-dashboards, -rapporter og -felter](embedding-content.md) |
| Udvid en eksisterende forretningsarbejdsproces til at overføre vigtige data til et Power BI-dashboard. |[Overfør data til et dashboard](walkthrough-push-data.md) |
| Godkend til Power BI. |[Godkend til Power BI](get-azuread-access-token.md) |
| Opret en brugerdefineret visualisering. |[Brug udviklerværktøjerne til at oprette brugerdefinerede visualiseringer](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> Power BI-API'erne refererer stadig til apparbejdsområder som grupper. Referencer til grupper betyder, at du arbejder med apparbejdsområder.

## <a name="power-bi-developer-samples"></a>Eksempler på Power BI Developer

Eksemplerne på Power BI Developer omfatter elementer til integration af dashboards, rapporter og felter.

[Eksempler på Power BI Developer](https://github.com/Microsoft/PowerBI-Developer-Samples)

* Eksempler i **App Owns Data** er til integration med brugere, der ikke anvender Power BI.
* Eksempler i **User Owns Data** er til integration med brugere, der anvender Power BI.

## <a name="github-repositories"></a>GitHub-lagre

* [.NET-SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript)
* [Brugerdefinerede visualiseringer](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>Udviklerværktøjer

Følgende er værktøjer, du kan bruge som en hjælp, når du udvikler Power BI-elementer.

Du kan gennemgå [værktøjet til konfiguration af integrering](https://aka.ms/embedsetup) for hurtigt at komme i gang og downloade en eksempelapp, hvor du kan se, hvordan du integrerer Power BI-indhold.

Vælg den løsning, der er den rette for dig:

* Med [Embedding for your customers](embedding.md#embedding-for-your-customers) kan du integrere dashboards og rapporter for de brugere, der ikke har en konto til Power BI. Kør løsningen [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData).

* Med [Embedding for your organization](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Kør løsningen [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData).

Hvis du vil se et komplet eksempel, hvor JavaScript API'en bruges, kan du bruge [værktøjet Playground](https://microsoft.github.io/PowerBI-JavaScript/demo). Med dette værktøj kan du nemt prøve dig frem med forskellige typer af Power BI Embedded-eksempler. Du kan også få flere oplysninger om JavaScript-API'en ved at gå til siden [wiki for PowerBI-JavaScript](https://github.com/Microsoft/powerbi-javascript/wiki).

## <a name="push-data-into-power-bi"></a>Overfør data til Power BI

Du kan bruge Power BI-API til at overføre data til et datasæt. Denne funktion giver dig mulighed at føje en række til en tabel i et datasæt. De nye data kan derefter afspejles på felter på et dashboard og i visualiseringer i rapporten.

![Eksempel på pushdata](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Næste trin

[Overfør data til et datasæt](walkthrough-push-data.md)  
[Introduktion til udviklerværktøjer til brugerdefinerede visualiseringer](../service-custom-visuals-getting-started-with-developer-tools.md)  
[Reference til Power BI REST-API](https://docs.microsoft.com/rest/api/power-bi/)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
