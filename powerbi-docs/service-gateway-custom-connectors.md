---
title: Brug brugerdefinerede dataconnectors med datagatewayen i det lokale miljø
description: Du kan bruge brugerdefinerede dataconnectors med datagatewayen i det lokale miljø.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 51d03582ec91b926526a075a356323eb4f95a84b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "77609874"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Brug brugerdefinerede dataconnectors med datagatewayen i det lokale miljø

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Med dataconnectors til Power BI kan du oprette forbindelse til og få adgang til data fra et program, en tjeneste eller en datakilde. Du kan udvikle brugerdefinerede dataconnectors og bruge dem i Power BI Desktop.

Hvis du vil vide mere om, hvordan du udvikler brugerdefinerede dataconnectors til Power BI, skal du se [GitHub-siden om SDK til dataconnector](https://aka.ms/dataconnectors). Dette websted indeholder oplysninger om, hvordan du kommer godt i gang og eksempler til Power BI og Power Query.

Når du opretter rapporter i Power BI Desktop, der bruger brugerdefinerede dataconnectors, kan du bruge datagatewayen i det lokale miljø til at opdatere rapporterne fra Power BI-tjenesten.

## <a name="enable-and-use-this-capability"></a>Aktivér og brug denne funktionalitet

Når du installerer versionen fra juli 2018 af datagatewayen i det lokale miljø eller en nyere version, kan du se fanen **Connectors** i programmet til datagatewayen i det lokale miljø. I feltet **Indlæs brugerdefinerede dataconnectors fra mappe** skal du vælge en mappe, der kan tilgås af den bruger, som kører gatewaytjenesten. Standardbrugeren er *NT SERVICE\PBIEgwService*. Gatewayen indlæser automatisk de brugerdefinerede connectorfiler, der er placeret i den pågældende mappe. De vises på listen over dataconnectors.

![Brugerdefinerede datatilslutninger](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Hvis du bruger datagatewayen i det lokale miljø (personlig tilstand), kan du uploade din Power BI-rapport til Power BI-tjenesten og bruge gatewayen til at opdatere den.

Du skal oprette en datakilde til din brugerdefinerede connector i forbindelse med datagatewayen i det lokale miljø. På siden med indstillinger for gatewayen i Power BI-tjenesten skulle der blive vist en indstilling, når du vælger gatewayklyngen for at tillade brugen af brugerdefinerede connectors med denne klynge. Sørg for, at alle gateways i klyngen har juli 2018-udgivelsen eller nyere, for at indstillingen er tilgængelig. Vælg indstillingen for at aktivere brugen af brugerdefinerede connectors med denne klynge.

![Siden Indstillinger for gatewayklynge](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Når denne indstilling er aktiveret, kan du se dine brugerdefinerede connectors som tilgængelige datakilder, du kan oprette under denne gatewayklynge. Når du har oprettet en datakilde, som bruger din nye brugerdefinerede connector, kan du opdatere Power BI-rapporter ved hjælp af den brugerdefinerede connector i Power BI-tjenesten.

![Siden Indstillinger for datakilde](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* Kontrollér, at den mappe, du opretter, er tilgængelig for gatewaytjenesten i baggrunden. Mapper under din brugers Windows-mappe eller systemmapper vil normalt ikke være tilgængelige. Der vises en meddelelse i programmet for datagatewayen i det lokale miljø, hvis der ikke er adgang til mappen. Denne instruktion gælder ikke for datagatewayen i det lokale miljø (personlig tilstand).
* Hvis brugerdefinerede connectors skal kunne fungere sammen med datagatewayen i det lokale miljø, skal de implementere sektionen "TestConnection" i koden til den brugerdefinerede connector. Dette afsnit er ikke påkrævet, når du bruger brugerdefinerede connectors med Power BI Desktop. Du kan derfor have en connector, der fungerer sammen med Power BI Desktop, men ikke med gatewayen. Du kan finde flere oplysninger om, hvordan du implementerer afsnittet TestConnection i [denne dokumentation](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support).
* OAuth for brugerdefinerede connectorer via gateways understøttes i øjeblikket kun for gatewayadministratorer, men ikke for andre brugere af datakilder.

## <a name="next-steps"></a>De næste trin

* [Administrer din datakilde – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Administrer din datakilde – SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Administrer din datakilde – SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Administrer din datakilde – Oracle](service-gateway-onprem-manage-oracle.md)  
* [Administrer din datakilde – Import/planlagt opdatering](service-gateway-enterprise-manage-scheduled-refresh.md)
* [Konfigurer proxyindstillinger for datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-proxy)
* [Brug Kerberos til SSO (enkeltlogon) fra Power BI til datakilder i det lokale miljø](service-gateway-sso-kerberos.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/).
