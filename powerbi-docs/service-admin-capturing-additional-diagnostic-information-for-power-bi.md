---
title: Hent flere diagnosticeringsoplysninger
description: Disse instruktioner indeholder to potentielle muligheder for manuelt at indsamle flere diagnosticeringsoplysninger fra Power BI-webklienten.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100166"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Hent yderligere diagnosticeringsoplysninger til Power BI

Denne artikel indeholder vejledning til manuelt at indsamle flere diagnosticeringsoplysninger fra Power BI-webklienten.

1. Gå til [Power BI](https://app.powerbi.com) med Microsoft Edge eller Internet Explorer.

1. Tryk på **F12** at åbne Microsoft Edge-Udviklerværktøjerne.

   ![Skærmbillede af Microsoft Edge Developer tools elementer fanen.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Vælg fanen **Netværk**. Her vises trafik, der allerede er hentet.

   ![Skærmbillede af Microsoft Edge Developer Network under fanen værktøjer.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Du kan:

    * I vinduet Gennemse og gengive du muligvis støder på problemer.

    * Skjule og vise vinduet med udviklerværktøjer som helst i løbet af sessionen ved at trykke på F12.

1. Hvis du vil stoppe profilering sessionen, kan du vælge den røde kvadrat under den **Network** fanen på developer tools område.

   ![Skærmbillede af Microsoft Edge Developer tools fanen netværk med et kald ud af knappen Stop.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Vælg ikonet disketten eksportere dataene som en HTTP-arkiv (HAR)-filen.

   ![Skærmbillede af Microsoft Edge Developer tools fanen netværk med en billedforklaring af ikonet disketten.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Angiv et filnavn, og gem HAR-filen.

    HAR-filen indeholder alle oplysninger om netværksanmodninger mellem browservinduet og Power BI, herunder:

    * Aktivitets-id'er for hver anmodning.

    * Det præcise tidsstempel for hver anmodning.

    * Alle fejloplysninger, returneres til klienten.

    Denne sporingen vil også indeholde de data, der bruges til at udfylde de visuelle elementer, der vises på skærmen.

1. Du kan levere HAR-filen til supporten til gennemsyn.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
