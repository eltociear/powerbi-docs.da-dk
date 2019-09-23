---
title: Power BI og ExpressRoute
description: Power BI og ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c7d12bf6a1a2a02c988f8351a1844be1080ad2b8
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074809"
---
# <a name="power-bi-and-expressroute"></a>Power BI og ExpressRoute

**ExpressRoute** er en Azure-tjeneste, der gør det muligt at oprette private forbindelser mellem Azure-datacentre (hvor Power BI findes) og infrastrukturen i det lokale miljø, eller oprette private forbindelser mellem Azure-datacentre og colocation-miljøet.

Du kan bruge **Power BI** og **ExpressRoute** til at oprette en privat netværksforbindelse fra din organisation til Power BI (eller bruge en ISP's colocation-facilitet), der omgår internettet og sørger for en bedre sikkerhed for følsomme Power BI-data og -forbindelser.

Du kan finde flere oplysninger i [Oversigt over ExpressRoute](/azure/expressroute/expressroute-introduction). Power BI er kompatibel med ExpressRoute med nogle få undtagelser, hvor Power BI henter eller sender data over det offentlige internet. Du kan få vist en liste over de URL-adresser, der anvendes i Power BI, under [URL-adresser i Power BI](power-bi-whitelist-urls.md).

![Diagram over ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)