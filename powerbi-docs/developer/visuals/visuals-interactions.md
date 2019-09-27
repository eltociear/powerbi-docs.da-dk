---
title: Interaktioner mellem visualiseringer i Power BI
description: I denne artikel beskrives det, hvordan du kontrollerer, om visualiseringer i Power BI tillader visuelle interaktioner.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 0155f0fce1bc0fec5c96aef1c7e1dc9cf64b122f
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193896"
---
# <a name="visual-interactions-in-power-bi-visuals"></a>Interaktioner mellem visualiseringer i Power BI

Visualiseringer kan forespørge om værdien af flaget `allowInteractions`, som angiver, om visualiseringen skal tillade visuelle interaktioner. Visualiseringer er f.eks. interaktive i forbindelse med visning eller redigering af en rapport, men ikke når de vises på et dashboard. Disse interaktioner er *klik*, *panorering*, *zoom*, *markeringer* m. fl. 

> [!NOTE]
> Du skal aktivere værktøjstip i alle scenarier, uanset hvilket flag der er angivet.

Flaget `allowInteractions` overføres som en boolesk værdi under initialiseringen af en visualisering som et medlem af grænsefladen IVisualHost.

I ethvert Power BI-scenarie, der kræver, at visualiseringer ikke er interaktive (f.eks. ved dashboardfelter), angives flaget `allowInteractions` som `false`. Ellers angives `allowInteractions` til `true` (f.eks. Rapport).

Du kan finde flere oplysninger i [lageret med SampleBarChart-visualiseringen](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001).

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId);
           ...
       }
   });
```
