---
title: Planlægning af en rapport i Power BI Report Builder
description: Med Power BI Paginated Report Builder kan du oprette mange slags sideinddelte rapporter. Hvis du vil oprette en nyttig rapport, der er let at forstå, er det en god idé at planlægge den først.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fd4a318d7a61f6f2298de6b9d5d23ad2ae063d28
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840504"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>Planlægning af en rapport i Power BI Report Builder
  Med Power BI Paginated Report Builder kan du oprette mange slags sideinddelte rapporter. Du kan f.eks. oprette rapporter, der viser en oversigt over eller detaljerede salgsdata, marketing- og salgstendenser, driftsrapporter eller dashboards. Du kan også oprette rapporter, der drager fordel af formateret tekst, f.eks. til salgsordrer, produktkataloger eller standardbreve. Alle disse rapporter oprettes ved hjælp af forskellige kombinationer af de samme grundlæggende byggesten i Report Builder. Hvis du vil oprette en nyttig rapport, der er let at forstå, er det en god idé at planlægge den først. Her er nogle ting, det kan være en god idé at overveje, før du går i gang:  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>I hvilket format skal rapporten vises?
  
Du kan gengive rapporter online i en browser, f.eks. på Power BI-portalen, eller eksportere dem til andre formater, f.eks. PDF, Word eller Excel. Det er vigtigt at overveje den endelige udformning af din rapport, da alle funktioner ikke er tilgængelige i alle eksportformater. 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>I hvilken struktur vil du præsentere dataene?
  
Du kan vælge mellem tabel, matrix (svarer til en rapport med tværgående faner eller pivottabeller), diagram, formaliafrie strukturer eller en kombination af disse til at præsentere data. Du kan finde flere oplysninger i [Tabeller, matrixer og lister i Power BI Report Builder](report-builder-tables-matrices-lists.md).  
  
## <a name="how-do-you-want-your-report-to-look"></a>Hvordan skal din rapport se ud?
  
Report Builder indeholder en masse rapportelementer, som du kan føje til din rapport for at gøre den nemmere at læse, fremhæve vigtige oplysninger, hjælpe din målgruppe med at navigere i rapporten osv. Det spiller en vigtig rolle at vide, hvordan rapporten skal vises, da det afgør, om du har brug for rapportelementer såsom tekstfelter, billeder, rektangler og linjer. Det kan også være en idé at vise eller skjule elementer, tilføje et dokumentkort, inkludere rapporter med detaljeadgang eller underrapporter eller linke til andre rapporter.   
  
## <a name="should-the-data-be-filtered"></a>Skal dataene filtreres?
  
Du vil muligvis indsnævre omfanget af rapporten for bestemte brugere eller lokationer eller for en bestemt tidsperiode. Hvis du vil filtrere rapportdataene, skal du bruge parametre til at hente og kun vise de ønskede data. Du kan finde flere oplysninger i [Rapportparametre i Power BI Report Builder](paginated-reports-parameters.md).  
  
## <a name="do-you-need-to-create-calculations"></a>Har du brug at oprette beregninger? 
  
     Sometimes, your data source and datasets do not contain the exact fields that you need for your report. In that situation, you might have to create your own calculated fields. For example, you might want to multiply the price per unit times the quantity to get a line item sales amount. Expressions are also used to provide conditional formatting and other advanced features. For more information, see [Expressions in Power BI Report Builder](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>Vil du skjule rapportelementer indledningsvist?
  
Overvej, om du vil skjule rapportelementer, herunder dataområder, grupper og kolonner, når rapporten køres første gang. Du kan f.eks. indledningsvist præsentere en oversigtstabel og derefter zoome ind på detaljeniveauet i de detaljerede data. 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>Hvordan vil du levere din rapport?  
  
     You can save your report to your local computer and continue to work on it, or run it locally for your own information. However, to share your report with others, you need to save the report to Power BI. Saving it to Power BI lets others run it whenever they want to. Alternatively, you can set up a subscription and e-mail delivery of the report to other individuals. You can have the report delivered in a specific export format if you prefer. 
  
## <a name="next-steps"></a>Næste trin

- [Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)
