---
title: Opret forbindelse til Azure Audit Logs med Power BI
description: Azure Audit Logs til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 42b56cbad4c47b8cc8133a1f35511ea48ac24055
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060604"
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Opret forbindelse til Azure Audit Logs med Power BI
Du kan analysere og visualisere de oplysninger, der er gemt i overvågningsloggene, med Azure Audit Logs-indholdspakken. Power BI henter dataene, opretter et brugsklart dashboard og genererer rapporter ud fra de pågældende data.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

[Opret forbindelse til Azure Audit Logs-indholdspakken](https://app.powerbi.com/getdata/services/azure-audit-logs), eller få yderligere oplysninger om [Azure Audit Logs-integration](https://powerbi.microsoft.com/integrations/azure-audit-logs) med Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Vælg **Azure Audit Logs** > **Hent**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. Når du bliver bedt om det, skal du angive dit **Azure-abonnements-id**. Få detaljer om, hvordan du finder dit [abonnements-id](#FindingParams), nedenfor.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. Som **Godkendelsesmetode** skal du vælge **oAuth2** \> **Log på**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Angiv legitimationsoplysningerne for din konto for at afslutte logonprocessen.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI henter dine Azure Audit Log-data og opretter et brugsklart dashboard samt rapport. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Azure Audit Logs-indholdspakken kræver adgang til overvågningsloggene på Azure-portalen. Du kan få flere oplysninger [her](/azure/azure-resource-manager/resource-group-audit/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
Der er to måder til nemt at finde sit abonnements-id.

1. Fra https://portal.azure.com -&gt; Gennemse -&gt; Abonnementer -&gt; Abonnements-id
2. Fra https://manage.windowsazure.com -&gt; Indstillinger -&gt; Abonnements-id

Abonnements-id'et er en lang række tal og tegn, der ligner eksemplet i trin \#4 ovenfor. 

## <a name="troubleshooting"></a>Fejlfinding
Hvis du ser en fejl i legitimationsoplysningerne eller der opstår en fejl, når du forsøger at opdatere, på grund af ugyldige legitimationsoplysninger, kan du prøve at slette alle forekomster af Azure Audit Logs-indholdspakken og genoprette forbindelsen.

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](fundamentals/power-bi-overview.md)  
[Grundlæggende begreber for designere i Power BI-tjenesten](service-basic-concepts.md)  

