---
title: Opret forbindelse til Microsoft Azure Consumption Insights med Power BI
description: Microsoft Azure Consumption Insights til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 09/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e51f936e44e8c8ee3442aedfb2389675774c0a47
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020425"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Opret forbindelse til Microsoft Azure Consumption Insights med Power BI
Udforsk og overvåg dine Microsoft Azure-forbrugsdata i Power BI-tjenesten med Power BI-indholdspakken. Dataene opdateres automatisk én gang dagligt.

Opret forbindelse til [Microsoft Azure Consumption Insights-indholdspakken](https://app.powerbi.com/getdata/services/azureconsumption) til Power BI-tjenesten.

> [!NOTE]
> Hvis du vil have en mere tilpasset konfiguration, skal du prøve at bruge [Azure Consumption Insights-connectoren](desktop-connect-azure-consumption-insights.md) i Power BI Desktop.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude i Power BI-tjenesten.
   
    ![Hent data](media/service-connect-to-azure-consumption-insights/getdata.png)
2. Markér **Hent** i feltet **Tjenester**.
   
   ![Hent tjenester](media/service-connect-to-azure-consumption-insights/services.png)
3. Vælg **Microsoft Azure Consumption Insights** \> **Hent det nu**. 
   
   ![Hent det nu](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Angiv den antal måneder, du vil importere data for, og dit Azure Enterprise-tilmeldingsnummer. Herunder kan du se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams).
   
    ![Opret forbindelse til Microsoft Azure Consumption Insights](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Angiv din Access-nøgle for at oprette forbindelse. Du kan finde din tilmeldingsnøgle på Azure EA-portalen. 
   
    ![Microsoft Azure Consumption Insights: nøgle](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Importprocessen starter automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
   ![Microsoft Azure Consumption Insights-dashboard](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdateringen eller prøve at opdatere det on-demand ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Microsoft Azure Consumption Insights-indholdspakken indeholder månedlige rapporteringsdata for det månedsinterval, du angav, da du oprettede forbindelse. Intervallet er et fleksibelt vindue, så de inkluderede datoer bliver opdateret, når datasættet opdateres.

## <a name="system-requirements"></a>Systemkrav
Indholdspakken kræver adgang til virksomhedsfunktioner på Azure Portal. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
Power BI-rapportering er tilgængelig for EA-kunder af typen Direct, Partner og Indirect, som kan få vist faktureringsoplysninger. Herunder kan du finde oplysninger om hver af de værdier, der forventes i forbindelsesflowet.

**Antal måneder**

* Den antal måneder (1-36) med data fra i dag, som du vil importere.

**Tilmeldingsnummer**

* Dette er dit Azure Enterprise-tilmeldingsnummer, som du kan finde på startskærmen på [Azure Enterprise Portal](https://ea.azure.com/) under **Tilmeldingsoplysninger**.
  
    ![Tilmeldingsnummer](media/service-connect-to-azure-consumption-insights/params2.png)

**Access-nøgle**

* Du kan finde din adgangsnøgle på Azure Enterprise Portal under **Downloadforbrug** > **API-adgangsnøgle**.
  
    ![Adgangsnøgle](media/service-connect-to-azure-consumption-insights/creds2.png)

**Yderligere hjælp**

* Hvis du har brug for yderligere hjælp til at konfigurere Power BI-pakken til Azure Enterprise, skal du logge på Azure Enterprise Portal og se API-hjælpefilen under **Hjælp**. Du kan også finde yderligere vejledning under **Rapporter** -> **Downloadforbrug** -> **API-adgangsnøgle**.
* Hvis du vil have en mere tilpasset konfiguration, skal du prøve at bruge [Azure Consumption Insights-connectoren](desktop-connect-azure-consumption-insights.md) i Power BI Desktop.

## <a name="next-steps"></a>Næste trin

[Azure Consumption Insights-connector](desktop-connect-azure-consumption-insights.md) i Power BI Desktop

[Hent data i Power BI](service-get-data.md)

