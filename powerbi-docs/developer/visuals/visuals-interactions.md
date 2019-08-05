---
title: Interaktioner mellem visualiseringer
description: Sådan kontrollerer du, at Power BI-visualiseringen tillader visuelle interaktioner
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 739e59c6da3c1e464e0462a928bc4f33ea0d01f8
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424487"
---
# <a name="visuals-interactions"></a>Interaktioner mellem visualiseringer

Visualiseringer kan forespørge om værdien af flaget "allowInteractions", der angiver, om visualiseringen skal tillade visuelle interaktioner.
Visualiseringer er f.eks. interaktive i forbindelse med visning eller redigering af en rapport, men ikke når de vises på et dashboard.
Disse interaktioner er klik, panorering, zoom, markeringer m. fl.
Bemærk, at værktøjstip skal være aktiveret i alle scenarier uden hensyn til dette flag.

Flaget "allowInteractions" overføres som en boolesk værdi under initialiseringen af visualiseringen som et medlem af grænsefladen IVisualHost.

I ethvert Power BI-scenarie, der kræver, at visualiseringer ikke er interaktive (f. eks. ved dashboardfelter), angives flaget "allowInteractions" til false.
Ellers er "allowInteractions" angivet til true (f.eks. ved Rapport).

Du kan finde flere oplysninger i [lageret med SampleBarChart-visualiseringen](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001)

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
