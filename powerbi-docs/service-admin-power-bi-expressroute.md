---
title: Power BI og ExpressRoute
description: Power BI og ExpressRoute
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Administration
ms.openlocfilehash: 3438fcb1fed71345454d1e518a3d87487b884f38
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34295968"
---
# <a name="power-bi-and-expressroute"></a>Power BI og ExpressRoute
Du kan bruge **Power BI** og **ExpressRoute** til at oprette en privat netværksforbindelse fra din organisation til Power BI (eller bruge en ISP's colocation-facilitet), der omgår internettet og sørger for en bedre sikkerhed for følsomme Power BI-data og -forbindelser.

**ExpressRoute** er en Azure-tjeneste, der gør det muligt at oprette private forbindelser mellem Azure-datacentre (hvor Power BI findes) og infrastrukturen i det lokale miljø, eller oprette private forbindelser mellem Azure-datacentre og colocation-miljøet.

![](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)

Du kan [få flere oplysninger om ExpressRoute](https://azure.microsoft.com/services/expressroute/) eller få at vide,[hvordan du tilmelder dig](https://azure.microsoft.com/pricing/details/expressroute/).

> [!NOTE]
> Power BI er understøttet i offentlig peering-tilstand, som beskrevet i [disse ofte stillede spørgsmål](https://docs.microsoft.com/azure/expressroute/expressroute-faqs).
> 
> 

## <a name="power-bi-expressroute-exceptions"></a>Undtagelser til Power BI ExpressRoute
Power BI er kompatibel med ExpressRoute med et par undtagelser, hvor Power BI henter eller sender data over det offentlige Internet. Disse specifikke undtagelser omfatter statiske data, som f.eks browserkonfigurationsfiler, der hentes fra noden til det nærmeste **netværk, der leverer indhold (CDN)**. Der findes nogle bredtfavnende undtagelser, som gælder for hele Power BI, og der findes nogle service- eller funktionsspecifikke undtagelser, der særskilt dokumenteres i de følgende afsnit.

### <a name="overall-exceptions-to-power-bi-and-expressroute"></a>Generelle undtagelser for Power BI og ExpressRoute
En undtagelse for **Power BI** og **ExpressRoute** betyder, at data, der bliver sendt til eller fra Power BI, føres over det offentlige internet, i stedet for at de bliver sendt over det private ExpressRoute-link.

De to overordnede undtagelser for Power BI ved anvendelse af ExpressRoute er:

* Statiske filer, der er hentet fra **netværk, der leverer indhold** og websteder
* **Telemetri**-data, der sendes via det offentlige Internet

Power BI bruger flere **netværk, der leverer indhold** eller websteder til effektivt at distribuere det nødvendige statiske indhold og filer til brugere baseret på geografisk landestandard via det offentlige internet. Disse statiske filer omfatter produktoverførsler (f.eks. **Power BI Desktop**, **datagateway i det lokale miljø** eller **Power BI-indholdspakker** fra forskellige uafhængige tjenesteudbydere), browserkonfigurationsfiler, der bruges til at starte og etablere relevante efterfølgende forbindelser med Power BI, samt den indledende sikre Power BI-logonside – de faktiske legitimationsoplysninger sendes kun via ExpressRoute.   

Visse **telemetridata** sendes også over det offentlige internet og over ExpressRoute. Telemetridata omfatter statistikker over brug og lignende data, som sendes til tjenester, der bruges til at overvåge brug og aktivitet.

### <a name="power-bi-saas-application-and-expressroute"></a>Power BI SaaS-program og ExpressRoute
Når en bruger starter en forbindelse til Power BI-tjenesten (powerbi.com eller gennem Cortana), hentes Power BI-landingssiden, logonsiden og statiske filer, der forbereder browseren til at etablere forbindelse til og interagere med Power BI, fra en CDN eller hjemmesider, som opretter forbindelse over det offentlige internet.

Når logon er etableret, foregår der efterfølgende Power BI-datainteraktion over ExpressRoute, med undtagelse af visse funktioner og tjenester, der afhænger af offentlige internet-data:

* **Kortvisningselementer** kræver forbindelse og dataoverførsel til Bing Virtual Earth-tjenesten eller geokodningstjenesten i Bing, som etableres over det offentlige Internet.
* Power BI-integration med **Cortana** kræver adgang til Bing over det offentlige internet.
* Når **brugerdefinerede links** tilføjes af en bruger, f.eks. en billedwidget eller en video, så anmoder Power BI om data baseret på linket, der er angivet af brugeren, som måske eller måske ikke bruger ExpressRoute.
* Brugere kan sende **feedback til Power BI** som tekst (og evt. billeder) over User Voice-feedbackmekanismen, som sender over det offentlige Internet.
* **Bing News-indholdsudbyderen** henter indhold fra Bing over det offentlige Internet.
* Når der oprettes forbindelse til **apps** (f.eks. indholdspakker), bliver brugere ofte anmodet om at indtaste legitimationsoplysninger og indstillinger ved hjælp af sider tilvejebragt af SaaS-leverandøren. Sider af denne art bruger måske eller måske ikke ExpressRoute.

| Brugeraktivitet | Destination |
| --- | --- |
| Landingsside (før logon) |`maxcdn.bootstrapcdn.com ; ajax.aspnetcdn.com ; netdna.bootstrapcdn.com ; cdn.optimizely.com; google-analytics.com ` |
| Logon |`*.mktoresp.com ; *.aadcdn.microsoftonline-p.com ; *.msecnd.com ; *.localytics.com ; ajax.aspnetcdn.com` |
| Dashboard, rapport, datasætadministration (omfatter kort og geokodning) |`*.localytics.com ; *.virtualearth.net ; platform.bing.com; powerbi.microsoft.com; c.microsoft.com; app.powerbi.com; *.powerbi.com; dc.services.visualstudio.com ` |
| Support |`support.powerbi.com ; powerbi.uservoice.com ; go.microsoft.com ` |

### <a name="power-bi-desktop-and-expressroute"></a>Power BI Desktop og ExpressRoute
Power BI Desktop er også ExpressRoute-kompatibelt med nogle få undtagelser, der er beskrevet på listen nedenfor:

* **Opdateringsmeddelelser**, der bruges til at finde ud af, om brugere har den nyeste version af Power BI Desktop, sendes via det offentlige Internet.
* Visse **telemetridata** sendes via det offentlige Internet.
* **Kortvisningselementer** kræver forbindelse og dataoverførsel til **Bing Virtual Earth**-tjenesten eller **geokodningstjenesten i Bing**, som begge etableres over det offentlige Internet.
* **Hent data** fra flere datakilder såsom **Web** eller SaaS-tredjepartsleverandører overføres via det offentlige Internet.

### <a name="power-bi-paas-and-expressroute"></a>Power BI PaaS og ExpressRoute
Power BI leverer API'er og andre platformsbaserede funktioner, som giver udviklere mulighed for at oprette tilpassede Power BI-løsninger og apps. Følgende tjenester, udover telemetri og CDN-data beskrevet tidligere i dette emne, bruges ved overførsel af Power BI PaaS-data via det offentlige internet:

| PaaS-aktivitet | Yderligere anvendte destinationer |
| --- | --- |
| Offentlig integrering (telemetri) |`c1.microsoft.com` |
| Brugerdefinerede visuelle elementer (CDN) |`*.azureedge.net` |

Nogle **brugerdefinerede visuals** er oprettet af tredjeparter, andre er oprettet af Microsoft. De bruger måske eller måske ikke ExpressRoute.

### <a name="power-bi-mobile-and-expressroute"></a>Power BI Mobile og ExpressRoute
Dette dokument berører ikke brug af Power BI-mobilapps.  

### <a name="on-premises-data-gateway-and-expressroute"></a>Datagateway og ExpressRoute i det lokale miljø
Når en **datagateway i det lokale miljø** bruges med Power BI, er overførsler kompatible med ExpressRoute med undtagelse af brugeraktiviteterne, der er dokumenteret i afsnittet **Power BI SaaS-program og ExpressRoute** tidligere i dette emne.  

