---
title: Datakilder i Power BI Desktop
description: Datakilder i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/13/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: da269e3bb025e8d53ee3bb7707f3bb78d592e011
ms.sourcegitcommit: d010b10bc14097a1948daeffbc91b864bd91f7c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/13/2019
ms.locfileid: "56225908"
---
# <a name="data-sources-in-power-bi-desktop"></a>Datakilder i Power BI Desktop
Med Power BI Desktop kan du oprette forbindelse til data fra mange forskellige kilder. Der findes en komplet liste over tilgængelige datakilder nederst på siden.

Hvis du vil oprette forbindelse til data, skal du vælge **Hent data** på båndet **Hjem**. Hvis du vælger pil ned eller teksten **Hent data** på knappen, vises menuen med de **mest almindelige** datatyper på følgende billede:

![Hent data i Power BI Desktop](media/desktop-data-sources/data-sources_01.png)

Hvis du vælger **Mere...** i menuen **Mest almindelige**, vises vinduet **Hent data**. Du kan også åbne vinduet **Hent data** (og omgå menuen **Mest almindelige**) ved at vælge **ikonet** **Hent data** direkte.

![Knappen Hent data](media/desktop-data-sources/data-sources_02.png)

> [!NOTE]
> Power BI-teamet udvider hele tiden de datakilder, der er tilgængelige for **Power BI Desktop** og **Power BI-tjenesten**. Du kan derfor ofte se tidlige versioner af igangværende datakilder markeret som *Beta* eller *Preview*. Alle datakilder, der er markeret som *Beta* eller *Preview*, har begrænset support og funktionalitet og skal ikke bruges i produktionsmiljøer.

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
* PDF (beta)
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
* SAP Business Warehouse-programserver
* SAP Business Warehouse-meddelelsesserver
* Amazon Redshift
* Impala
* Google BigQuery
* Vertica
* Snowflake
* Essbase (beta)
* Dremio
* Exasol
* MarkLogic (Beta)
* AtScale-kuber (beta)
* BI Connector
* Jethro (beta)
* Kyligence Enterprise (beta)

> [!NOTE]
> Nogle databaseforbindelser kræver, at du aktiverer dem ved at vælge **Filer > Indstillinger > Indstillinger** og derefter vælger **Funktioner til eksempelvisning** og aktiverer forbindelsen. Hvis du ikke kan se nogle af de forbindelser, der er nævnt ovenfor, og du vil bruge dem, skal du kontrollere dine indstillinger for **Funktioner til eksempelvisning**. Bemærk også, at alle datakilder, der er markeret som *Beta* eller *Preview*, har begrænset support og funktionalitet og skal ikke bruges i produktionsmiljøer.

På følgende billede vises vinduet **Hent data** for **Database**.

![Hent data > Databaser](media/desktop-data-sources/data-sources_04.png)

Kategorien **Power BI** indeholder følgende dataforbindelser:

* Power BI-datasæt
* Power BI-dataflow (beta)

På følgende billede vises vinduet **Hent data** for **Power BI**.

![Hent data > Power BI](media/desktop-data-sources/data-sources_05.png)

Kategorien **Azure** indeholder følgende dataforbindelser:

* Azure SQL Database
* Azure SQL Data Warehouse
* Azure Analysis Services-database
* Azure Blob Storage
* Azure Table Storage
* Azure Cosmos DB (beta)
* Azure Data Lake Storage
* Azure HDInsight (HDFS)
* Azure HDInsight Spark
* Interaktiv HDInsight-forespørgsel
* Azure Data Explorer (beta)

På følgende billede vises vinduet **Hent data** for **Azure**.

![Hent data > Azure](media/desktop-data-sources/data-sources_06.png)

Kategorien **Onlinetjenester** indeholder følgende dataforbindelser:

* SharePoint Online-liste
* Microsoft Exchange Online
* Dynamics 365 (online)
* Dynamics NAV
* Dynamics 365 Business Central
* Dynamics 365 Business Central (i det lokale miljø)
* Common Data Service til apps (beta)
* Microsoft Azure Consumption Insights (beta)
* Azure DevOps (beta)
* Azure DevOps Server (beta)
* Salesforce-objekter
* Salesforce-rapporter
* Google Analytics
* Adobe Analytics
* appFigures (beta)
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
* Emigo datakilde (beta)
* Microsoft Graph Security (beta)

På følgende billede vises vinduet **Hent data** for **Onlinetjenester**.

![Hent data > Onlinetjenester](media/desktop-data-sources/data-sources_07.png)

Kategorien **Andet** indeholder følgende dataforbindelser:

* Web
* SharePoint-liste
* OData-feed
* Active Directory
* Microsoft Exchange
* Hadoop-fil (HDFS)
* Spark
* R Script
* Python-script
* ODBC
* OLE DB
* Workforce Dimensions (beta)
* Denado
* Paxata (beta)
* SurveyMonkey (beta)
* QubolePresto (beta)
* Hurtig Base (beta)
* Tom forespørgsel

På følgende billede vises vinduet **Hent data** for **Andet**.

![Hent data > Andet](media/desktop-data-sources/data-sources_08.png)

> [!NOTE]
> På nuværende tidspunkt er det ikke muligt at oprette forbindelse til brugerdefinerede datakilder, der er beskyttet via Azure Active Directory.

## <a name="connecting-to-a-data-source"></a>Opret forbindelse til en datakilde
For at oprette forbindelse til en datakilde skal du vælge datakilden i vinduet **Hent data** og vælge **Opret forbindelse**. På følgende billede er **Web** valgt fra kategorien **Andet** for dataforbindelsen.

![Opret forbindelse til web](media/desktop-data-sources/data-sources_08.png)

Der vises et forbindelsesvindue, som er specifikt for typen af dataforbindelse. Hvis der kræves legitimationsoplysninger, bliver du bedt om at angive dem. På følgende billede vises en URL-adresse, der angives for at oprette forbindelse til en webdatakilde.

![angive web-URL-adresse](media/desktop-data-sources/datasources_fromwebbox.png)

Når der er angivet forbindelsesoplysninger for URL-adressen eller ressourcen, skal du vælge **OK**. Power BI Desktop opretter forbindelse til datakilden og viser de tilgængelige datakilder i **navigatoren**.

![Skærmen Navigator](media/desktop-data-sources/datasources_fromnavigatordialog.png)

Du kan enten indlæse data ved at vælge knappen **Indlæs** nederst i ruden **Navigator**, eller du kan redigere forespørgslen, før du indlæser data, ved at vælge knappen **Rediger**.

Det er det eneste, du skal gøre for at oprette forbindelse til datakilder i Power BI Desktop! Prøv at oprette forbindelse til data fra vores stadig større liste over datakilder, og vend ofte tilbage – vi tilføjer hele tiden nye datakilder på denne liste.

## <a name="next-steps"></a>Næste trin
Du kan gøre mange forskellige ting med Power BI Desktop. Du kan finde flere oplysninger om funktionerne i følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datatyper i Power BI Desktop](desktop-data-types.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)    
