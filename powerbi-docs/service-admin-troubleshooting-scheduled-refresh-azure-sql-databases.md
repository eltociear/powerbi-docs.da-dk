---
title: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases
description: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.author: maggies
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 292f80b4fec7da9ff6ce42e3611bf4d6353bae2d
ms.sourcegitcommit: 90bd747b7c460d17b74cd386d3f5714234b1f6c9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2019
ms.locfileid: "74791963"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI

Du kan finde detaljerede oplysninger om opdatering under [Opdater data i Power BI](refresh-data.md) og [Konfigurer planlagt opdatering](refresh-scheduled-refresh.md).

Hvis du får vist en fejl med fejlkoden 400, når du redigerer legitimationsoplysningerne, kan du under konfigurationen af den planlagte opdatering af Azure SQL-database prøve følgende for at konfigurere den relevante firewallregel:

1. Log på [Azure Portal](https://portal.azure.com).

1. Gå til den Azure SQL-database, du konfigurerer opdateringen for.

1. Øverst i bladet **Oversigt** skal du vælge **Indstil serverfirewall**.

1. På bladet **Indstillinger for firewall** skal du kontrollere, at **Tillad adgang til Azure-tjenester** er indstillet til **ON**.

    ![Tilladte tjenester i Azure](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
