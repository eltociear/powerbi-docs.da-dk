---
title: Datagateway i det lokale miljø
description: Dette er en oversigt over datagatewayen i det lokale miljø til Power BI. Du kan bruge denne gateway til at arbejde med DirectQuery-datakilder. Du kan også bruge denne gateway til at opdatere clouddatasæt med data i det lokale miljø.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/26/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 21ceec0ea522bd45a937096bcd778f2695c1edc3
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="on-premises-data-gateway"></a>Datagateway i det lokale miljø

En datagateway i det lokale miljø fungerer som en bro, der giver hurtig og sikker dataoverførsel mellem data i det lokale miljø (data, der ikke er i cloudmiljøet) og tjenesterne Power BI, Microsoft Flow, Logic Apps og PowerApps.

Du kan bruge en enkelt gateway sammen med forskellige tjenester på samme tid. Hvis du både bruger Power BI og PowerApps, kan der bruges en enkelt gateway til begge dele. Det afhænger af den konto, du logger på med.

> [!NOTE]
> Datagatewayen i det lokale miljø implementerer datakomprimering og transportkryptering i alle tilstande.
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Begrænsninger for Analysis Services-liveforbindelser
Du kan bruge en liveforbindelse til tabellariske eller flerdimensionelle forekomster.

| **Serverversion** | **Påkrævet SKU** |
| --- | --- |
| 2012 SP1 CU4 eller nyere |Business Intelligence- og Enterprise-SKU |
| 2014 |Business Intelligence- og Enterprise-SKU |
| 2016 |Standard-SKU eller nyere |

* Funktionen til formatering på celleniveau og oversættelse understøttes ikke.
* Handlinger og navngivne sæt er ikke synlige for Power BI, men du kan stadig oprette forbindelse til flerdimensionelle kuber, der også indeholder handlinger eller navngivne sæt, og oprette visuelle elementer og rapporter.

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>Download og installér datagatewayen i det lokale miljø
Hvis du vil downloade gatewayen, skal du vælge **Datagateway** i menuen Downloads. Download [datagatewayen i det lokale miljø](http://go.microsoft.com/fwlink/?LinkID=820925).

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>Installér gatewayen i personlig tilstand
> [!NOTE]
> Personal fungerer kun med Power BI.
> 
> 

Når den personlige gateway er installeret, skal du starte **guiden Konfiguration af Power BI Gateway – Personal**.

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

Du skal derefter logge på Power BI for at registrere gatewayen i cloudtjenesten.

![](media/service-gateway-onprem/personal-gateway-signin.png)

Du skal også angive brugernavn og adgangskode til Windows, som Windows-tjenesten skal køre som. Du kan angive en anden Windows-konto fra din egen. Gatewaytjenesten kører med denne konto.

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

Når installationen er fuldført, skal du gå til dine datasæt i Power BI og sørge for, at der angives legitimationsoplysninger for dine datakilder i det lokale miljø.

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>Lagring af krypterede legitimationsoplysninger i clouden
Når du føjer en datakilde til gatewayen, skal du angive legitimationsoplysninger for den pågældende datakilde. Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Legitimationsoplysningerne krypteres sikkert ved hjælp af asymmetrisk kryptering, så de ikke kan dekrypteres i clouden, før de gemmes i clouden. Legitimationsoplysningerne sendes til den maskine, der kører gatewayen, hvor de dekrypteres, når datakilderne tilgås.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
* [Azure Information Protection](https://docs.microsoft.com/en-us/microsoft-365/enterprise/protect-files-with-aip
) understøttes ikke i øjeblikket
* [Access Online](https://products.office.com/en-us/access) understøttes ikke i øjeblikket

## <a name="tenant-level-administration"></a>Administration på lejerniveau 

Der er i øjeblikket ikke ét enkelt sted, hvor lejeradministratorer kan administrere alle de gateways, som andre brugere har installeret og konfigureret.  Hvis du er en lejeradministrator, anbefaler vi, at du beder brugerne i din organisation om at tilføje dig som administrator af hver enkelt gateway, de installerer. Dette gør det muligt for dig at administrere alle gateways i din organisation via siden Indstillinger for Gateway eller en via [PowerShell-kommandoer](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters). 


## <a name="troubleshooting"></a>Fejlfinding
Hvis du har problemer med at installere og konfigurere en gateway, skal du se [Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md). Hvis du mener, at du har et problem med din firewall, skal du se afsnittet om [firewall eller proxy](service-gateway-onprem-tshoot.md#firewall-or-proxy) i artiklen om fejlfinding.

Hvis du mener, at du oplever proxyproblemer med gatewayen, skal du se [Konfiguration af proxyindstillinger for Power BI-gateways](service-gateway-proxy.md).

## <a name="next-steps"></a>Næste trin
[Administrer din datakilde – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Administrer din datakilde – SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Administrer din datakilde – SQL Server](service-gateway-enterprise-manage-sql.md)  
[Administrer din datakilde – Oracle](service-gateway-onprem-manage-oracle.md)  
[Administrer din datakilde – Import/Planlagt opdatering](service-gateway-enterprise-manage-scheduled-refresh.md)  
[Datagateway i det lokale miljø – detaljeret](service-gateway-onprem-indepth.md)  
[Datagateway i det lokale miljø (personlig tilstand) – den nye version af den personlige gateway](service-gateway-personal-mode.md)
[Konfiguration af proxyindstillinger for datagatewayen i det lokale miljø](service-gateway-proxy.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

