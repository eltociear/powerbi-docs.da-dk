---
title: 'Tredjepartstjeneste: Facebook-connector til Power BI Desktop'
description: 'Tredjepartstjeneste: Facebook-connector til Power BI Desktop'
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
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 894791ddc4eb632ad4dc0ee55f19bbadad5e28d6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Facebook-connector til Power BI Desktop
Facebook-connectoren i **Power BI Desktop** er afhængig af Facebook Graph API'en. Som sådan kan funktioner og tilgængelighed variere over tid.

Du kan se et [selvstudium om Facebook-connectoren til Power BI Desktop](desktop-tutorial-facebook-analytics.md).

Facebooks Graph-API v1.0 udløb den 30.<sup></sup> april 2015. Power BI bruger Graph-API'en i baggrunden for Facebook-connectoren, hvilket giver dig mulighed for at oprette forbindelse til dine data og analysere dem.

Forespørgsler, der er oprettet før den 30.<sup></sup> april 2015, fungerer muligvis ikke længere, eller de returnerer færre data. Efter den 30.<sup></sup> april 2015 benytter Power BI v2.8 i alle kald til Facebook-API'en. Hvis din forespørgsel blev oprettet før den 30. april 2015, og du ikke har brugt den siden, skal du sandsynligvis godkende igen for at godkende det nye sæt tilladelser, som vi spørger om.

Selvom vi forsøger at udgive opdateringer i overenstemmelse med eventuelle ændringer, kan API'en ændres på en måde, som kan påvirke resultaterne af de forespørgsler, vi genererer. I nogle tilfælde vil visse forespørgsler ikke længere være understøttet. På grund af denne afhængighed kan vi ikke garantere resultaterne af dine forespørgsler, når du bruger denne connector.

Du kan få mere at vide om ændringen i Facebook-API'en [her](https://developers.facebook.com/docs/apps/changelog#v2_0).

