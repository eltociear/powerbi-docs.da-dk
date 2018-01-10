---
title: "Oversigt over udviklerhåndbog, Power BI-rapportserver"
description: "Velkommen til udviklerhåndbogen til Power BI-rapportserver, der er en placering i det lokale miljø til lagring og administration af dine Power BI- og mobilrapporter samt dine sideinddelte rapporter."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: b8dc3463a2b32f7f2151031795b785beebc47f9d
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2018
---
# <a name="developer-handbook-overview-power-bi-report-server"></a>Oversigt over udviklerhåndbog, Power BI-rapportserver
Velkommen til udviklerhåndbogen til Power BI-rapportserver, der er en placering i det lokale miljø til lagring og administration af dine Power BI- og mobilrapporter samt dine sideinddelte rapporter.

![](media/developer-handbook-overview/admin-handbook.png)

I denne håndbog fremhæves de muligheder, du som udvikler har for at arbejde med Power BI-rapportserver.

## <a name="embedding"></a>Integration
Du kan integrere en hvilken som helst rapport på Power BI-rapportserver i en iFrame ved at føje parameteren `?rs:Embed=true` for forespørgselsstrengen til URL-adressen. Dette fungerer for Power BI-rapporter samt for andre rapporttyper.

### <a name="report-viewer-control"></a>Kontrolelementet Rapportfremviser
Du kan gøre brug af kontrolelementet Rapportfremviser i forbindelse med sideinddelte rapporter. Det giver dig mulighed for at placere kontrolelementet inde i et .NET-vindue eller --webprogram. Du kan finde flere oplysninger under [Introduktion til kontrolelementet Rapportfremviser](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

## <a name="apis"></a>API'er
Du har flere API-indstillinger, som du kan bruge til at interagere med Power BI-rapportserver. De omfatter bl.a. følgende.

* [REST API'er](rest-api.md)
* [Adgang til URL-adresse](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [WMI-provider](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Du kan også bruge de åbne kilder for [PowerShell-hjælpeprogrammer](https://github.com/Microsoft/ReportingServicesTools) til at administrere din rapportserver.

> [!NOTE]
> PowerShell-hjælpeprogrammerne understøtter i øjeblikket ikke Power BI Desktop-filer (.pbix).
> 
> 

## <a name="custom-extensions"></a>Brugerdefinerede udvidelser
Udvidelsesbiblioteket er et sæt klasser, grænseflader og værdityper, der er inkluderet i Power BI-rapportserver. Dette bibliotek giver adgang til systemets funktionalitet, og det er designet til at være det fundament, som Microsoft .NET Framework-programmer kan bruge til at udvide komponenter til Power BI-rapportserver.

Der findes flere typer udvidelser, som du kan oprette.

* Udvidelser til databehandling
* Udvidelser til levering
* Udvidelser til gengivelse i forbindelse med sideinddelte rapporter
* Udvidelser til sikkerhed

Du kan finde flere oplysninger under [Udvidelsesbibliotek](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library).

## <a name="next-steps"></a>Næste trin
[Introduktion til kontrolelementet Rapportfremviser](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)  
[Oprettelse af programmer ved hjælp af webtjenesten og .NET Framework](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework)  
[Adgang til URL-adresse](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[Udvidelsesbibliotek](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[WMI-provider](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

