---
title: Interaktioner mellem visualiseringer i Power BI
description: I denne artikel beskrives det, hvordan du kontrollerer, om visualiseringer i Power BI tillader visuelle interaktioner.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b8b1a1a59ee9fae5a1c248548a14c5f91438edc9
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "79378932"
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
