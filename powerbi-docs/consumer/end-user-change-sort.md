---
title: Rediger, hvordan et diagram sorteres i en rapport
description: Rediger, hvordan et diagram sorteres i en rapport i Power BI
author: mihart
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 06/25/2020
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c70229a37a697fedba54cde1899073f20710f542
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/09/2020
ms.locfileid: "86161761"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Rediger, hvordan et diagram sorteres i en rapport i Power BI

[!INCLUDE[consumer-appliesto-ynnn](../includes/consumer-appliesto-ynnn.md)]


> [!IMPORTANT]
> **Denne artikel er beregnet til Power BI-brugere, der ikke har redigeringstilladelser til rapporten eller datasættet, og som kun arbejder i onlineversionen af Power BI (Power BI-tjenesten). Hvis du er rapport*designer*eller *administrator* eller *ejer*, indeholder denne artikel muligvis ikke alle de oplysninger, du har brug for. Du kan få mere at vide under [Sorter efter kolonne i Power BI Desktop](../create-reports/desktop-sort-by-column.md)** .

I Power BI-tjenesten kan du ændre, hvordan en visualisering ser ud, ved at sortere den efter forskellige datafelter. Hvis du ændrer, hvordan du sorterer en visualisering, kan du fremhæve de oplysninger, du vil formidle. Uanset om du bruger numeriske data (f.eks. salgstal) eller tekstdata (f.eks. navne på stater), kan du sortere visualiseringerne efter behov. Power BI indeholder mange sorteringsmuligheder og genvejsmenuer, som du kan bruge. 

Visuals i et dashboard kan ikke sorteres. Men i en Power BI-rapport kan du sortere de fleste visualiseringer efter ét felt, og nogle gange to felter, ad gangen. Sortering er ikke tilgængelig for visse typer visualiseringer: trækort, målere, kort osv. 

## <a name="get-started"></a>Kom i gang

Du kommer i gang ved at åbne en rapport, som er blevet delt med dig. Vælg en visualisering (der kan sorteres), og vælg **Flere handlinger** (...).  Der er tre sorteringsindstillinger: **Sortér faldende**, **Sortér stigende**, og **Sortér efter**. 
    

![søjlediagram sorteret alpha af X-akse](media/end-user-change-sort/power-bi-more-actions.png)

### <a name="sort-alphabetically-or-numerically"></a>Sortér alfabetisk eller numerisk

Visuals kan sorteres alfabetisk efter tekstnavnene på kategorierne i visual'et eller efter de numeriske værdier for hver kategori. Dette diagram er f.eks. sorteret alfabetisk efter kategorien **Store Name** på X-aksen.

![søjlediagram sorteret alpha af X-akse](media/end-user-change-sort/powerbi-sort-category.png)

Det er nemt at ændre sorteringen fra en kategori (gem navn) til en værdi (salg pr. kvadratfod) i stedet. Vælg **Flere handlinger** (...), og vælg **Sortér efter**. Vælg en numerisk værdi, der bruges i visual'et.  I dette eksempel har vi valgt **Sales Per Sq Ft**.

![Skærmbillede, der viser, hvordan du vælger Sortér efter og derefter en værdi](media/end-user-change-sort/power-bi-sort-value.png)

Hvis det er nødvendigt, kan du ændre sorteringsrækkefølgen mellem stigende og faldende.  Vælg **Flere handlinger** (...) igen, og vælg **Sortér faldende** eller **Sortér stigende**. Det felt, der bruges til at sortere efter, er med fed skrift og har en gul linje.

   ![video viser valg af Sortér efter og derefter stigende, faldende](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Det er ikke alle visualiseringer, der kan sorteres. Følgende visualiseringer kan f.eks. ikke sorteres: træstruktur, kort (map), kartogram, punkt, måler, kort (card) og vandfald.

## <a name="sorting-by-multiple-columns"></a>Sortering efter flere kolonner
Dataene i denne tabel er sorteret efter **Number of customers**.  Det ses på den lille pil under ordet *Number*. Pilen, der peger nedad, hvilket betyder, at kolonnen er sorteret i *faldende* rækkefølge.

![skærmbillede, der viser den første kolonne, som bruges til sortering](media/end-user-change-sort/power-bi-sort-first.png)


Hvis du vil føje flere kolonner til sorteringsrækkefølgen, skal du trykke på Skift og klikke på den kolonneoverskrift, du vil tilføje som den næste i sorteringsrækkefølgen. Hvis du f. eks. klikker på **Number of customers** og trykker på Skift og klikker på **Total revenue**, sorteres tabellen først efter kunder og derefter efter omsætning. Den røde kontur viser områder, hvor sorteringsrækkefølgen er ændret.

![skærmbillede, der viser den anden kolonne, som bruges til sortering](media/end-user-change-sort/power-bi-sort-second.png)

Hvis du trykker på Skift og klikker på den samme kolonne igen, ændres sorteringsretningen for den pågældende kolonne. Hvis du trykker på Skift og klikker på en kolonne, som du tidligere har føjet til sorteringsrækkefølgen, vises den pågældende kolonne bagest i sorteringsrækkefølgen.


## <a name="saving-changes-you-make-to-sort-order"></a>Gem dine ændringer af sorteringsrækkefølgen
Filtre, udsnitsværktøjer, sortering og andre ændringer af datavisningen, du foretager, gemmes i Power BI-rapporter – selvom du arbejder i [Læsevisning](end-user-reading-view.md). Det betyder, at hvis du navigerer væk fra en rapport og vender tilbage igen senere, er dine sorteringsændringer blevet gemt.  Hvis du vil ændre indstillingerne tilbage til de indstillinger, som rapportens *designer* oprindeligt valgte, skal du vælge **Nulstil til standard** på den øverste menulinje. 

![fast sortering](media/end-user-change-sort/power-bi-reset.png)

Hvis knappen **Nulstil til standard** er nedtonet, betyder det, at rapportens *designer* har deaktiveret muligheden for at gemme (bevare) dine egne ændringer.

<a name="other"></a>
## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

### <a name="sorting-using-other-criteria"></a>Sortering ved hjælp af andre kriterier
Der kan nogle gange være behov for at sortere en visualisering ved hjælp af et andet felt (der ikke er inkluderet i visualiseringen) eller andre kriterier.  Det kan f.eks. være, at du vil sortere efter måned i sekventiel rækkefølge (og ikke i alfabetisk rækkefølge), eller at du vil sortere efter hele tal i stedet for cifre (f.eks. 0, 1, 9, 20 og ikke 0, 1, 20, 9).  

Kun den person, der har designet rapporten, kan foretage disse ændringer for dig. Du kan finde kontaktoplysninger for *designeren* ved at vælge rapportens navn på overskriftslinjen.

![Rulleliste med kontaktoplysninger](media/end-user-change-sort/power-bi-contact.png)

Hvis du er *designer* og har redigeringstilladelser til indholdet, kan du læse [Sortér efter kolonne i Power BI Desktop](../create-reports/desktop-sort-by-column.md) for at få mere at vide om, hvordan du opdaterer datasættet og aktiverer denne type sortering.

## <a name="next-steps"></a>Næste trin
Få mere at vide om [Visualiseringer i Power BI-rapporter](end-user-visualizations.md).

[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)
