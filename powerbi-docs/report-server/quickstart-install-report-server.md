---
title: 'Hurtigstart: Installer Power BI-rapportserver'
description: "Installationen af selve Power BI-rapportserver er meget hurtig. Download, installation og konfiguration er hurtigt overstået, og du kan få det hele op at køre på få minutter."
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
ms.date: 06/28/2017
ms.author: maghan
ms.openlocfilehash: 934b4d3f2da44a161cd76d14c9f042aaf697f26d
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>Hurtigstart: Installer Power BI-rapportserver
Installationen af selve Power BI-rapportserver er meget hurtig. Download, installation og konfiguration er hurtigt overstået, og du kan få det hele op at køre på få minutter.

Dette er et hurtigt overblik over, hvordan du installerer en rapportserver, hvis du bare vil i gang med at bruge en ny server. Du kan finde mere detaljerede oplysninger om installation af en rapportserver i [Installér Power BI-rapportserver](install-report-server.md).

 **Download** ![download](media/quickstart-install-report-server/download.png "download")

Hvis du vil downloade Power BI-rapportserver, skal du gå til [Rapportering i det lokale miljø med Power BI-rapportserver](https://powerbi.microsoft.com/report-server/). Hvis du vil hente Power BI Desktop optimeret til Power BI-rapportserver, skal du gå til [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=837581).

![tip](media/quickstart-install-report-server/fyi-tip.png "tip") Se de aktuelle produktbemærkninger i [Power BI-rapportserver – produktbemærkninger](release-notes.md).

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>Inden du starter
Før du installerer Power BI-rapportserver, anbefales det, at du læser [Hardware- og softwarekrav til installation af Power BI-rapportserver](system-requirements.md).

## <a name="step-1-download"></a>Trin 1: Download
Download installationsfilerne til Power BI-rapportserver lokalt. Hvis du vil downloade Power BI-rapportserver, skal du gå til [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=839351).

![Download Power BI-rapportserver](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>Trin 2: Kør installationsprogrammet
Kør filen PowerBIReportServer.exe, som du har downloadet, og gå gennem installationsskærmbillederne. Du får mulighed for at vælge installationsstien samt vælge den udgave, der skal installeres. Du kan vælge mellem en evaluering, der udløber inden 180 dage, en udviklerudgave eller at angive en produktnøgle.

![Installér Power BI-rapportserver](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>Trin 3: Konfigurer serveren
Når du er færdig, skal du køre Configuration Manager for at afslutte konfigurationen af serveren. Du skal oprette en ReportServer-katalogdatabase samt bekræfte webadresserne til webportalen og webtjenesten.

![Konfigurer Power BI-rapportserver](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>Trin 4: Gå til webportalen
Nu, hvor du har konfigureret, bør du kunne åbne en browser til webportalen på serveren. Det vil som standard være `http://localhost/reports`. Du kan muligvis også gennemse ved at bruge computerens navn i stedet for at bruge localhost som standard under forudsætning af, at du ikke blokeres af nogen form for firewall.

![Webportalen til Power BI-rapportserver](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>Næste trin
[Administratorhåndbog](admin-handbook-overview.md)  
[Sådan finder du produktnøglen til din rapportserver](find-product-key.md)  
[Installér Power BI-rapportserver](install-report-server.md)  
[Installér Power BI Desktop optimeret til Power BI-rapportserver](install-powerbi-desktop.md)  
[Browserunderstøttelse af Power BI-rapportserver](browser-support.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

