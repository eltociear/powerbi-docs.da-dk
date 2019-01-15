---
title: Brug brugerdefinerede dataconnectors med datagatewayen i det lokale miljø
description: Du kan bruge brugerdefinerede dataconnectors med datagatewayen i det lokale miljø.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/08/2018
LocalizationGroup: Gateways
ms.openlocfilehash: b3eb244cb09b26855bdd5284f781f2c5aa188100
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54283822"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Brug brugerdefinerede dataconnectors med datagatewayen i det lokale miljø

Med dataconnectors til Power BI kan du oprette forbindelse til og få adgang til data fra et program, en tjeneste eller en datakilde. Du kan udvikle brugerdefinerede dataconnectors og bruge dem i Power BI Desktop.

Hvis du vil vide mere om, hvordan du udvikler brugerdefinerede dataconnectors til Power BI, skal du se dokumentationen [her](http://aka.ms/dataconnectors).

Når du opretter rapporter i Power BI Desktop, der bruger brugerdefinerede dataconnectors, kan du bruge datagatewayen i det lokale miljø til at opdatere rapporterne fra Power BI-tjenesten.

## <a name="here-is-a-guide-on-how-to-enable-and-use-this-capability"></a>Her er en vejledning i, hvordan du aktiverer og bruger denne funktion

Når du installerer juli 2018-versionen af datagatewayen i det lokale miljø eller en nyere version, kan du se fanen "Forbindelser" i konfigurationen, og du kan vælge en mappe, du vil indlæse brugerdefinerede connectors fra. Du skal vælge en mappe, som den bruger, der kører gatewaytjenesten, har adgang til (det er som standard “NT SERVICE\PBIEgwService”). Gatewayen indlæser automatisk filerne til den brugerdefinerede connector i mappen, og du skulle få dem vist på listen over dataconnectors.

![Brugerdefineret connector 1](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Hvis du bruger en personlig version af datagatewayen i det lokale miljø, skulle du kunne uploade din Power BI-rapport til Power BI-tjenesten og bruge gatewayen til at opdatere den.

I virksomhedsversionen af gatewayen skal du stadig oprette en datakilde til den brugerdefinerede connector. På siden med indstillinger for gatewayen i Power BI-tjenesten skulle der blive vist en ny indstilling, når du vælger gatewayklyngen for at tillade brugen af brugerdefinerede connectors med denne klynge. Sørg for, at alle gateways i klyngen har juli 2018-udgivelsen eller nyere, for at indstillingen er tilgængelig. Vælg indstillingen for at aktivere brugen af brugerdefinerede connectors med denne klynge.

![Brugerdefineret connector 2](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Når denne indstilling er aktiveret, kan du se dine brugerdefinerede connectors som datakilder, du kan oprette under denne gatewayklynge. Når du opretter en datakilde ved hjælp af den nye brugerdefinerede connector, kan du nu opdatere Power BI-rapporter ved hjælp af den brugerdefinerede connector i Power BI-tjenesten.

![Brugerdefineret connector 3](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* Kontrollér, at den mappe, du opretter, er tilgængelig for gatewaytjenesten i baggrunden. Mapper under din brugers Windows-mappe eller systemmapper vil normalt ikke være tilgængelige. I gatewaykonfigurationen vises der en meddelelse, hvis mappen ikke er tilgængelig (dette gælder ikke den personlige version af gatewayen)
* Hvis du vil kunne bruge brugerdefinerede connectors med datagatewayen i det lokale miljø, skal de implementere sektionen “TestConnection” i koden til den brugerdefinerede connector. Dette er ikke påkrævet, når du bruger brugerdefinerede connectors med Power BI Desktop. Derfor kan du have en, der virker med Desktop, men ikke med gatewayen. I [denne dokumentation](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support) kan du se, hvordan du implementerer sektionen TestConnection.

## <a name="next-steps"></a>Næste trin

* [Administrer din datakilde – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Administrer din datakilde – SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Administrer din datakilde – SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Administrer din datakilde – Oracle](service-gateway-onprem-manage-oracle.md)  
* [Administrer din datakilde – Import/Planlagt opdatering](service-gateway-enterprise-manage-scheduled-refresh.md)  
* [Datagateway i det lokale miljø, detaljeret](service-gateway-onprem-indepth.md)  
* [Datagateway i det lokale miljø (personlig tilstand)](service-gateway-personal-mode.md)
* [Konfigurer proxyindstillinger for datagatewayen i det lokale miljø](service-gateway-proxy.md)  
* [Brug Kerberos til SSO (enkeltlogon) fra Power BI til datakilder i det lokale miljø](service-gateway-sso-kerberos.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
