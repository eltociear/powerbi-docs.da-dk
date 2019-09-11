---
title: Interaktioner mellem visualiseringer i Power BI
description: I denne artikel beskrives det, hvordan du kontrollerer, om visualiseringer i Power BI tillader visuelle interaktioner.
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f2fb2d451deb63b5e9c08472654e28d0e1a469db
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236602"
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
