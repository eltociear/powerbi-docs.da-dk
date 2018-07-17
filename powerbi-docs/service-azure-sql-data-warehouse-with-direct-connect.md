---
title: Azure SQL Data Warehouse med DirectQuery
description: Azure SQL Data Warehouse med DirectQuery
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/20/2018
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: 0f2c3649a2c6e0582fe7536473f7a6ee9067ee1d
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37137439"
---
# <a name="azure-sql-data-warehouse-with-directquery"></a>Azure SQL Data Warehouse med DirectQuery
Med Azure SQL Data Warehouse med DirectQuery kan du oprette dynamiske rapporter, der er baseret på data og målinger, du allerede har i Azure SQL Data Warehouse. Med DirectQuery sendes forespørgsler tilbage til dit Azure SQL Data Warehouse i realtid, når du udforsker dataene. Dette, kombineret med skalaen for SQL Data Warehouse, gør det muligt for brugere at oprette dynamiske rapporter på få minutter med terabytes af data. Desuden kan brugere med indførelsen af knappen **Åbn i Power BI** oprette direkte forbindelse fra Power BI til deres SQL Data Warehouse uden at skulle angive oplysninger manuelt.

Når du bruger SQL Data Warehouse-forbindelsen:

* Angiv det fuldt kvalificerede servernavn, når du opretter forbindelse (se flere oplysninger nedenfor)
* Kontrollér, at firewallreglerne for serveren er konfigureret til at "Tillade adgang til Azure-tjenester"
* Hver handling, f.eks. markering af en kolonne eller tilføjelse af et filter, vil direkte forespørge Data Warehouse
* Felterne er angivet til at opdatere ca. hver 15 minutter, og opdateringen skal ikke planlægges.  Dette kan tilpasses i Avancerede indstillinger, når du opretter forbindelse.
* Spørgsmål og svar er ikke tilgængelig for DirectQuery-datasæt
* skemaændringer hentes ikke automatisk

Disse begrænsninger og noter kan ændres, når vi fortsætter med at forbedre oplevelsen. Trinnet til at oprette forbindelse er beskrevet nedenfor.

## <a name="using-the-open-in-power-bi-button"></a>Brug knappen "Åbn i Power BI"

> [!Important]
> Vi har forbedret vores netværksmuligheder til Azure SQL Data Warehouse.  For at få den bedste oplevelse og oprette forbindelse til din Azure SQL Data Warehouse-datakilde kan du bruge Power BI Desktop.  Når du har bygget din model og rapport, kan du udgive den på Power BI-tjenesten.  Den direkte forbindelse til Azure SQL Data Warehouse i Power BI-tjenesten frarådes nu.
>

Den nemmeste måde at flytte mellem dit SQL Data Warehouse og Power BI er med knappen **Åbn i Power BI** i Azure Preview-portalen. Med denne knap kan du nemt og problemfrit begynde at oprette nye dashboards i Power BI.

1. For at komme i gang skal du gå til din SQL Data Warehouse-forekomst i Azure Preview-portalen. Bemærk, at SQL Data Warehouse på nuværende tidspunkt kun har en tilstedeværelse i Azure Preview-portalen.
2. Klik på knappen **Åbn i Power BI**
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/openinpowerbi.png)
3. Hvis vi ikke kan logge dig på direkte, eller hvis du ikke har en Power BI-konto, skal du logge på.
4. Du bliver dirigeret til SQL Data Warehouse-forbindelsessiden, hvor oplysningerne fra dit SQL Data Warehouse er udfyldt på forhånd. Angiv dine legitimationsoplysninger, og tryk på Tilslut for at oprette forbindelse.

## <a name="connecting-through-power-bi"></a>Opret forbindelse via Power BI
SQL Data Warehouse er også angivet på siden Power BI Hent data. 

1. Vælg **Hent data** nederst i venstre navigationsrude.  
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/getdatabutton.png)
2. I **Databaser** skal du vælge **Hent**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/databases.png)
3. Vælg **SQL Data Warehouse** \> **Tilslut**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/azuresqldatawarehouseconnect.png)
4. Angiv de nødvendige oplysninger for at oprette forbindelse. Sektionen **Find parametre** nedenfor viser, hvor disse data kan være placeret i Azure-portalen.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servername.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servernamewithadvanced.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/username.png)
   
   > [!NOTE]
   > Brugernavnet er en bruger, der er defineret i din Azure SQL Data Warehouse-forekomst.
   > 
   > 
5. Analysér datasættet ved at vælge det nye felt eller det nyoprettede dataset, der er angivet med en stjerne. Dette datasæt har samme navn som din database.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/dataset2.png)
6. Du kan udforske alle tabellerne og kolonnerne. Hvis du markerer en kolonne, sendes en forespørgsel tilbage til datakilden og opretter dynamisk det visuelle element. Filtre skal også oversættes til forespørgsler tilbage til dit datawarehouse. Disse visuelle elementer kan gemmes i en ny rapport og fastgøres tilbage i dit dashboard.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/explore3.png)

## <a name="finding-parameter-values"></a>Find parameterværdier
Din fulde servernavn og databasenavn kan findes i Azure Preview-portalen. Bemærk, at SQL Data Warehouse på nuværende tidspunkt kun har en tilstedeværelse i Azure Preview-portalen.

![](media/service-azure-sql-data-warehouse-with-direct-connect/azureportal.png)

> [!NOTE]
> Hvis din Power BI-lejer befinder sig i det samme område som Azure SQL Data Warehouse, er der ingen gebyrer for udgående data. Du kan se, hvor din Power BI-befinder sig, ved hjælp af [disse instruktioner](https://docs.microsoft.com/power-bi/service-admin-where-is-my-tenant-located).
>

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](power-bi-overview.md)  
[Hent data til Power BI](service-get-data.md)  
[Azure SQL Data Warehouse](https://azure.microsoft.com/documentation/services/sql-data-warehouse/)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)