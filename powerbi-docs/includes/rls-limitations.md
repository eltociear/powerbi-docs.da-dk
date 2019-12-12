---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: davidi
ms.openlocfilehash: 6d1a239954a64da1c92cc68b56912e6f4ab67228
ms.sourcegitcommit: 9a265d8117cc202f5f700286b5ff42a631aacdb4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2019
ms.locfileid: "74882808"
---
## <a name="limitations"></a>Begrænsninger

Her følger en liste over de aktuelle begrænsninger for sikkerhed på rækkeniveau i cloudmodeller.

* Hvis du tidligere har defineret roller og regler i Power BI-tjenesten, skal du genoprette dem i Power BI Desktop.

* Du kan kun definere RLS for de datasæt, der er oprettet ved hjælp af Power BI Desktop. Hvis du vil aktivere RLS for de datasæt, der er oprettet i Excel, skal du først konvertere dine filer til PBIX-filer (Power BI Desktop). [Få mere at vide](../desktop-import-excel-workbooks.md)

* Det er kun Import- og DirectQuery-forbindelser, der understøttes. Dynamiske forbindelser til Analysis Services skal håndteres i modellen i det lokale miljø.

## <a name="known-issues"></a>Kendte problemer

Der er et kendt problem, hvor der vises en fejlmeddelelse, når du forsøger at publicere en Power BI Desktop-rapport, som allerede er publiceret. Scenariet er som følger.

1. Anna har et datasæt, der er publiceret i Power BI-tjenesten, og hvor RLS er konfigureret.

1. Anna opdaterer rapporten i Power BI Desktop og publicerer den igen.

1. Anna modtager en fejl.

**Midlertidig løsning:** Udgiv Power BI Desktop-filen igen vha. Power BI-tjenesten, indtil problemet er løst. Det kan du gøre ved at vælge **Hent data** > **Filer**.
