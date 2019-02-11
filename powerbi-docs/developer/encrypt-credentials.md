---
title: Kryptér legitimationsoplysninger
description: Gennemgang – kryptér legitimationsoplysningerne for datakilder til gatewayen i det lokale miljø
author: mahirdiab
manager: eligr
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: mahirdiab
ms.openlocfilehash: 050628dfe179a39ca24d2df72f1296acf48aa261
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763078"
---
# <a name="encrypt-credentials"></a>Kryptér legitimationsoplysninger
Når du kalder [Opret datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) eller [Opdater datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) under en **virksomhedsgateway i det lokale miljø** ved hjælp af [REST-API'er til Power BI](https://docs.microsoft.com/rest/api/power-bi/), skal legitimationsoplysningerne krypteres ved hjælp af gatewayens offentlige nøgle.

I nedenstående kodeeksempel kan du se, hvordan du krypterer legitimationsoplysninger i .NET.

De nedenstående angivne legitimationsoplysninger til metoden EncodeCredentials skal være i et af følgende formater afhængigt af typen af legitimationsoplysninger:

**Basis-/Windows-legitimationsoplysninger**
```
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**Nøglelegitimationsoplysninger**
```
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**OAuth2-legitimationsoplysninger**
```
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```


**Anonyme legitimationsoplysninger**
```
var credentials = "{\"credentialData\":\"\"}";
```

**Kryptér legitimationsoplysninger**
```
public static class AsymmetricKeyEncryptionHelper
{

    private const int SegmentLength = 85;
    private const int EncryptedLength = 128;

    public static string EncodeCredentials(string credentials, string publicKeyExponent, string publicKeyModulus)
    {
        using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
        {
            var parameters = rsa.ExportParameters(false);
            parameters.Exponent = Convert.FromBase64String(publicKeyExponent);
            parameters.Modulus = Convert.FromBase64String(publicKeyModulus);
            rsa.ImportParameters(parameters);
            return Encrypt(credentials, rsa);
        }
    }

    private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
    {
        byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

        // Split the message into different segments, each segment's length is 85. So the result may be 85,85,85,20.
        bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0;

        int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length / SegmentLength) + 1);

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
```
