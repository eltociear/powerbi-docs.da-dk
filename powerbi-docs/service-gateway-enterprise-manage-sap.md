---
title: Administrer din datakilde – SAP HANA
description: Sådan administrerer du en datagateway i det lokale miljø samt de datakilder, der hører til denne gateway. Denne artikel er specifik for SAP HANA.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: a09388e8b22131c9b82771385b69142b18e3cc84
ms.sourcegitcommit: 73228d0a9038b8369369c059ad06168d2c5ff062
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/02/2019
ms.locfileid: "68730012"
---
# <a name="manage-your-data-source---sap-hana"></a>Administrer din datakilde – SAP HANA

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Når du har [installeret datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-install), skal du [tilføje datakilder](service-gateway-data-sources.md#add-a-data-source), der kan bruges sammen med gatewayen. Denne artikel indeholder oplysninger om, hvordan du arbejder med gateways og SAP HANA-datakilder, der enten bruges til planlagte opdateringer eller DirectQuery.

## <a name="add-a-data-source"></a>Tilføj en datakilde

Du kan finde oplysninger om, hvordan du tilføjer en datakilde i [Tilføj en datakilde](service-gateway-data-sources.md#add-a-data-source). Vælg SAP HANA som **datakildetype**.

![Tilføj SAP HANA-datakilden](media/service-gateway-enterprise-manage-sap/datasourcesettings2-sap.png)

Når du har valgt SAP HANA-datakildetypen, skal du derefter udfylde oplysninger om **Server**, **Brugernavn** og **Adgangskode** for datakilden.

> [!NOTE]
> Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Hvis du vil have mere at vide om, hvor legitimationsoplysningerne gemmes, skal du se [Lagring af krypterede legitimationsoplysninger i cloudmiljøet](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Angivelse af indstillinger for datakilden](media/service-gateway-enterprise-manage-sap/datasourcesettings3-sap.png)

Vælg **Tilføj**, når du har udfyldt det hele. Du kan nu bruge denne datakilde for planlagt opdatering eller DirectQuery op mod en SAP HANA-server, der er i det lokale miljø. Du får vist *Forbindelsen blev oprettet*, hvis det lykkes.

![Visning af forbindelsesstatus](media/service-gateway-enterprise-manage-sap/datasourcesettings4.png)

### <a name="advanced-settings"></a>Avancerede indstillinger

Du kan eventuelt konfigurere niveauet for beskyttelse af personlige oplysninger for datakilden. Dette styrer, hvordan data kan kombineres. Dette bruges kun for planlagte opdateringer. Det gælder ikke for DirectQuery. Hvis du vil vide mere om niveauer for beskyttelse af personlige oplysninger, skal du se [Niveauer for beskyttelse af personlige oplysninger (Power-forespørgsel)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Angivelse af niveauet for beskyttelse af personlige oplysninger](media/service-gateway-enterprise-manage-sap/datasourcesettings9.png)

## <a name="using-the-data-source"></a>Brug datakilden

Når du har oprettet datakilden, bliver den tilgængelig til brug med enten DirectQuery-forbindelser eller via en planlagt opdatering.

> [!NOTE]
> Servernavnet og databasenavnet skal matche mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø.

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse skal stemme overens. Hvis du f.eks. angiver en IP-adresse for servernavnet i Power BI Desktop, skal du bruge IP-adressen for datakilden i konfigurationen af gatewayen. Hvis du bruger *SERVER\INSTANCE* i Power BI Desktop, skal du bruge det samme i den datakilde, der er konfigureret for gatewayen.

Det er tilfældet for både DirectQuery og planlagt opdatering.

### <a name="using-the-data-source-with-directquery-connections"></a>Brug datakilden med DirectQuery-forbindelser

Du skal sikre, at servernavnet og databasenavnet matcher mellem Power BI Desktop og den konfigurerede datakilde for gatewayen. Du skal også at sikre, at din bruger er angivet under fanen **Brugere** i datakilden for at kunne publicere DirectQuery-datasæt. Valget til DirectQuery sker i Power BI Desktop, når du importerer data første gang. Du kan finde flere oplysninger om brug af DirectQuery under [Brug DirectQuery i Power BI Desktop](desktop-use-directquery.md).

Når du publicerer fra enten Power BI Desktop eller **Hent Data**, bør dine rapporter begynde at fungere. Det kan tage flere minutter, efter du har oprettet datakilden i gatewayen, før forbindelsen kan bruges.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Brug datakilden med planlagt opdatering

Hvis du er angivet under fanen **Brugere** i den datakilde, der er konfigureret i gatewayen, og server- og databasenavnet stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med en planlagt opdatering.

![Visning af brugerne](media/service-gateway-enterprise-manage-sap/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Næste trin

* [Fejlfinding af datagateway i det lokale miljø](/data-integration/gateway/service-gateway-tshoot)
* [Foretag fejlfinding af gateways – Power BI](service-gateway-onprem-tshoot.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

