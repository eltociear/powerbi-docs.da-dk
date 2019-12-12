---
title: Rediger, hvordan et diagram sorteres i en rapport
description: Rediger, hvordan et diagram sorteres i en rapport i Power BI
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/01/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: fdd43320fec2b96aa708cb5bb1a21e269a117d2a
ms.sourcegitcommit: e492895259aa39960063f9b337a144a60c20125a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/05/2019
ms.locfileid: "74830655"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Rediger, hvordan et diagram sorteres i en rapport i Power BI

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]


> [!IMPORTANT]
> **Denne artikel henvender sig til Power BI brugere, der ikke har redigeringstilladelser til rapporten eller datasættet. Hvis du vil have mere detaljerede instruktioner til sortering, skal du læse [Sortér efter kolonne i Power BI Desktop](../desktop-sort-by-column.md)** .

I Power BI-tjenesten kan du ændre, hvordan en visualisering ser ud, ved at sortere den efter forskellige datafelter. Hvis du ændrer, hvordan du sorterer en visualisering, kan du fremhæve de oplysninger, du vil formidle.

Visuals på et dashboard kan ikke sorteres, men i en Power BI-rapport kan du sortere de fleste visualiseringer 

Uanset om du bruger numeriske data (f.eks. salgstal) eller tekstdata (f.eks. navne på stater), kan du sortere visualiseringerne efter behov. Power BI indeholder mange sorteringsmuligheder og genvejsmenuer, som du kan bruge. 

## <a name="get-started"></a>Kom i gang

For at komme i gang skal du vælge et visual og vælge **Flere handlinger** (...).  Der er tre sorteringsindstillinger: **Sortér faldende**, **Sortér stigende**, og **Sortér efter**. 
    

![søjlediagram sorteret alpha af X-akse](media/end-user-change-sort/power-bi-more-actions.png)

### <a name="sort-alphabetically-or-numerically"></a>Sortér alfabetisk eller numerisk

Visuals kan sorteres alfabetisk efter navnene på kategorierne i visual'et eller efter de numeriske værdier for hver kategori. Dette diagram er f.eks. sorteret alfabetisk efter kategorien **Store Name** på X-aksen.

![søjlediagram sorteret alpha af X-akse](media/end-user-change-sort/powerbi-sort-category.png)

Det er nemt at ændre sorteringen fra en kategori (gem navn) til en værdi (salg pr. kvadratfod) i stedet. Vælg **Flere handlinger** (...), og vælg **Sortér efter**. Vælg en numerisk værdi, der bruges i visual'et.  I dette eksempel har vi valgt **Sales Per Sq Ft**.

![Skærmbillede, der viser, hvordan du vælger Sortér efter og derefter en værdi](media/end-user-change-sort/power-bi-sort-value.png)

Hvis det er nødvendigt, kan du ændre sorteringsrækkefølgen mellem stigende og faldende.  Vælg **Flere handlinger** (...) igen, og vælg **Sortér faldende** eller **Sortér stigende**. Det felt, der bruges til at sortere efter, er med fed skrift og har en gul linje.

   ![video viser valg af Sortér efter og derefter stigende, faldende](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Det er ikke alle visualiseringer, der kan sorteres. Følgende visualiseringer kan f.eks. ikke sorteres: træstruktur, kort (map), kartogram, punkt, måler, kort (card) og vandfald.

## <a name="saving-changes-you-make-to-sort-order"></a>Gem dine ændringer af sorteringsrækkefølgen
Power BI-rapporter bevarer filtre, udsnit, sortering og andre ændringer af datavisning. Hvis du navigerer væk fra en rapport og vender tilbage igen senere, er dine sorteringsændringer blevet gemt.  Hvis du vil ændre indstillingerne tilbage til de indstillinger, som rapportens designer oprindeligt valgte, skal du vælge **Nulstil til standard** på den øverste menulinje. 

![fast sortering](media/end-user-change-sort/power-bi-reset.png)

Hvis knappen **Nulstil til standard** er nedtonet, betyder det, at rapportens *designer* har deaktiveret muligheden for at gemme (bevare) dine egne ændringer.

<a name="other"></a>
## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

### <a name="sorting-using-other-criteria"></a>Sortering ved hjælp af andre kriterier
Der kan nogle gange være behov for at sortere en visualisering ved hjælp af et andet felt (der ikke er inkluderet i visualiseringen) eller andre kriterier.  Det kan f.eks. være, at du vil sortere efter måned i sekventiel rækkefølge (og ikke i alfabetisk rækkefølge), eller at du vil sortere efter hele tal i stedet for cifre (f.eks. 0, 1, 9, 20 og ikke 0, 1, 20, 9).  Kun den person, der har designet rapporten, kan foretage disse ændringer for dig. Du kan finde kontaktoplysninger for *designeren* ved at vælge rapportens navn på overskriftslinjen.

![Rulleliste med kontaktoplysninger](media/end-user-change-sort/power-bi-contact.png)

## <a name="next-steps"></a>Næste trin
Få mere at vide om [Visualiseringer i Power BI-rapporter](end-user-visualizations.md).

[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)
