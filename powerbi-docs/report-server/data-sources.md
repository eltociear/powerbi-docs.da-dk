---
title: "Power BI-rapportdatakilder på Power BI-rapportserver"
description: "Power BI-rapporter kan oprette forbindelse til forskellige datakilder. Der er forskellige datakilder tilgængelige, afhængigt af hvordan dataene bruges."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: caa45aab2c31974abb041a82eb2216ebee2eb148
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI-rapportdatakilder på Power BI-rapportserver
Power BI-rapporter kan oprette forbindelse til forskellige datakilder. Der er forskellige datakilder tilgængelige, afhængigt af hvordan dataene bruges. Dataene kan importeres, eller der kan foretages forespørgsler om data direkte ved hjælp af DirectQuery eller en direkte forbindelse til SQL Server Analysis Services.

Disse datakilder gælder kun for Power BI-rapporter, der bruges på Power BI-rapportserver. Du kan finde oplysninger om de datakilder, der understøttes sammen med sideinddelte rapporter, under [Datakilder, der understøttes af Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Alle datakilder i en Power BI Desktop-rapport skal være understøttet for at kunne konfigurere planlagt opdatering.
> 
> 

## <a name="list-of-supported-data-sources"></a>Liste over understøttede datakilder
Det er muligt, at andre datakilder fungerer, selvom de ikke står på listen over understøttede datakilder.

| **Datakilde** | **Cachelagrede data** | **Planlagt opdatering** | **Live/DirectQuery** |
| --- | --- | --- | --- |
| SQL Server-database |Ja |Ja |Ja |
| SQL Server Analysis Services |Ja |Ja |Ja |
| Azure SQL Database |Ja |Ja |Ja |
| Azure SQL Data Warehouse |Ja |Ja |Ja |
| Excel |Ja |Ja |Nej |
| Access-database |Ja |Ja |Nej |
| Active Directory |Ja |Ja |Nej |
| Amazon Redshift |Ja |Nej |Nej |
| Azure Blob Storage |Ja |Ja |Nej |
| Azure Data Lake Store |Ja |Nej |Nej |
| Azure HDInsight (HDFS) |Ja |Ja |Nej |
| Azure HDInsight (Spark) |Ja |Ja |Nej |
| Azure Table Storage |Ja |Ja |Nej |
| Dynamics 365 (online) |Ja |Nej |Nej |
| Facebook |Ja |Nej |Nej |
| Mappe |Ja |Ja |Nej |
| Google Analytics |Ja |Nej |Nej |
| Hadoop File (HDFS) |Ja |Nej |Nej |
| IBM DB2-database |Ja |Ja |Nej |
| Impala |Ja |Nej |Nej |
| JSON |Ja |Ja |Nej |
| Microsoft Exchange |Ja |Nej |Nej |
| Microsoft Exchange Online |Ja |Nej |Nej |
| MySQL Database |Ja |Ja |Nej |
| OData-feed |Ja |Ja |Nej |
| ODBC |Ja |Ja |Nej |
| OLE DB |Ja |Ja |Nej |
| Oracle Database |Ja |Ja |Ja |
| PostgreSQL-database |Ja |Ja |Nej |
| Power BI-tjeneste |Nej |Nej |Nej |
| R Script |Ja |Nej |Nej |
| Salesforce-objekter |Ja |Nej |Nej |
| Salesforce-rapporter |Ja |Nej |Nej |
| SAP Business Warehouse-server |Ja |Ja |Ja |
| SAP HANA-database |Ja |Ja |Ja |
| SharePoint-mappe (i det lokale miljø) |Ja |Ja |Nej |
| SharePoint-liste (i det lokale miljø) |Ja |Ja |Nej |
| SharePoint Online-liste |Ja |Nej |Nej |
| Snowflake |Ja |Nej |Nej |
| Sybase-database |Ja |Ja |Nej |
| Teradata-database |Ja |Ja |Ja |
| Tekst/CSV |Ja |Ja |Nej |
| Web |Ja |Ja |Nej |
| XML |Ja |Ja |Nej |
| appFigures (beta) |Ja |Nej |Nej |
| Azure Analysis Services-database (beta) |Ja |Nej |Nej |
| Azure Cosmos DB (beta) |Ja |Nej |Nej |
| Azure HDInsight Spark (beta) |Ja |Nej |Nej |
| Common Data Service (beta) |Ja |Nej |Nej |
| comScore Digital Analytix (beta) |Ja |Nej |Nej |
| Dynamics 365 for Customer Insights (beta) |Ja |Nej |Nej |
| Dynamics 365 for Financials (beta) |Ja |Nej |Nej |
| GitHub (beta) |Ja |Nej |Nej |
| Google BigQuery (beta) |Ja |Nej |Nej |
| IBM Informix-database (beta) |Ja |Nej |Nej |
| IBM Netezza (beta) |Ja |Nej |Nej |
| Kusto (beta) |Ja |Nej |Nej |
| MailChimp (beta) |Ja |Nej |Nej |
| Microsoft Azure Consumption Insights (beta) |Ja |Nej |Nej |
| Mixpanel (beta) |Ja |Nej |Nej |
| Planview Enterprise (beta) |Ja |Nej |Nej |
| Projectplace (beta) |Ja |Nej |Nej |
| QuickBooks Online (beta) |Ja |Nej |Nej |
| Smartsheet |Ja |Nej |Nej |
| Spark (beta) |Ja |Nej |Nej |
| SparkPost (beta) |Ja |Nej |Nej |
| SQL Sentry (beta) |Ja |Nej |Nej |
| Stripe (beta) |Ja |Nej |Nej |
| SweetIQ (beta) |Ja |Nej |Nej |
| Troux (beta) |Ja |Nej |Nej |
| Twilio (beta) |Ja |Nej |Nej |
| tyGraph (beta) |Ja |Nej |Nej |
| Vertica (beta) |Ja |Nej |Nej |
| Visual Studio Team Services (beta) |Ja |Nej |Nej |
| Webtrends (beta) |Ja |Nej |Nej |
| Zendesk (beta) |Ja |Nej |Nej |

> [!IMPORTANT]
> Sikkerhed på rækkeniveau, der er konfigureret på datakilden, skal fungere for bestemte DirectQuery-forbindelser (SQL Server, Azure SQL Database, Oracle og Teradata) og direkte forbindelser, hvis vi antager, at Kerberos er konfigureret korrekt i dit miljø.
> 
> 

## <a name="next-steps"></a>Næste trin
Nu hvor datakilden er valgt, kan du [oprette en rapport](quickstart-create-powerbi-report.md) ved hjælp af dataene fra denne datakilde.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

