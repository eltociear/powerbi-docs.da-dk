---
title: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases
description: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9439ac6bd0b4df568b964f548372fb94d2fd0b26
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
Du kan finde detaljerede oplysninger om konfiguration af planlagt opdatering under [Opdater data i Power BI](refresh-data.md).

Hvis du får vist en fejl med fejlkoden 400 under redigering af legitimationsoplysningerne, kan du under konfigurationen af den planlagte opdatering af Azure SQL Database prøve følgende for at konfigurere den relevante firewallregel:

1. Log på din Azure-administrationsportalen
2. Gå til den Azure SQL-server, du konfigurerer opdateringen for
3. Slå 'Windows Azure-tjenester' til i sektionen om tilladte tjenester

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

