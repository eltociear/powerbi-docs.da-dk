---
title: Power BI-arbejdsområderoller
description: Tabel over Power BI-arbejdsområderoller
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 04/23/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 9a6ca5abf3c26af876666ef45fe7ae192e69f2a3
ms.sourcegitcommit: 9ec2c608b90bf651df613f0714addd251a885039
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/24/2020
ms.locfileid: "82120339"
---
Her er egenskaberne for de fire roller: administratorer, medlemmer, bidragydere og fremvisere. Al denne funktionalitet, undtagen visning og interaktion, kræver en Power BI Pro-licens.

|Funktion   | Administrator  | Medlem  | Bidragsyder  | Fremviser |
|---|---|---|---|---|
| Opdatere og slette arbejdsområdet.  | X  |   |   |   | 
| Tilføje/fjerne personer, herunder andre administratorer.  | X  |   |   |   |
| Tilføje medlemmer eller andre med lavere tilladelser.  |  X | X  |   |   |
| Publicer og opdater en app. |  X | X  |   |   |
| Dele et element eller dele en app.<sup>1</sup> |  X | X  |   |   |
| Give andre tilladelse til at dele elementer igen.<sup>1</sup> |  X | X  |   |   |
| Fremhæve apps på kollegaers startside |  X | X  |   |   |
| Fremhæve dashboards og rapporter på kollegaers startside |  X | X  | X |   |
| Oprette, redigere og slette indhold i arbejdsområdet.  |  X | X  | X  |   |
| Publicere rapporter til arbejdsområdet, slette indhold.  |  X | X  | X  |   |
| Oprette en rapport i et andet arbejdsområde, der er baseret på et datasæt i dette arbejdsområde.<sup>1</sup> |  X | X  | X  |   |
| Kopiere en rapport.<sup>2</sup> | X | X | X |  |
| Få vist og interagere med et element.<sup>3</sup> |  X | X  | X  | X  |
| Læs data, der er gemt i dataflow i arbejdsområdet | X | X | X | X |

1. Bidragydere og seere kan dele elementer i et arbejdsområde, hvis de har tilladelsen Del igen.
2. Hvis du vil kopiere en rapport og oprette en rapport i et andet arbejdsområde, der er baseret på et datasæt i dette arbejdsområde, skal du have tilladelsen Opret for datasættet. Personer med rolle som administrator, medlem eller bidragyder har Build-tilladelse til datasæt for dette arbejdsområde gennem deres rolle i arbejdsområdet.
3. Selvom du ikke har en Power BI Pro-licens, kan du få vist og interagere med elementer i Power BI-tjenesten, hvis elementerne findes i et arbejdsområde i en Premium-kapacitet.

