---
title: Fejlfinding af det integrerede program
description: "Denne artikel beskriver nogle almindelige problemer, som kan opstå under integrationen af indhold fra Power BI."
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
ms.date: 11/27/2017
ms.author: asaxton
ms.openlocfilehash: f6ffc56f524da84e865d17981faddef58534c785
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/27/2017
---
# <a name="troubleshooting-your-embedded-application"></a>Fejlfinding af det integrerede program

Denne artikel beskriver nogle almindelige problemer, som kan opstå under integrationen af indhold fra Power BI.

## <a name="app-registration"></a>Programregistrering

**Fejl ved programregistrering**

Fejlmeddelelser internt på Azure-portalen eller Power BI-programmets registreringsside angiver utilstrækkelige rettigheder. For at registrere et program skal du være administrator i Azure AD-lejeren, eller programregistreringer skal være aktiverede for brugere uden administratorstatus.

**Power BI-tjenesten vises ikke i Azure-portalen under registrering af et nyt program**

Mindst en bruger skal være tilmeldt Power BI. Hvis du ikke kan se **Power BI-tjeneste** på listen i API-listen, er ingen brugere tilmeldt Power BI.

## <a name="rest-api"></a>REST API

**API-opkald returnerer 401**

En fiddler-optagelse kan være påkrævet med henblik på yderligere efterforskning. Det påkrævede tilladelsesomfang kan være utilstrækkeligt for det registrerede program internt i Azure AD. Bekræft, at det påkrævede omfang er til stede i programregistreringen til Azure AD internt på Azure-portalen.

**API-opkald returnerer 403**

En fiddler-optagelse kan være påkrævet med henblik på yderligere efterforskning. Der kan være flere grunde til en 403-fejl.

* Azure AD auth-tokenet kan være udløbet.
* Den godkendte bruger er ikke medlem af gruppen (programarbejdsområde).
* Den godkendte bruger er ikke en administrator af gruppen (programarbejdsområde).
* Godkendelsesheaderen kan være angivet forkert. Kontroller for tastefejl.

Programmets backend skal muligvis opdatere godkendelsestokenet før kaldet til GenerateToken.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**Generering af token mislykkes ved angivelse af effektiv identitet**

GenerateToken kan mislykkes af forskellige grunde, når effektiv identitet er angivet.

* Datasæt understøtter ikke effektiv identitet
* Brugernavn blev ikke angivet
* Rolle blev ikke angivet
* DatasetId blev ikke angivet
* Brugeren har ikke de korrekte tilladelser

Du kan benytte følgende metoder for at bekræfte årsagen:

* Udfør [hentning af datasæt](https://msdn.microsoft.com/library/mt784653.aspx). Er egenskaben IsEffectiveIdentityRequired sand?
* Brugernavn er obligatorisk for enhver EffectiveIdentity.
* Hvis IsEffectiveIdentityRolesRequired er sandt, så er Rolle påkrævet.
* DatasetId er obligatorisk for enhver EffectiveIdentity.
* For Analysis Services skal den overordnede bruger være en gateway-administrator.

## <a name="data-sources"></a>Datakilder

**ISV vil have andre legitimationsoplysninger til den samme datakilde**

En datakilde kan have et enkelt sæt legitimationsoplysninger til én overordnet bruger. Hvis du har brug for at oprette andre legitimationsoplysninger, skal du oprette andre overordnede brugere. Derefter skal du tildele de andre legitimationsoplysninger til hver af den overordnede brugers kontekst og integrere vha. den pågældende brugers Azure AD-token.

## <a name="content-rendering"></a>Indholdsgengivelse

**Gengivelse eller forbrug af integreret indhold mislykkes eller får timeout**

Sørg for, at det integrerede token ikke er udløbet. Sørg for at kontrollere den integrerede tokens udløb og opdatere den. Du kan få flere oplysninger under [Opdatér token ved hjælp af JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Rapport eller dashboard indlæses ikke**

Hvis brugeren ikke kan se rapporten eller dashboardet, skal du sørge for, at rapporten eller dashboardet indlæses korrekt i powerbi.com. Rapporten eller dashboardet fungerer ikke internt i programmet, hvis det ikke indlæses internt i powerbi.com.

**Rapport- eller dashboard-ydeevne er langsom**

Åbn filen fra Power BI Desktop, eller internt i powerbi.com, og bekræft, at ydeevnen er acceptabel for at udelukke, at der er problemer med dit program eller integrations-API'er.

## <a name="tools-for-troubleshooting"></a>Værktøjer til fejlfinding

### <a name="fiddler-trace"></a>Fiddler-sporing

[Fiddler](http://www.telerik.com/fiddler) er et gratis værktøj fra Telerik, der overvåger HTTP-trafik.  Du kan se det, der sendes frem og tilbage vha. Power BI-API'er fra klientcomputeren. Dette kan vise fejl og andre relaterede oplysninger.

![Fiddler-sporing](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>F12 i browser for front-end fejlløsning

F12 starter udviklervinduet i din browser. Dette giver adgang til at se netværkstrafik og andre oplysninger.

![F12 Browser-fejlfinding](media/embedded-troubleshoot/browser-f12.png)

Du kan se svar på ofte stillede spørgsmål under [Power BI Embedded – ofte stillede spørgsmål](embedded-faq.md).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)