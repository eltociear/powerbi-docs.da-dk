---
title: Relationsvisning i Power BI Desktop
description: Relationsvisning i Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 310babc105289e747a885f8809bfdf0d494fa9b2
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2018
---
# <a name="relationship-view-in-power-bi-desktop"></a>Relationsvisning i Power BI Desktop
Med **Relationsvisning** vises alle tabeller, kolonner og relationer i din model. Det kan være særligt nyttigt, når din model indeholder komplekse relationer mellem mange tabeller.

Lad os se nærmere på det.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Ikonet Relationsvisning – Klik her for at få vist din model i Relationsvisning

**B.** Relation – Du kan holde markøren over en relation for at få vist de kolonner, der er bruges. Dobbeltklik på en relation for at åbne den i dialogboksen **Rediger relationer**. 

I figuren ovenfor kan du se, at tabellen *Stores* har en *StoreKey*-kolonne, der er relateret til tabellen *Salg*, som også har en *StoreKey*-kolonne. Vi kan se, at det er en relation af typen *Mange til én* (\*: 1), og ikonet midt på linjen viser, at den tværgående filterretning er angivet til *Begge*. Pilen på ikonet viser retningen af kontekstflowet for filteret.

Du kan finde flere oplysninger om relationer under [Opret og administrer relationer i Power BI Desktop](desktop-create-and-manage-relationships.md).

