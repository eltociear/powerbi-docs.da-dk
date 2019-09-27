---
title: Hent yderligere diagnosticeringsoplysninger
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
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100166"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Hent yderligere diagnosticeringsoplysninger til Power BI

Denne artikel indeholder vejledning i, hvordan du manuelt indsamler flere diagnosticeringsoplysninger fra Power BI-webklienten.

1. Gå til [Power BI](https://app.powerbi.com) med Microsoft Edge eller Internet Explorer.

1. Tryk på **F12** for at åbne udviklerværktøjerne i Microsoft Edge.

   ![Skærmbillede af fanen Elementer i udviklerværktøjerne i Microsoft Edge.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Vælg fanen **Netværk**. Her vises trafik, der allerede er hentet.

   ![Skærmbillede af fanen Netværk i udviklerværktøjerne i Microsoft Edge.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Du kan:

    * Navigere i vinduet og gengive et eventuelt problem.

    * Når som helst skjule og få vist vinduet med udviklerværktøjer under sessionen ved at trykke på F12.

1. Hvis du vil stoppe profileringen af sessionen, kan du vælge den røde kvadrat under fanen **Netværk** i området med udviklerværktøjer.

   ![Skærmbillede af fanen Netværk i udviklerværktøjer i Microsoft Edge med stopknappen fremhævet.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Vælg disketteikonet for at eksportere dataene som en HTTP Archive-fil (HAR).

   ![Skærmbillede af fanen Netværk i udviklerværktøjer i Microsoft Edge med disketteikonet fremhævet.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Angiv et filnavn, og gem HAR-filen.

    HAR-filen indeholder alle oplysninger om netværksanmodninger mellem browservinduet og Power BI, inklusive:

    * Aktivitets-id'erne for hver anmodning.

    * Det nøjagtige tidsstempel for hver anmodning.

    * Alle fejloplysninger, der returneres til klienten.

    Denne sporingen vil også indeholde de data, der bruges til at udfylde de visuelle elementer, der vises på skærmen.

1. Du kan levere HAR-filen til supporten til gennemsyn.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
