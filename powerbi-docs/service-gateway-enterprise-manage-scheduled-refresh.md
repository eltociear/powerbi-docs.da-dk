---
title: "Administrer din datakilde – Import/Planlagt opdatering"
description: "Sådan administrerer du en datagateway i det lokale miljø samt de datakilder, der hører til denne gateway. Denne artikel gælder kun for de datakilder, der kan bruges med import/planlagt opdatering."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 8002cf2df278cd3329b62b5322a6faabc9394f57
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>Administrer din datakilde – Import/Planlagt opdatering
Når du har installeret datagatewayen i det lokale miljø, skal du tilføje datakilder, der kan bruges sammen med gatewayen. Denne artikel indeholder oplysninger om, hvordan du arbejder med gateways og datakilder, der bruges til planlagt opdatering, i modsætning til DirectQuery eller direkte forbindelser.

## <a name="download-and-install-the-gateway"></a>Download og installér gatewayen
Du kan downloade gatewayen fra Power BI-tjenesten. Vælg **Downloads** > **Datagateway**, eller gå til [siden til download af gateway](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Tilføj en gateway
Hvis du vil tilføje en gateway, skal du blot [downloade](https://go.microsoft.com/fwlink/?LinkId=698863) og installere virksomhedsgatewayen på en server i dit miljø. Når du har installeret gatewayen, vises den på listen over gateways under **Administrer gateways**.

> [!NOTE]
> **Administrer gateways** vises ikke, før du er administrator af mindst én gateway. Det kan du blive ved enten at blive tilføjet som administrator eller ved at installere og konfigurere en gateway.
> 
> 

## <a name="remove-a-gateway"></a>Fjern en gateway
Hvis du fjerner en gateway, slettes også eventuelle datakilder under denne gateway.  Dette vil også ødelægge alle dashboards og rapporter, der anvender disse datakilder.

1. Vælg tandhjulsikonet ![](media/service-gateway-enterprise-manage-scheduled-refresh/pbi_gearicon.png) i øverste højre hjørne > **Administrer gateways**.
2. Gateway > **Fjern**
   
   ![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Tilføj en datakilde
Du kan tilføje en datakilde ved enten at vælge en gateway og klikke på **Tilføj datakilde** eller gå til Gateway > **Tilføj datakilde**.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings1.png)

Du kan derefter vælge **Datakildetype** på listen. Alle datakilder, der er angivet på listen, kan bruges til planlagt opdatering med virksomhedsgatewayen. Analysis Services, SQL Server og SAP HANA kan enten bruges til planlagt opdatering eller DirectQuery/direkte forbindelser.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

Du skal derefter angive oplysninger om datakilden, herunder kildeoplysninger og -legitimationsoplysninger, som skal bruges til at få adgang til datakilden.

> [!NOTE]
> Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Du kan finde flere oplysninger i hovedartiklen om datagateways i det lokale miljø, hvor det beskrives, hvordan du gemmer [legitimationsoplysninger](service-gateway-onprem.md#credentials).
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

Du kan klikke på **Tilføj**, når du har udfyldt det hele.  Du kan nu bruge denne datakilde til planlagt opdatering med dine data i det lokale miljø. Du får vist *Forbindelsen blev oprettet*, hvis det lykkes.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

### <a name="advanced-settings"></a>Avancerede indstillinger
Du kan konfigurere niveauet for beskyttelse af personlige oplysninger for datakilden. Dette styrer, hvordan data kan blandes. Dette bruges kun til planlagt opdatering. [Få mere at vide](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Fjern en datakilde
Hvis du fjerner en datakilde, ødelægger det alle dashboards eller rapporter, der anvender den pågældende datakilde.  

Hvis du vil fjerne en datakilde, skal du gå til datakilden > **Fjern**.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings6.png)

## <a name="manage-administrators"></a>Administrer administratorer
Under fanen Administratorer for gatewayen kan du tilføje og fjerne brugere, som kan administrere gatewayen. Du kan kun tilføje brugere på nuværende tidspunkt. Sikkerhedsgrupper kan ikke tilføjes.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings8.png)

## <a name="manage-users"></a>Administrer brugere
Under fanen Brugere for datakilden kan du tilføje og fjerne brugere eller sikkerhedsgrupper, som kan bruge denne datakilde.

> [!NOTE]
> Listen over brugere kan kun bruges til at styre, hvem der har tilladelse til at publicere rapporter. Rapporternes ejere kan oprette dashboards eller indholdspakker og dele dem med andre brugere.
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings5.png)

## <a name="using-the-data-source-for-scheduled-refresh"></a>Brug af datakilden med planlagt opdatering
Når du har oprettet datakilden, bliver den tilgængelig til brug med enten DirectQuery-forbindelser eller via planlagt opdatering.

> [!NOTE]
> Server- og databasenavn skal stemme overens mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø!
> 
> 

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse skal stemme overens. Hvis du f.eks. angiver en IP-adresse for servernavnet i Power BI Desktop, skal du bruge IP-adressen til datakilden i konfigurationen af gatewayen. Hvis du bruger *SERVER\FOREKOMST* i Power BI Desktop, skal du bruge det samme i den datakilde, der er konfigureret for gatewayen.

Hvis du er angivet på fanen **Brugere** for den datakilde, der er konfigureret i gatewayen, og server- og databasenavnet stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med planlagt opdatering.

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> Hvis dit datasæt indeholder flere datakilder, skal hver enkelt datakilde tilføjes i gatewayen. Hvis en eller flere datakilder ikke er føjet til gatewayen, kan du ikke se gatewayen som tilgængelig i forbindelse med planlagt opdatering.
> 
> 

## <a name="limitations"></a>Begrænsninger
* OAuth er ikke en understøttet godkendelsesplan for datagatewayen i det lokale miljø. Du kan ikke tilføje datakilder, der kræver OAuth. Hvis dit datasæt har en datakilde, der kræver OAuth, kan du ikke bruge gatewayen til planlagt opdatering.

## <a name="next-steps"></a>Næste trin
[Datagateway i det lokale miljø](service-gateway-onprem.md)  
[Datagateway i det lokale miljø – detaljeret](service-gateway-onprem-indepth.md)  
[Fejlfinding af datagateway i det lokale miljø](service-gateway-onprem-tshoot.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

