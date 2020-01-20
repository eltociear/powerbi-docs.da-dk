---
title: Konfigurer legitimationsoplysninger programmatisk for Power BI
description: Sådan konfigurerer du legitimationsoplysninger programmatisk for Power BI med henblik på automatisering
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: 222edd901409fa71d98308f27407838d54564834
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836584"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Konfigurer legitimationsoplysninger programmatisk for Power BI

Følg disse trin for at konfigurere legitimationsoplysninger programmatisk for Power BI.

## <a name="configure-a-credential-flow-for-data-sources"></a>Konfigurer et flow for legitimationsoplysninger for datakilder

1. Foretag et kald til [Hent datakilder](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup) for at finde datakilderne for datasættet. I svarteksten for hver enkelt datakilde kan du se typen, forbindelsesoplysningerne, gatewayen og id'et for datakilden.

    ```csharp
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First(); // select a datasource
    ```

2. Opret en streng for legitimationsoplysningerne i henhold til [Opdater eksempler på datakilder](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) afhængigt af typen af legitimationsoplysninger.

    ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

3. Opret detaljerne for legitimationsoplysningerne.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    credentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.None,
                    PrivacyLevelEnum.Private);
    ```

4. Brug gatewayen og id'et for datakilden fra trin 1 og detaljerne for legitimationsoplysningerne fra trin 4 til at foretage et kald til [Opdater datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) for at angive legitimationsoplysningerne.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

### <a name="expired-on-premises-data-source-credentials-flow"></a>Udløbet flow for legitimationsoplysninger for datakilde i det lokale miljø

1. [Følg trin 1 og 2 fra forrige scenario](#configure-a-credential-flow-for-data-sources).

2. Foretag et kald til [Hent gateway](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) for at hente den offentlige nøgle til gatewayen.

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. Kryptér strengen for legitimationsoplysningerne med den offentlige nøgle for gatewayen. Forskellige gatewayversioner kan have forskellige størrelser af offentlige nøgler.
    
    Se eksemplet i SDK-koden, der er tilgængelig fra PowerBI-CSharp GitHub-lageret, [PowerBI-CSharp//PowerBI. API/extensions/v2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2).
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)

4. Opret detaljerne for legitimationsoplysningerne med krypterede legitimationsoplysninger.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    encryptedCredentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.RSA-OAEP,
                    PrivacyLevelEnum.Private);
    ```

5. Foretag et kald til [Opdater datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) for at angive legitimationsoplysningerne.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>Konfigurer en ny datakilde for en datagateway

1. Installér [Datagatewayen i det lokale miljø](https://powerbi.microsoft.com/gateway/) på din computer.

2. Foretag et kald til [Hent gateway](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) for at hente id'et og den offentlige nøgle for gatewayen.

    ```csharp
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First(); // select a gateway
    ```

3. Opret detaljerne for legitimationsoplysningerne ligesom i forrige scenario ved hjælp af den offentlige nøgle for gatewayen, der blev hentet i trinnet [Udløbet flow for legitimationsoplysninger for datakilde i det lokale miljø](#expired-on-premises-data source-credentials-flow-on-premises-data-gateway).

4. udarbejd teksten til anmodningen

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
    dataSourceType: "SQL",
    connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
    credentialDetails: credentialDetails,
    dataSourceName: "my sql datasource");
    ```

5. Foretag et kald til API'en for [Opret datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource).

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="troubleshooting"></a>Fejlfinding

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>Der blev ikke fundet noget id eller nogen datakilde for gatewayen ved kald til Hent datakilder

Dette problem betyder, at datasættet ikke er forbundet til en gateway. Når du opretter et nyt datasæt, oprettes der automatisk en datakilde uden legitimationsoplysninger for hver cloudforbindelse på brugerens cloudgateway. Denne gateway bruges til at gemme legitimationsoplysninger for cloudforbindelser.

Når du har oprettet datasættet, sker der en automatisk binding mellem datasættet og en passende gateway, som indeholder matchende datakilder for alle forbindelser. Hvis sådan en gateway ikke findes, eller der findes flere passende gateways, mislykkes den automatiske binding.

Opret manglende datakilder i det lokale miljø, hvis det er nødvendigt, og bind datasættet til en gateway manuelt ved hjælp af [Bind til gateway](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway).

Hvis du vil finde gateways, der kan bindes, skal du bruge [Find gateways](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways).