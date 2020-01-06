---
title: Forbind en rapport til et datasæt ved hjælp af dynamisk binding
description: Få mere at vide om, hvordan du integrerer en rapport ved hjælp af dynamisk binding.
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 11/07/2019
ms.openlocfilehash: f797dd55202ff4cba87cc3a15601d85091e94823
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2020
ms.locfileid: "74164050"
---
# <a name="connect-a-report-to-a-dataset-using-dynamic-binding"></a>Forbind en rapport til et datasæt ved hjælp af dynamisk binding 

Når en rapport har forbindelse til et datasæt, kan du bruge dynamisk binding. Forbindelsen mellem rapporten og datasættet kaldes for *binding*. Når bindingen fastsættes under integreringen – i modsætning til tidligere, hvor den blev fastsat på forhånd – kaldes bindingen for [dynamisk binding](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FLate_binding&data=02%7C01%7CKesem.Sharabi%40microsoft.com%7C5d5b0d2d62cf4818f0c108d7635b151e%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637087115150775585&sdata=AbEtdJvgy4ivi4v4ziuui%2Bw2ibTQQXBQNYRKbXn5scA%3D&reserved=0).
 
Når du integrerer en Power BI rapport ved hjælp af *dynamisk binding*, kan du forbinde den samme rapport til forskellige datasæt, afhængigt af brugerens legitimationsoplysninger.
 
Det betyder, at du kan bruge én rapport til at vise forskellige oplysninger, afhængigt af det datasæt den er forbundet til. En rapport, der viser værdier for detailhandel, kan f.eks. forbindes til forskellige detailhandleres datasæt og give forskellige resultater, afhængigt af hvilken detailhandlers datasæt den er forbundet til.
 
Rapporten og datasættet behøver ikke at være placeret i det samme arbejdsområde. Begge arbejdsområder (det, der indeholder rapporten, og det, der indeholder datasættet) skal være tildelt en [kapacitet](azure-pbie-create-capacity.md).

Som en del af integreringsprocessen skal du sørge for, at du *genererer et token med tilstrækkelige tilladelser* og *tilpasser konfigurationsobjektet*.


## <a name="generating-a-token-with-sufficient-permissions"></a>Generering af et token med tilstrækkelige tilladelser

Dynamisk binding understøttes i begge scenarier: *Integrering for din organisation* og *Integrering for dine kunder*. I nedenstående tabel beskrives overvejelserne for hvert scenarie.


|Scenarie  |Ejerskab af data  |Token  |Krav  |
|---------|---------|---------|---------|
|*Integrering for din organisation*    |Brugeren ejer data         |Adgangstoken til Power BI-brugere         |Den bruger, hvis Azure AD-token bruges, skal have de relevante tilladelser til alle artefakter.         |
|*Integrering for dine kunder*     |Appen ejer data         |Adgangstoken til brugere, der ikke har Power BI         |Skal indeholde tilladelser til både rapporten og det dynamisk bundne datasæt. Brug [API'en til generering af et integreringstoken til flere elementer](embed-sample-for-customers.md#multiEmbedToken) for at generere et integreringstoken, der understøtter flere artefakter.         |

## <a name="adjusting-the-config-object"></a>Tilpasning af konfigurationsobjektet
Føj `datasetBinding` til konfigurationsobjektet. Brug eksemplet nedenfor som reference.

```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    // -----  Adjustment required for dynamic binding ---- //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // ---- End of dynamic binding adjustment ---- //
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```

## <a name="next-steps"></a>Næste trin

Hvis du er nybegynder i forhold til at integrere i Power BI, kan du gennemse disse selvstudier for at få mere at vide om, hvordan du integrerer dit Power BI-indhold:
* [Selvstudium: Integrer Power BI-indhold i en applikation for dine kunder](embed-sample-for-customers.md)
* [Selvstudium: Integrer Power BI-indhold i en applikation for din organisation](embed-sample-for-your-organization.md)