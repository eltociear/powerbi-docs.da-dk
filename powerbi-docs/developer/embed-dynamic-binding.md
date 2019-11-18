---
title: Dynamisk binding
description: Få mere at vide om, hvordan du integrerer en rapport ved hjælp af dynamisk binding.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 09/25/2019
ms.openlocfilehash: 8b42b397f726e492eda80a99eb730c215eb17ccb
ms.sourcegitcommit: 23ad768020a9daf129f69a462a2d46d59d2349d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/22/2019
ms.locfileid: "72776231"
---
# <a name="dynamic-binding"></a>Dynamisk binding

Dynamisk binding giver mulighed for dynamisk at vælge et datasæt, mens du integrerer en rapport. Rapporten og datasættet behøver ikke at være placeret i det samme arbejdsområde. Slutbrugerne får vist forskellige resultater, afhængigt af det valgte datasæt.

Begge arbejdsområder (det, der indeholder rapporten, og det, der indeholder datasættet) skal være tildelt en kapacitet.

Integration af en rapport ved hjælp af dynamisk binding består af to faser:
1. Generering af et token
2. Tilpasning af konfigurationsobjektet

## <a name="generating-a-token"></a>Generering af et token
Du genererer et token ved at bruge [API'en til generering af et integreringstoken for flere elementer](embed-sample-for-customers.md#multiEmbedToken).

Dynamisk binding understøttes i begge integreringsscenarier, *Integrering for din organisation* og *Integrering for dine kunder*.

| Løsning                   | Token                               | Krav                                                                                                                                                  |
|---------------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *Integrering for din organisation* | Adgangstoken til Power BI-brugere     | Den bruger, hvis Azure AD-token bruges, skal have de relevante tilladelser til alle artefakter.                                                                    |
| *Integrering for dine kunder*    | Adgangstoken til brugere, der ikke har Power BI | Skal indeholde tilladelser til både rapporten og det dynamisk bundne datasæt. Brug den nye API til at generere et integreringstoken, som understøtter flere artefakter. |

## <a name="adjusting-the-config-object"></a>Tilpasning af konfigurationsobjektet
Føj `datasetBinding` til konfigurationsobjektet. Brug eksemplet nederst på siden som reference.

Hvis du er nybegynder i forhold til at integrere i Power BI, kan du gennemse disse selvstudier for at få mere at vide om, hvordan du integrerer dit Power BI-indhold:
* [Integrer Power BI-indhold i en applikation for dine kunder](embed-sample-for-customers.md)
* [Selvstudium: Integrer Power BI-indhold i en applikation for din organisation](embed-sample-for-your-organization.md)

 ### <a name="example"></a>Eksempel
```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    /////////////////////////////////////////////
    // Adjustment required for dynamic binding //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // End of dynamic binding adjustment            //
    /////////////////////////////////////////////
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```