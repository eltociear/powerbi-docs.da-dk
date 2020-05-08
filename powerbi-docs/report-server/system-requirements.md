---
title: Hardware- og softwarekrav til installation af Power BI-rapportserver
description: I denne artikel kan du se minimumkrav til hardware og software, hvis du vil installere og køre Power BI-rapportserver.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 02/20/2020
ms.openlocfilehash: 20b41762f7b38bd4ed26add97abb4eec1da0c000
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "77558550"
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Hardware- og softwarekrav til installation af Power BI-rapportserver

I denne artikel kan du se minimumkrav til hardware og software, hvis du vil installere og køre Power BI-rapportserver.

## <a name="processor-memory-and-operating-system-requirements"></a>Krav til processor, hukommelse og operativsystem

| Komponent | Krav |
| --- | --- |
| .NET Framework |4.7<br><br>Du kan installere .NET Framework manuelt fra [Microsoft .NET Framework 4.7 (webinstallation) til Windows](https://support.microsoft.com/en-us/kb/3186500).<br/><br/> Du kan få yderligere oplysninger, anbefalinger og vejledning om .NET Framework 4.7 i [.NET Framework-installationsvejledning for udviklere](https://docs.microsoft.com/dotnet/framework/deployment/deployment-guide-for-developers).<br/><br/>Windows 8.1 og Windows Server 2012 R2 kræver [KB2919355](https://support.microsoft.com/kb/2919355), før du installerer .NET Framework 4.7. |
| Harddisk |Power BI-rapportserver kræver minimum 1 GB ledig plads på harddisken.<br><br>Yderligere plads kræves på den databaseserver, der skal hoste rapportserverdatabasen. |
| Hukommelse |**Minimum:** 1 GB<br/><br/> **Anbefalet:** Mindst 4 GB |
| Processorhastighed |**Minimum:** x64-processor: 1,4 GHz<br/><br/> **Anbefalet:** 2,0 GHz eller hurtigere |
| Processortype |x64-processor: AMD Opteron, AMD Athlon 64, Intel Xeon med Intel EM64T-understøttelse, Intel Pentium IV med EM64T-understøttelse |
| Operativsystem |Windows Server 2019 Datacenter<br><br>Windows Server 2019 Standard<br><br>Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Installation af Power BI-rapportserver er kun understøttet på x64-processorer.


## <a name="database-server-version-requirements"></a>Krav til version af databaseserver

SQL Server bruges til at hoste rapportserverdatabaserne. Forekomsten af SQL Server-databaseprogrammet kan være en lokal eller ekstern forekomst. De understøttede versioner af SQL Server-databaseprogrammet, som kan bruges til at hoste rapportserverdatabaserne, er følgende:

* Azure SQL Managed Instance (Power BI-rapportserver januar 2020-version og nyere)
* SQL Server 2019
* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012

Når du opretter rapportserverdatabasen på en fjerncomputer, skal du konfigurere forbindelsen til at bruge en domænebrugerkonto eller en tjenestekonto med netværksadgang. Hvis du beslutter at bruge en ekstern SQL Server-forekomst, skal du overveje grundigt, hvilke legitimationsoplysninger rapportserveren skal bruge til at oprette forbindelse til SQL Server-forekomsten. Få mere at vide i [Konfigurer en rapportservers databaseforbindelse](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)

## <a name="considerations"></a>Overvejelser

Power BI-rapportserver installerer standardværdier for at konfigurere de hovedindstillinger, der kræves for at gøre en rapportserver driftsklar. Der er følgende betingelser:

* De understøttede sprog til Power BI-rapportserver er engelsk, tysk, spansk, japansk, italiensk, fransk, russisk, kinesisk (forenklet), kinesisk (traditionelt), portugisisk (Brasilien), koreansk
* Et SQL Server-databaseprogram skal være tilgængeligt efter konfigurationen, og før du konfigurerer databasen for rapportserveren. Forekomsten af databaseprogrammet hoster rapportserverdatabasen, som oprettes af Reporting Services Configuration Manager. Databaseprogrammet er ikke påkrævet til selve konfigurationen.
* I [Reporting Services-funktioner, der understøttes af udgaver af SQL Server](https://docs.microsoft.com/sql/reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016) vises forskellene mellem diverse udgaver af SQL Server.
* Den brugerkonto, der kører konfigurationen, skal være den lokale administratorgruppe.
* Den brugerkonto, der kører Reporting Services Configuration Manager, skal have tilladelse til at få adgang til og oprette databaser på den forekomst af databaseprogrammet, der hoster rapportserverdatabaserne.
* Konfigurationen skal kunne bruge standardværdierne til at reservere de URL-adresser, der giver adgang til rapportserveren og webportalen. Disse værdier er port 80, et stærkt jokertegn og navnene på de virtuelle mapper i formatet **ReportServer** og **Reports**.

## <a name="read-only-domain-controller-rodc"></a>Skrivebeskyttet domænecontroller (RODC)

 Du kan installere rapportserveren i et miljø, der har en skrivebeskyttet domænecontroller (RODC). Reporting Services skal dog have adgang til en skrivebeskyttet domænecontroller for at fungere korrekt. Hvis Reporting Services kun har adgang til en skrivebeskyttet domænecontroller, kan der opstå fejl under forsøg på at administrere tjenesten.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI-rapporter og Analysis Services-liveforbindelser

Du kan bruge en liveforbindelse til tabellariske eller flerdimensionelle forekomster. Analysis Services-serveren skal være den korrekte version og udgave for at fungere korrekt.

| **Serverversion** | **Påkrævet SKU** |
| --- | --- |
| 2012 SP1 CU4 eller nyere |Business Intelligence- og Enterprise-SKU |
| 2014 |Business Intelligence- og Enterprise-SKU |
| 2016 og nyere |Standard-SKU eller nyere |

## <a name="next-steps"></a>De næste trin

[Hvad er Power BI-rapportserveren?](get-started.md)  
[Administratoroversigt](admin-handbook-overview.md)  
[Installér Power BI-rapportserver](install-report-server.md)  
[Download Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)  
[Download SQL Server Data Tools (SSDT)](https://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
