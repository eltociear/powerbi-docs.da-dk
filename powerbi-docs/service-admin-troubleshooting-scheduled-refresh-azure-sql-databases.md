---
title: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases
description: Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5f699ed013f35edd4f958b3c958e56ebeb05029c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Fejlfinding i forbindelse med planlagt opdatering af Azure SQL Databases i Power BI
Du kan finde detaljerede oplysninger om konfiguration af planlagt opdatering under [Opdater data i Power BI](refresh-data.md).

Hvis du får vist en fejl med fejlkoden 400 under redigering af legitimationsoplysningerne, kan du under konfigurationen af den planlagte opdatering af Azure SQL Database prøve følgende for at konfigurere den relevante firewallregel:

1. Log på din Azure-administrationsportalen
2. Gå til den Azure SQL-server, du konfigurerer opdateringen for
3. Slå 'Windows Azure-tjenester' til i sektionen om tilladte tjenester

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

