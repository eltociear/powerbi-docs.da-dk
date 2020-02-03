---
title: Funktioner og egenskaber for visualiseringer i Power BI
description: I denne artikel beskrives egenskaberne og funktionerne for visualiseringer i Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7d24ea77fd73ca6a83176d1b8560c88fa98a8d6b
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819186"
---
# <a name="add-context-menu-to-power-bi-visual"></a>Føj en genvejsmenu til Power BI-visual

Du kan bruge `selectionManager.showContextMenu()` med parametre `selectionId` og en placering (som et `{x:, y:}`-objekt) for at få Power BI til at vise en genvejsmenu for dit visual.

> [!IMPORTANT]
> `selectionManager.showContextMenu()` blev introduceret i API 2.2.0 til visuals.

Den tilføjes typisk som en højreklikhændelse (eller langt tryk for touchenheder), og der blev tilføjet en genvejsmenu til eksempelsøjlediagrammet til reference:

```typescript
    public update(options: VisualUpdateOptions) {
        //...
        //handle context menu
        this.svg.on('contextmenu', () => {
            const mouseEvent: MouseEvent = d3.event as MouseEvent;
            const eventTarget: EventTarget = mouseEvent.target;
            let dataPoint = d3.select(eventTarget).datum();
            this.selectionManager.showContextMenu(dataPoint? dataPoint.selectionId : {}, {
                x: mouseEvent.clientX,
                y: mouseEvent.clientY
            });
            mouseEvent.preventDefault();
        });
```
