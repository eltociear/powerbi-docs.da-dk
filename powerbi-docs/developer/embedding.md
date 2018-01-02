---
title: Integrering med Power BI
description: Power BI tilbyder API'er til integrering af dine dashboards og rapporter i applikationer.
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: 36eb4231b6b3d3278d571722bde731051ffdf05e
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="embedding-with-power-bi"></a>Integrering med Power BI
Power BI tilbyder API'er til integrering af dine dashboards og rapporter i applikationer. Power BI-API'erne tilbyder en ensartet række egenskaber og adgang til de nyeste funktioner i Power BI, f.eks. dashboards, gateways og apparbejdsområder, når du integrerer indhold.

## <a name="a-single-api"></a>En enkelt API
Der er to hovedscenarier, når du integrerer Power BI-indhold. Integrering i forbindelse med din organisation og integrering i forbindelse med dine kunder. Power BI REST-API'en gør begge scenarier mulige. På denne måde kan du integrere dashboards og rapporter i din brugerdefinerede applikation ved hjælp af den samme API for enten at betjene din organisation eller dine kunder. Du kan fuldt ud benytte JavaScript- og REST-API'erne til dine integreringsbehov.

Du kan få vist et eksempel på, hvordan integrering fungerer under [Eksempel på integrering af JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Integrering i forbindelse med din organisation
Med integrering i forbindelse med din organisation har du mulighed for at udvide Power BI-tjenesten. Dette kræver, at slutbrugeren af din applikation logger på Power BI-tjenesten, når de vil have vist dit indhold. Når en person i din organisation logger på, har vedkommende kun adgang til dashboards og rapporter, der er delt med ham eller hende i Power BI-tjenesten. 

*Eksempler på integrering i forbindelse med din organisation omfatter intern webapplikationer, SharePoint Online-webdelen og integrering med Microsoft Teams.*

Se følgende for integrering i forbindelse med din organisation:

* [Integrer et dashboard i en app](integrate-dashboard.md)
* [Integrer et felt i en app](integrate-tile.md)
* [Integrer en rapport i en app](integrate-report.md)

Funktionaliteten i selvbetjeningsportalen, f.eks. rediger, gem og meget mere, er tilgængelig via [JavaScript-API'en](https://github.com/Microsoft/PowerBI-JavaScript) ved integrering i forbindelse med Power BI-brugere.

## <a name="embedding-for-your-customers"></a>Integrering i forbindelse med dine kunder
Integrering i forbindelse med dine kunder giver mulighed for at integrere dashboards og rapporter for brugere, der ikke har en Power BI-konto. Dine kunder behøver ikke at have kendskab til Power BI. Der kræves mindst én Power BI Pro-konto. Power BI Pro-kontoen skal fungere som en masterkonto for din applikation. Tænk på denne konto som en proxykonto. Power BI Pro-kontoen giver dig også mulighed for at generere integreringstokens, der giver adgang til dashboards og rapporter i Power BI-tjenesten. 

*Et eksempel på integrering i forbindelse med din kunder er en ISV-applikation, der sælges til andre firmaer.*

![Integreringsflow for integrering i forbindelse med dine kunder](media/embedding/powerbi-embed-flow.png)

Hvis du vil integrere dashboards, rapporter og felter, kan du bruge de samme API'er, som du vil bruge til integrering i forbindelse med din organisation.

> [!IMPORTANT]
> Integrering er afhængig af Power BI-tjenesten, men der er ingen afhængighed af Power BI for dine kunder. De behøver ikke at tilmelde sig Power BI for at få vist det integrerede indhold i din applikation.
> 
> 

Når du er klar til at overgå til produktion, skal apparbejdsområdet tildeles en kapacitet. Power BI Embedded i Microsoft Azure tilbyder kapacitet, som du kan bruge til dine applikationer.

Du kan finde oplysninger om, hvordan du integrerer under [Sådan integrerer du Power BI-dashboards, -rapporter og -felter](embedding-content.md).

Hvis du bruger tjenesten Power BI Workspace Collections i Azure, kan du finde oplysninger om, hvordan du overfører indhold under [Overfør indhold fra tjenesten Power BI Workspace Collections i Azure](migrate-from-powerbi-embedded.md).

## <a name="next-steps"></a>Næste trin
[Sådan integrerer du Power BI-dashboards, -rapporter og -felter](embedding-content.md)  
[Sådan overfører du indhold fra arbejdsområdesamlinger i Power BI Embedded til Power BI](migrate-from-powerbi-embedded.md)  
[Power BI Premium – hvad er det?](../service-premium.md)  
[Git-lager til JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript)  
[Git-lager til Power BI C#](https://github.com/Microsoft/PowerBI-CSharp)  
[Eksempel på JavaScript-integrering](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Hvidbog for kapacitetsplanlægning af integreret analyse](https://aka.ms/pbiewhitepaper)  
[Hvidbog til Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

