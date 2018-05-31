---
title: Hvad kan udviklere bruge Power BI til?
description: Power BI tilbyder en bred vifte af muligheder for udviklere. Det går fra integration til brugerdefinerede visualiseringer og streaming af datasæt.
services: powerbi
author: markingmyname
ms.author: maghan
ms.date: 05/03/2018
ms.topic: overview
ms.service: powerbi
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 473052ee652c1fd6e68294efdbd7334cbb2df714
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810960"
---
# <a name="what-can-developers-do-with-power-bi"></a>Hvad kan udviklere bruge Power BI til?

Udviklere har forskellige muligheder, når de forsøger at inkludere Power BI-indhold i programmer. Disse indstillinger omfatter **integrering med Power BI**, **brugerdefinerede visuelle elementer** og **pushoverførsel af data i Power BI**.

## <a name="embedding"></a>Integration
Power BI-tjenesten (SaaS) og tjenesten Power BI Embedded i Azure (PaaS) har API'er, du kan bruge til at integrere dine dashboards og rapporter. Det betyder, at du har en række funktioner og adgang til de nyeste funktioner i Power BI, f.eks. dashboards, gateways og apparbejdsområder, når du integrerer indhold.

![PBIE-eksempel](media/what-can-you-do/what-can-you-do-01.png)

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
