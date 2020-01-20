---
title: Kryptér legitimationsoplysninger
description: Gennemgang – Kryptér legitimationsoplysninger til datakilder for gateway i det lokale miljø
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: b1fc4a505aa993c606743eefb6e8fb8c0379317d
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836611"
---
# <a name="encrypt-credentials"></a>Kryptér legitimationsoplysninger

Når du kalder [Opret datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) eller [Opdater datakilde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) under en **virksomhedsgateway i det lokale miljø** ved hjælp af [REST-API'er til Power BI](https://docs.microsoft.com/rest/api/power-bi/), skal legitimationsoplysningerne krypteres ved hjælp af gatewayens offentlige nøgle.

I nedenstående kodeeksempel kan du se, hvordan du krypterer legitimationsoplysninger i .NET.

De nedenstående angivne legitimationsoplysninger til metoden EncodeCredentials skal være i et af følgende formater afhængigt af typen af legitimationsoplysninger:

**Basis-/Windows-legitimationsoplysninger**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**Nøglelegitimationsoplysninger**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**OAuth2-legitimationsoplysninger**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

**Anonyme legitimationsoplysninger**

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**Kryptér legitimationsoplysninger**

Kryptér værdien af legitimationsoplysningerne ved hjælp af gatewayens offentlige nøgle. Forskellige gatewayversioner kan have forskellige størrelser af offentlige nøgler.

Se eksemplet i SDK-koden, der er tilgængelig fra PowerBI-CSharp GitHub-lageret, [PowerBI-CSharp//PowerBI. API/extensions/v2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2).

- [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
- [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
- [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
- [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)