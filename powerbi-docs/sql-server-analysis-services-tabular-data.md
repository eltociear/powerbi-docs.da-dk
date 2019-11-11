---
title: Dynamiske SQL Server Analysis Services-data i Power BI
description: Dynamiske SQL Server Analysis Services-data i Power BI. Dette gøres via en datakilde, som blev konfigureret for en virksomhedsgateway.
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: Minewiskan
ms.author: owend
ms.reviewer: ''
ms.custom: ''
ms.date: 08/10/2017
LocalizationGroup: Data from databases
ms.openlocfilehash: 00b7c98236f37505fbb0ddec81a45b65bf3e3ee6
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73871180"
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>Dynamiske SQL Server Analysis Services-data i Power BI

I Power BI er der to måder du kan oprette forbindelse til en live SQL Server Analysis Services-server på. I **Hent data** kan du oprette forbindelse til en SQL Server Analysis Services-server, eller du kan oprette forbindelse til en [Power BI Desktop-fil](service-desktop-files.md) eller [Excel-projektmappe](service-excel-workbook-files.md), der allerede har forbindelse til en Analysis Services-server. Som bedste praksis anbefaler Microsoft på det kraftigste, at du bruger Power BI Desktop, da det indeholder samme omfattende værktøjssæt og muligheden for at opbevare en lokal sikkerhedskopi af Power BI Desktop-filen.

>[!IMPORTANT]
> * En administrator skal installere og konfigurere en datagateway i det lokale miljø, før der kan oprettes en direkte forbindelse til Analysis Services-serveren. Du kan finde flere oplysninger i [Datagateway i det lokale miljø](service-gateway-onprem.md).
> * Når du bruger gatewayen, forbliver dine data i det lokale miljø.  De rapporter, du opretter baseret på disse data, gemmes i Power BI-tjenesten. 
> * [Forespørsel i Spørgsmål og svar på naturligt sprog](service-q-and-a-direct-query.md) er i forhåndsvisning for live Analysis Services-forbindelser.

## <a name="to-connect-to-a-model-from-get-data"></a>Sådan opretter du forbindelse til en model fra Hent data

1. Vælg **Hent data** i **Mit arbejdsområde**. Du kan også skifte til et gruppearbejdsområde, hvis der findes et.

   ![Opret forbindelse til knappen Hent data](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)

2. Vælg **Databaser og mere**.

   ![Opret forbindelse til Hent data 1](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)

3. Vælg **SQL Server Analysis Services** > **Opret forbindelse**.

   ![Opret forbindelse til Hent data 2](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)

4. Vælg en server. Hvis du ikke kan se nogen servere angivet her, betyder det enten, at en gateway og datakilde ikke er konfigureret, eller din konto ikke er angivet under fanen **Brugere** i datakilden, i gatewayen. Kontakt din administrator.

5. Vælg den model, du vil oprette forbindelse til. Det kan være enten tabelformat eller flerdimensionel.

Når du har oprettet forbindelse til modellen, vises den på dit Power BI-websted i **Mit arbejdsområde/Datasæt**. Hvis du har skiftet til et gruppearbejdsområde, vises datasættet i gruppen.

![Opret forbindelse til datasæt](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>Dashboardfelter

Hvis du fastgør visuelle elementer fra en rapport til dashboardet, opdateres de fastgjorte felter automatisk hvert 10. minut. Hvis dataene på din lokale Analysis Services-server opdateres, bliver felterne automatisk opdateret efter 10 minutter.

## <a name="common-issues"></a>Almindelige problemer

* Fejl: kan ikke indlæse modelskema – Denne fejl opstår, når den bruger, der opretter forbindelse til SSAS, ikke har adgang til SSAS-databasen, -kuben og -modellen.

## <a name="next-steps"></a>Næste trin

* [Datagateway i det lokale miljø](service-gateway-onprem.md)  
* [Administrer Analysis Services-datakilder](service-gateway-enterprise-manage-ssas.md)  
* [Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)