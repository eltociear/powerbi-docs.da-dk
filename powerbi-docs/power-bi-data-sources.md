---
title: Power BI-datakilder
description: Denne artikel indeholder en liste over de datakilder, som Power BI understøtter, herunder oplysninger om DirectQuery og datagatewayen i det lokale miljø.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/22/2019
ms.author: kfollis
ms.openlocfilehash: be7f95b2bbbd6e5e6314c7fd57869a30c176746c
ms.sourcegitcommit: 320d83ab392ded71bfda42c5491acab3d9d357b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/10/2019
ms.locfileid: "74958488"
---
# <a name="power-bi-data-sources"></a>Power BI-datakilder

Følgende tabel indeholder de datakilder, som Power BI understøtter for datasæt, herunder oplysninger om DirectQuery og datagatewayen i det lokale miljø. Du kan finde oplysninger om dataflow under [Opret forbindelse til datakilder for Power BI-dataflow](service-dataflows-data-sources.md).

| Datakilde | Opret forbindelse fra skrivebord | Opret forbindelse og opdater fra tjenesten | DirectQuery/direkte forbindelse | Gateway (understøttes) | Gateway (påkrævet) |
|---|---|---|---|---|---|---|---|
| Access-database | Ja | Ja | Nej | Ja <sup>1</sup> | Ja |
| ActiveDirectory | Ja | Ja | Nej | Ja | Ja |
| Adobe Analytics | Ja | Ja | Nej | Nej | Nej |
| Amazon Redshift | Ja | Ja | Ja | Ja | Nej |
| appFigures | Ja | Ja | Nej | Nej | Nej |
| AtScale-kuber | Ja | Ja | Ja | Ja | Nej |
| Azure Analysis Services | Ja | Ja | Ja | Ja <sup>2</sup> | Nej |
| Azure Blob Storage | Ja | Ja | Nej | Ja | Nej |
| Azure Cosmos DB | Ja | Ja | Nej | Nej | Nej |
| Azure Cost Management | Ja | Ja | Nej | Nej | Nej |
| Azure Data Explorer (kusto) | Ja | Ja | Ja | Nej | Nej |
| Azure Data Lake Storage Gen1 | Ja | Ja | Nej | Nej | Nej |
| Azure Data Lake Storage Gen2 | Ja | Ja | Nej | Nej | Nej |
| Azure DevOps | Ja | Ja | Nej | Nej | Nej |
| Azure DevOps Server | Ja | Ja | Nej | Ja | Ja |
| Azure HDInsight (HDFS) | Ja | Ja | Nej | Nej | Nej |
| Azure HDInsight Spark | Ja | Ja | Ja | Nej | Nej |
| Azure SQL Database | Ja | Ja | Ja | Ja <sup>2</sup> | Nej |
| Azure SQL Data Warehouse | Ja | Ja | Ja | Nej | Nej |
| Azure Table Storage | Ja | Ja | Nej | Ja | Nej |
| BI Connector | Ja | Ja | Ja | Ja | Ja |
| BI360 – Budgeting & Financial Reporting | Ja | Ja | Nej | Nej | Nej |
| Common Data Service | Ja | Ja | Nej | Nej | Nej |
| Data.World – Hent datasæt | Ja | Ja | Nej | Nej | Nej |
| Denodo | Ja | Ja | Ja | Ja | Ja |
| Dremio | Ja | Ja | Ja | Ja | Ja |
| Dynamics 365 (online) | Ja | Ja | Nej | Nej | Nej |
| Dynamics 365 Business Central | Ja | Ja | Nej | Nej | Nej |
| Dynamics 365 Business Central (i det lokale miljø) | Ja | Ja | Nej | Nej | Nej |
| Dynamics 365 Customer Insights | Ja | Ja | Nej | Nej | Nej |
| Dynamics NAV | Ja | Ja | Nej | Nej | Nej |
| Emigo-datakilde | Ja | Ja | Nej | Nej | Nej |
| Entersoft Business Suite | Ja | Ja | Nej | Nej | Nej |
| Essbase | Ja | Ja | Ja | Ja | Ja |
| Exasol | Ja | Ja | Ja | Ja | Ja |
| Excel | Ja <sup>3</sup> | Ja <sup>3</sup> | Nej | Ja <sup>3</sup> | Nej <sup>4</sup> |
| Facebook | Ja | Ja | Nej | Nej | Nej |
| Fil | Ja | Ja | Nej | Ja | Ja |
| Mappe | Ja | Ja | Nej | Ja | Ja |
| GitHub | Ja | Ja | Nej | Nej | Nej |
| Google Analytics | Ja | Ja | Nej | Nej | Nej |
| Google BigQuery | Ja | Ja | Nej | Nej | Nej |
| Hadoop File (HDFS) | Ja | Nej | Nej | Nej | Nej |
| Interaktiv HDInsight-forespørgsel | Ja | Ja | Ja | Nej | Nej |
| IBM DB2 | Ja | Ja | Ja | Ja | Ja |
| IBM Informix Database | Ja | Ja | Nej | Ja | Ja |
| IBM Netezza | Ja | Ja | Ja | Ja | Ja |
| Impala | Ja | Ja | Ja | Ja | Ja |
| Indexima | Ja | Ja | Ja | Ja | Ja |
| Industrial App Store | Ja | Ja | Nej | Nej | Nej |
| Information Grid | Ja | Ja | Nej | Nej | Nej |
| Intersystems IRIS | Ja | Ja | Ja | Ja | Ja |
| Intune Data Warehouse | Ja | Ja | Nej | Nej | Nej |
| Jethro ODBC | Ja | Ja | Ja | Ja | Ja |
| JSON | Ja | Ja | Nej | Ja** | Nej <sup>4</sup> |
| Kyligence Enterprise | Ja | Ja | Ja | Ja | Ja |
| MailChimp | Ja | Ja | Nej | Nej | Nej |
| Marketo | Ja | Ja | Nej | Nej | Nej |
| MarkLogic ODBC | Ja | Ja | Ja | Ja | Ja |
| Microsoft Azure Consumption Insights | Ja | Ja | Nej | Nej | Nej |
| Microsoft Exchange | Ja | Ja | Nej | Ja | Nej |
| Microsoft Exchange Online | Ja | Ja | Nej | Nej | Nej |
| Microsoft Graph Security | Ja | Ja | Nej | Ja | Nej |
| Mixpanel | Ja | Ja | Nej | Nej | Nej |
| MySQL | Ja | Ja | Nej | Ja | Ja |
| OData | Ja | Ja | Nej | Ja | Nej |
| ODBC | Ja | Ja | Nej | Ja | Ja |
| OleDb | Ja | Ja | Nej | Ja | Ja |
| Oracle | Ja | Ja | Ja | Ja | Ja |
| Paxatas | Ja | Ja | Nej | Ja | Nej |
| PDF | Ja | Ja | Nej | Ja | Nej <sup>4</sup> |
| Planview Enterprise One – CTM | Ja | Ja | Nej | Nej | Nej |
| Planview Enterprise One – PRM | Ja | Ja | Nej | Nej | Nej |
| Planview Projectplace | Ja | Ja | Nej | Nej | Nej |
| PostgreSQL | Ja | Ja | Ja | Ja | Ja |
| Power BI-dataflow | Ja | Ja | Nej | Nej | Nej |
| Power BI-datasæt | Ja | Ja | Ja | Nej | Nej |
| Dataflow for Power Platform | Ja | Ja | Nej | Nej | Nej |
| Python-script | Ja | Ja <sup>5</sup> | Nej | Ja <sup>5</sup> | Ja |
| QubolePresto | Ja | Ja | Ja | Ja | Ja |
| Quick Base | Ja | Ja | Nej | Ja | Ja |
| QuickBooks Online | Ja | Ja | Nej | Nej | Nej |
| R-script | Ja | Ja <sup>5</sup> | Nej | Ja <sup>5</sup> | Nej |
| Roamler | Ja | Ja | Nej | Ja | Nej |
| Salesforce-objekter | Ja | Ja | Nej | Nej | Nej |
| Salesforce-rapporter | Ja | Ja | Nej | Nej | Nej |
| SAP Business Warehouse-meddelelsesserver | Ja | Ja | Ja | Ja | Ja |
| SAP Business Warehouse-server | Ja | Ja | Ja | Ja | Ja |
| SAP HANA | Ja | Ja | Ja | Ja | Ja |
| SharePoint-mappe | Ja | Ja | Nej | Ja | Nej <sup>4</sup> |
| SharePoint-liste | Ja | Ja | Nej | Ja | Nej <sup>4</sup> |
| SharePoint Online-liste | Ja | Ja | Nej | Ja <sup>2</sup> | Nej |
| Smartsheet | Ja | Ja | Nej | Nej | Nej |
| Snowflake | Ja | Ja | Ja | Ja | Ja |
| Spark | Ja | Ja | Ja | Ja | Nej |
| SparkPost | Ja | Ja | Nej | Nej | Nej |
| SQL Server | Ja | Ja | Ja | Ja | Ja |
| SQL Server Analysis Services | Ja | Ja | Ja | Ja | Ja |
| Stripe | Ja | Ja | Nej | Nej | Nej |
| SurveyMonkey | Ja | Ja | Nej | Ja | Nej |
| SweetIQ | Ja | Ja | Nej | Nej | Nej |
| Sybase | Ja | Ja | Nej | Ja | Ja |
| TeamDesk | Ja | Ja | Nej | Ja | Nej |
| Tenforce | Ja | Ja | Nej | Nej | Nej |
| Teradata | Ja | Ja | Ja | Ja | Ja |
| Tekst/CSV | Ja | Ja | Nej | Ja | Nej <sup>4</sup> |
| Twilio | Ja | Ja | Nej | Nej | Nej |
| tyGraph | Ja | Ja | Nej | Nej | Nej |
| Vertica | Ja | Ja | Ja | Ja | Ja |
| Web | Ja | Ja | Nej | Ja | Ja |
| Webtrends | Ja | Ja | Nej | Nej | Nej |
| Workforce Dimensions | Ja | Ja | Nej | Ja | Nej |
| XML | Ja | Ja | Nej | Ja | Nej <sup>4</sup> |
| Zendesk | Ja | Ja | Nej | Nej | Nej |
| | | | | | | | |

<sup>1</sup> Understøttes med [ACE OLEDB-provideren](https://www.microsoft.com/download/details.aspx?id=54920) installeret på samme maskine som gatewayen.

<sup>2</sup> Understøttes med den samme M-funktion som versionen i det lokale miljø.

<sup>3</sup> Filer af typen Excel 1997-2003 (.xls) kræver [ACE OLEDB-provideren](https://www.microsoft.com/download/details.aspx?id=54920).

<sup>4</sup> Kræves til teknologiversionen i det lokale miljø.

<sup>5</sup> Understøttes kun med den [personlige gateway](service-gateway-personal-mode.md).

## <a name="single-sign-on-sso-for-directquery-sources"></a>Enkeltlogon til DirectQuery-kilder

Når indstillingen for enkeltlogon er aktiveret, og dine brugere får adgang til rapporter, som er baseret på datakilden, sender Power BI deres godkendte Azure AD-legitimationsoplysninger i forespørgslerne til den underliggende datakilde. På den måde kan Power BI overholde de sikkerhedsindstillinger, der er konfigureret på datakildeniveauet.
Indstillingen for SSO gælder for alle datasæt, der bruger denne datakilde. Den påvirker ikke den godkendelsesmetode, der bruges til import af scenarier. Følgende datakilder understøtter enkeltlogon for forbindelser via DirectQuery:

- Azure SQL Database
- Azure SQL Data Warehouse
- Impala
- SAP HANA
- SAP BW
- SAP BW-meddelelsesserver
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure MFA (Multi-Factor Authentication) understøttes ikke. Brugere, der gerne vil bruge enkeltlogon med DirectQuery, skal fritages fra multifaktorgodkendelse.

## <a name="next-steps"></a>Næste trin

[Opret forbindelse til data i Power BI Desktop](desktop-quickstart-connect-to-data.md)  
[Brug af DirectQuery in Power BI](desktop-directquery-about.md)  
[Dynamiske data i SQL Server Analysis Services i Power BI](sql-server-analysis-services-tabular-data.md)  
[Hvad er en datagateway i det lokale miljø?](service-gateway-onprem.md)  
