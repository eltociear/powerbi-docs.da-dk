---
title: Løsning af "Der er ikke tillid til din virksomheds SSL-certifikat"
description: Når du logger på Power BI-appen til Android, kan du få vist meddelelsen "Godkendelsen lykkedes ikke, da denne enhed ikke har tillid til din virksomheds SSL-certifikat
.": ''
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: 494e148a62675aab1a6e799c4e4b61f022483d9f
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34444951"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>Løsning af "Der er ikke tillid til din virksomheds SSL-certifikat" – Power BI
Når du logger på Microsoft Power BI-appen til Android, kan du få vist meddelelsen "Godkendelsen lykkedes ikke, da denne enhed ikke har tillid til din virksomheds SSL-certifikat. Kontakt virksomhedens it-administrator." 

Løsningen afhænger af, hvilket operativsystem du har på din Android-enhed, men der er en række andre problemer, der kan medføre denne fejl.

## <a name="on-android-7-or-later"></a>På Android 7 eller senere
Se efter en opdatering til appen **Chrome**, og installér opdateringen.

## <a name="on-android-6-and-earlier"></a>På Android 6 eller tidligere
Du skal muligvis installere en opdateret version af System Webview på enheden. Den kan være installeret på din enhed, og du skal muligvis blot klikke på **Opdater**.

Hvis System Webview ikke er installeret på din enhed:

1. Luk Power BI på din Android-enhed.
2. Åbn Google Play Butik, og søg efter **System Webview** af Google Inc.
3. Installér appen.
4. Genstart Power BI-appen, og log på.

## <a name="time-zone-settings"></a>Indstillinger for tidszone
Tidszonen kan være angivet forkert på din enhed. 

Gå til **Indstillinger** > **System** > **Dato og klokkeslæt** for at se indstillingerne.

## <a name="custom-authentication-server"></a>Brugerdefineret godkendelsesserver
Hvis du bruger en brugerdefineret godkendelsesserver, kan det skyldes, at certifikatet i virksomhedens godkendelsesserver ikke er gyldigt. Kontakt din organisations it-administrator for at få hjælp.

## <a name="next-steps"></a>Næste trin
* [Download Android-appen](http://go.microsoft.com/fwlink/?LinkID=544867) fra Android App Store.
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

