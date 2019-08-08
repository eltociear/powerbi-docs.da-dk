---
title: Datagateway i det lokale miljø
description: Dene artikel er en oversigt over datagatewayen i det lokale miljø til Power BI. Du kan bruge denne gateway til at arbejde med DirectQuery-datakilder. Du kan også bruge denne gateway til at opdatere clouddatasæt med data i det lokale miljø.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 07/15/2019
ms.openlocfilehash: 883d5c83019df293628d096f5834c9b5c6d425b6
ms.sourcegitcommit: 73228d0a9038b8369369c059ad06168d2c5ff062
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/02/2019
ms.locfileid: "68730280"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Hvad er en datagateway i det lokale miljø?

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Datagateway'en i det lokale miljø fungerer som en bro, der giver hurtig og sikker dataoverførsel mellem lokale data (data, der ikke er i cloudmiljøet) og adskillige Microsoft-cloudtjenester. Disse cloudtjenester omfatter Power BI, PowerApps, Microsoft Flow, Azure Analysis Services og Azure Logic Apps. Ved hjælp af en gateway kan organisationer opbevare databaser og andre datakilder på deres netværk i det lokale miljø og samtidig bruge disse data i det lokale miljø sikkert i cloudtjenester.

## <a name="how-the-gateway-works"></a>Sådan virker gatewayen

![Oversigt over gateways](media/service-gateway-onprem/on-premises-data-gateway.png)

Du kan finde flere oplysninger om, hvordan gatewayen fungerer i [Arkitektur for datagateway i det lokale miljø](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Typer af gateways

Der er to forskellige typer gateways til hvert sit scenarie:

* **Datagateway i det lokale miljø** gør det muligt for flere brugere at oprette forbindelse til flere datakilder i det lokale miljø. Du kan bruge en datagateway i det lokale miljø til alle understøttede tjenester med en enkelt gatewayinstallation. Denne gateway er velegnet til komplekse scenarier, hvor flere personer tilgår flere datakilder.

* **Datagateway i det lokale miljø (personlig tilstand)** gør det muligt for én bruger at oprette forbindelse til datakilder og kan ikke deles med andre. En datagateway i det lokale miljø (personlig tilstand) kan kun bruges med Power BI. Denne gateway er velegnet til scenarier, hvor du er den eneste, der opretter rapporter, og du ikke behøver at dele datakilder med andre.

## <a name="use-a-gateway"></a>Brug en gateway

Du skal udføre fire primære trin, når du vil bruge en gateway.

1. [Download og installér gatewayen](/data-integration/gateway/service-gateway-install) på en lokal computer.
2. [Konfigurer](/data-integration/gateway/service-gateway-app) gatewayen på baggrund af din firewall og andre netværkskrav.
3. [Tilføj gatewayadministratorer](/data-integration/gateway/service-gateway-manage), der også kan administrere andre netværkskrav.
4. [Foretag fejlfinding](service-gateway-onprem-tshoot.md) af gatewayen i tilfælde af fejl.

## <a name="next-steps"></a>Næste trin

* [Installér datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-install)


Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
