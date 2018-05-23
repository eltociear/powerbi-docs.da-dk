---
title: Administrer din SAP HANA-datakilde
description: Sådan administrerer du en datagateway i det lokale miljø og de datakilder, der hører til denne gateway. Denne artikel er specifik for SAP HANA.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: f9407f7267b0d33ab2d1a1d36856b96a815d8e1e
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="manage-your-sap-hana-data-source"></a>Administrer din SAP HANA-datakilde
Når du har installeret datagatewayen i det lokale miljø, skal du tilføje datakilder, der kan bruges sammen med gatewayen. I denne artikel kan du se, hvordan du arbejder med gateways og datakilder. Du kan bruge SAP HANA-datakilden enten til planlagte opdateringer eller DirectQuery.

## <a name="download-and-install-the-gateway"></a>Download og installér gatewayen
Du kan downloade gatewayen fra Power BI-tjenesten. Vælg **Downloads** > **Datagateway**, eller gå til [siden til download af gateway](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-sap/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Tilføj en gateway
Hvis du vil tilføje en Gateway, skal du blot [downloade](https://go.microsoft.com/fwlink/?LinkId=698861) og installere gatewayen på en server i dit miljø. Når du har installeret gatewayen, vises den på listen over gateways under **Administrer gateways**.

> [!NOTE]
> **Administrer gateways** vises ikke, før du er administrator af mindst én gateway. Det kan du blive ved enten at blive tilføjet som administrator eller ved at installere og konfigurere en gateway.
> 
> 

## <a name="remove-a-gateway"></a>Fjern en gateway
Hvis du fjerner en gateway, slettes også eventuelle datakilder under denne gateway.  Dette vil også ødelægge alle dashboards og rapporter, der anvender disse datakilder.

1. Vælg tandhjulsikonet ![](media/service-gateway-enterprise-manage-sap/pbi_gearicon.png) i øverste højre hjørne > **Administrer gateways**.
2. Gateway > **Fjern**
   
   ![](media/service-gateway-enterprise-manage-sap/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Tilføj en datakilde
Du kan tilføje en datakilde ved enten at vælge en gateway og klikke på **Tilføj datakilde** eller gå til Gateway > **Tilføj datakilde**.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings1.png)

Du kan derefter vælge **Datakildetype** på listen.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings2-sap.png)

Derefter skal du angive oplysninger om datakilden, herunder **Server**, **Brugernavn** og **Adgangskode**.

> [!NOTE]
> Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Du kan finde flere oplysninger om, hvordan du gemmer [legitimationsoplysninger](service-gateway-onprem.md#credentials) i hovedartiklen om datagateways i det lokale miljø.
> 
> 

![](media/service-gateway-enterprise-manage-sap/datasourcesettings3-sap.png)

Du kan klikke på **Tilføj**, når du har udfyldt det hele.  Du kan nu bruge denne datakilde for planlagt opdatering eller DirectQuery op mod en SAP HANA-server, der er i det lokale miljø. Du får vist *Forbindelsen er oprettet*, hvis det lykkes.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings4.png)

### <a name="advanced-settings"></a>Avancerede indstillinger
Du kan konfigurere niveauet for beskyttelse af personlige oplysninger for datakilden. Dette styrer, hvordan data kan blandes. Dette bruges kun til planlagt opdatering. Det gælder ikke for DirectQuery. [Få mere at vide](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-sap/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Fjern en datakilde
Hvis du fjerner en datakilde, ødelægger det alle dashboards eller rapporter, der anvender den pågældende datakilde.  

Hvis du vil fjerne en datakilde, skal du gå til datakilden > **Fjern**.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings6.png)

## <a name="manage-administrators"></a>Administrer administratorer
Under fanen Administratorer for gatewayen kan du tilføje og fjerne brugere (eller sikkerhedsgrupper), som kan administrere gatewayen.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings8.png)

## <a name="manage-users"></a>Administrer brugere
Under fanen Brugere for datakilden kan du tilføje og fjerne brugere eller sikkerhedsgrupper, som kan bruge denne datakilde.

> [!NOTE]
> Listen over brugere kan kun bruges til at styre, hvem der har tilladelse til at publicere rapporter. Rapporternes ejere kan oprette dashboards eller indholdspakker og dele dem med andre brugere.
> 
> 

![](media/service-gateway-enterprise-manage-sap/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Brug datakilden
Når du har oprettet datakilden, bliver den tilgængelig til brug med enten DirectQuery-forbindelser eller via planlagt opdatering.

> [!NOTE]
> Server- og databasenavn skal stemme overens mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø!
> 
> 

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse skal stemme overens. Hvis du f.eks. angiver en IP-adresse for servernavnet i Power BI Desktop, skal du bruge IP-adressen til datakilden i konfigurationen af gatewayen. Hvis du bruger *SERVER\FOREKOMST* i Power BI Desktop, skal du bruge det samme i den datakilde, der er konfigureret for gatewayen.

Det er tilfældet for både DirectQuery og planlagt opdatering.

### <a name="using-the-data-source-with-directquery-connections"></a>Brug af datakilden med DirectQuery-forbindelser
Du skal sikre dig, at servernavn og databasenavn stemmer overens mellem Power BI Desktop og den konfigurerede datakilde for gatewayen. Du skal også at sikre dig, at din bruger er angivet på fanen **Brugere** i datakilden for at kunne publicere DirectQuery-datasæt. Valget til DirectQuery sker i Power BI Desktop, når du importerer data første gang. [Få mere at vide](desktop-use-directquery.md)

Når du publicerer fra enten Power BI Desktop eller **Hent data**, bør dine rapporter begynde at fungere. Det kan tage flere minutter, efter du har oprettet datakilden i gatewayen, før forbindelsen kan bruges.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Brug datakilden med planlagt opdatering
Hvis du er angivet under fanen **Brugere** for den datakilde, der er konfigureret i gatewayen, og server- og databasenavn stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med planlagt opdatering.

![](media/service-gateway-enterprise-manage-sap/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Næste trin
[Datagateway i det lokale miljø](service-gateway-onprem.md)  
[Datagateway i det lokale miljø – detaljeret](service-gateway-onprem-indepth.md)  
[Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

