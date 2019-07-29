---
title: Administrer din datakilde – Import/Planlagt opdatering
description: Sådan administrerer du en datagateway i det lokale miljø samt de datakilder, der hører til denne gateway. Denne artikel gælder kun for de datakilder, der kan bruges med import/planlagt opdatering.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2a3cdc3e6c4fc4f18613994a919f8ab733df5e14
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271680"
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>Administrer din datakilde – Import/Planlagt opdatering

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Når du har [installeret datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-install), skal du [tilføje datakilder](service-gateway-data-sources.md#add-a-data-source), der kan bruges sammen med gatewayen. Denne artikel indeholder oplysninger om, hvordan du arbejder med gateways og datakilder, der bruges til planlagte opdateringer, i modsætning til DirectQuery eller direkte forbindelser.

## <a name="add-a-data-source"></a>Tilføj en datakilde

Du kan finde oplysninger om, hvordan du tilføjer en datakilde i [Tilføj en datakilde](service-gateway-data-sources.md#add-a-data-source).

Alle datakildetyper, der er angivet på listen, kan bruges til planlagte opdateringer med datagatewayen i det lokale miljø. Analysis Services, SQL Server og SAP HANA kan bruges til enten planlagte opdateringer eller DirectQuery/direkte forbindelser.

![Vælg datakilde](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

Du skal derefter udfylde oplysninger om datakilden, herunder kildeoplysninger og legitimationsoplysninger, som skal bruges til at få adgang til datakilden.

> [!NOTE]
> Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Hvis du vil have mere at vide om, hvor legitimationsoplysningerne gemmes, skal du se [Lagring af krypterede legitimationsoplysninger i cloudmiljøet](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud).

![Angivelse af indstillinger for datakilden](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

Du kan få vist en liste over datakildetyper, der kan bruges til planlagte opdateringer, i [Liste over tilgængelige datakildetyper](service-gateway-data-sources.md#list-of-available-data-source-types).

Vælg **Tilføj**, når du har udfyldt det hele. Du kan nu bruge denne datakilde til planlagt opdatering med dine data i det lokale miljø. Du får vist *Forbindelsen blev oprettet*, hvis det lykkes.

![Visning af forbindelsesstatus](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

### <a name="advanced-settings"></a>Avancerede indstillinger

Du kan eventuelt konfigurere niveauet for beskyttelse af personlige oplysninger for datakilden. Dette styrer, hvordan data kan kombineres. Dette bruges kun for planlagte opdateringer. Hvis du vil vide mere om niveauer for beskyttelse af personlige oplysninger, skal du se [Niveauer for beskyttelse af personlige oplysninger (Power-forespørgsel)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Angivelse af niveauet for beskyttelse af personlige oplysninger](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="using-the-data-source-for-scheduled-refresh"></a>Brug af datakilden med planlagt opdatering

Når du har oprettet datakilden, bliver den tilgængelig til brug med enten DirectQuery-forbindelser eller via en planlagt opdatering.

> [!NOTE]
> Servernavnet og databasenavnet skal matche mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø.

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse skal stemme overens. Hvis du f.eks. angiver en IP-adresse for servernavnet i Power BI Desktop, skal du bruge IP-adressen for datakilden i konfigurationen af gatewayen. Hvis du bruger *SERVER\INSTANCE* i Power BI Desktop, skal du bruge det samme i den datakilde, der er konfigureret for gatewayen.

Hvis du er angivet under fanen **Brugere** i den datakilde, der er konfigureret i gatewayen, og server- og databasenavnet stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med en planlagt opdatering.

![Visning af brugerne](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> Hvis dit datasæt indeholder flere datakilder, skal hver enkelt datakilde tilføjes i gatewayen. Hvis en eller flere datakilder ikke er føjet til gatewayen, kan du ikke se gatewayen som tilgængelig i forbindelse med en planlagt opdatering.

## <a name="limitations"></a>Begrænsninger

OAuth er ikke en understøttet godkendelsesplan for datagatewayen i det lokale miljø. Du kan ikke tilføje datakilder, der kræver OAuth. Hvis dit datasæt har en datakilde, der kræver OAuth, kan du ikke bruge gatewayen til planlagt opdatering.

## <a name="next-steps"></a>Næste trin

* [Fejlfinding af datagateway i det lokale miljø](/data-integration/gateway/service-gateway-tshoot)
* [Foretag fejlfinding af gateways – Power BI](service-gateway-onprem-tshoot.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
