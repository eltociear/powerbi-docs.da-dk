---
title: Administrer din datakilde – SQL
description: Sådan administrerer du en datagateway i det lokale miljø og de datakilder, der hører til denne gateway.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 7d9e670d2567181a0dc99c23997ac3bc2d35f3c9
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271572"
---
# <a name="manage-your-data-source---sql-server"></a>Administrer din datakilde – SQL Server

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Når du har [installeret datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-install), kan du tilføje [datakilder](service-gateway-data-sources.md#add-a-data-source), der kan bruges sammen med gatewayen. Denne artikel indeholder oplysninger om, hvordan du arbejder med gateways og SQL Server-datakilder, der enten bruges til planlagte opdateringer eller DirectQuery.

## <a name="add-a-data-source"></a>Tilføj en datakilde

Du kan finde oplysninger om, hvordan du tilføjer en datakilde i [Tilføj en datakilde](service-gateway-data-sources.md#add-a-data-source).

![Vælg SQL Server-datakilden](media/service-gateway-enterprise-manage-sql/datasourcesettings2.png)

> [!NOTE]
> Når du bruger DirectQuery, understøtter gatewayen kun **SQL Server 2012 SP1** og efterfølgende versioner.

Du skal derefter udfylde oplysningerne om datakilden, herunder **Server** og **Database**.  

Du skal også vælge en **Godkendelsesmetode**. Denne kan enten være **Windows** eller **Basic**. Du skal vælge **Basic**, hvis du vil bruge SQL-godkendelse i stedet for Windows-godkendelse. Indtast derefter legitimationsoplysningerne, der skal bruges til denne datakilde.

> [!NOTE]
> Alle forespørgsler på datakilden kører ved hjælp af disse legitimationsoplysninger, medmindre Kerberos SSO (enkeltlogon) er konfigureret og aktiveret for datakilden. Med SSO bruges de gemte legitimationsoplysninger i forbindelse med import af datasæt, men den aktuelle Power BI-bruger bruges til DirectQuery-datasæt for at udføre forespørgslerne ved hjælp af SSO. Hvis du vil vide mere om, hvordan legitimationsoplysninger gemmes, skal du se [Lagring af krypterede legitimationsoplysninger i cloudmiljøet](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud) eller den artikel, der beskriver, hvordan du [bruger Kerberos til SSO (enkeltlogon) fra Power BI datakilder i det lokale miljø](service-gateway-sso-kerberos.md).

![Angivelse af indstillinger for datakilden](media/service-gateway-enterprise-manage-sql/datasourcesettings3.png)

Vælg **Tilføj**, når du har udfyldt det hele. Du kan nu bruge denne datakilde til planlagt opdatering eller DirectQuery op mod en SQL Server, der er i det lokale miljø. Du får vist *Forbindelsen blev oprettet*, hvis det lykkes.

![Visning af forbindelsesstatus](media/service-gateway-enterprise-manage-sql/datasourcesettings4.png)

### <a name="advanced-settings"></a>Avancerede indstillinger

Du kan eventuelt konfigurere niveauet for beskyttelse af personlige oplysninger for datakilden. Dette styrer, hvordan data kan kombineres. Dette bruges kun for planlagte opdateringer. Det gælder ikke for DirectQuery. Hvis du vil vide mere om niveauer for beskyttelse af personlige oplysninger, skal du se [Niveauer for beskyttelse af personlige oplysninger (Power-forespørgsel)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Angivelse af niveauet for beskyttelse af personlige oplysninger](media/service-gateway-enterprise-manage-sql/datasourcesettings9.png)

## <a name="using-the-data-source"></a>Brug datakilden

Når du har oprettet datakilden, bliver den tilgængelig til brug med enten DirectQuery-forbindelser eller via en planlagt opdatering.

> [!NOTE]
> Servernavnet og databasenavnet skal matche mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø.

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse skal stemme overens. Hvis du f.eks. angiver en IP-adresse for servernavnet i **Power BI Desktop**, skal du bruge IP-adressen for datakilden i konfigurationen af gatewayen. Hvis du bruger *SERVER\INSTANCE* i Power BI Desktop, skal du bruge det samme i den datakilde, der er konfigureret for gatewayen.

Det er tilfældet for både DirectQuery og planlagt opdatering.

### <a name="using-the-data-source-with-directquery-connections"></a>Brug datakilden med DirectQuery-forbindelser

Du skal sikre, at servernavnet og databasenavnet matcher mellem **Power BI Desktop** og den konfigurerede datakilde for gatewayen. Du skal også at sikre, at din bruger er angivet under fanen **Brugere** i datakilden for at kunne publicere DirectQuery-datasæt. Valget til DirectQuery sker i Power BI Desktop, når du importerer data første gang. Du kan finde flere oplysninger om brug af DirectQuery under [Brug DirectQuery i Power BI Desktop](desktop-use-directquery.md).

Når du publicerer fra enten Power BI Desktop eller **Hent Data**, bør dine rapporter begynde at fungere. Det kan tage flere minutter, efter du har oprettet datakilden i gatewayen, før forbindelsen kan bruges.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Brug datakilden med planlagt opdatering

Hvis du er angivet under fanen **Brugere** i den datakilde, der er konfigureret i gatewayen, og server- og databasenavnet stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med en planlagt opdatering.

![Visning af brugerne](media/service-gateway-enterprise-manage-sql/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Næste trin

* [Opret forbindelse til data i det lokale miljø i SQL Server](service-gateway-sql-tutorial.md)
* [Fejlfinding af datagateway i det lokale miljø](/data-integration/gateway/service-gateway-tshoot)
* [Foretag fejlfinding af gateways – Power BI](service-gateway-onprem-tshoot.md)
* [Brug Kerberos til SSO (enkeltlogon) fra Power BI til datakilder i det lokale miljø](service-gateway-sso-kerberos.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

