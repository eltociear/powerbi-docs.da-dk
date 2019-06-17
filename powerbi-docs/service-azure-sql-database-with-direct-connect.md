---
title: Azure SQL Database med DirectQuery
description: Azure SQL Database med DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/20/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 5365c076b75d0989df8db15c1dc16f4e11bc3f09
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448357"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database med DirectQuery

Få mere at vide om, hvordan du kan oprette direkte forbindelse til Azure SQL Database og oprette rapporter, der bruger livedata. Du kan beholde dine data ved kilden i stedet for i Power IB.

Med DirectQuery sendes forespørgsler tilbage til din Azure SQL Database, mens du udforsker dataene i rapportvisning. Denne oplevelse foreslås til brugere, der kender de databaser og enheder, de opretter forbindelse til.

**Bemærk!**

* Angiv det fuldt gyldige servernavn, når du opretter forbindelse (se yderligere oplysninger nedenfor)
* Kontrollér, at firewallreglerne for databasen er konfigureret til at "[Tillade adgang til Azure-tjenester](https://msdn.microsoft.com/library/azure/ee621782.aspx)".
* Hver handling, f.eks. markering af en kolonne eller tilføjelse af et filter, vil sende en forespørgsel tilbage til databasen
* Felterne opdateres ca. hver time (opdateringen skal ikke planlægges). Dette kan tilpasses i Avancerede indstillinger, når du opretter forbindelse.
* Spørgsmål og svar er ikke tilgængelige for DirectQuery-datasæt
* Skemaændringer hentes ikke automatisk

Disse begrænsninger og noter kan ændres, efterhånden som vi fortsat forbedrer oplevelserne. Trinnene til at oprette forbindelse er beskrevet nedenfor.

> [!Important]
> Vi har forbedret vores netværksmuligheder til Azure SQL Database.  For at få den bedste oplevelse og oprette forbindelse til din Azure SQL Database-datakilde kan du bruge Power BI Desktop.  Når du har bygget din model og rapport, kan du udgive den på Power BI-tjenesten.  Den direkte forbindelse til Azure SQL Database i Power BI-tjenesten frarådes nu.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop og DirectQuery

For at kunne oprette forbindelse til Azure SQL Database med DirectQuery skal du bruge Power BI Desktop. Denne metode sikrer yderligere fleksibilitet og funktioner. De rapporter, der oprettes ved hjælp af Power BI Desktop, kan derefter publiceres til Power BI-tjenesten. Du kan få mere at vide om at oprette forbindelse til [Azure SQL Database med DirectQuery](desktop-use-directquery.md) i Power BI Desktop.

## <a name="finding-parameter-values"></a>Find parameterværdier

Dit fulde gyldige servernavn og databasenavn kan findes på Azure-portalen.

![Ny opdatering til Azure Portal](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Opdatering til Azure Portal](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](includes/direct-query-sso.md)]

## <a name="next-steps"></a>Næste trin

* [Brug DirectQuery i Power BI Desktop](desktop-use-directquery.md)  
* [Hvad er Power BI?](power-bi-overview.md)  
* [Hent data til Power BI](service-get-data.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
