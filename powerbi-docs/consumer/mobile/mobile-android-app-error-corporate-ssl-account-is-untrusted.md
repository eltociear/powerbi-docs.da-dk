---
title: Løsning af "Der er ikke tillid til din virksomheds SSL-certifikat"
description: Når du logger på Power BI-appen til Android, kan du få vist meddelelsen "Godkendelsen lykkedes ikke, da denne enhed ikke har tillid til din virksomheds SSL-certifikat
.": ''
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mshenhav
ms.openlocfilehash: 2b296d465b312486a91e1407b5866e15b0b48b54
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280786"
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

