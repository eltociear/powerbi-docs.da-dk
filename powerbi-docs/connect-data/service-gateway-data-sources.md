---
title: Administrer datakilder
description: Få mere at vide om, hvordan du administrerer datakilder i Power BI.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 07/22/2020
ms.author: arthii
ms.custom: seodec18
LocalizationGroup: Gateways
ms.openlocfilehash: 92c3a65b11435403b61a06324f534e6d82e4b7cb
ms.sourcegitcommit: efe11c819be75887c4242afa64d32bb0698da569
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/24/2020
ms.locfileid: "87123482"
---
# <a name="manage-data-sources"></a>Administrer datakilder

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

Power BI understøtter mange [datakilder i det lokale miljø](power-bi-data-sources.md), som hver især har sine egne krav. En gateway kan bruges til en enkelt datakilde eller flere datakilder. I dette eksempel viser vi dig, hvordan du tilføjer SQL Server som en datakilde. Trinnene svarer til trinnene for andre datakilder.

De fleste handlinger til administration af datakilder kan også udføres vha. API'er. Du kan finde flere oplysninger i [REST API'er (gateways)](/rest/api/power-bi/gateways).

## <a name="add-a-data-source"></a>Tilføj en datakilde

1. I øverste højre hjørne af Power BI-tjenesten skal du vælge tandhjulsikonet ![tandhjulsikonet for indstillinger](media/service-gateway-data-sources/icon-gear.png) > **Administrer gateways**.

    ![Administrer gateways](media/service-gateway-data-sources/manage-gateways.png)

2. Vælg en gateway, og vælg derefter **Tilføj datakilde**. Eller gå til **Gateways** > **Tilføjdata kilde**.

    ![Tilføj datakilde](media/service-gateway-data-sources/add-data-source.png)

3. Vælg **Datakildetype**.

    ![Vælg SQL Server](media/service-gateway-data-sources/select-sql-server.png)

4. Angiv oplysninger for datakilden. I dette eksempel er det **Server**, **Database** og andre oplysninger. 

    ![Indstillinger for datakilde](media/service-gateway-data-sources/data-source-settings.png)

5. Du kan vælge **godkendelsesmetoden** **Windows** eller **Basic** (SQL-godkendelse) for SQL Server. Hvis du vælger **Basic**, skal du angive legitimationsoplysningerne for datakilden.

    > [!NOTE]
    > Hvis den valgte godkendelsesmetode er OAuth, vil forespørgsler, der kører længere end politikken for udløb af OAuth-tokenet, muligvis mislykkes.

6. Du kan konfigurere **Enkeltlogon (SSO)** for din datakilde under [Avancerede indstillinger](service-gateway-sso-overview.md). 

    ![avancerede indstillinger](media/service-gateway-data-sources/advanced-settings-02.png)

Du kan enten konfigurere **Brug SSO via Kerberos til DirectQuery-forespørgsler** eller **Brug SSO via Kerberos til DirectQuery- og importforespørgsler** for DirectQuery-baserede rapporter og **Brug SSO via Kerberos til DirectQuery- og importforespørgsler** for opdateringsbaserede rapporter.

Hvis du bruger **Brug SSO via Kerberos til DirectQuery-forespørgsler** og bruger denne datakilde til en DirectQuery-baseret rapport, benyttes den bruger, der er knyttet til den (Azure) Active Directory-bruger, der logger på Power BI-tjenesten. I forbindelse med en opdateret rapport vil den bruge de legitimationsoplysninger, du angiver i felterne **Brugernavn** og **Adgangskode**.

Hvis du bruger **Brug SSO via Kerberos til DirectQuery- og importforespørgsler**, behøver du ikke at angive legitimationsoplysninger. Hvis denne datakilde bruges til en DirectQuery-baseret rapport, benyttes den bruger, der er knyttet til den (Azure) Active Directory-bruger, der logger på Power BI-tjenesten.  I forbindelse med en opdateret rapport bruges sikkerhedskonteksten for datasættets ejer

> [!NOTE]
>SSO til importforespørgsler er kun tilgængelig for listen over SSO-datakilder, der bruger [Kerberos-begrænset delegering](service-gateway-sso-kerberos.md).

7. Under **Avancerede indstillinger** kan du eventuelt konfigurere [niveauet for beskyttelse af personlige oplysninger](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540) for din datakilde (gælder ikke for [DirectQuery](desktop-directquery-about.md)).

    ![Avancerede indstillinger](media/service-gateway-data-sources/advanced-settings.png)

8. Vælg **Tilføj** Du får vist *Forbindelsen er oprettet*, hvis processen lykkes.

    ![Forbindelsen er oprettet](media/service-gateway-data-sources/connection-successful.png)

Du kan nu bruge denne datakilde til at inkludere data fra SQL Server i dine Power BI-dashboards og -rapporter.

## <a name="remove-a-data-source"></a>Fjern en datakilde

Du kan fjerne en datakilde, hvis du ikke længere bruger den. Hvis du fjerner en datakilde, ødelægger det alle dashboards og rapporter, der anvender den pågældende datakilde.

Hvis du vil fjerne en datakilde, skal du gå til datakilden og derefter vælge **Fjern**.

![Fjern en datakilde](media/service-gateway-data-sources/remove-data-source.png)

## <a name="use-the-data-source-for-scheduled-refresh-or-directquery"></a>Brug af datakilden til planlagt opdatering eller DirectQuery

Når du opretter datakilden, er den tilgængelig til brug med enten DirectQuery-forbindelser eller via en planlagt opdatering.

> [!NOTE]
>Server- og databasenavne skal matche mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø.

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse navne skal være ens. Hvis du f.eks. angiver en IP-adresse for servernavnet i Power BI Desktop, skal du bruge IP-adressen til datakilden i konfigurationen af gatewayen. Hvis du bruger *SERVER\INSTANCE* i Power BI Desktop, skal du bruge det samme i den datakilde, der er konfigureret for gatewayen.

Hvis du er angivet under fanen **Brugere** i den datakilde, der er konfigureret i gatewayen, og server- og databasenavnet stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med en planlagt opdatering.

![Gateway-forbindelse](media/service-gateway-data-sources/gateway-connection.png)

> [!WARNING]
> Hvis dit datasæt indeholder flere datakilder, skal hver enkelt datakilde føjes til gatewayen. Hvis en eller flere datakilder ikke er føjet til gatewayen, kan du ikke se gatewayen som tilgængelig i forbindelse med en planlagt opdatering.

### <a name="limitations"></a>Begrænsninger

OAuth er kun en understøttet godkendelsesplan for brugerdefinerede connectors med datagatewayen i det lokale miljø. Du kan ikke tilføje andre datakilder, der kræver OAuth. Hvis dit datasæt har en datakilde, der kræver OAuth, og denne datakilde ikke er en brugerdefineret connector, kan du ikke bruge gatewayen til planlagt opdatering.

## <a name="manage-users"></a>Administrer brugere

Når du har føjet en datakilde til en gateway, giver du brugere og mailaktiverede sikkerhedsgrupper adgang til den specifikke datakilde (ikke hele gatewayen). Brugerlisten for datakilden styrer kun, hvem der har tilladelse til at udgive rapporter, der indeholder data fra datakilden. Rapporternes ejere kan oprette dashboards, indholdspakker og apps og derefter dele disse med andre brugere.

Du kan også give brugere og sikkerhedsgrupper administrativ adgang til gatewayen.

> [!NOTE]
> Brugere med adgang til datakilden kan associere datasæt med datakilden, og oprette forbindelse, baseret på sikkerhedsoplysningerne (enten de gemte legitimationsoplysninger eller enkeltlogon), som blev valgt under oprettelse af en datakilde.

### <a name="add-users-to-a-data-source"></a>Føj brugere til en datakilde

1. I øverste højre hjørne af Power BI-tjenesten skal du vælge tandhjulsikonet ![tandhjulsikonet for indstillinger](media/service-gateway-data-sources/icon-gear.png) > **Administrer gateways**.

2. Vælg den datakilde, hvor du vil tilføje brugere.

3. Vælg **Brugere**, og angiv en bruger fra din organisation, som du vil give adgang til den valgte datakilde. På følgende skærmbillede tilføjer du f.eks. Maggie og Adam.

    ![Fanen Brugere](media/service-gateway-data-sources/users-tab.png)

4. Hvis du vælger **Tilføj**, vises det tilføjede medlems navn i feltet.

    ![Tilføj bruger](media/service-gateway-data-sources/add-user.png)

Husk, at du skal føje brugere til hver enkelt datakilde, som du vil give adgang til. Hver datakilde har en separat liste over brugere. Føj brugere separat til hver enkelt datakilde.

### <a name="remove-users-from-a-data-source"></a>Fjern brugere fra en datakilde

Under fanen **Brugere** for datakilden kan du fjerne brugere og sikkerhedsgrupper, som bruger denne datakilde.

![Fjern bruger](media/service-gateway-data-sources/remove-user.png)

## <a name="store-encrypted-credentials-in-the-cloud"></a>Lagring af krypterede legitimationsoplysninger i clouden

Når du føjer en datakilde til gatewayen, skal du angive legitimationsoplysninger for den pågældende datakilde. Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Legitimationsoplysningerne er krypteret på en sikker måde. De anvender symmetrisk kryptering, så de ikke kan dekrypteres i cloudmiljøet, før de er gemt i cloudmiljøet. Legitimationsoplysningerne sendes til den maskine, der kører gateway'en, i det lokale miljø, hvor de dekrypteres, når datakilderne tilgås.

## <a name="list-of-available-data-source-types"></a>Liste over tilgængelige datakildetyper

Du kan finde oplysninger om, hvilke datakilder datagatewayen i det lokale miljø understøtter, i [Power BI-datakilder](power-bi-data-sources.md).

## <a name="next-steps"></a>Næste trin

* [Administrer din datakilde – Analysis Services](service-gateway-enterprise-manage-ssas.md)
* [Administrer din datakilde – SAP HANA](service-gateway-enterprise-manage-sap.md)
* [Administrer din datakilde – SQL Server](service-gateway-enterprise-manage-sql.md)
* [Administrer din datakilde – Oracle](service-gateway-onprem-manage-oracle.md)
* [Administrer din datakilde – Import/planlagt opdatering](service-gateway-enterprise-manage-scheduled-refresh.md)
* [Vejledning til installation af en datagateway](service-gateway-deployment-guidance.md)

Har du flere spørgsmål? Prøv at spørge [Power BI-community'et](https://community.powerbi.com/).
