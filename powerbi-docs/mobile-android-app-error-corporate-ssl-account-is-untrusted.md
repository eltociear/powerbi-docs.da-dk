---
title: 'Fejl: '
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "Når du logger på Power BI-appen til Android, kan du få vist meddelelsen \"Godkendelsen lykkedes ikke, da denne enhed ikke har tillid til din virksomheds SSL-certifikat"
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>Fejl: "Der er ikke tillid til din virksomheds SSL-certifikat" – Power BI
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
* Har du spørgsmål? [Prøv at spørge Power BI-communityet](http://community.powerbi.com/)

