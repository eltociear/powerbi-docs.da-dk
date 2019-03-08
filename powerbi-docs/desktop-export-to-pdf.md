---
title: Eksportér dine rapporter til PDF-format fra Power BI Desktop
description: Eksportér nemt til PDF-format fra Power BI Desktop, og udskriv derefter PDF-rapporterne
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/28/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 2f64973650edd951a9a780090426afba3e8471f5
ms.sourcegitcommit: 883a58f63e4978770db8bb1cc4630e7ff9caea9a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/07/2019
ms.locfileid: "57555579"
---
# <a name="export-reports-to-pdf-from-power-bi-desktop"></a>Eksportér rapporter til PDF-format fra Power BI Desktop
I **Power BI Desktop** eller Power BI-tjenesten kan du eksportere rapporter til en PDF-fil, så det er nemt at dele eller udskrive dine rapporter fra PDF.

![Eksportér til PDF](media/desktop-export-to-pdf/export-to-pdf_01.png)

Processen med at eksportere din rapport fra **Power BI Desktop** til en PDF-fil, så du kan udskrive PDF-filen eller dele PDF-dokumentet med andre, er helt enkel. Du skal blot vælge **Fil > Eksportér til PDF** fra Power BI Desktop.

Processen **Eksportér til PDF** vil eksportere alle *synlige* sider i rapporten, hvor hver rapportside eksporteres til en enkelt side i PDF-filen. De rapportsider, der ikke er synlige, f.eks. værktøjstip eller skjulte sider, eksporteres ikke til PDF-filen. 

![Eksport til PDF i gang](media/desktop-export-to-pdf/export-to-pdf_02.png)

Når du vælger **Fil > Eksportér til PDF**, bliver eksporten igangsat, og der vises en dialogboks med en meddelelse om, at eksporten er i gang. Dialogboksen forbliver på skærmen, indtil eksporten er fuldført. Under eksporten vil al interaktion med rapporten være deaktiveret. Den eneste måde at interagere med rapporten på, er at vente, indtil eksporten er fuldført, eller du kan annullere eksporten. 

Når eksporten er fuldført, indlæses PDF-filen i PDF-fremviseren på computeren. 

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
Der er et par ting, du skal være opmærksom på i forbindelse med funktionen **Eksportér til PDF**:

* Funktionen eksporterer brugerdefinerede visualiseringen, men den eksporterer *ikke* en eventuel baggrund, du har anvendt i rapporten.

Da baggrunden ikke eksporteres til PDF-filen, skal du være ekstra opmærksom på de rapporter, hvor der bruges en mørk baggrund. Hvis teksten i din rapport er lys eller hvid, så den kan læses på den mørke baggrund, vil det være svært at læse den i den eksporterede PDF-fil, da baggrunden ikke eksporteres sammen med resten af rapporten. 



## <a name="next-steps"></a>Næste trin
Der findes alle mulige interessante visualiseringer og funktioner i **Power BI Desktop**. Du kan finde flere oplysninger i følgende ressourcer:

* [Brug visualiseringer til at forbedre Power BI-rapporter](desktop-visual-elements-for-reports.md)
* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)


