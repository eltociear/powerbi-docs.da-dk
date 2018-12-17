---
title: Rediger, hvordan et diagram sorteres i en rapport i Power BI
description: Rediger, hvordan et diagram sorteres i en rapport i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: Conceptual
ms.date: 09/20/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: f4ca6633eb401e7df8041ea385284210c14995ad
ms.sourcegitcommit: 4f46d71ff6026c1c158f007425aefdcb501f48ee
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2018
ms.locfileid: "52979327"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Rediger, hvordan et diagram sorteres i en rapport i Power BI
I en Power BI-rapport kan du sortere de fleste visualiseringer alfabetisk efter navnene på kategorierne i diagrammet eller efter de numeriske værdier for hver kategori. Dette diagram er f.eks. sorteret efter kategorien **lagernavn**.

![](media/end-user-change-sort/pbi_chartsortcategory.png)

Det er nemt at ændre sorteringen fra en kategori (gem navn) til en værdi (salg pr. kvadratfod) i stedet.

1. Vælg ellipserne (...), og vælg **Sortér efter > Salg pr. kvadratmeter**.
2. Hvis det er nødvendigt, skal du vælge ellipsen igen og vælge **Sortér faldende**.

   ![](media/end-user-change-sort/sort.gif)

   **BEMÆRK**! Det er ikke alle visualiseringer, der kan sorteres.  Følgende visualiseringer kan f.eks, ikke sorteres: træstruktur, kort, udfyldt kort, punktdiagram, måler, kort, kort med flere rækker, vandfaldsdiagram.

## <a name="saving-changes-you-make-to-sort-order"></a>Gem dine ændringer af sorteringsrækkefølgen
Power BI-rapporter bevarer filtre, udsnit, sortering og andre ændringer af datavisning. Hvis du navigerer væk fra en rapport og vender tilbage igen senere, er dine ændringer blevet gemt.  Hvis du vil ændre indstillingerne tilbage til de indstillinger, som rapportopretteren oprindeligt valgte, skal du vælge **Nulstil til standard** på den øverste menulinje. 

![fast sortering](media/end-user-change-sort/power-bi-reset-to-default.png)

Hvis knappen **Nulstil til standard** er nedtonet, betyder det, at rapportens opretter har deaktiveret muligheden for at gemme dine egne ændringer.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Sortering ved hjælp af andre kriterier
Der kan nogle gange være behov for at sortere visuelle elementer med brug af et andet felt eller andre kriterier.  Det kan f.eks. være, at du vil sortere efter måned (og ikke i alfabetisk rækkefølge), eller at du vil sortere efter hele tal i stedet for cifre (f.eks. 0, 1, 9, 20 og ikke 0, 1, 20, 9).  

I nogle tilfælde kan du muligvis sortere det visuelle element på den måde, du ønsker, f.eks. efter måned.  Men er det ikke muligt, kan det være fordi, datasættet bag rapporten skal tilpasses. Bed rapportopretteren om at opdatere datasættet.

## <a name="next-steps"></a>Næste trin
Få mere at vide om [Visualiseringer i Power BI-rapporter](end-user-visualizations.md).

[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)