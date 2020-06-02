---
title: Power BI-arbejdsområderoller
description: Tabel over Power BI-arbejdsområderoller
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 05/26/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 708599eb3f39d4c627a11753cb964d6425f75640
ms.sourcegitcommit: a7b142685738a2f26ae0a5fa08f894f9ff03557b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/28/2020
ms.locfileid: "84120356"
---
|Funktion   | Administrator  | Medlem  | Bidragsyder  | Fremviser |
|---|---|---|---|---|
| Opdatere og slette arbejdsområdet.  |  |   |   |   | 
| Tilføje/fjerne personer, herunder andre administratorer.  |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) |   |   |   |
| Tilføje medlemmer eller andre med lavere tilladelser.  |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Publicer og opdater en app. |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Dele et element eller dele en app.<sup>1</sup> |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Give andre tilladelse til at dele elementer igen.<sup>1</sup> |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Fremhæve apps på kollegaers startside |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Fremhæve dashboards og rapporter på kollegaers startside |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) |   |
| Oprette, redigere og slette indhold i arbejdsområdet.  |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Publicere rapporter til arbejdsområdet, slette indhold.  |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Opret en rapport i et andet arbejdsområde, der er baseret på et datasæt i dette arbejdsområde.<sup>2</sup> |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Kopiere en rapport.<sup>2</sup> | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Planlæg dataopdateringer via gatewayen i det lokale miljø.<sup>3</sup> | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Rediger indstillinger for gatewayforbindelse.<sup>3</sup> | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Få vist og interager med et element.<sup>4</sup> |  ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png)  |
| Læs data, der er gemt i dataflow i arbejdsområdet | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Afkrydsning for ja](media/power-bi-workspace-roles-table/green-checkmark.png) |

<sup>1</sup> Bidragydere og seere kan også dele elementer i et arbejdsområde, hvis de har tilladelsen Del igen.

<sup>2</sup> Hvis du vil kopiere en rapport og oprette en rapport i et andet arbejdsområde, der er baseret på et datasæt i dette arbejdsområde, skal du have tilladelsen [Opret for datasættet](../connect-data/service-datasets-build-permissions.md). Personer med rolle som administrator, medlem eller bidragyder får automatisk Build-tilladelse til datasæt for dette arbejdsområde gennem deres rolle i arbejdsområdet.

<sup>3</sup> Vær opmærksom på, at du også skal have tilladelser til gatewayen. Disse tilladelser administreres andre steder, uafhængigt af rollerne og tilladelserne til arbejdsområder. Se [Administrer en gateway i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-manage) for at få flere oplysninger.

<sup>4</sup> Selvom du ikke har en Power BI Pro-licens, kan du få vist og interagere med elementer i Power BI-tjenesten, hvis elementerne findes i et arbejdsområde i en Premium-kapacitet.

