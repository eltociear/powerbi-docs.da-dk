---
title: Fremhævning
description: Fremhævning af markerede datapunkter i Power BI-visualiseringer
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1ee45781ddc29eee9eeab23a5d748fb7752fe907
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424809"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>Fremhæv datapunkter i Power BI-visualiseringer

Når et element markeres, filtreres matrixen `values` i objektet `dataView` som standard, så der kun vises de markerede værdier. Det medfører, at det kun er de markerede data, der vises i alle andre visualiseringer på siden.

![standardfunktionsmåde af fremhævning af "datavisning"](./media/highlight-dataview.png)

Hvis du angiver egenskaben `supportsHighlight` i `capabilities.json` til `true`, får du vist den fulde ikke-filtrerede matrix `values` sammen med en `highlights`-matrix. Matrixen `highlights` har samme længde som matrixen for værdier, og alle værdier, der ikke er markeret, angives til `null`. Når denne egenskab er aktiveret, er det visualiseringens ansvar at fremhæve de relevante data ved at sammenligne `values`-matrixen med `highlights`-matrixen.

![fremhævning af "datavisning" understøtter fremhævning](./media/highlight-dataview-supports.png)

I eksemplet vil du bemærke den ene søjle, der er markeret. Og det er den eneste værdi i den fremhævede matrix. Det er også vigtigt at bemærke, at der kan være flere markeringer og delvis fremhævning. Der findes en tilsvarende numerisk værdi i matrixerne for værdier og fremhævninger, men de vil være forskellige.
