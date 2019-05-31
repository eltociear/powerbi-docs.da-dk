---
title: Opret forbindelse til Microsoft Azure Consumption Insights med Power BI
description: Microsoft Azure Consumption Insights til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222139"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Opret forbindelse til Microsoft Azure Consumption Insights med Power BI
Udforsk og overvåg dine Microsoft Azure-forbrugsdata i Power BI med Power BI-indholdspakken. Dataene opdateres automatisk én gang om dagen.

Opret forbindelse til [Microsoft Azure Consumption Insights-indholdspakken](https://app.powerbi.com/getdata/services/azureconsumption) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. Markér **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Vælg **Microsoft Azure Consumption Insights** \> **Hent det nu**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Angiv den antal måneder, du vil importere data for, og dit Azure Enterprise-tilmeldingsnummer. Herunder kan du se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams).
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Angiv din Access-nøgle for at oprette forbindelse. Du kan finde din nøgle til tilmelding på Azure EA-portalen. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Importprocessen starter automatisk. Når du er færdig, vises et nyt dashboard, rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Mens dit datasæt er planlagt til daglig opdatering, du kan ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Til Microsoft Azure Consumption Insights-indholdspakken indeholder månedlige rapporteringsdata for det månedsinterval, du har angivet, når der oprettes forbindelse. Intervallet er et fleksibelt vindue, så de inkluderede datoer bliver opdateret, når datasættet opdateres.

## <a name="system-requirements"></a>Systemkrav
Indholdspakken kræver adgang til Enterprise-funktionerne på Azure-portalen. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
Power BI-rapportering er tilgængeligt for EA Direct, Partner og Indirect-kunder, der kan få vist faktureringsoplysninger. Læs nedenfor for at få oplysninger om hver af de værdier, der forventer forbindelsesflowet.

**Antal måneder**

* Antallet af måneder (1-36) af data fra i dag, du vil importere.

**Tilmeldingsnummer**

* Dit Azure Enterprise-tilmeldingsnummer, som du kan finde på den [Azure Enterprise Portal](https://ea.azure.com/) startskærm under **tilmeldingsoplysninger**.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Access-nøgle**

* Du kan finde din adgangsnøgle i Azure Enterprise portal, under **Download Usage** > **API Access Key**.
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Yderligere hjælp**

* Log på Azure Enterprise Portal for at få yderligere hjælp til at konfigurere Azure Enterprise Power BI-pakken, og få vist API-hjælpefilen under **hjælpe**. Du kan også finde yderligere oplysninger under **rapporter** -> **Download Usage** -> **API Access Key**.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

