---
title: Datakilder i Power BI Desktop
description: Datakilder i Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1558f78f8f496814ac7745afe9b86f327ef7772b
ms.sourcegitcommit: 509be8852ba7595b9441c9479224f9dca298b26d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/09/2018
ms.locfileid: "33923448"
---
# <a name="data-sources-in-power-bi-desktop"></a>Datakilder i Power BI Desktop
Med Power BI Desktop kan du oprette forbindelse til data fra mange forskellige kilder. Der findes en komplet liste over tilgængelige datakilder nederst på siden.

Hvis du vil oprette forbindelse til data, skal du vælge **Hent data** på båndet **Hjem**. Hvis du vælger pil ned eller teksten **Hent data** på knappen, vises menuen med de **mest almindelige** datatyper på følgende billede:

![Hent data i Power BI Desktop](media/desktop-data-sources/data-sources_01.png)

Hvis du vælger **Mere...** i menuen **Mest almindelige**, vises vinduet **Hent data**. Du kan også åbne vinduet **Hent data** (og omgå menuen **Mest almindelige**) ved at vælge **ikonet** **Hent data** direkte.

![Knappen Hent data](media/desktop-data-sources/data-sources_02.png)

> [!NOTE]
> Power BI-teamet udvider hele tiden de datakilder, der er tilgængelige for **Power BI Desktop** og **Power BI-tjenesten**. Du kan derfor ofte se tidlige versioner af igangværende datakilder markeret som *Beta* eller *Preview*. Alle datakilder, der er markeret som *Beta* eller *Preview*, har begrænset support og funktionalitet og skal ikke bruges i produktionsmiljøer.
> 
> 

## <a name="data-sources"></a>Datakilder
Datatyper er organiseret i følgende kategorier:

* Alle
* Fil
* Database
* Power BI
* Azure
* Onlinetjenester
* Andet

Kategorien **Alle** inkluderer alle dataforbindelsestyper fra alle kategorier.

Kategorien **Fil** indeholder følgende dataforbindelser:

* Excel
* Tekst/CSV
* XML
* JSON
* Mappe
* SharePoint-mappe

På følgende billede vises vinduet **Hent data** for **Fil**.

![Hent data > Filer](media/desktop-data-sources/data-sources_03.png)

Kategorien **Database** indeholder følgende dataforbindelser:

* SQL Server-database
* Access-database
* SQL Server Analysis Services-database
* Oracle-database
* IBM DB2-database
* IBM Informix-database (beta)
* IBM Netezza
* MySQL-database
* PostgreSQL-database
* Sybase-database
* Teradata-database
* SAP HANA-database
* SAP Business Warehouse Application Server
* SAP Business Warehouse Message Server (beta)
* Amazon Redshift
* Impala
* Google BigQuery
* Snowflake
* Exasol

> [!NOTE]
> Nogle databaseforbindelser kræver, at du aktiverer dem ved at vælge **Filer > Indstillinger > Indstillinger** og derefter vælger **Funktioner til eksempelvisning** og aktiverer forbindelsen. Hvis du ikke kan se nogle af de forbindelser, der er nævnt ovenfor, og du vil bruge dem, skal du kontrollere dine indstillinger for **Funktioner til eksempelvisning**. Bemærk også, at alle datakilder, der er markeret som *Beta* eller *Preview*, har begrænset support og funktionalitet og skal ikke bruges i produktionsmiljøer.
> 
> 

På følgende billede vises vinduet **Hent data** for **Database**.

![Hent data > Databaser](media/desktop-data-sources/data-sources_04.png)

Kategorien **Power BI** indeholder følgende dataforbindelser:

* Power BI-datasæt
* Power BI-datagrupper (beta)

På følgende billede vises vinduet **Hent data** for **Power BI**.

![Hent data > Power BI](media/desktop-data-sources/data-sources_05.png)

Kategorien **Azure** indeholder følgende dataforbindelser:

* Azure SQL Database
* Azure SQL Data Warehouse
* Azure Analysis Services-database
* Azure Blob Storage
* Azure Table Storage
* Azure Cosmos DB (beta)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (beta)
* HDInsight Interactive Query (beta)
* Azure KustoDB (beta)

På følgende billede vises vinduet **Hent data** for **Azure**.

![Hent data > Azure](media/desktop-data-sources/data-sources_06.png)

Kategorien **Onlinetjenester** indeholder følgende dataforbindelser:

* SharePoint Online-liste
* Microsoft Exchange Online
* Dynamics 365 (online)
* Dynamics NAV (beta)
* Dynamics 365 Business Central
* Common Data Service til Apps (beta)
* Common Data Service (beta)
* Microsoft Azure Consumption Insights (beta)
* Visual Studio Team Services (beta)
* Salesforce-objekter
* Salesforce-rapporter
* Google Analytics
* Adobe Analytics
* appFigures (beta)
* comScore Digital Analytix (beta)
* Dynamics 365 for Customer Insights (beta)
* Data.World – Get Dataset (beta)
* Facebook
* GitHub (beta)
* MailChimp (beta)
* Marketo (beta)
* Mixpanel (beta)
* Planview Enterprise One – PRM (beta)
* Planview Projectplace (beta)
* QuickBooks Online (beta)
* Smartsheet
* SparkPost (beta)
* Stripe (beta)
* SweetIQ (beta)
* Planview Enterprise One – CMT (beta)
* Twilio (beta)
* tyGraph (beta)
* Webtrends (beta)
* Zendesk (beta)
* TeamDesk (beta)

På følgende billede vises vinduet **Hent data** for **Onlinetjenester**.

![Hent data > Onlinetjenester](media/desktop-data-sources/data-sources_07.png)

Kategorien **Andet** indeholder følgende dataforbindelser:

* Vertica (beta)
* Web
* SharePoint-liste
* OData-feed
* Active Directory
* Microsoft Exchange
* Hadoop-fil (HDFS)
* Spark (beta)
* R Script
* ODBC
* OLE DB
* Tom forespørgsel

På følgende billede vises vinduet **Hent data** for **Andet**.

![Hent data > Andet](media/desktop-data-sources/data-sources_08.png)

> [!NOTE]
> På nuværende tidspunkt er det ikke muligt at oprette forbindelse til brugerdefinerede datakilder, der er beskyttet via Azure Active Directory.
> 
> 

## <a name="connecting-to-a-data-source"></a>Opret forbindelse til en datakilde
For at oprette forbindelse til en datakilde skal du vælge datakilden i vinduet **Hent data** og vælge **Opret forbindelse**. På følgende billede er **Web** valgt fra kategorien **Andet** for dataforbindelsen.

![Opret forbindelse til web](media/desktop-data-sources/data-sources_08a.png)

Der vises et forbindelsesvindue, som er specifikt for typen af dataforbindelse. Hvis der kræves legitimationsoplysninger, bliver du bedt om at angive dem. På følgende billede vises en URL-adresse, der angives for at oprette forbindelse til en webdatakilde.

![angive web-URL-adresse](media/desktop-data-sources/datasources_fromwebbox.png)

Når der er angivet forbindelsesoplysninger for URL-adressen eller ressourcen, skal du vælge **OK**. Power BI Desktop opretter forbindelse til datakilden og viser de tilgængelige datakilder i **navigatoren**.

![Skærmen Navigator](media/desktop-data-sources/datasources_fromnavigatordialog.png)

Du kan enten indlæse data ved at vælge knappen **Indlæs** nederst i ruden **Navigator**, eller du kan redigere forespørgslen, før du indlæser data, ved at vælge knappen **Rediger**.

Det er det eneste, du skal gøre for at oprette forbindelse til datakilder i Power BI Desktop! Prøv at oprette forbindelse til data fra vores stadig større liste over datakilder, og vend ofte tilbage – vi tilføjer hele tiden nye datakilder på denne liste.

## <a name="next-steps"></a>Næste trin
Du kan gøre mange forskellige ting med Power BI Desktop. Du kan finde flere oplysninger om funktionerne i følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datatyper i Power BI Desktop](desktop-data-types.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)    
