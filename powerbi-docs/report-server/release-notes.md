---
title: "Produktbemærkninger til Power BI-rapportserver"
description: "I dette emne beskrives begrænsninger og problemer med Power BI-rapportserver."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 7f59e3788b24344b5f86b146fb41e440eb0a2098
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-server-release-notes"></a>Produktbemærkninger til Power BI-rapportserver
I dette emne beskrives begrænsninger og problemer med Power BI-rapportserver.

Hvis du vil downloade Power BI-rapportserver og Power BI Desktop optimeret til Power BI-rapportserver, skal du gå til [Rapportering i det lokale miljø med Power BI-rapportserver](https://powerbi.microsoft.com/report-server/).

## <a name="october-2017"></a>Oktober 2017
* Understøttelse af importerede data i Power BI-rapporter
* Mulighed for at få vist Excel-projektmapper i webportalen. Dette gøres ved at konfigurere Office Online Server.
* Understøttelse af den nye Power BI-tabel og matrixvisuals.
* Understøttelse af REST API

## <a name="june-2017"></a>Juni 2017
* Ingen nye elementer i juni 2017.

## <a name="may-2017"></a>Maj 2017
* Power BI-rapporter skal oprettes med Power BI Desktop, som er optimeret til Power BI-rapportserver for at fungere sammen med Power BI-rapportserver. Du kan downloade Power BI Desktop via downloadlinket øverst på denne side.
* Power BI-rapporter understøtter kun liveforbindelse til Analysis Services (tabellarisk eller flerdimensionel).
* Ingen understøttelse af R-visuals.

**Problemer og indvirkning på kunden:** Hvis du har både SQL Server Reporting Services og Power BI-rapportserver på samme computer og fjerner en af delene, vil du ikke længere kunne oprette forbindelse til den tilbageværende rapportserver med konfigurationsstyring for rapportserveren.

**Løsning** For at omgå problemet skal du udføre følgende handlinger efter at have fjernet en af serverne.

1. Start en kommandoprompt i administratortilstand.
2. Gå til den mappe, hvor den tilbageværende rapportserver er installeret.
   
    *Standardplacering for Power BI-rapportserver: C:\Programmer\Microsoft Power BI-rapportserver.*
   
    *Standardplacering for SQL Server Reporting Services: C:\Programmer\Microsoft SQL Server Reporting Services*
3. Derefter skal du gå til næste mappe. Det vil enten være *SSRS* eller *PBIRS* afhængigt af, hvad der er tilbage.
4. Gå til WMI-mappen.
5. Kør følgende kommando:
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    Du kan ignorere følgende fejl, hvis den vises.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>Næste trin
[Nyheder i Power BI-rapportserver](whats-new.md)  
[Brugerhåndbog](user-handbook-overview.md)  
[Administratorhåndbog](admin-handbook-overview.md)  
[Hurtigstart: Installér Power BI Report Server](quickstart-install-report-server.md)  
[Installér Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

