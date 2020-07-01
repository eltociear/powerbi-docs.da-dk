---
title: Fejlfinding af planlagt opdatering af Azure SQL Databases
description: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
author: davidiseminger
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.author: davidi
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6efc7b031b9eb5708fe55c5b4167af0428ff7c19
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485708"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI

Du kan finde detaljerede oplysninger om opdatering under [Opdater data i Power BI](refresh-data.md) og [Konfigurer planlagt opdatering](refresh-scheduled-refresh.md).

Hvis du får vist en fejl med fejlkoden 400, når du redigerer legitimationsoplysningerne, kan du under konfigurationen af den planlagte opdatering af Azure SQL-database prøve følgende for at konfigurere den relevante firewallregel:

1. Log på [Azure-portalen](https://portal.azure.com).

1. Gå til den Azure SQL-database, du konfigurerer opdateringen for.

1. Øverst i bladet **Oversigt** skal du vælge **Indstil serverfirewall**.

1. På bladet **Indstillinger for firewall** skal du kontrollere, at **Tillad adgang til Azure-tjenester** er indstillet til **ON**.

    ![Tilladte tjenester i Azure](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
