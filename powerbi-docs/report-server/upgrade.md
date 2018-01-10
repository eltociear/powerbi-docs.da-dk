---
title: Opgrader Power BI Report Server
description: Find ud af, hvordan du opgraderer Power BI Report Server.
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: cf8924cb555b3da3f6d72340c76394ce33025169
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2018
---
# <a name="upgrade-power-bi-report-server"></a>Opgrader Power BI Report Server
Find ud af, hvordan du opgraderer Power BI Report Server.

 **Download** ![download](media/upgrade/download.png "download")

Hvis du vil downloade Power BI Report Server og Power BI Desktop optimeret til Power Bi Report Server, skal du gå til [Rapportering i det lokale miljø med Power BI Report Server](https://powerbi.microsoft.com/report-server/).

![tip](media/upgrade/fyi-tip.png "tip") Se de aktuelle produktbemærkninger i [Power BI Report Server – produktbemærkninger](release-notes.md).

## <a name="before-you-begin"></a>Inden du starter
Inden du opgraderer en rapportserver, anbefales det, at du udfører følgende trin for at sikkerhedskopiere rapportserveren.

### <a name="backing-up-the-encryption-keys"></a>Sikkerhedskopiering af krypteringsnøgler
Du skal sikkerhedskopiere krypteringsnøgler, første gang du konfigurerer en rapportserverinstallation. Du skal også sikkerhedskopiere nøglerne, hver gang du ændrer identiteten for tjenestekontiene eller omdøber computeren. Du kan finde flere oplysninger i [Sikkerhedskopiér og gendan krypteringsnøgler til rapporttjenester](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys).

### <a name="backing-up-the-report-server-databases"></a>Sikkerhedskopiér rapportserverdatabaser
Da en rapportserver er en tilstandsløs server, gemmes alle programdata i databaserne **reportserver** og **reportservertempdb**, der kører på en forekomst af SQL Server Database Engine. Du kan sikkerhedskopiere databaserne **reportserver** og **reportservertempdb** vha.en af de understøttede metoder til sikkerhedskopiering af SQL Server-databaser. Anbefalinger, der er specifikke for rapportserverdatabaserne, omfatter følgende:

* Brug den fulde gendannelsesmodel til sikkerhedskopiering af **reportserver**-databasen.
* Brug den enkle gendannelsesmodel til sikkerhedskopiering af **reportservertempdb**-databasen.
* Du kan bruge forskellige tidsplaner til sikkerhedskopiering af hver database. Den eneste årsag til at sikkerhedskopiere **reportservertempdb** er for at undgå at skulle oprette den igen, hvis der er en hardwarefejl. I tilfælde af hardwarefejl er det ikke nødvendigt at genoprette dataene i **reportservertempdb**, men du skal dog bruge tabelstrukturen. Hvis du mister **reportservertempdb**, er den eneste måde at få den tilbage på at genoprette rapportserverdatabasen. Hvis du opretter **reportservertempdb** igen, er det vigtigt, at den har samme navn som den primære rapportserverdatabase.

Du kan finde flere oplysninger om sikkerhedskopiering og gendannelse af SQL Server-relationsdatabaser ved at læse [Sikkerhedskopiering og gendannelse af SQL Server-databaser](https://docs.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases).

### <a name="backing-up-the-configuration-files"></a>Sikkerhedskopiér konfigurationsfilerne
Power BI Report Server bruger konfigurationsfilerne til at gemme programindstillinger. Du skal sikkerhedskopiere filerne, første gang du konfigurerer serveren, og efter du udruller brugerdefinerede udvidelser. Filer, der skal sikkerhedskopieres, omfatter:

* config.json
* RSHostingService.exe.config
* Rsreportserver.config
* Rssvrpolicy.config
* Reportingservicesservice.exe.config
* Web.config til Report Server ASP.NET-programmer
* Machine.config til ASP.NET

## <a name="upgrade-the-report-server"></a>Opgrader rapportserveren
Det er nemt at opgradere Power BI Report Server. Der er kun et par trin til installation af filerne.

1. Find placeringen for PowerBIReportServer.exe, og start installationen.
2. Vælg **Opgrader Power BI Report Server**.
   
    ![](media/upgrade/reportserver-upgrade1.png "Opgrader Power BI Report Server")
3. Læs og acceptér licensens vilkår og betingelser, og vælg derefter **Opgrader**.
   
    ![](media/upgrade/reportserver-upgrade-eula.png "Licensaftale")
4. Når opgraderingen er udført, kan du vælge **Konfigurer Report Server** for at starte Reporting Services Configuration Manager, eller vælge **Luk** for at afslutte installationen.
   
    ![](media/upgrade/reportserver-upgrade-configure.png)

## <a name="upgrade-power-bi-desktop"></a>Opgrader Power BI Desktop
Når rapportserveren er opgraderet, skal du sikre dig, at Power Bi-rapportforfattere opgraderer til versionen af Power BI Desktop, der er optimeret til Power Bi Report Server, som stemmer overens med serveren.

## <a name="next-steps"></a>Næste trin
[Administratorhåndbog](admin-handbook-overview.md)  
[Installér Power BI Desktop optimeret til Power BI Report Server](install-powerbi-desktop.md)  
[Bekræft installationen af en rapporteringstjeneste](https://docs.microsoft.com/sql/reporting-services/install-windows/verify-a-reporting-services-installation)  
[Konfigurer kontoen til rapportservertjenesten](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager)  
[Konfigurer rapportserverens URL-adresser](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager)  
[Konfigurer en rapportservers databaseforbindelse](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)  
[Initialiser en rapportserver](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server)  
[Konfigurer SSL-forbindelser på en rapportserver](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server)  
[Konfigurer Windows-tjenestekonti og -tilladelser](https://docs.microsoft.com/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)  
[Browserunderstøttelse af Power BI Report Server](browser-support.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

