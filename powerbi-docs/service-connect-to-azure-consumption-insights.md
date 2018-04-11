---
title: Opret forbindelse til Microsoft Azure Consumption Insights med Power BI
description: Microsoft Azure Consumption Insights til Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggies
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 709921a98f6e06572063cf78a83e42bd6b439262
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Opret forbindelse til Microsoft Azure Consumption Insights med Power BI
Udforsk og overvåg dine Microsoft Azure-forbrugsdata i Power BI med Power BI-indholdspakken. Dataene opdateres automatisk én gang dagligt.

Opret forbindelse til [Microsoft Azure Consumption Insights-indholdspakken](https://app.powerbi.com/getdata/services/azureconsumption) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Vælg **Microsoft Azure Consumption Insights** \> **Hent**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Angiv den antal måneder, du vil importere data for, og dit Azure Enterprise-tilmeldingsnummer. Herunder kan du se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams).
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Angiv din Access-nøgle for at oprette forbindelse. Du finder nøglen til tilmelding på Azure EA Portal. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Importprocessen starter automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Microsoft Azure Consumption Insights-indholdspakken indeholder månedlige rapporteringsdata for det månedsinterval, du angiver under forbindelsesflowet. Intervallet er et fleksibelt vindue, så de inkluderede datoer bliver opdateret, når datasættet opdateres.

## <a name="system-requirements"></a>Systemkrav
Indholdspakken kræver adgang til virksomhedsfunktioner på Azure Portal. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søg efter parametre
Power BI-rapportering er tilgængeligt for EA-kunder af typen Direct, Partner og Indirect, som kan få vist faktureringsoplysninger. Herunder kan du finde oplysninger om hver af de værdier, der forventes i forbindelsesflowet.

**Antal måneder**

* Dette skal være et tal mellem 1-36, der repræsenterer det antal måneder (fra i dag), du vil importere data for.

**Tilmeldingsnummer**

* Dette er dit Azure Enterprise-tilmeldingsnummer, som findes på startskærmen på [Azure Enterprise Portal](https://ea.azure.com/) under "Enrollment Detail".
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Access-nøgle**

* Du finder din nøgle på Azure Enterprise Portal under "Download Usage" > "API Access Key"
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Yderligere hjælp**

* Hvis du vil have yderligere hjælp til at konfigurere Azure Enterprise Power BI-pakken, skal du logge på Azure Enterprise Portal for at få vist API-hjælpefilen under "Help" og yderligere oplysninger under Reports -> Download Usage -> API Access Key. 

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

