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
ms.openlocfilehash: 662b5e094a38aafad9a87593b9c5b797e2db7870
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
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

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
For at oprette forbindelse skal du bruge:  

* En konto, der kan få adgang til yourorganization.service-now.com med basisgodkendelse (enkeltlogon understøttes ikke i denne version).  
* Kontoen skal have rollen rest_service og læseadgang til hændelsestabellen.  

## <a name="troubleshooting"></a>Fejlfinding
Hvis du oplever en fejl i forbindelse med legitimationsoplysningerne under indlæsningen, skal du gennemse adgangskravene ovenfor. Hvis du har de nødvendige tilladelser og stadig oplever problemer, skal du kontakte din ServiceNow-administrator for at sikre, at du har eventuelle yderligere tilladelser, der kan være nødvendige, til din brugerdefinerede forekomst.

Hvis du oplever lange indlæsningstider, skal du gennemse antallet af hændelser og antallet af dage, du har angivet under oprettelse af forbindelsen, og overveje at reducere dem.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)
