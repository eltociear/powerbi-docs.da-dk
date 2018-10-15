---
title: SQL Database Auditing-indholdspakke
description: SQL Database Auditing-indholdspakke til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f0c98d88ad9b87e57cf8f1cf7c36a58e30b684ea
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545354"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>SQL Database Auditing-indholdspakke til Power BI
Power BI-indholdspakken til Azure [SQL Database Auditing](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) gør det muligt at forstå din databaseaktivitet og få indsigt i de afvigelser og uregelmæssigheder, der kunne være årsag til forretningsmæssige bekymringer eller give mistanke til brud på sikkerheden. 

Opret forbindelse til [SQL Database Auditing-indholdspakke](https://app.powerbi.com/getdata/services/sql-db-auditing) til Power BI.

>[!NOTE]
>Indholdspakken importerer data fra alle tabeller, der indeholder "AuditLogs" i navnet, og føjer dem til en samlet datamodeltabel ved navn "AuditLogs". De sidste 250.000 hændelser medtages, og dataene opdateres dagligt.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. Vælg Hent i feltet Tjenester.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. Vælg **SQL Database Auditing** \> **Hent**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. I vinduet Opret forbindelse til SQL Database Auditing:
   
   - Angiv kontonavnet til Azure Table Storage eller den URL-adresse, hvor dine logfiler lagres.
   
   - Angiv navnet på den SQL-server, som du vil bruge. Angiv "\*" for at indlæse overvågningslogger for alle servere.
   
   - Angiv navnet på den SQL-database, som du vil bruge. Angiv "\*" for at indlæse overvågningslogger for alle databaser.
   
   - Angiv navnet på den Azure-tabel, der indeholder de logfiler, du er interesseret i. Angiv "\*" for at indlæse overvågningslogger fra alle de tabeller, der har "AuditLogs" i deres navn.
   
   >[!IMPORTANT]
   >Af hensyn til ydeevnen er det en god ide altid at angive et specifikt tabelnavn, selvom alle overvågningslogger gemmes i en samlet tabel.
   
   - Angiv startdatoen for de overvågningslogger, som du er interesseret i. Angiv "\*" for at indlæse overvågningslogger med en kortere tidsgrænse eller "1d" for at indlæse overvågningslogger fra den sidste dag.
   
   - Angiv slutdatoen for de overvågningslogger, som du er interesseret i. Angiv "\*" for at indlæse overvågningslogger uden en øvre tidsgrænse.
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. Vælg **Nøgle** som godkendelsesmetode, og angiv din **kontonøgle** \> **Log på**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. Når Power BI har importeret dataene, vises der et nyt dashboard, en ny rapport og et nyt datasæt i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="next-steps"></a>Næste trin
[Hent data til Power BI](service-get-data.md)
[Hvad er Power BI?](power-bi-overview.md)
