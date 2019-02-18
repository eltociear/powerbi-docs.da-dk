---
title: Fejlfinding af logonproblemer i Power BI Desktop
description: Løsninger på almindelige logonproblemer i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 7b34bd31592f59048899ccf04385d7b302fd3204
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223277"
---
# <a name="troubleshooting-sign-in-for-power-bi-desktop"></a>Fejlfinding af logonproblemer i Power BI Desktop
Der kan være situationer, hvor du forsøger at logge på **Power BI Desktop**, men støder på fejl. Der er to primære årsager til logonproblemer: **Proxy-godkendelsesfejl** og **fejl ved omdirigering til URL-adresser, der ikke er HTTPS**. 

Hvis du vil finde ud af, hvad der forårsager dit logonproblem, skal du først kontakte administratoren og levere diagnosticeringsoplysninger, så administratoren kan finde årsagen til problemet. Ved at spore problemer, der er knyttet til logonproblemet, kan administratorer afgøre, hvilke af følgende fejl der er skyld i dit problem. 

Lad os se på disse problemer hver for sig. I slutningen af denne artikel kan du se en beskrivelse af, hvordan du henter *sporingsoplysninger* i Power BI Desktop, som kan hjælpe dig med at spore fejlfindingsproblemer.


## <a name="proxy-authentication-required-error"></a>Fejlen Proxygodkendelse kræves

På følgende skærm vises et eksempel på fejlen *Proxygodkendelse kræves*.

![Logonfejl i forbindelse med fejlen Proxygodkendelse kræves](media/desktop-troubleshooting-sign-in/desktop-tshoot-sign-in_01.png)

Følgende undtagelser i *Power BI Desktop*-sporingsfiler er knyttet til denne fejl:

* *Microsoft.PowerBI.Client.Windows.Services.PowerBIWebException*
* *HttpStatusCode: ProxyAuthenticationRequired*

Når denne fejl opstår, skyldes det højst sandsynligt, at en proxyserver til godkendelse på netværket blokerer webanmodninger, der er udstedt af **Power BI Desktop**. 

Hvis dit netværk bruger en proxyserver til godkendelse, kan din administrator løse problemet ved at hvidliste følgende domæner på proxyserveren til godkendelse:

* app.powerbi.com
* api.powerbi.com
* domæner i navneområdet *.analysis.windows.net

For kunder, der er en del af en cloudløsning til offentlige myndigheder, kan dette problem løses ved at hvidliste følgende domæner på proxyserveren til godkendelse:

* app.powerbigov.us
* api.powerbigov.us
* domæner i navneområdet *.analysis.usgovcloudapi.net

## <a name="non-https-url-redirect-not-supported-error"></a>Der opstod en fejl under omdirigering til URL-adresse, der ikke er HTTPS

Aktuelle versioner af **Power BI Desktop** bruger den aktuelle version af ADAL (Active Directory Authentication Library), der ikke tillader omdirigering til ikke-sikrede (ikke-HTTPS) URL-adresser. 

Følgende undtagelser i *Power BI Desktop*-sporingsfiler er knyttet til denne fejl:

* *Microsoft.IdentityModel.Clients.ActiveDirectory.AdalServiceException: Omdirigering til URL-adresser, der ikke er HTTPS, understøttes ikke i webvisning*
* *ErrorCode: non_https_redirect_failed*

Hvis fejlen *ErrorCode: non_https_redirect_failed* opstår, betyder det, at en eller flere omdirigeringssider eller providere i rækken af omdirigeringer ikke er et HTTPS-beskyttet slutpunkt, eller at en certifikatudsteder af en eller flere omdirigeringer ikke er blandt de rodnøgler, enheden har tillid til. Alle providere i rækken af logonomdirigeringer skal bruge en HTTPS-sikret URL-adresse. Du kan få løst dette problem ved at kontakte administratoren og anmode om, at sikrede URL-adresser bruges til deres godkendelseswebsteder. 

## <a name="how-to-collect-a-trace-in-power-bi-desktop"></a>Sådan indhenter du sporingsoplysninger i Power BI Desktop

Hvis du vil indhente sporingsoplysninger i **Power BI Desktop**, skal du udføre disse trin:

1. Aktivér sporing i **Power BI Desktop** ved at gå til **Filer > Indstillinger > Indstillinger** og derefter vælge **Diagnosticering** i indstillingerne i venstre rude. I den rude, der vises, skal du markere afkrydsningsfeltet ud for **Aktivér sporing** som vist på følgende billede. Du skal muligvis genstarte **Power BI Desktop**.
   
   ![Aktivér sporing i Power BI Desktop](media/desktop-troubleshooting-sign-in/desktop-tshoot-sign-in_02.png)

2. Udfør derefter de trin, der genskaber fejlen. Når det sker, føjer **Power BI Desktop** hændelser til sporingsloggen, som er gemt på den lokale computer.

3. Gå til mappen Sporinger på din lokale computer. Du kan finde denne mappe ved at vælge linket i den **diagnosticering**, hvor sporing er aktiveret, der vises som *mappen Åben crashdump/Sporinger* på forrige billede. Den findes ofte på den lokale computer på følgende placering:

    `C:\Users/<user name>/AppData/Local/Microsoft/Power BI Desktop/Traces`

Der kan være mange sporingsfiler i denne mappe. Sørg for kun at sende de seneste filer til din administrator, så det er lettere at identificere fejlen hurtigt. 

