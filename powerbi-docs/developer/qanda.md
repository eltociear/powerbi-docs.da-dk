---
title: "Spørgsmål og svar i Power BI Embedded"
description: "Power BI Embedded giver dig mulighed for at integrere spørgsmål og svar i et program og giver brugerne mulighed for at stille spørgsmål på et naturligt sprog."
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
ms.date: 11/20/2017
ms.author: asaxton
ms.openlocfilehash: 856377112ccd7cb045ff80d3294ff9b8181122ee
ms.sourcegitcommit: 97ca2ed578f4f0e11f2d014872fe1b80dfd8a28e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/20/2017
---
# <a name="qa-in-power-bi-embedded"></a>Spørgsmål og svar i Power BI Embedded
Power BI Embedded giver dig mulighed for at integrere spørgsmål og svar i et program og giver brugerne mulighed for at stille spørgsmål på et naturligt sprog og få øjeblikkelige svar i form af visuelle elementer som diagrammer eller grafer.

![Interaktive spørgsmål i en integreret ramme](media/qanda/embedded-qanda.gif)

Der findes to tilstande for integrering af spørgsmål og svar i dit program: **interaktivt** og **kun resultat**. I **interaktiv** tilstand kan du skrive spørgsmål og få dem vist i det visuelle element. Hvis du har gemt eller stillet et spørgsmål, du vil have vist, kan du bruge tilstanden **kun resultat** ved at angive spørgsmålet i din integrerede konfiguration.

Her kan du se, hvordan JavaScript-koden vil se ud.

```
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnAMode.Interactive | models.QnAMode.ResultOnly,
    question:    optional parameter for Explore mode (QnAMode.Interactive) and mandatory for Render Result mode (QnAMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>Stil spørgsmål
Hvis du har brugt **resultattilstanden** med et stillet spørgsmål, kan du indsætte ekstra spørgsmål i rammen og straks få dem besvaret og dermed erstatte det forrige resultat. Der vises et nyt visuelt element, som svarer til det nye spørgsmål.

Et eksempel på denne form for brug kan være en liste med ofte stillede spørgsmål. Brugeren kan gennemse spørgsmålene og få dem besvaret i den samme integrerede del.

**Kodestykke for forbrug af JS SDK:**  

```        
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>Visuelt gengivet hændelse
I **interaktiv** tilstand kan programmet få besked via en hændelse for ændrede data, hver gang det gengivne visuelle element ændres, for at målrette den opdaterede inputforespørgsel, efterhånden som den skrives.

Hvis du lytter til hændelsen *visualRendered*, kan du gemme spørgsmål til senere brug. 

**Kodestykke for forbrug af JS SDK:**  

```
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>Integrer token
Opret et integreret token ud fra et datasæt for at starte en spørgsmål og svar-session. Du kan finde flere oplysninger under [Opret token for spørgsmål og svar](https://msdn.microsoft.com/library/mt784614.aspx#qanda).

## <a name="next-steps"></a>Næste trin
Hvis du vil prøve at bruge spørgsmål og svar, kan du gå til [Eksempel på JavaScript-integrering](https://microsoft.github.io/PowerBI-JavaScript/demo/).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
