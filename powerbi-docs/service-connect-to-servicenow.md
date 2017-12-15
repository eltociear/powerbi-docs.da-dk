---
title: Opret forbindelse til ServiceNow med Power BI
description: ServiceNow til Power BI
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
ms.openlocfilehash: a0dec79f1ecb0aea1f13ff81303183242aceab9d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-servicenow-with-power-bi-for-incident-reporting"></a>Opret forbindelse til ServiceNow med Power BI til rapportering af hændelser
ServiceNow byder på flere produkter og løsninger, herunder forretningsrelateret og driftsrelateret administration samt IT-administration, som kan hjælpe med at forbedre din virksomhed. Denne indholdspakke indeholder flere rapporter og giver dig indsigt i dine åbne, seneste løste og nyligt lukkede hændelser.  

Opret forbindelse til Power BI-indholdspakken til [ServiceNow Incidents](https://app.powerbi.com/getdata/services/servicenow).

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-servicenow/pbi_getdata.png) 
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-servicenow/pbi_getservices.png) 
3. Vælg **ServiceNow Incidents** \> **Hent**.
   
   ![](media/service-connect-to-servicenow/connect.png)
4. Angiv URL-adressen til din forekomst af ServiceNow og intervallet af dage/poster, der skal importeres. Bemærk, så snart én grænse nås, stopper importen.
   
   ![](media/service-connect-to-servicenow/params.png)
5. Angiv dine legitimationsoplysninger til ServiceNow **Basic**, når du bliver bedt om det. Bemærk, at enkeltlogon ikke understøttes i dag. Du kan se flere oplysninger om systemkravene nedenfor.
   
   ![](media/service-connect-to-servicenow/creds.png)
6. Når logonflowet er fuldført, starter importprocessen. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
    ![](media/service-connect-to-servicenow/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
For at oprette forbindelse skal du bruge:  

* En konto, der kan få adgang til yourorganization.service-now.com med basisgodkendelse (enkeltlogon understøttes ikke i denne version).  
* Kontoen skal have rollen rest_service og læseadgang til hændelsestabellen.  

## <a name="troubleshooting"></a>Fejlfinding
Hvis du oplever en fejl i forbindelse med legitimationsoplysningerne under indlæsningen, skal du gennemse adgangskravene ovenfor. Hvis du har de nødvendige tilladelser og stadig oplever problemer, skal du kontakte din ServiceNow-administrator for at sikre, at du har eventuelle yderligere tilladelser, der kan være nødvendige, til din brugerdefinerede forekomst.

Hvis du oplever lange indlæsningstider, skal du gennemse antallet af hændelser og antallet af dage, du har angivet under oprettelse af forbindelsen, og overveje at reducere dem.

## <a name="next-steps"></a>Næste trin
[Introduktion til Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

