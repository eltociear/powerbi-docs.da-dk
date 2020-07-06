---
title: Føj flere felter til et hierarki-udsnitsværktøj
description: Få mere at vide om, hvordan du opretter et hierarkiudsnitsværktøj, der indeholder flere felter i et hierarki.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/11/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 2b9c4a8f4695f8d701eba535180194d29dd8bdec
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238181"
---
# <a name="add-multiple-fields-to-a-hierarchy-slicer"></a>Føj flere felter til et hierarki-udsnitsværktøj

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Hvis du vil filtrere flere relaterede felter i et enkelt udsnitsværktøj, kan du gøre det ved at opbygge det, der kaldes et *hierarki-udsnitsværktøj*. Du kan oprette disse udsnitsværktøjer i enten Power BI Desktop eller i Power BI-tjenesten.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="Hierarki-udsnitsværktøj i Power BI":::

Når du føjer flere felter til udsnittet, vises der som standard en pil eller *vinkel* ud for de elementer, der kan udvides, for at få elementerne på næste niveau vist.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="Rulleliste for hierarki-udsnitsværktøj i Power BI":::
 
 
Når du vælger et eller flere underordnede til et element, kan du se en delvist markeret cirkel for elementet på øverste niveau.
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="Enkeltmarkeringstilstand for hierarki-udsnitsværktøj i Power BI":::

## <a name="format-the-slicer"></a>Formatér udsnittet

Funktionsmåden for udsnittet er ikke blevet ændret. Du kan også indstille dit udsnitsværktøj, som du vil. Du kan f.eks. angive det til enkeltmarkeringstilstand. Eller du kan skifte mellem en liste og en rullemenu. 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="Hierarki-udsnitsværktøj, der er formateret som et rullelisteudsnitsværktøj":::

### <a name="change-the-expandcollapse-icon"></a>Rediger ikonet Udvid/skjul

Hierarki-udsnitsværktøjer har nogle andre formateringsindstillinger. Du kan ændre ikonet Udvid/skjul fra standard pilen til et plus-/minustegn eller en tekstmarkør.

1. Vælg udsnitsværktøjet, og vælg derefter **Format**.
1. Udvid **Elementer** og vælg **ikonet Udvid/skjul**.
1. Vælg mellem **Chevron**, **Plus/minus** og **Tekstmarkør**.
 
    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-caret.png" alt-text="Vælg et udvid-/skjul-ikon til hierarki-udsnitsværktøjet":::
 
### <a name="change-the-indentation"></a>Rediger indrykningen

Hvis der ikke er meget plads i din rapport, kan det være en god idé at reducere mængden, du rykker de underordnede elementer ind. Indrykningen er som standard 15 pixel, men du kan øge eller reducere værdien. 

1. Vælg udsnitsværktøjet, og vælg derefter **Format**.
1. Udvid **Elementer**, og træk **Trinvis layoutindrykning** mindre eller større. Du kan også blot angive et tal i feltet.

    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-indentation.png" alt-text="Angiv indrykningen for hierarki-udsnitsværktøjet":::

## <a name="next-steps"></a>Næste trin

- [Udsnitsværktøjer i Power BI](../visuals/power-bi-visualization-slicers.md)
- Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)