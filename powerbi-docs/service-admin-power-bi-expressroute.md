---
title: Power BI og ExpressRoute
description: Power BI og ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0c4618150094a4eabb0dc9745e9ac93e4f342ff1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291090"
---
# <a name="power-bi-and-expressroute"></a>Power BI og ExpressRoute

**ExpressRoute** er en Azure-tjeneste, der gør det muligt at oprette private forbindelser mellem Azure-datacentre (hvor Power BI findes) og infrastrukturen i det lokale miljø, eller oprette private forbindelser mellem Azure-datacentre og colocation-miljøet.

Du kan bruge **Power BI** og **ExpressRoute** til at oprette en privat netværksforbindelse fra din organisation til Power BI (eller bruge en ISP's colocation-facilitet), der omgår internettet og sørger for en bedre sikkerhed for følsomme Power BI-data og -forbindelser.

Du kan finde flere oplysninger i [Oversigt over ExpressRoute](/azure/expressroute/expressroute-introduction). Power BI er kompatibel med ExpressRoute med nogle få undtagelser, hvor Power BI henter eller sender data over det offentlige internet. Du kan få vist en liste over de URL-adresser, der anvendes i Power BI, under [URL-adresser i Power BI](power-bi-whitelist-urls.md).

![Diagram over ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)