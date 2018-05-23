---
title: Hent yderligere diagnosticeringsoplysninger
description: Hent yderligere diagnosticeringsoplysninger
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 76860e740d43a1907692a7cd4fed1a6df68c93d4
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
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

