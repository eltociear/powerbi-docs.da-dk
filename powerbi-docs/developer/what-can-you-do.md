---
title: Hvad kan udviklere bruge Power BI til?
description: "Power BI tilbyder en bred vifte af muligheder for udviklere. Det går fra integration til brugerdefinerede visualiseringer og streaming af datasæt."
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
ms.date: 07/20/2017
ms.author: asaxton
ms.openlocfilehash: a10cd93a06d14e3e66fd9cce480dc0ec99e67aeb
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="what-can-developers-do-with-power-bi"></a>Hvad kan udviklere bruge Power BI til?
Power BI tilbyder en bred vifte af muligheder for udviklere. Det går fra integration til brugerdefinerede visualiseringer og streaming af datasæt.

## <a name="embedding"></a>Integration
Power BI-tjenesten og Power BI Embedded i Azure er gået sammen om at tilbyde en enkelt API til integration af dine dashboards og rapporter. Det betyder, at du har én API-grænseflade, en ensartet række funktioner og adgang til de nyeste funktioner i Power BI, f.eks. dashboards, gateways og apparbejdsområder, når du integrerer indhold. Du kan finde flere oplysninger under [Integration med Power BI](embedding.md).

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>Brugerdefinerede visualiseringer
Med brugerdefinerede visualiseringer kan du oprette dine egne visualiseringer, som du kan bruge i Power BI-rapporter. Brugerdefinerede visualiseringer skrives i TypeScript, hvilket er en delmængde af JavaScript, som understøtter nogle avancerede funktioner og tidlig adgang til ES6/ES7-funktionalitet. Formatering af visualiseringer håndteres ved hjælp af overlappende typografiark. For nemheds skyld bruger vi præcompileren Less, der understøtter nogle avancerede funktioner, f.eks. indlejring, variabler, mixin'er, betingelser, løkker osv. Hvis du ikke vil bruge nogen af disse funktioner, kan du bare skrive almindelige overlappende typografiark i Less-filen.

Du kan se yderligere oplysninger om, hvordan du udvikler og publicerer en brugerdefineret visualisering, under [Publicer brugerdefinerede visualiseringer i Office Store](office-store.md).

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Overfør data til Power BI
Du kan bruge Power BI-API til at overføre data til et datasæt. Det giver dig mulighed at føje en række til en tabel i et datasæt. De nye data kan derefter afspejles på felter på et dashboard og i visualiseringer i rapporten.

Du kan finde flere oplysninger under [Overfør data til et dashboard](walkthrough-push-data.md)

## <a name="next-steps"></a>Næste trin
[Integration med Power BI](embedding.md)  
[Sådan overfører du indhold fra samlinger i arbejdsområdet i Power BI Embedded til Power BI](migrate-from-powerbi-embedded.md)  
[Git-lager for JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript)  
[Git-lager for Power BI C#](https://github.com/Microsoft/PowerBI-CSharp)  
[Publicer brugerdefinerede visualiseringer i Office Store](office-store.md)  
[Git-lager for Power BI-visualiseringer](https://github.com/Microsoft/PowerBI-visuals)  
[Integreret JavaScript-eksempel](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Power BI-API på Apiary](http://docs.powerbi.apiary.io/#)  
[Hvidbog til Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

