---
title: Eksportér rapporter til PDF
description: Få mere at vide om, hvordan du eksporterer en Power BI-rapport til PDF.
author: mihart
manager: kvivek
ms.custom: ''
ms.reviewer: cmfinlan
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: c18257f1f4e4e3f325c8d4d895e3b6abf88e900c
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794984"
---
# <a name="export-reports-from-power-bi-to-pdf"></a>Eksportér rapporter fra Power BI til PDF
Med Power BI kan du publicere din rapport i PDF-format og nemt oprette et dokument ud fra din Power BI-rapport. Når du **eksporterer til PDF**, bliver hver side i Power BI-rapporten en enkelt side i PDF-dokumentet.

## <a name="how-to-export-your-power-bi-report-to-pdf"></a>Sådan eksporterer du en Power BI-rapport til PDF
Vælg en rapport for at vise den på lærredet i Power BI-tjenesten. Du kan også vælge en rapport fra din startside, dine programmer eller en hvilken som helst anden sektion i navigationsruden til venstre.

1. Vælg **Fil** > **Eksportér til PDF** på menulinjen.

    ![Vælg Fil på menulinjen – pil, der peger på Eksportér til PDF](media/end-user-pdf/power-bi-export-pdf.png)

    Der vises en statuslinje i øverste højre hjørne. Det kan tage nogle få minutter at eksportere, og du kan fortsætte med at arbejde i Power BI, mens rapporten eksporteres.

    ![Meddelelse om eksportstatus](media/end-user-pdf/power-bi-export-message.png)

    Når dette er fuldført, ændres meddelelsesbanneret for at give dig besked om, at Power BI-tjenesten er færdig med eksporten.

2. Derefter finder du din fil der, hvor din browser viser downloadede filer. På det følgende billede vises det som et downloadbanner i bunden af browservinduet.

    ![Placering af den downloadede fil](media/end-user-pdf/power-bi-save-file.png)

Så nemt er det. Du kan downloade filen og åbne den med en hvilken som helst PDF-fremviser, f.eks. den der er tilgængelig i Microsoft Edge.


## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Der er nogle få overvejelser og begrænsninger, du skal huske på, når du arbejder med funktionen **Eksportér til PDF**.

- Interaktivitet i sessionen, såsom fremhævning og filtrering, detailudledning osv., understøttes endnu ikke under eksport til PDF. Den eksporterede PDF viser de oprindelige visualiseringer, sådan som de blev gemt i rapporten. Hvis du har anvendt filtre og udsnit og gerne vil bevare disse i eksporten, skal du gemme rapporten og derefter foretage eksporten.

* **R-visualiseringer** understøttes ikke i øjeblikket. I PDF'en vil disse visualiseringer være tomme, og der vises en fejlmeddelelse.  

* **Brugerdefinerede visualiseringer**, der er blevet **certificeret**, understøttes. Hvis du vil have flere oplysninger om certificerede brugerdefinerede visualiseringer, herunder hvordan du får en brugerdefineret visualisering certificeret, skal du se [Sådan får du en brugerdefineret visualisering certificeret](../power-bi-custom-visuals-certified.md). Brugerdefinerede visualiseringer, som ikke er certificeret, understøttes ikke. De vises med en fejlmeddelelse i PDF'en.   

* Rapporter med mere end 30 rapportsider kan ikke eksporteres i øjeblikket.

* Processen med at eksportere rapporten til PDF kan tage nogle minutter at fuldføre, så vær tålmodig. Faktorer, som kan påvirke den tid, det kræver, omfatter rapportens struktur og den aktuelle belastning på Power BI-tjenesten.

* Hvis menuelementet **Eksportér til PDF** ikke er tilgængeligt i Power BI-tjenesten, er det sandsynligvis fordi, din lejeradministrator har deaktiveret funktionen. Kontakt din lejeradministrator for at få flere oplysninger.

* Baggrundsbilleder beskæres med diagrammets omgivende område. Det anbefales, at du fjerner baggrundsbilleder, før du eksporterer til PDF.

* Rapporter, der ejes af en bruger uden for dit Power BI-lejerdomæne (f.eks. en rapport, der ejes af nogen uden for din organisation, og som er delt med dig), kan ikke publiceres til PDF.

* Hvis du deler et dashboard med en person uden for din organisation (og dermed en bruger, der ikke er i din Power BI-lejer), kan denne bruger ikke eksportere det delte dashboards tilknyttede rapporter til PDF. Hvis du f.eks. er aaron@contoso.com, kan du dele med cassie@cohowinery.com. Men cassie@cohowinery.com kan ikke eksportere de tilknyttede rapporter til PDF.

* I Power BI-tjenesten anvendes din Power BI-sprogindstilling som sprog i forbindelse med PDF-eksporten. Hvis du vil se eller angive dine sprogindstillinger, skal du vælge tandhjulsikonet > **Indstillinger** > **Generelt** > **Sprog**.

## <a name="next-steps"></a>Næste trin
[Udskriv en rapport](end-user-print.md)