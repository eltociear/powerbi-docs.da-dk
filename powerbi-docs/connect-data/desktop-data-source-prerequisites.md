---
title: Power BI datakildeforudsætninger
description: Power BI datakildeforudsætninger
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 498636d61f61764cfaef29db32454f55f1328243
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83293599"
---
# <a name="power-bi-data-source-prerequisites"></a>Power BI datakildeforudsætninger
For hver dataprovider understøtter Power BI en bestemt providerversion på objekter. Du kan finde flere oplysninger om de tilgængelige datakilder til Power BI under [Datakilder](desktop-data-sources.md). I nedenstående tabel beskrives disse krav.

| Datakilde | Provider | Mindste providerversion | Mindste datakildeversion | Understøttede datakildeobjekter | Downloadlink |
| --- | --- | --- | --- | --- | --- |
| SQL Server |ADO.net (indbygget i .Net Framework) |.NET Framework 3.5 (kun) |SQL Server 2005 eller nyere |Tabeller/visninger, skalarfunktioner, tabelfunktioner |Inkluderet i .NET Framework 3.5 eller nyere |
| Giv adgang |Microsoft Access Database Engine (ACE) |ACE 2010 SP1 |Ingen begrænsning |Tabeller/visninger |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (kun .xls-filer) (se note 1) |Microsoft Access Database Engine (ACE) |ACE 2010 SP1 |Ingen begrænsning |Tabeller, ark |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (se note 2) |ODP.NET |ODAC 11.2 version 5 (11.2.0.3.20) |9.x eller nyere |Tabeller/visninger |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | System.Data.OracleClient (indbygget i .NET Framework) |.NET Framework 3.5 |9.x eller nyere |Tabeller/visninger |Inkluderet i .NET Framework 3.5 eller nyere |
| IBM DB2 |ADO.Net-klient fra IBM (del af driverpakken til IBM-dataserver) |10.1 |9.1 eller nyere |Tabeller/visninger |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |Tabeller/visninger, skalarfunktioner |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |NPGSQL ADO.NET-udbyder (leveres med Power BI Desktop) |4.0.10 |9.4 |Tabeller/visninger |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |.NET Data Provider for Teradata |14 eller nyere |12 eller nyere |Tabeller/visninger |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP Sybase SQL Anywhere |iAnywhere.Data.SQLAnywhere til .NET 3.5 |16 eller nyere |16 eller nyere |Tabeller/visninger |[Downloadlink](https://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>Excel-filer, der har en .xlsx-udvidelse, kræver ikke en separat providerinstallation.

>[!NOTE]
>Oracle-providers kræver også Oracle-klientsoftware (version 8.1.7 eller nyere).
> 
> 

