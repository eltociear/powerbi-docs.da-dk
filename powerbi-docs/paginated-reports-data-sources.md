---
title: Understøttede datakilder for sideinddelte rapporter i Power BI
description: I denne artikel får du mere at vide om understøttede datakilder for sideinddelte rapporter i Power BI-tjenesten, og hvordan du opretter forbindelse til datakilder i Azure SQL Database.
author: onegoodsausage
ms.author: andremi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 07/19/2019
ms.openlocfilehash: fcc6e7880a3f27c6b35fe2192e76a0b2cc82abd0
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874863"
---
# <a name="supported-data-sources-for-power-bi-paginated-reports"></a>Understøttede datakilder for sideinddelte rapporter i Power BI

I denne artikel præsenteres understøttede datakilder for sideinddelte rapporter i Power BI-tjenesten, og hvordan du opretter forbindelse til datakilder i Azure SQL Database. Nogle datakilder understøttes i det oprindelige miljø. Du kan oprette forbindelse til andre vha. datagateways.

## <a name="natively-supported-data-sources"></a>Datakilder, der understøttes i det oprindelige miljø

Følgende liste over datakilder understøttes i det oprindelige miljø i sideinddelte rapporter:

| Datakilde | Godkendelse | Noter |
| --- | --- | --- |
| Azure SQL Database <br>Azure SQL Data Warehouse | Basic, enkeltlogon (SSO), OAuth2 |   |
| Administreret forekomst af Azure SQL | Grundlæggende | via det offentlige slutpunkt ved hjælp af Azure SQL Database-udvidelsen  |
| Azure Analysis Services | SSO, OAuth2 |   |
| Power BI-datasæt | SSO | Power BI Premium-datasæt og datasæt, der ikke er Premium |
| Power BI Premium-datasæt (XMLA) | SSO |   |
| Angiv data | I/T | Data er integreret i rapporten. |

Med undtagelse af Azure SQL Database er alle datakilder klar til brug, når du har uploadet rapporten til Power BI-tjenesten. Datakilderne bruges som standard til enkeltlogon (SSO), hvor det er relevant. Du kan ændre godkendelsestypen til OAuth2 for Azure Analysis Services.

Du skal angive flere oplysninger for Azure SQL Database-datakilder, som beskrevet i afsnittet [Godkendelse i Azure SQL Database](#azure-sql-database-authentication).

## <a name="other-data-sources"></a>Andre datakilder

Foruden ovenstående datakilder, der understøttes i det oprindelige miljø, kan følgende datakilder tilgås via en [Power BI-datagateway](service-gateway-onprem.md):

- SQL Server
- SQL Server Analysis Services
- Oracle
- Teradata

Du kan ikke få adgang til Azure SQL Database og Azure Analysis Services via en Power BI-datagateway i forbindelse med sideinddelte rapporter.

## <a name="azure-sql-database-authentication"></a>Godkendelse i Azure SQL Database

Du skal angive en godkendelsestype, før du kører rapporten, i forbindelse med Azure SQL Database-datakilder. Dette gælder kun, første gang du bruger en datakilde i et arbejdsområde. Ved denne første gang får du vist følgende meddelelse:

![Publicerer i Power BI](media/paginated-reports-data-sources/power-bi-paginated-publishing.png)

Hvis du ikke angiver nogen legitimationsoplysninger, opstår der en fejl, når du kører rapporten. Vælg **Fortsæt** for at gå til siden **Legitimationsoplysninger for datakilde** for den rapport, du netop har uploadet:

![Indstillinger for Azure SQL Database](media/paginated-reports-data-sources/power-bi-paginated-settings-azure-sql.png)

Vælg linket **Rediger legitimationsoplysninger** for en given datakilde for at få vist dialogboksen **Konfigurer**:

![Konfigurer Azure SQL Database](media/paginated-reports-data-sources/power-bi-paginated-configure-azure-sql.png)

Her er de understøttede godkendelsestyper for Azure SQL Database-datakilder:

- Basic (brugernavn og adgangskode)
- SSO (enkeltlogon)
- OAuth2 (gemt AAD-token)

[Understøttelse af AAD-godkendelse](https://docs.microsoft.com/azure/sql-database/sql-database-aad-authentication-configure) skal være aktiveret for den Azure SQL Database-server, som datakilden opretter forbindelse til, for at SSO og OAuth2 fungerer korrekt. Til OAuth2-godkendelsesmetoden opretter AAD et token og gemmer det til fremtidig adgang til datakilderne. Hvis du i stedet vil bruge [SSO-godkendelsesmetoden](https://docs.microsoft.com/power-bi/service-azure-sql-database-with-direct-connect#single-sign-on), skal du vælge SSO-muligheden lige under den, **Slutbrugere bruger deres egne OAuth2-legitimationsoplysninger til at få adgang til denne datakilde via DirectQuery**.
  
## <a name="next-steps"></a>Næste trin

[Publicer en sideinddelt rapport i Power BI-tjenesten](paginated-reports-view-power-bi-service.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
