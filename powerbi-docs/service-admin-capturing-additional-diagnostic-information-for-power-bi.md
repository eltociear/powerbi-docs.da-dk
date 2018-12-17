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
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 8a8ec433a6ebb620593648cdb222df0f60b2f21e
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025142"
---
# <a name="capturing-additional-diagnostic-information"></a>Hent yderligere diagnosticeringsoplysninger
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Hent yderligere diagnosticeringsoplysninger til Power BI
Disse instruktioner indeholder to potentielle muligheder for manuelt at indsamle flere diagnosticeringsoplysninger fra Power BI-webklienten.  Kun én af disse muligheder skal følges.

## <a name="network-capture---edge--internet-explorer"></a>Netværkshentning – Edge og Internet Explorer
1. Gå til [Power BI](https://app.powerbi.com) med Edge eller Internet Explorer.
2. Åbn Edge-udviklerværktøjerne ved at trykke på F12.
3. Vinduet med udviklerværktøjer åbnes: 
   
   ![Udviklerværktøjer](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Gå til fanen Netværk. Her vises trafik, der allerede er hentet. 
   
   ![Fanen Edge-netværk](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Du kan navigere i vinduet og gengive et eventuelt problem. Du kan altid skjule og vise vinduet med udviklerværktøjer under sessionen ved at trykke på F12.
6. Hvis du vil stoppe hentningen, kan du vælge den røde kvadrat under netværksfanen i området med udviklerværktøjer.
   
   ![Stop hentningen](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Vælg disketteikonet, og indstil til **Export as HAR**
   
   ![Eksportér filen](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Angiv et filnavn, og gem HAR-filen.
   
    HAR-filen indeholder alle oplysninger om netværksanmodninger mellem browservinduet og Power BI.  Dette omfatter aktivitets-id'er for hver anmodning, det præcise tidsstempel for hver anmodning og alle fejloplysninger, der returneres til klienten.  Denne sporingen vil også indeholde de data, der bruges til at udfylde de visuelle elementer, der vises på skærmen.
9. Du kan levere HAR-filen til supporten til gennemsyn.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

