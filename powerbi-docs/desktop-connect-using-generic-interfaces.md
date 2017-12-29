---
title: "Opret forbindelse til data med generiske grænseflader i Power BI Desktop"
description: "Få mere at vide om, hvordan du opretter forbindelse mellem forskellige datakilder og generiske grænseflader i Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 2083343e8642470b8eb21bf13ba75fe784351b1c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-data-using-generic-interfaces-in-power-bi-desktop"></a>Opret forbindelse til data med generiske grænseflader i Power BI Desktop
Du kan oprette forbindelse til en lang række forskellige datakilder i **Power BI Desktop** ved hjælp af de indbyggede dataforbindelser, der strækker sig lige fra **Access-databaser** til **Zendesk**-ressourcer, som vist i vinduet **Hent data**. Du kan også oprette forbindelse til mange *andre* typer datakilder, hvilket giver dig endnu flere muligheder for at oprette forbindelse, ved hjælp af de generiske grænseflader (f.eks **ODBC** eller **REST API'er**), der er indbygget i **Power BI Desktop**.

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_1.png)

## <a name="power-bi-desktop-data-interfaces"></a>Datagrænseflader i Power BI Desktop
**Power BI Desktop** indeholder en stadig stigende samling af dataforbindelser, der er udviklet til at oprette forbindelse til en bestemt datakilde. Dataforbindelsen **SharePoint-liste** leverer f.eks. specifikke felter og understøttende oplysninger under den forbindelsessekvens, der er udviklet til **SharePoint-lister**. Det samme er gældende for de andre datakilder, der findes i det vindue, der vises, når du vælger **Hent data > Flere...**  (som vist i det forrige billede).

Desuden kan du i **Power BI Desktop** oprette forbindelse til de datakilder, der ikke er specifikt identificeret på listerne **Hent Data**, ved hjælp af en af følgende generiske datagrænseflader:

* **ODBC**
* **OLE DB**
* **OData**
* **REST API'er**
* **R-Scripts**

Ved at angive de relevante parametre i de forbindelsesvinduer, som disse generiske grænseflader leverer, vil det antal datakilder, som du kan få adgang til og bruge i **Power BI Desktop**, vokse væsentligt.

Du kan finde en liste over de datakilder, disse generiske grænseflader kan få adgang til, i de følgende afsnit.

Kan du ikke finde den datakilde, du vil bruge med **Power BI Desktop**? [Fortæl os](https://ideas.powerbi.com/) det, så vi kan føje den til listen over ideer og anmodninger.

## <a name="data-sources-accessible-through-odbc"></a>Datakilder, der er tilgængelige via ODBC
Med **ODBC**-connectoren i **Power BI Desktop** kan du importere data fra en ODBC-driver fra en tredjepart ved at angive et **datakildenavn** eller en  *forbindelsesstreng*. Du kan også vælge at angive en SQL-sætning, som skal køres mod ODBC-driveren.

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_2.png)

Følgende liste indeholder nogle eksempler på de datakilder, som **Power BI Desktop** kan oprette forbindelse til ved hjælp af den generiske grænseflade **ODBC**.

| Generisk connector i Power BI Desktop | Ekstern datakilde | Link til flere oplysninger |
| --- | --- | --- |
| ODBC |Cassandra |[Cassandra ODBC-driveren](http://www.simba.com/drivers/cassandra-odbc-jdbc/) |
| ODBC |Couchbase DB |[Couchbase og Power BI](https://powerbi.microsoft.com/en-us/blog/visualizing-data-from-couchbase-server-v4-using-power-bi/) |
| ODBC |DynamoDB |[DynamoDB ODBC-driveren](http://www.simba.com/drivers/dynamodb-odbc-jdbc/) |
| ODBC |Google BigQuery |[BigQuery ODBC-driveren](http://www.simba.com/drivers/bigquery-odbc-jdbc/) |
| ODBC |Hbase |[Hbase ODBC-driveren](http://www.simba.com/drivers/hbase-odbc-jdbc/) |
| ODBC |Hive |[Hive ODBC-driveren](http://www.simba.com/drivers/hive-odbc-jdbc/) |
| ODBC |IBM Netezza |[IBM Netezza-oplysninger](https://www.ibm.com/support/knowledgecenter/SSULQD_7.2.1/com.ibm.nz.datacon.doc/c_datacon_plg_overview.html) |
| ODBC |Presto |[Presto ODBC-driveren](http://www.simba.com/drivers/presto-odbc-jdbc/) |
| ODBC |Projekt Online |[Project Online-artikel](desktop-project-online-connect-to-data.md) |
| ODBC |Progress OpenEdge |[Blogindlæg om Progress OpenEdge ODBC-driveren](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.progress.com%2Fblogs%2Fconnect-microsoft-power-bi-to-openedge-via-odbc-driver&data=02%7C01%7CMatt.Masson%40microsoft.com%7C5e63742e6c454308b58a08d4034b5923%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636137069555329811&sdata=gSu2Rq3vZ0uBVOgjaXxd8Y3uBf%2B8DidX6PG33jwAduY%3D&reserved=0) |

## <a name="data-sources-accessible-through-ole-db"></a>Datakilder, der er tilgængelige via OLE DB
Med **OLE DB**-connectoren i **Power BI Desktop** kan du importere data fra en OLE DB-driver fra en tredjepart ved at angive en *forbindelsesstreng*. Du kan også vælge at angive en SQL-sætning, som skal køres mod OLE DB-driveren.

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_3.png)

Følgende liste indeholder nogle eksempler på de datakilder, som **Power BI Desktop** kan oprette forbindelse til ved hjælp af den generiske grænseflade **OLE DB**.

| Generisk connector i Power BI Desktop | Ekstern datakilde | Link til flere oplysninger |
| --- | --- | --- |
| OLE DB |SAS OLE DB |[SAS-provider til OLE DB](https://support.sas.com/downloads/package.htm?pid=648) |
| OLE DB |Sybase OLE DB |[Sybase-provider til OLE DB](http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc35888.1550/doc/html/jon1256941734395.html) |

## <a name="data-sources-accessible-through-odata"></a>Datakilder, der er tilgængelige via OData
Med **OData**-connectoren i **Power BI Desktop** kan du importere data fra en hvilken som helst URL-adresse til **OData** ved at skrive eller indsætte URL-adressen til **OData**. Du kan tilføje flere URL-adressedele ved at indtaste eller indsætte disse links i tekstfelterne i vinduet **OData Feed**.

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_4.png)

Følgende liste indeholder nogle eksempler på de datakilder, som **Power BI Desktop** kan oprette forbindelse til ved hjælp af den generiske grænseflade **OData**.

| Generisk connector i Power BI Desktop | Ekstern datakilde | Link til flere oplysninger |
| --- | --- | --- |
| OData |Kommer snart |Vend snart tilbage for at se en liste over OData-datakilder |

## <a name="data-sources-accessible-through-rest-apis"></a>Datakilder, der er tilgængelige via REST API'er
Du kan oprette forbindelse til datakilder med **REST API'er** og dermed bruge data fra alle mulige forskellige datakilder, der understøtter **REST**.

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_5.png)

Følgende liste indeholder nogle eksempler på de datakilder, som **Power BI Desktop** kan oprette forbindelse til ved hjælp af den generiske grænseflade **REST API'er**.

| Generisk connector i Power BI Desktop | Ekstern datakilde | Link til flere oplysninger |
| --- | --- | --- |
| REST API'er |Couchbase DB |[Couchbase REST API-oplysninger](https://powerbi.microsoft.com/en-us/blog/visualizing-data-from-couchbase-server-v4-using-power-bi/) |

## <a name="data-sources-accessible-through-r-script"></a>Datakilder, der er tilgængelige via R Script
Du kan bruge **R Scripts** til at få adgang til datakilder og bruge disse data i **Power BI Desktop**.

![](media/desktop-connect-using-generic-interfaces/r-scripts-2.png)

Følgende liste indeholder nogle eksempler på de datakilder, som **Power BI Desktop** kan oprette forbindelse til ved hjælp af den generiske brugergrænseflade **OData**.

| Generisk connector i Power BI Desktop | Ekstern datakilde | Link til flere oplysninger |
| --- | --- | --- |
| R Script |SAS-filer |[R Script-vejledning fra CRAN](https://cran.r-project.org/doc/manuals/R-data.html) |
| R Script |SPSS-filer |[R Script-vejledning fra CRAN](https://cran.r-project.org/doc/manuals/R-data.html) |
| R Script |Statistiske R-filer |[R Script-vejledning fra CRAN](https://cran.r-project.org/doc/manuals/R-data.html) |

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Hvis du vil have mere at vide om datakilder, kan du se følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
