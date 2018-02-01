---
title: "Løs problemer, når Power BI Desktop startes"
description: "Løs problemer, når Power BI Desktop startes"
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 515832b9e6b737a942b08b491b78337d78398ee3
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/25/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Løs problemer, når Power BI Desktop ikke vil starte
I **Power BI Desktop** kan brugere, der har installeret og kører tidligere versioner af **Power BI-datagatewayen i det lokale miljø**, blokeres, så de ikke kan starte Power BI Desktop, hvilket skyldes administrative politikbegrænsninger, som Power BI-gatewayen i det lokale miljø har angivet for navngivne pipes på den lokale computer. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Løs problemer med datagatewayen i det lokale miljø og Power BI Desktop
Der er tre muligheder for at løse det problem, der er knyttet til den lokale datagateway og start af Power BI Desktop:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Løsning 1: Installér den nyeste version af Power BI-datagatewayen i det lokale miljø
Den nyeste version af Power BI-datagatewayen i det lokale miljø angiver ikke begrænsninger for navngivne pipes på den lokale computer, og den tillader, at Power BI Desktop starter korrekt. Dette er den anbefalede løsning, hvis du vil fortsætte med at bruge Power BI-datagatewayen i det lokale miljø. Du kan downloade den nyeste version af Power BI-datagatewayen i det lokale miljø fra [denne placering](https://go.microsoft.com/fwlink/?LinkId=698863). Bemærk, at linket er et direkte link til download af den eksekverbare installationsfil.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Løsning 2: Fjern eller stop Windows-tjenesten til Power BI-datagatewayen i det lokale miljø
Hvis du ikke længere har brug for Power BI-datagatewayen i det lokale miljø, kan du fjerne den, eller du kan stoppe Windows-tjenesten til Power BI-datagatewayen i det lokale miljø, hvilket medfører, at politikbegrænsningen fjernes, og at Power BI Desktop kan starte.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Løsning 3: Kør Power BI Desktop med administratorrettigheder
Du kan også starte Power BI Desktop som administrator, hvilket også gør det muligt for Power BI Desktop at starte. Det anbefales stadig, at du installerer den nyeste version af Power BI-datagatewayen i det lokale miljø som beskrevet tidligere i denne artikel.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Hjælp til andre problemer, når du starter Power BI Desktop
Vi bestræber os på at dække så mange af de problemer, der kan opstå i forbindelse med **Power BI Desktop**, som muligt. Vi kigger jævnligt på problemer, der kan påvirke mange kunder, og inkluderer dem i vores artikler.

Hvis problemet med at starte **Power BI Desktop** ikke er knyttet til den lokale datagateway, eller hvis tidligere løsninger ikke virker, kan du sende en supporthændelse til [Power BI-support](https://support.powerbi.com) (https://support.powerbi.com), så vi kan hjælpe med at identificere og løse problemet.

Hvis der fremover opstår andre problemer med **Power BI Desktop** (det håber vi ikke!), er det en god ide at aktivere sporing og indsamle logfiler, så vi bedre kan isolere og identificere problemet. Hvis du vil aktivere sporing, skal du vælge **Filer > Indstillinger > Indstillinger**, vælge **Diagnosticering** og derefter markere **Aktivér sporing** under *Indstillinger for diagnosticering*. Vi er klar over, at **Power BI Desktop** skal køre, for at du kan angive denne indstilling, som er mere nyttig, hvis der fremover opstår problemer med at starte **Power BI Desktop**.

