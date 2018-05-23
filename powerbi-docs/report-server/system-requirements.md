---
title: Hardware- og softwarekrav til installation af Power BI-rapportserver
description: Her kan du finde minimumskrav til hardware og for at kunne installere og køre Power BI-rapportserver.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 2963dbe2a5d1109e4396568624e16bf49d98da10
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Hardware- og softwarekrav til installation af Power BI-rapportserver
Her kan du finde minimumskrav til hardware og for at kunne installere og køre Power BI-rapportserver.

## <a name="processor-memory-and-operating-system-requirements"></a>Krav til processor, hukommelse og operativsystem
| Komponent | Krav |
| --- | --- |
| .NET Framework |4.6<br><br>Du kan installere .NET Framework manuelt fra [Microsoft .NET Framework 4.6 (webinstallation) til Windows](http://support.microsoft.com/kb/3045560).<br/><br/> Du kan få yderligere oplysninger, anbefalinger og vejledning om .NET Framework 4.6 i [.NET Framework-installationsvejledning for udviklere](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Windows 8.1 og Windows Server 2012 R2 kræver [KB2919355](http://support.microsoft.com/kb/2919355), før du installerer .NET Framework 4.6. |
| Harddisk |Power BI-rapportserver kræver minimum 1 GB ledig plads på harddisken.<br><br>Yderligere plads kræves på den databaseserver, der skal hoste rapportserverdatabasen. |
| Hukommelse |**Minimum:** 1 GB<br/><br/> **Anbefalet:** Mindst 4 GB |
| Processorhastighed |**Minimum:** x64-processor: 1,4 GHz<br/><br/> **Anbefalet:** 2,0 GHz eller hurtigere |
| Processortype |x64-processor: AMD Opteron, AMD Athlon 64, Intel Xeon med Intel EM64T-understøttelse, Intel Pentium IV med EM64T-understøttelse |
| Operativsystem |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Installation af Power BI-rapportserver er kun understøttet på x64-processorer.
> 
> 

## <a name="database-server-version-requirements"></a>Krav til version af databaseserver
SQL Server bruges til at hoste rapportserverdatabaserne. Forekomsten af SQL Server-databaseprogrammet kan være en lokal eller ekstern forekomst. De understøttede versioner af SQL Server-databaseprogrammet, som kan bruges til at hoste rapportserverdatabaserne, er følgende:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

Oprettelse af rapportserverdatabasen på en fjerncomputer kræver, at du konfigurerer forbindelsen til at bruge en domænebrugerkonto eller en tjenestekonto, som har netværksadgang. Hvis du beslutter at bruge en ekstern SQL Server-forekomst, skal du overveje grundigt, hvilke legitimationsoplysninger rapportserveren skal bruge til at oprette forbindelse til SQL Server-forekomsten. Få mere at vide i [Konfigurer en rapportservers databaseforbindelse](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)

## <a name="considerations"></a>Overvejelser
Power BI-rapportserver installerer standardværdier for at konfigurere de hovedindstillinger, der kræves for at gøre en rapportserver driftsklar. Der er følgende betingelser:

* Et SQL Server-databaseprogram skal være tilgængeligt efter konfigurationen, og før du konfigurerer databasen for rapportserveren. Forekomsten af databaseprogrammet hoster rapportserverdatabasen, som oprettes af Reporting Services Configuration Manager. Databaseprogrammet er ikke påkrævet til selve konfigurationen.
* Den brugerkonto, der bruges til at køre konfigurationen, skal være den lokale administratorgruppe.
* Den brugerkonto, der bruges til Reporting Services Configuration Manager, skal have tilladelse til at få adgang til og oprette databaser på forekomsten af databaseprogrammet, der hoster rapportserverdatabaserne.
* Konfigurationen skal kunne bruge standardværdierne til at reservere de URL-adresser, der giver adgang til rapportserveren og webportalen. Disse værdier er port 80, et stærkt jokertegn og navnene på de virtuelle mapper i formatet **ReportServer** og **Reports**.

## <a name="read-only-domain-controller-rodc"></a>Skrivebeskyttet domænecontroller (RODC)
 Mens rapportserveren kan installeres i et miljø, der har en skrivebeskyttet domænecontroller (RODC), skal Reporting Services have adgang til en domænecontroller med læse-/skriveadgang for at fungere korrekt. Hvis Reporting Services kun har adgang til en skrivebeskyttet domænecontroller, kan der opstå fejl under forsøg på at administrere tjenesten.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI-rapporter og Analysis Services-liveforbindelser
Du kan bruge en liveforbindelse til tabellariske eller flerdimensionelle forekomster. Analysis Services-serveren skal være den korrekte version og udgave, og den skal fungere korrekt.

| **Serverversion** | **Påkrævet SKU** |
| --- | --- |
| 2012 SP1 CU4 eller nyere |Business Intelligence- og Enterprise-SKU |
| 2014 |Business Intelligence- og Enterprise-SKU |
| 2016 og nyere |Standard-SKU eller nyere |

## <a name="next-steps"></a>Næste trin
[Brugerhåndbog](user-handbook-overview.md)  
[Administratorhåndbog](admin-handbook-overview.md)  
[Installer Power BI-rapportserver](install-report-server.md)  
[Installér Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

