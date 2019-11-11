---
title: 'Tjeneste fra tredjepart: Facebook-connector til Power BI Desktop'
description: 'Tjeneste fra tredjepart: Facebook-connector til Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 644e68ec827915c5457e22e1c1486a8f6f3299f6
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877026"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Facebook-connector til Power BI Desktop
Facebook-connectoren i **Power BI Desktop** er afhængig af Facebook Graph API'en. Som sådan kan funktioner og tilgængelighed variere over tid.

Du kan se et [selvstudium om Facebook-connectoren til Power BI Desktop](desktop-tutorial-facebook-analytics.md).

Facebook lod v1.0 af sin Graph API udløbe d. 30 april 2015. Power BI bruger Graph-API'en i baggrunden for Facebook-connectoren, hvilket giver dig mulighed for at oprette forbindelse til dine data og analysere dem.

Forespørgsler, der er oprettet før d. 30. april 2015, fungerer muligvis ikke længere, eller de returnerer færre data. Efter d. 30. april 2015 benytter Power BI v2.8 i alle kald til Facebook-API'en. Hvis din forespørgsel blev oprettet før den 30. april 2015, og du ikke har brugt den siden, skal du sandsynligvis godkende igen for at godkende det nye sæt tilladelser, som vi spørger om.

Selvom vi forsøger at udgive opdateringer i overenstemmelse med eventuelle ændringer, kan API'en ændres på en måde, som kan påvirke resultaterne af de forespørgsler, vi genererer. I nogle tilfælde vil visse forespørgsler ikke længere være understøttet. På grund af denne afhængighed kan vi ikke garantere resultaterne af dine forespørgsler, når du bruger denne connector.

Du kan få mere at vide om ændringen i Facebook-API'en [her](https://developers.facebook.com/docs/apps/changelog#v2_0).

