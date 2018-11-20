---
title: SQL Database Auditing-indholdspakke
description: SQL Database Auditing-indholdspakke til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/09/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b3b461bedc9eb60607f56c82c5af8de0ed690c06
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507579"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>SQL Database Auditing-indholdspakke til Power BI

> [!IMPORTANT]
> SQL Database Auditing-indholdspakken frarådes og er ikke længere tilgængelig.
 
Power BI-indholdspakken til Azure [SQL Database Auditing](/azure/sql-database/sql-database-auditing/) gør det muligt at forstå din databaseaktivitet og få indsigt i de afvigelser og uregelmæssigheder, der kunne være årsag til forretningsmæssige bekymringer eller give mistanke til brud på sikkerheden. 

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
