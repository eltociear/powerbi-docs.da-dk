---
title: Fejlfinding i forbindelse med opdatering af scenarier
description: Fejlfinding i forbindelse med opdatering af scenarier
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 10/26/2017
ms.author: davidi
ms.openlocfilehash: 373a903ceac0e0ff9290a231d5e6eda42a2dcfc1
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/23/2017
---
# <a name="troubleshooting-refresh-scenarios"></a>Fejlfinding i forbindelse med opdatering af scenarier
Her kan du finde oplysninger om forskellige scenarier, som du kan stå overfor, når du opdaterer data i Power BI-tjenesten.

> [!NOTE]
> Hvis der opstår en situation, der ikke er angivet nedenfor, og det medfører problemer for dig, kan du bede om yderligere hjælp på [communitywebstedet](http://community.powerbi.com/), eller du kan oprette en [supportbillet](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="refresh-using-web-connector-doesnt-work-properly"></a>Opdater ved at bruge Web-connector virker ikke korrekt
Hvis du har et web-connectorscript, der bruger funktionen [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx), og du har opdateret dit datasæt eller din rapport efter den 18. november 2016, skal du bruge en gateway, for at opdatering virker korrekt.

## <a name="unsupported-data-source-for-refresh"></a>Ikke-understøttet datakilde til opdatering
Når du konfigurerer et datasæt, kan du få en fejl, der indikerer, at datasættet bruger en ikke-understøttet datakilde til opdatering. Se [Fejlfinding af ikke-understøttet datakilde til opdatering](service-admin-troubleshoot-unsupported-data-source-for-refresh.md) for at få yderligere oplysninger.

## <a name="dashboard-doesnt-reflect-changes-after-refresh"></a>Dashboard viser ikke ændringer efter opdatering
Vent ca. 10-15 minutter på, at opdateringen vises på dashboardfelterne.  Hvis den stadig ikke vises, skal du fastgøre visualiseringen til dashboardet igen.

## <a name="gatewaynotreachable-when-setting-credentials"></a>GatewayNotReachable ved indstilling af legitimationsoplysninger
Du kan støde på GatewayNotReachable, når du forsøger at indstille legitimationsoplysninger for en datakilde. Dette kan være pga. en forældet gateway.  Installér den seneste gateway, og prøv igen.

## <a name="processing-error-the-following-system-error-occurred-type-mismatch"></a>Behandlingsfejl: Der opstod følgende systemfejl: Typerne passer ikke sammen.
Det kan være et problem med dit M-script i din Power BI Desktop-fil eller Excel-projektmappe.  Det kan også være pga. en forældet Power BI Desktop-version.

## <a name="tile-refresh-errors"></a>Fejl ved feltopdatering
Se en liste over fejl, du kan støde på ved dashboardfelter, og forklaringer i [Fejlfinding af feltfejl](refresh-troubleshooting-tile-errors.md).

## <a name="refresh-fails-when-updating-data-from-sources-that-use-aad-oauth"></a>Opdater mislykkes ved opdatering af data fra kilder, der bruger AAD OAuth
Azure Active Director (**AAD**) OAuth-token, der bruges af mange forskellige datakilder, udløber om ca. en time. Du kan løbe ind i situationer, hvor indlæsning af data tager længere tid end tokenudløb (mere end en time), da Power BI-tjenesten venter i op til to timer ved indlæsning af data. I den situation kan dataindlæsningsprocessen mislykkes med en fejl i legitimationsoplysninger.

Datakilder, der bruger AAD OAuth, omfatter bl.a. **Microsoft Dynamics CRM Online**, **SharePoint Online** (SPO). Hvis du opretter forbindelse til disse datakilder og får en fejl i legitimationsoplysninger, når indlæsning af data tager længere tid end en time, kan dette være årsagen.

Microsoft undersøger en løsning, der giver dataindlæsningsprocessen mulighed for at opdatere tokenen og fortsætte. Hvis din forekomst af Dynamics CRM Online eller SharePoint Online (eller anden AAD OAuth-datakilde), er så stor, at den kunne støde på grænsen for dataindlæsning på to timer, kan du også opleve en timeout for dataindlæsning fra Power BI-tjenesten.

Bemærk også, at for at opdatering skal virke korrekt, skal du, når du opretter forbindelse til en **SharePoint Online**-datakilde ved brug af AAD OAuth, bruge den samme konto, som når du logger på **Power BI-tjenesten**.

## <a name="uncompressed-data-limits-for-refresh"></a>Ikke-komprimerede datagrænser for opdater
Den maksimale størrelse for datasæt, der importeres i **Power BI-tjenesten**, er 1 GB. Disse datasæt er meget komprimerede for at sikre høj ydeevne. I en delt kapacitet sætter tjenesten derudover en grænse for mængden af ikke-komprimeret data, der behandles under en opdatering, til 10 GB. Denne grænse tager højde for komprimeringen, og er derfor meget højere end 1 GB. Datasæt i Power BI Premium er ikke underlagt denne grænse. Hvis opdatering i Power BI-tjenesten mislykkedes af denne årsag, skal du reducere mængden af data, der importeres i Power BI, og prøve igen.

## <a name="scheduled-refresh-timeout"></a>Timeout for planlagt opdatering
Planlagt opdatering for importerede datasæt får timeout efter to timer. Denne timeout er øget til fem timer for datasæt på **Premium**-arbejdsområder. Hvis du støder på denne grænse, kan du overveje at reducere dit datasæts størrelse eller kompleksitet eller overveje at inddele datasættet i mindre dele.

## <a name="next-steps"></a>Næste trin
[Dataopdatering](refresh-data.md)  
[Fejlfinding af datagateway i det lokale miljø](service-gateway-onprem-tshoot.md)  
[Fejlfinding af Power BI Gateway – personlig](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

