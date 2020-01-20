---
title: Relationsvisning i Power BI Desktop
description: Relationsvisning i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: cd9671b8c38cb2aa1502c3aa00a871d125f819b1
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2020
ms.locfileid: "75760474"
---
# <a name="work-with-relationship-view-in-power-bi-desktop"></a>Arbejde med relationsvisning i Power BI Desktop
Med **Relationsvisning** vises alle tabeller, kolonner og relationer i din model. Det kan være særligt nyttigt, når din model indeholder komplekse relationer mellem mange tabeller.

Lad os se nærmere på det.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Ikonet Relationsvisning – Klik her for at få vist din model i Relationsvisning

**B.** Relation – Du kan holde markøren over en relation for at få vist de kolonner, der er bruges. Dobbeltklik på en relation for at åbne den i dialogboksen **Rediger relationer**. 

I figuren ovenfor kan du se, at tabellen *Stores* har en *StoreKey*-kolonne, der er relateret til tabellen *Salg*, som også har en *StoreKey*-kolonne. Vi kan se, at det er en relation af typen *Mange til én* (\*: 1), og ikonet midt på linjen viser, at den tværgående filterretning er angivet til *Begge*. Pilen på ikonet viser retningen af kontekstflowet for filteret.

Du kan finde flere oplysninger om relationer under [Opret og administrer relationer i Power BI Desktop](desktop-create-and-manage-relationships.md).

