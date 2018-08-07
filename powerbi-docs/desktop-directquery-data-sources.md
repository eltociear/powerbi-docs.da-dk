---
title: Understøttede datakilder i forbindelse med DirectQuery i Power BI
description: Hent en liste over, hvilke datakilder der kan bruges i forbindelse med DirectQuery.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 61421db59a6488394cad0b8a921590a90b020bff
ms.sourcegitcommit: df7a58dae14ef311516c9b3098f87742786f0479
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2018
ms.locfileid: "39280633"
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
* SAP Business Warehouse Application Server
* SAP Business Warehouse Message Server (beta)
* SAP HANA
* Snowflake
* Spark (beta) (version 0.9 og nyere)
* SQL Server
* Teradata Database
* Vertica (beta)

Datakilder med **(beta)** eller **(prøveversion)** i navnet kan ændres og understøttes ikke til produktionsanvendelse. De understøttes desuden muligvis ikke efter publicering af en rapport til **Power BI-tjenesten**, hvilket betyder, at der kan opstå en fejl, når du åbner en publiceret rapport eller udforsker datasættet.

Den eneste forskel mellem datakilder med **(beta)** og **(prøveversion)** i navnet er, at datakilder med **(prøveversion)** i navnet skal aktiveres som en prøveversionsfunktion, før de kan bruges. For at aktivere en dataconnector **(prøveversion)** skal du i **Power BI Desktop** gå til **Filer > Indstillinger > Indstillinger** og derefter vælge **Prøveversionsfunktioner**.

> [!NOTE]
> DirectQuery-forespørgsler til SQL Server kræver godkendelse ved hjælp af aktuelle legitimationsoplysninger til Windows-godkendelse eller databaselegitimationsoplysninger, for at der kan oprettes adgang. Andre typer legitimationsoplysninger understøttes ikke.
>

## <a name="on-premises-gateway-requirements"></a>Krav til gateways i det lokale miljø
I følgende tabel kan du se, om der kræves en **datagateway i det lokale miljø** for at oprette forbindelse til den angivne datakilde, efter en rapport er publiceret i **Power BI tjenesten**.

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
| Snowflake |Ja |
| Spark (beta), version 0.9 og nyere |Understøttes endnu ikke i **Power BI-tjenesten** |
| Azure HDInsight Spark (beta) |Nej |
| IBM Netezza |Ja |
| SAP Buisness Warehouse Application Server |Ja |
| SAP Buisness Warehouse Message Server |Understøttes endnu ikke i **Power BI-tjenesten** |
| Google BigQuery |Nej |


## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om DirectQuery i følgende ressourcer:

* [DirectQuery i Power BI](desktop-directquery-about.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [Datagateway i det lokale miljø](service-gateway-onprem.md)

