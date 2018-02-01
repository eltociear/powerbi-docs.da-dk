---
title: "Understøttede datakilder i forbindelse med DirectQuery i Power BI"
description: Hent en liste over, hvilke datakilder der kan bruges i forbindelse med DirectQuery.
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 6e93a6d216603ee247979c586481115ba3f67d77
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/25/2018
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Understøttede datakilder i forbindelse med DirectQuery i Power BI
**Power BI Desktop** og **Power BI-tjenesten** indeholder mange datakilder, som du kan oprette forbindelse til, og som kan give dig adgang til data. I denne artikel beskrives, hvilke datakilder til Power BI der understøtter forbindelsesmetoden, der er kendt som **DirectQuery**. Du kan finde flere oplysninger om DirectQuery under [**DirectQuery i Power BI**](desktop-directquery-about.md).

Følgende datakilder understøtter DirectQuery i Power BI:

* Amazon Redshift
* Azure HDInsight Spark (beta)
* Azure SQL Database
* Azure SQL Data Warehouse
* Google BigQuery (beta)
* IBM Netezza (beta)
* Impala (version 2.x)
* Oracle Database (version 12 og nyere)
* SAP Business Warehouse (beta)
* SAP HANA
* Snowflake
* Spark (beta) (version 0.9 og nyere)
* SQL Server
* Teradata Database
* Vertica (beta)

Datakilder med **(beta)** eller **(prøveversion)** i navnet kan ændres og understøttes ikke til produktionsanvendelse. De understøttes desuden muligvis ikke efter publicering af en rapport til **Power BI-tjenesten**, hvilket betyder, at der kan opstå en fejl, når du åbner en publiceret rapport eller udforsker datasættet.

Den eneste forskel mellem datakilder med **(beta)** og **(prøveversion)** i navnet er, at datakilder med **(prøveversion)** i navnet skal aktiveres som en prøveversionsfunktion, før de kan bruges. For at aktivere en datatilslutning af typen **(prøveversion)** skal du i **Power BI Desktop** gå til **Fil > Indstillinger** og derefter **Indstillinger > Indstillinger > Prøveversionsfunktioner**.

## <a name="on-premises-gateway-requirements"></a>Krav til gateways i det lokale miljø
I følgende tabel kan du se, om der kræves en **datagateway i det lokale miljø** for at oprette forbindelse til den angivne datakilde, efter en rapport er publiceret til **Power BI service**.

| Kilde | Er en gateway påkrævet? |
| --- | --- |
| SQL Server |Ja |
| Azure SQL Database |Nej |
| Azure SQL Data Warehouse |Nej |
| SAP HANA |Ja |
| Oracle Database |Ja |
| Teradata Database |Ja |
| Amazon Redshift |Nej |
| Impala (version 2.x) |Ja |
| Snowflake (prøveversion) |Understøttes endnu ikke i **Power BI-tjenesten** |
| Spark (beta), version 0.9 og nyere |Understøttes endnu ikke i **Power BI-tjenesten** |
| Azure HDInsight Spark (beta) |Understøttes endnu ikke i **Power BI-tjenesten** |
| IBM Netezza (beta) |Understøttes endnu ikke i **Power BI-tjenesten** |
| SAP Business Warehouse (beta) |Understøttes endnu ikke i **Power BI-tjenesten** |

## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om DirectQuery i følgende ressourcer:

* [DirectQuery i Power BI](desktop-directquery-about.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [Datagateway i det lokale miljø](service-gateway-onprem.md)

