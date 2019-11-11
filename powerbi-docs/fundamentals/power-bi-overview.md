---
title: Hvad er Power BI?
description: Oversigt over Power BI, og hvordan de forskellige dele passer sammen – Power BI Desktop, Power BI-tjeneste, Power BI Mobil, rapportserver og Power BI Embedded.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: overview
ms.date: 09/04/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 9da9465bea8512b541d3f1af3983df70d184ac26
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875665"
---
# <a name="what-is-power-bi"></a>Hvad er Power BI?
**Power BI** er en samling af softwaretjenester, apps og forbindelser, der arbejder sammen for at forvandle usammenhængende data til faste, visuelt fordybende og interaktive indsigter. Dine data kan være et Excel-regneark eller en samling cloudbaserede hybride data warehouses og hybride data warehouses i det lokale miljø. Med Power BI kan du nemt oprette forbindelse til dine datakilder, visualisere og finde vigtigt indhold samt dele det med alle, du vil.

## <a name="the-parts-of-power-bi"></a>Delene i Power BI
Power BI består af: 
- Et skrivebordsprogram til Windows, der hedder **Power BI Desktop**.
- En onlinetjeneste af typen SaaS (*Software som en service*) kaldet **Power BI-tjeneste**. 
- Power BI-**mobilapps** til Windows-, iOS- og Android-enheder.

![Power BI Desktop, tjeneste, mobil](media/power-bi-overview/power-bi-overview-blocks.png)

Disse tre elementer &mdash; Power BI Desktop, tjenesten og mobilappsene &mdash; er designet til at lade dig oprette, dele og bruge forretningsindsigt på en måde, der opfylder dit behov og din rolle mest effektivt.

Med det fjerde element **Power BI-rapportserver** kan du publicere Power BI-rapporter til en server i det lokale miljø, når du har oprettet dem i Power BI Desktop. Læs mere om [Power BI-rapportserver](#on-premises-reporting-with-power-bi-report-server).

## <a name="how-power-bi-matches-your-role"></a>Sådan passer Power BI til din rolle
Din brug af Power BI kan afhænge af din rolle i et projekt eller på et team. Andre personer med andre roller bruger måske Power BI på en anden måde.

Du bruger f.eks. primært **Power BI-tjenesten** til at få vist rapporter og dashboards. En talfokuseret kollega med ansvar for oprettelse af forretningsrapporter bruger måske overvejende **Power BI Desktop** til oprettelse af rapporter og udgiver derefter de pågældende rapporter til Power BI-tjenesten, hvor du kan se dem. En anden kollega arbejder måske med salg og bruger hovedsageligt **Power BI-telefonappen** til at overvåge sine salgskvoter og til at analysere nye salgsemners oplysninger.

Hvis du er udvikler, bruger du måske Power BI-API'er til at pushe data til datasæt eller til at integrere dashboards og rapporter i dine egne brugerdefinerede programmer. Har du en ide til et nyt visuelt element? Skab det selv, og del det med andre.  

Det kan også være, du bruger alle elementer af Power BI på forskellige tidspunkter, afhængigt af hvad du arbejder med, eller hvad din rolle er i et bestemt projekt.

Den måde, du bruger Power BI på, kan være baseret på, hvilken funktion eller tjeneste i Power BI der er det bedste værktøj i din situation. Du kan f.eks. bruge Power BI Desktop til at oprette rapporter for dit eget team om statistikker for kundeengagementer, og du kan få vist lager og produktionsfremskridt på et dashboard i realtid i Power BI-tjenesten. Alle dele af Power BI er tilgængelige for dig, og derfor er det fleksibelt og overbevisende.

Udforsk dokumenter, der er relevante for din rolle:
- Power BI Desktop til [*designere*](../desktop-what-is-desktop.md)
- Power BI for [*forbrugere*](../consumer/end-user-consumer.md)
- Power BI for [*udviklere*](../developer/what-can-you-do.md)
- Power BI for [*administratorer*](../service-admin-administering-power-bi-in-your-organization.md)

## <a name="the-flow-of-work-in-power-bi"></a>Arbejdsgangen i Power BI
En typisk arbejdsgang i Power BI starter med at oprette forbindelse til datakilder og at oprette en rapport i Power BI Desktop. Du publicerer derefter den pågældende rapport fra Power BI Desktop til Power BI-tjenesten og deler den, så slutbrugerne i Power BI-tjenesten og på mobilenhederne kan se og interagere med rapporten.
Denne arbejdsproces er almindelig og viser, hvordan de tre hovedelementer i Power BI komplementerer hinanden.

Her er en detaljeret [sammenligning af Power BI Desktop og Power BI-tjenesten](../designer/service-service-vs-desktop.md).

## <a name="on-premises-reporting-with-power-bi-report-server"></a>Rapportering i det lokale miljø med Power BI-rapportserveren

Men hvad hvis du ikke er klar til at flytte til et cloudbaseret miljø og har brug for at beholde dine rapporter bag en firmafirewall?  Læs videre.

Du kan oprette, udrulle og administrere Power BI – Mobil og sideinddelte rapporter i det lokale miljø med udvalget af brugsklare værktøjer og tjenester, som Power BI-rapportserver indeholder.

![diagram til det lokale miljø](media/power-bi-overview/power-bi-report-server2.png)

Power BI-rapportserveren er en løsning, som du udruller bag firewallen, og som derefter leverer dine rapporter til de rette brugere på forskellige måder, uanset om de skal vises i en webbrowser, på en mobilenhed eller som en mail. Og da Power BI-rapportserveren er kompatibel med Power BI i clouden, kan du flytte til clouden, når du er klar. 

Læs mere om [Power BI-rapportserver](../report-server/get-started.md).

## <a name="next-steps"></a>Næste trin
- [Hurtig introduktion: Find vej i Power BI-tjenesten](../service-the-new-power-bi-experience.md)   
- [Selvstudium: Kom i gang med Power BI-tjenesten](../service-get-started.md)
- [Hurtig introduktion: Opret forbindelse til data i Power BI Desktop](../desktop-quickstart-connect-to-data.md)
