---
title: Hent yderligere diagnosticeringsoplysninger
description: Hent yderligere diagnosticeringsoplysninger
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: 7910270ecafd383600ff19e6c6c2bfc1ad6e6d4a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="capturing-additional-diagnostic-information"></a>Hent yderligere diagnosticeringsoplysninger
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Hent yderligere diagnosticeringsoplysninger til Power BI
Disse instruktioner indeholder to potentielle muligheder for manuelt at indsamle flere diagnosticeringsoplysninger fra Power BI-webklienten.  Kun én af disse muligheder skal følges.

## <a name="network-capture---edge--internet-explorer"></a>Netværkshentning – Edge og Internet Explorer
1. Gå til [Power BI](https://app.powerbi.com) med Edge eller Internet Explorer.
2. Åbn Edge-udviklerværktøjerne ved at trykke på F12.
3. Vinduet med udviklerværktøjer åbnes: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Gå til fanen Network. Her vises trafik, der allerede er hentet. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Du kan navigere i vinduet og gengive et eventuelt problem. Du kan altid skjule og vise vinduet med udviklerværktøjer under sessionen ved at trykke på F12.
6. Hvis du vil stoppe hentningen, kan du vælge den røde kvadrat under netværksfanen i området med udviklerværktøjer.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Vælg disketteikonet, og indstil til **Export as HAR**
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Angiv et filnavn, og gem HAR-filen.
   
    HAR-filen indeholder alle oplysninger om netværksanmodninger mellem browservinduet og Power BI.  Dette omfatter aktivitets-id'er for hver anmodning, det præcise tidsstempel for hver anmodning og alle fejloplysninger, der returneres til klienten.  Denne sporingen vil også indeholde de data, der bruges til at udfylde de visuelle elementer, der vises på skærmen.
9. Du kan levere HAR-filen til supporten til gennemsyn.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
