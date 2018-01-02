---
title: Opret forbindelse til Azure Audit Logs med Power BI
description: Azure Audit Logs til Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: cb52b8dc6aefc199ef09946bf8b58c98171c5aba
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Opret forbindelse til Azure Audit Logs med Power BI
Du kan analysere og visualisere de oplysninger, der er gemt i overvågningsloggene, med Azure Audit Logs-indholdspakken. Power BI henter dataene, opretter et brugsklart dashboard og genererer rapporter ud fra de pågældende data.

[Opret forbindelse til Azure Audit Logs-indholdspakken](https://app.powerbi.com/getdata/services/azure-audit-logs), eller få yderligere oplysninger om [Azure Audit Logs-integration](https://powerbi.microsoft.com/integrations/azure-audit-logs) med Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent Data** nederst i venstre navigationsrude.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Vælg **Azure Audit Logs** > **Hent**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. Når du bliver bedt om det, skal du angive dit **Azure abonnements-id**. Få detaljer om, hvordan du finder dit [abonnements-id](#FindingParams), nedenfor.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. Til **Godkendelsesmetode** skal du vælge **oAuth2** \>**Log på**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Angiv dine legitimationsoplysninger til din konto for at afslutte logonprocessen.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI henter dine Azure Audit Log-data og opretter et brugsklart dashboard samt rapport. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være programsat til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere ved behov ved brug af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Azure Audit Logs-indholdspakken kræver adgang til overvågningsloggene i Azure-portalen. Du kan få flere oplysninger [her](https://azure.microsoft.com/en-us/documentation/articles/insights-debugging-with-events/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
Der er to måder til nemt at finde dit abonnements-id.

1. Fra https://portal.azure.com -&gt; Gennemse -&gt; Abonnementer -&gt; Abonnements-id
2. Fra https://manage.windowsazure.com -&gt; Indstillinger -&gt; Abonnements-id

Abonnements-id'et er et langt sæt tal og tegn, der ligner eksemplet i trin \#4 ovenfor. 

## <a name="troubleshooting"></a>Fejlfinding
Hvis du ser en fejl i legitimationsoplysningerne eller en fejl, når du forsøger at opdatere på grund af ugyldige legitimationsoplysninger, kan du prøve at slette alle forekomster af Azure Audit Logs-indholdspakken og genoprette forbindelsen.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)  
[Power BI – Grundlæggende begreber](service-basic-concepts.md)  

