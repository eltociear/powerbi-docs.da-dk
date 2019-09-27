---
title: 'Tjeneste fra tredjepart: Facebook-connector til Power BI Desktop'
description: 'Tjeneste fra tredjepart: Facebook-connector til Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6b02717c49a1207dfec39ebb1529e7e9b222fa62
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65512867"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Facebook-connector til Power BI Desktop
Facebook-connectoren i **Power BI Desktop** er afhængig af Facebook Graph API'en. Som sådan kan funktioner og tilgængelighed variere over tid.

Du kan se et [selvstudium om Facebook-connectoren til Power BI Desktop](desktop-tutorial-facebook-analytics.md).

Facebook lod v1.0 af sin Graph API udløbe d. 30 april 2015. Power BI bruger Graph-API'en i baggrunden for Facebook-connectoren, hvilket giver dig mulighed for at oprette forbindelse til dine data og analysere dem.

Forespørgsler, der er oprettet før d. 30. april 2015, fungerer muligvis ikke længere, eller de returnerer færre data. Efter d. 30. april 2015 benytter Power BI v2.8 i alle kald til Facebook-API'en. Hvis din forespørgsel blev oprettet før den 30. april 2015, og du ikke har brugt den siden, skal du sandsynligvis godkende igen for at godkende det nye sæt tilladelser, som vi spørger om.

Selvom vi forsøger at udgive opdateringer i overenstemmelse med eventuelle ændringer, kan API'en ændres på en måde, som kan påvirke resultaterne af de forespørgsler, vi genererer. I nogle tilfælde vil visse forespørgsler ikke længere være understøttet. På grund af denne afhængighed kan vi ikke garantere resultaterne af dine forespørgsler, når du bruger denne connector.

Du kan få mere at vide om ændringen i Facebook-API'en [her](https://developers.facebook.com/docs/apps/changelog#v2_0).

