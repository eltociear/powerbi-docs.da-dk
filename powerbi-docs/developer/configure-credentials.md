---
title: Konfigurer legitimationsoplysninger programmatisk for Power BI
description: Sådan konfigurerer du legitimationsoplysninger programmatisk for Power BI med henblik på automatisering
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/25/2019
ms.openlocfilehash: 2b4e2f5a4e95b412459dd8fe8d497966e541b389
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892676"
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

1. [Følg trin 1 og 2 fra forrige scenario](#configure-credential-flow-for-data-sources).

2. Foretag et kald til [Hent gateway](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) for at hente den offentlige nøgle til gatewayen.

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. Kryptér strengen for legitimationsoplysningerne ned den offentlige nøgle for gatewayen ved hjælp af RSA-krypteringsalgoritmen.

    Brug følgende hjælpeklasse til kryptering:

    ```csharp
        public static class AsymmetricKeyEncryptionHelper
        {
            private const int SegmentLength = 85;
            private const int EncryptedLength = 128;

            /// <summary>

            /// Encrypts credentials using the RSA algorithm

            /// </summary>

            public static string EncodeCredentials(string credentialData, string publicKeyExponent, string publicKeyModulus)
            {
                using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
                {
                    var parameters = rsa.ExportParameters(false);

                    parameters.Exponent = Convert.FromBase64String(publicKeyExponent);

                    parameters.Modulus = Convert.FromBase64String(publicKeyModulus);

                    rsa.ImportParameters(parameters);

                    return Encrypt(credentialData, rsa);
                }
            }

             private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
            {

                byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

                // Split the message into different segments, each segment's length is 85. So, the result may be 85,85,85,20. 

                bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0; 

                int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length SegmentLength) + 1);

                byte[] encryptedData = new byte[segmentNumber * EncryptedLength];

                int encryptedDataPosition = 0;

                for (var i = 0; i < segmentNumber; i++)
                {
                    int lengthToCopy;

                    if (i == segmentNumber - 1 && hasIncompleteSegment)

                        lengthToCopy = plainTextArray.Length % SegmentLength;

                    else

                        lengthToCopy = SegmentLength;

                    var segment = new byte[lengthToCopy];

                    Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

                    var segmentEncryptedResult = rsa.Encrypt(segment, true);

                    Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

                    encryptedDataPosition += segmentEncryptedResult.Length;

                }

                return Convert.ToBase64String(encryptedData);

            }

        }

        var encryptedCredentials = AsymmetricKeyEncryptionHelper.EncodeCredentials(credentials);
    ```

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
