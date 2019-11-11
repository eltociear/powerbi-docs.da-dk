---
title: Understøttede datakilder i forbindelse med DirectQuery i Power BI
description: Hent en liste over, hvilke datakilder der kan bruges i forbindelse med DirectQuery.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/16/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 4c2e2904790d69e5df388d34b5a737f1890d7e12
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878271"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Understøttede datakilder i forbindelse med DirectQuery i Power BI

**Power BI Desktop** og **Power BI-tjenesten** indeholder mange datakilder, som du kan oprette forbindelse til, og som kan give dig adgang til data. I denne artikel beskrives, hvilke datakilder til Power BI der understøtter forbindelsesmetoden, der er kendt som **DirectQuery**. Du kan finde flere oplysninger om DirectQuery under [**DirectQuery i Power BI**](desktop-directquery-about.md).

Følgende datakilder understøtter DirectQuery i Power BI:

* Amazon Redshift
* AtScale (beta)
* Azure Data Explorer
* Azure HDInsight Spark
* [Azure SQL Database](service-azure-sql-database-with-direct-connect.md)
* [Azure SQL Data Warehouse](service-azure-sql-data-warehouse-with-direct-connect.md)
* Denodo
* Google BigQuery
* Interaktiv HDInsight-forespørgsel
* IBM DB2 (Microsoft-udbyder))
* IBM Netezza
* Impala (version 2.x)
* MarkLogic
* Oracle Database (version 12 og nyere)
* Oracle Essbase
* PostgreSQL
* SAP Business Warehouse-programserver
* SAP Business Warehouse-meddelelsesserver
* SAP HANA
* Snowflake
* Spark (version 0.9 og nyere)
* SQL Server
* Teradata
* Vertica

Datakilder med **(beta)** eller **(prøveversion)** i navnet kan ændres og understøttes ikke til produktionsanvendelse. De understøttes desuden muligvis ikke efter publicering af en rapport til **Power BI-tjenesten**, hvilket betyder, at der kan opstå en fejl, når du åbner en publiceret rapport eller udforsker datasættet.

Den eneste forskel mellem datakilder med **(beta)** og **(prøveversion)** i navnet er, at datakilder med **(prøveversion)** i navnet skal aktiveres som en prøveversionsfunktion, før de kan bruges. For at aktivere en dataconnector **(prøveversion)** skal du i **Power BI Desktop** gå til **Filer > Indstillinger > Indstillinger** og derefter vælge **Prøveversionsfunktioner**.

> [!NOTE]
> DirectQuery-forespørgsler til SQL Server kræver godkendelse ved hjælp af aktuelle legitimationsoplysninger til Windows-godkendelse eller databaselegitimationsoplysninger, for at der kan oprettes adgang. Andre typer legitimationsoplysninger understøttes ikke.
>

## <a name="on-premises-gateway-requirements"></a>Krav til gateways i det lokale miljø
I følgende tabel kan du se, om der kræves en **datagateway i det lokale miljø** for at oprette forbindelse til den angivne datakilde, efter en rapport er publiceret i **Power BI tjenesten**.

| Kilde | Er en gateway påkrævet? |
| --- | --- |
| Amazon Redshift |Nej |
| Azure HDInsight Spark (beta) |Nej |
| Azure SQL Database |Nej |
| Azure SQL Data Warehouse |Nej |
| Google BigQuery |Nej |
| IBM Netezza |Ja |
| IBM DB2 (IBM-udbyder) |Ja |
| IBM DB2 (Microsoft-udbyder) |Nej |
| IBM Informix Database |Nej |
| Impala (version 2.x) |Ja |
| MySQL |Ja |
| ODBC |Ja |
| Oracle Database |Ja |
| PostgreSQL |Ja |
| SAP Business Warehouse-programserver |Ja |
| SAP Business Warehouse-meddelelsesserver |Ja |
| SAP HANA |Ja |
| Snowflake |Ja |
| Spark (beta), version 0.9 og nyere |Ja |
| SQL Server |Ja |
| Sybase |Ja |
| Teradata |Ja |
| Vertica |Ja |


## <a name="single-sign-on-sso-for-directquery-sources"></a>Enkeltlogon til DirectQuery-kilder

Når indstillingen for enkeltlogon er aktiveret, og dine brugere får adgang til rapporter, som er baseret på datakilden, sender Power BI deres godkendte Azure AD-legitimationsoplysninger i forespørgslerne til den underliggende datakilde. På den måde kan Power BI overholde de sikkerhedsindstillinger, der er konfigureret på datakildeniveauet.

Indstillingen SSO gælder for alle datasæt, der bruger denne datakilde. Den påvirker ikke den godkendelsesmetode, der bruges til import af scenarier. Følgende datakilder understøtter enkeltlogon for forbindelser via DirectQuery:

- Azure SQL Database
- Azure SQL Data Warehouse
- Impala
- SAP HANA
- SAP BW
- SAP BW-meddelelsesserver (prøveversion)
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure MFA (Multi-Factor Authentication) understøttes ikke. Brugere, der gerne vil bruge enkeltlogon med DirectQuery, skal fritages fra multifaktorgodkendelse.

## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om DirectQuery i følgende ressourcer:

* [DirectQuery i Power BI](desktop-directquery-about.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [Datagateway i det lokale miljø](service-gateway-onprem.md)

