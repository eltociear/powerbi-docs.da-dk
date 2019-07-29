---
title: Vejledning til udrulning af en datagateway til Power BI
description: Få de bedste praksisser og overvejelser ved udrulning af en gateway til Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 4351804330982b32582c4c782ef7c2fa0e92f197
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271713"
---
# <a name="guidance-for-deploying-a-data-gateway-for-power-bi"></a>Vejledning til udrulning af en datagateway til Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Denne artikel indeholder en vejledning til og nogle overvejelser om udrulning af en datagateway til Power BI i dit netværksmiljø.

Du kan finde oplysninger om, hvordan du downloader, installerer, konfigurerer og administrerer datagatewayen i det lokale miljø, i [Hvad er en datagateway i det lokale miljø?](/data-integration/gateway/service-gateway-onprem) Du kan også få mere at vide om datagatewayen i det lokale miljø og Power BI ved at besøge [Microsoft Power-bloggen](https://powerbi.microsoft.com/blog/) og [Microsoft Power BI-community'et](https://community.powerbi.com/).

## <a name="installation-considerations-for-the-on-premises-data-gateway"></a>Overvejelser ved installationen af datagatewayen i det lokale miljø

Før du installerer datagatewayen i det lokale miljø for din Power BI-cloudtjeneste, er der en række ting, du skal være opmærksom på. I de følgende afsnit beskrives disse overvejelser.

### <a name="number-of-users"></a>Antal brugere

Antallet af brugere, som forbruger en rapport, der bruger gatewayen, er en vigtig metrik i forbindelse med beslutningen om, hvor gatewayen skal installeres. Her er nogle spørgsmål, som bør tages med i overvejelserne:

* Bruges disse rapporter på forskellige tidspunkter på dagen af brugerne?
* Hvilke typer forbindelser bruger de (DirectQuery eller Import)?
* Bruger alle brugerne den samme rapport?

Hvis samtlige brugere tilgår en given rapport på samme tidspunkt hver dag, bør du sørge for at installere gatewayen på en computer, der har kapacitet til at håndtere alle disse anmodninger (se de følgende afsnit for at få oplysninger om ydelsestællere og minimumkrav, der kan hjælpe dig med at finde ud af dette).

Der findes en begrænsning i **Power BI**, der kun tillader *én* gateway pr. *rapport*, så selvom en rapport er baseret på flere datakilder, så skal alle disse kilder gå gennem en enkelt gateway. Men hvis et dashboard er baseret på *adskillige* rapporter, så kan du bruge en dedikeret gateway til hver bidragende rapport og derigennem distribuere gateway-belastningen mellem de pågældende rapporter, der bidrager til det enkelte dashboard.

### <a name="connection-type"></a>Forbindelsestype

**Power BI** giver mulighed for to typer forbindelser: **DirectQuery** og **Import**. Ikke alle datakilder understøtter begge forbindelsestyper, og mange årsager kan bidrage til, at man vælger den ene frem for den anden, som f.eks. sikkerhedskrav, ydeevne, datagrænser og datamodelstørrelser. Du kan få mere at vide om forbindelsestyper og understøttede datakilder ved at se [listen over tilgængelige datakildetyper](service-gateway-data-sources.md#list-of-available-data-source-types).

Brugen af gatewayen kan variere, afhængigt af den anvendte forbindelsestype. Du bør f.eks. altid prøve at adskille **DirectQuery**-datakilder fra **Planlagt opdatering**-datakilder, når det er muligt (hvis altså de er i forskellige rapporter og kan adskilles). Dette forhindrer, at gatewayen ophobes med tusindvis af DirectQuery-anmodninger samtidigt med morgenens planlagte opdatering af en stor datamodelstørrelse, der bruges til virksomhedens primære dashboard. Følgende overvejelser bør tages i hver situation:

* **Planlagt opdatering**: Afhængigt af din forespørgselstørrelse og antallet af foretagne opdateringer pr. dag kan du vælge at forblive mellem de anbefalede mindstekrav til hardware eller opgradere til en computer med større ydeevne. Hvis en given forespørgsel ikke foldes, så sker transformationen på gatewayens computer og dermed drager gatewayens computer fordel af at have mere tilgængelig RAM.

* I relation til **DirectQuery**: En forespørgsel sendes hver gang, en given bruger åbner rapporten eller gransker data. Så hvis du forventer, at flere end 1000 brugere tilgår data samtidigt, så bør du sørge for, at din computer har robuste og kapacitetstunge hardwarekomponenter. Flere CPU-kerner vil resultere i et forbedret gennemløb for en **DirectQuery**-forbindelse.

Du kan finde kravene til den computer, som du installerer på, under [installationskrav](/data-integration/gateway/service-gateway-install#requirements) for datagatewayen i det lokale miljø.

### <a name="location"></a>Placering

Gateway-installationens placering kan have stor indvirkning på din forespørgselsydeevne, så du bør sørge for, at din gateway, datakildeplacering og Power BI-lejeren er placeret så tæt på hinanden som muligt for at minimere netværksventetid. For at fastsætte din Power BI-lejerplacering i Power BI-tjenesten, skal du vælge **?** - ikonet i det øverste højre hjørne og vælge **Om Power BI**.

![Bestem placering af Power BI-lejer](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_02.png)

Hvis du planlægger at bruge Power BI-gatewayen med Azure Analysis Services, skal du også sørge for, at dataområderne i begge matcher. Se [denne video](https://guyinacube.com/2018/01/power-bi-azure-analysis-services-gateway-data-region/) for at få flere oplysninger om, hvordan du angiver dataområder for flere tjenester.

## <a name="next-steps"></a>Næste trin

* [Konfiguration af proxyindstillinger](/data-integration/gateway/service-gateway-proxy)  
* [Foretag fejlfinding af gateways – Power BI](service-gateway-onprem-tshoot.md)  
* [Ofte stillede spørgsmål om datagatewayen i det lokale miljø – Power BI](service-gateway-power-bi-faq.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

