---
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: mblythe
ms.openlocfilehash: c658e683e86a899d45728220dee3706a0d617f0f
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284096"
---
## <a name="limitations"></a>Begrænsninger

Her følger en liste over de aktuelle begrænsninger for sikkerhed på rækkeniveau i cloudmodeller.

* Hvis du tidligere har defineret roller og regler i Power BI-tjenesten, skal du genoprette dem i Power BI Desktop.

* Du kan kun definere RLS for de datasæt, der er oprettet ved hjælp af Power BI Desktop. Hvis du vil aktivere RLS for de datasæt, der er oprettet i Excel, skal du først konvertere dine filer til PBIX-filer (Power BI Desktop). [Få mere at vide](../desktop-import-excel-workbooks.md)

* Det er kun ETL- og DirectQuery-forbindelser, der understøttes. Dynamiske forbindelser til Analysis Services skal håndteres i modellen i det lokale miljø.

## <a name="known-issues"></a>Kendte problemer

Der er et kendt problem, hvor der vises en fejlmeddelelse, når du forsøger at publicere en Power BI Desktop-rapport, som allerede er publiceret. Scenariet er som følger.

1. Anna har et datasæt, der er publiceret i Power BI-tjenesten, og hvor RLS er konfigureret.

1. Anna opdaterer rapporten i Power BI Desktop og publicerer den igen.

1. Anna modtager en fejl.

**Midlertidig løsning:** Udgiv Power BI Desktop-filen igen vha. Power BI-tjenesten, indtil problemet er løst. Det kan du gøre ved at vælge **Hent data** > **Filer**.
