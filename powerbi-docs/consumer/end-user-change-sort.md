---
title: Rediger, hvordan et diagram sorteres i en rapport
description: Rediger, hvordan et diagram sorteres i en rapport i Power BI
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e325d13dd8001e8da41dc5602bf3f7dbba2f371f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73852373"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Rediger, hvordan et diagram sorteres i en rapport i Power BI

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

I Power BI-tjenesten kan du ændre, hvordan en visualisering ser ud, ved at sortere den efter forskellige datafelter. Hvis du ændrer, hvordan du sorterer en visualisering, kan du fremhæve de oplysninger, du vil formidle, og sikre, at visualiseringen afspejler eller fremhæver den tendens.

Uanset om du bruger numeriske data, f.eks. salgstal, eller tekstdata, f.eks. navne på byer, kan du sortere visualiseringerne, som du vil, for at få dem til at se ud, som du vil. Power BI indeholder mange sorteringsmuligheder og genvejsmenuer, som du kan bruge. Vælg **Flere handlinger** (...) for en hvilken som helst visualisering, og vælg derefter det felt, du vil sortere efter.

![søjlediagram sorteret alpha af X-akse](media/end-user-change-sort/power-bi-more-actions.png)

Visualiseringer på et dashboard kan ikke sorteres, men i en Power BI-rapport kan du sortere de fleste visualiseringer alfabetisk efter navnene på kategorierne i diagrammet eller efter de numeriske værdier for hver kategori. Dette diagram er f.eks. sorteret alfabetisk efter kategorien **butiksnavn**.

![søjlediagram sorteret alpha af X-akse](media/end-user-change-sort/pbi-chartsortcategory.png)

Det er nemt at ændre sorteringen fra en kategori (gem navn) til en værdi (salg pr. kvadratfod) i stedet.

1. Vælg **Flere handlinger** (...), og vælg **Sortér efter > Salg pr. kvm**.
2. Hvis det er nødvendigt, skal du vælge **Flere handlinger** (...) igen og vælge **Sortér faldende**. Det felt, der bruges til at sortere efter, er med fed skrift og har en gul linje.

   ![video viser valg af Sortér efter og derefter stigende, faldende](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Det er ikke alle visualiseringer, der kan sorteres. Følgende visualiseringer kan f.eks. ikke sorteres: træstruktur, kort (map), kartogram, punkt, måler, kort (card) og vandfald.

## <a name="saving-changes-you-make-to-sort-order"></a>Gem dine ændringer af sorteringsrækkefølgen
Power BI-rapporter bevarer filtre, udsnit, sortering og andre ændringer af datavisning. Hvis du navigerer væk fra en rapport og vender tilbage igen senere, er dine ændringer blevet gemt.  Hvis du vil ændre indstillingerne tilbage til de indstillinger, som rapportens designer oprindeligt valgte, skal du vælge **Nulstil til standard** på den øverste menulinje. 

![fast sortering](media/end-user-change-sort/power-bi-reset.png)

Hvis knappen **Nulstil til standard** er nedtonet, betyder det, at rapportens designer har deaktiveret muligheden for at gemme (bevare) dine egne ændringer.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Sortering ved hjælp af andre kriterier
Der kan nogle gange være behov for at sortere en visualisering ved hjælp af et andet felt (der ikke er inkluderet i visualiseringen) eller andre kriterier.  Det kan f.eks. være, at du vil sortere efter måned (og ikke i alfabetisk rækkefølge), eller at du vil sortere efter hele tal i stedet for cifre (f.eks. 0, 1, 9, 20 og ikke 0, 1, 20, 9).  Designeren af rapporten kan opdatere datasættet for at aktivere denne type sortering. Du kan finde kontaktoplysninger til designeren ved at vælge rapportens navn på overskriftslinjen.

![Rulleliste med kontaktoplysninger](media/end-user-change-sort/power-bi-contact.png)

## <a name="next-steps"></a>Næste trin
Få mere at vide om [Visualiseringer i Power BI-rapporter](end-user-visualizations.md).

[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)
