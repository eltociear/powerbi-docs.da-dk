---
title: Løs problemer, når Power BI Desktop startes
description: Løs problemer, når Power BI Desktop startes
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: bdf3791d74510b1630bc13c279ed0cd5ebddc3ec
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813451"
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Løs problemer, når Power BI Desktop ikke vil starte
I **Power BI Desktop** kan brugere, der har installeret og kører tidligere versioner af **Power BI datagatewayen i det lokale miljø**, blive blokeret, så de ikke kan starte Power BI Desktop. Det skyldes administrative politikbegrænsninger, som Power BI gatewayen i det lokale miljø har angivet for navngivne pipes på den lokale computer. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Løs problemer med datagatewayen i det lokale miljø og Power BI Desktop
Der er tre muligheder for at løse det problem, der er knyttet til datagatewayen i det lokale miljø, og gøre det muligt at starte Power BI Desktop:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Løsning 1: Installér den nyeste version af Power BI datagatewayen i det lokale miljø
Den nyeste version af Power BI datagatewayen i det lokale miljø angiver ikke begrænsninger for navngivne pipes på den lokale computer, hvilket gør det muligt at starte Power BI Desktop korrekt. Dette er den anbefalede løsning, hvis du vil fortsætte med at bruge Power BI datagatewayen i det lokale miljø. Du kan downloade den nyeste version af Power BI datagatewayen i det lokale miljø fra [denne placering](https://go.microsoft.com/fwlink/?LinkId=698863). Bemærk, at linket er et direkte link til download af den eksekverbare installationsfil.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Løsning 2: Fjern eller stop Windows tjenesten til Power BI datagatewayen i det lokale miljø
Hvis du ikke længere har brug for Power BI datagatewayen i det lokale miljø, kan du fjerne den. Du kan også stoppe Windows tjenesten til Power BI datagatewayen i det lokale miljø, hvilket medfører, at politikbegrænsningen fjernes, og at Power BI Desktop kan starte.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Løsning 3: Kør Power BI Desktop med administratorrettigheder
Du kan også starte Power BI Desktop som administrator, hvilket også gør det muligt for Power BI Desktop at starte. Det anbefales stadig, at du installerer den nyeste version af Power BI datagatewayen i det lokale miljø, som beskrevet tidligere i denne artikel.

Det er vigtigt at bemærke, at Power BI Desktop er udviklet som en arkitektur til flere processer, og flere af disse processer kommunikerer ved hjælp af navngivne Windows-pipes. Der kan være andre processer, som er i konflikt med disse navngivne pipes. Den mest almindelige årsag til denne konflikt er sikkerhed, herunder situationer, hvor antivirussoftware eller firewalls kan blokere pipes eller omdirigere trafik til en bestemt port. Du kan muligvis løse problemet ved at starte Power BI Desktop med administratorrettigheder. Hvis det ikke er muligt at starte med administratorrettigheder, kan du kontakte din administrator for at finde ud af, hvilke sikkerhedsregler der anvendes, som forhindrer kommunikation fra navngivne pipes, og whiteliste Power BI Desktop og de respektive underprocesser.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>Løs problemer, når der oprettes forbindelse til SQL Server
Hvis der vises en fejlmeddelelse, der svarer til følgende, når du opretter forbindelse til en SQL Server-database, kan du ofte løse problemet ved at starte **Power BI Desktop** som administrator, og opret derefter SQL Server-forbindelse:

    "An error happened while reading data from the provider: 'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies. Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"

Når du starter som administrator og opretter forbindelse, registreres de påkrævede DLL'er korrekt. Herefter er det ikke nødvendigt at starte Power BI Desktop som administrator.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Hjælp til andre problemer, når du starter Power BI Desktop
Vi bestræber os på at dække så mange af de problemer, der kan opstå i forbindelse med **Power BI Desktop**, som muligt. Vi kigger jævnligt på problemer, der kan påvirke mange kunder, og inkluderer dem i vores artikler.

Hvis problemet med at starte **Power BI Desktop** ikke er knyttet til datagatewayen i det lokale miljø, eller hvis tidligere løsninger ikke virker, kan du sende en supporthændelse til [Power BI-support](https://support.powerbi.com) (https://support.powerbi.com)) for at få hjælp til at identificere og løse problemet.

Hvis der fremover opstår andre problemer med **Power BI Desktop** (det håber vi ikke!), er det en god ide at aktivere sporing og indsamle logfiler, så vi bedre kan isolere og identificere problemet. Hvis du vil aktivere sporing, skal du vælge **Filer > Indstillinger > Indstillinger**, vælge **Diagnosticering** og derefter markere **Aktivér sporing** under *Indstillinger for diagnosticering*. Vi er klar over, at **Power BI Desktop** skal køre, for at du kan angive denne indstilling, som er mere nyttig, hvis der fremover opstår problemer med at starte **Power BI Desktop**.

