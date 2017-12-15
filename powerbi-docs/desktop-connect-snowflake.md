---
title: Opret forbindelse til Snowflake-databehandlingswarehouse i Power BI Desktop
description: Opret let forbindelse til og brug Snowflake-databehandlingswarehouse i Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: bb1c649d62ad9c8a3c4fb854db2478feecc82e70
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-snowflake-in-power-bi-desktop"></a>Opret forbindelse til Snowflake i Power BI Desktop
I Power BI Desktop kan du oprette forbindelse til et **Snowflake**-databehandlingswarehouse og bruge de underliggende data på samme måde som enhver anden datakilde i Power BI Desktop. 

> [!NOTE]
> Du *skal* også installere **Snowflake ODBC-driveren** på computere, der bruger **Snowflake**-connectoren, vha. den arkitektur, der svarer til installationen af  **Power BI Desktop**, dvs. enten 32-bit eller 64-bit. Du skal blot følge nedenstående link og [downloade den relevante Snowflake ODBC-driver](http://go.microsoft.com/fwlink/?LinkID=823762).
> 
> 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Opret forbindelse til et Snowflake-databehandlingswarehouse
Hvis du vil oprette forbindelse til et **Snowflake**-databehandlingswarehouse, skal du vælge **Hent data** fra båndet **Hjem** i Power BI Desktop. Vælg **Database** blandt kategorierne til venstre, hvorefter du kan se **Snowflake**.

![](media/desktop-connect-snowflake/connect_snowflake_2b.png)

I det viste vindue, **Snowflake**, skal du skrive eller indsætte navnet på dit Snowflake-databehandlingswarehouse i feltet og vælge **OK**. Bemærk, at du kan vælge at **importere** data direkte i Power BI, eller du kan bruge **DirectQuery**. Du kan få mere at vide om [brug af DirectQuery](desktop-use-directquery.md).

![](media/desktop-connect-snowflake/connect_snowflake_3.png)

Når du bliver bedt om det, skal du angive dit brugernavn og din adgangskode.

![](media/desktop-connect-snowflake/connect_snowflake_4.png)

> [!NOTE]
> Når du angiver dit brugernavn og din adgangskode for en bestemt **Snowflake**-server, anvendes de samme legitimationsoplysninger i efterfølgende forsøg på at oprette forbindelse via Power BI Desktop. Du kan ændre disse legitimationsoplysninger ved at gå til **Filer > Indstillinger > Indstillinger for datakilde**.
> 
> 

Når du har oprettet forbindelse, vises et vindue af typen **Navigator**, hvor de data, der er tilgængelige på serveren, vises. Her kan du vælge et eller flere elementer, der skal importeres og bruges i **Power BI Desktop**.

![](media/desktop-connect-snowflake/connect_snowflake_5.png)

Du kan **indlæse** den valgte tabel, der fører hele tabellen ind i **Power BI Desktop**, eller du kan **redigere** forespørgslen, der åbner **Forespørgselseditor**, så du kan filtrere og finindstille det datasæt, du vil bruge, og derefter indlæse dette finindstillede datasæt i **Power BI Desktop**.

## <a name="next-steps"></a>Næste trin
Der er alle mulige forskellige former for data, du kan oprette forbindelse til ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder under følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

