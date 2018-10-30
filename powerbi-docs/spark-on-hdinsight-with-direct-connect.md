---
title: Spark on HDInsight med DirectQuery
description: Spark on HDInsight med DirectQuery
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 92b8d0e0ecfa9bae36e552e30cf8f1a7fcecff4b
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/25/2018
ms.locfileid: "50100743"
---
# <a name="spark-on-hdinsight-with-directquery"></a>Spark on HDInsight med DirectQuery

Med Spark on Azure HDInsight med DirectQuery kan du oprette dynamiske rapporter, der er baseret på data og målinger, du allerede har i din Spark-klynge. Med DirectQuery sendes forespørgsler tilbage til din Azure HDInsight Spark-klynge, mens du udforsker dataene i rapportvisning. Denne oplevelse foreslås for brugere, der kender de enheder, de opretter forbindelse til.

> [!WARNING]
> Automatisk feltopdatering er blevet deaktiveret for dashboardfelter, der er bygget på Spark-baserede datasæt. Du kan vælge **Opdater dashboardfelter** for at opdatere manuelt. Rapporter påvirkes ikke og bør forblive opdateret. 

Du kan bruge følgende trin til at oprette forbindelse til din Spark på Azure HDInsight-datakilde ved hjælp af DirectQuery i Power BI-tjenesten.

> [!Important]
> Vi har forbedret vores netværksmuligheder til Spark.  For at få den bedste oplevelse og oprette forbindelse til din Spark-datakilde kan du bruge Power BI Desktop.  Når du har bygget din model og rapport, kan du udgive den på Power BI-tjenesten.  Den direkte forbindelse til Spark i Power BI-tjenesten frarådes nu.

1. Vælg **Hent data** nederst i venstre navigationsrude.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata.png)
2. Vælg **Databases & More** (Databaser og mere).

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata-databases.png)
3. Vælg connectoren **Spark på HDInsight**, og vælg **Opret forbindelse**.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata-databases-connect.png)
4. Angiv navnet på den **server**, du vil oprette forbindelse til, samt dit **brugernavn** og din **adgangskode**. Serveren er altid i formatet \<klyngenavn\>. azurehdinsight.net. Du kan se flere oplysninger om, hvordan du finder disse værdier, nedenfor.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-server-name.png)

     ![](media/spark-on-hdinsight-with-direct-connect/spark-username.png)
5. Når du har oprettet forbindelse, kan du se et nyt datasæt med navnet "SparkDataset". Du kan også få adgang til datasættet via det pladsholderfelt, der er oprettet.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-dataset.png)
6. Når du foretager detailudledning af datasættet, kan du udforske alle tabeller og kolonner i databasen. Hvis du markerer en kolonne, sendes en forespørgsel tilbage til datakilden, og det visuelle element oprettes dynamisk. Disse visuelle elementer kan gemmes i en ny rapport og fastgøres tilbage i dit dashboard.

## <a name="finding-your-spark-on-hdinsight-parameters"></a>Find dine Spark på HDInsight-parametre

Serveren er altid i formatet \<klyngenavn\>.azurehdinsight.net og kan ses på Azure-portalen.

![](media/spark-on-hdinsight-with-direct-connect/spark-server-name-parameter.png)

Brugernavnet og adgangskoden findes også på Azure-portalen.

## <a name="limitations"></a>Begrænsninger

Disse begrænsninger og noter kan ændres, når vi fortsætter med at forbedre oplevelserne. Du kan finde yderligere dokumentation i [Brug BI-værktøjer med Apache Spark til Azure HDInsight](/azure/hdinsight/spark/apache-spark-use-bi-tools/)

* Power BI-tjenesten understøtter kun en konfiguration med Spark 2.0 og HDInsight 3.5.
* Enhver handling, f.eks. markering af en kolonne eller tilføjelse af et filter, sender en forespørgsel tilbage til databasen – så før du vælger meget store felter, bør du overveje at vælge en passende visualiseringstype.
* Spørgsmål og svar er ikke tilgængelig for DirectQuery-datasæt.
* Skemaændringer hentes ikke automatisk.
* Power BI understøtter 16.000 kolonner **på tværs af alle tabeller** inden for et datasæt. Power BI omfatter desuden en intern kolonne med rækkenummer pr. tabel. Det betyder, at hvis du har 100 tabeller i datasættet, vil det tilgængelige antal kolonner være 15.900. Afhængigt af mængden af data, du arbejder med fra din Spark-datakilde, kan du støde på denne begrænsning.

## <a name="troubleshooting"></a>Fejlfinding

Hvis du har problemer med at udføre forespørgsler mod klyngen, skal du kontrollere, at appen stadig kører og om nødvendigt genstarte den.

Du kan også tildele flere ressourcer på Azure-portalen under **Configuration** > **Scale Cluster** (Konfiguration/Skalér klynge):

![](media/spark-on-hdinsight-with-direct-connect/spark-scale.png)

## <a name="next-steps"></a>Næste trin

[Kom i gang: Opret Apache Spark-klyngen på HDInsight Linux, og kør interaktive forespørgsler ved hjælp af Spark SQL](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql/)  
[Hvad er Power BI?](power-bi-overview.md)  
[Hent data til Power BI](service-get-data.md)
[Brug Kerberos på gatewayen i det lokale miljø til SSO](service-gateway-sso-kerberos.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)