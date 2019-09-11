---
title: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases
description: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/04/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 4bc14b9a3d863732c581e8a144d612d864d65af8
ms.sourcegitcommit: c799941c8169cd5b6b6d63f609db66ab2af93891
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/06/2019
ms.locfileid: "70391849"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI

Du kan finde detaljerede oplysninger om opdatering under [Opdater data i Power BI](refresh-data.md) og [Konfigurer planlagt opdatering](refresh-scheduled-refresh.md).

Hvis du får vist en fejl med fejlkoden 400, når du redigerer legitimationsoplysningerne, kan du under konfigurationen af den planlagte opdatering af Azure SQL-database prøve følgende for at konfigurere den relevante firewallregel:

1. Log på [Azure Portal](https://portal.azure.com).

1. Gå til den Azure SQL-database, du konfigurerer opdateringen for.

1. Øverst i bladet **Oversigt** skal du vælge **Indstil serverfirewall**.

1. På bladet **Indstillinger for firewall** skal du kontrollere, at **Tillad adgang til Azure-tjenester** er indstillet til **ON**.

    ![Tilladte tjenester i Azure](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
