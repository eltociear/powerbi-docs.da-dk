---
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: mblythe
ms.openlocfilehash: b2be085c48b303304d46ea93c272e6a860143c51
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074857"
---
## <a name="limitations"></a>Begrænsninger

Her følger en liste over de aktuelle begrænsninger for sikkerhed på rækkeniveau i cloudmodeller.

* Hvis du tidligere har defineret roller og regler i Power BI-tjenesten, skal du genoprette dem i Power BI Desktop.

* Du kan kun definere RLS for de datasæt, der er oprettet ved hjælp af Power BI Desktop. Hvis du vil aktivere RLS for de datasæt, der er oprettet i Excel, skal du først konvertere dine filer til PBIX-filer (Power BI Desktop). [Få mere at vide](../desktop-import-excel-workbooks.md)

* Det er kun ETL- og DirectQuery-forbindelser, der understøttes. Dynamiske forbindelser til Analysis Services skal håndteres i modellen i det lokale miljø.

* Cortana understøttes ikke med RLS på nuværende tidspunkt.

## <a name="known-issues"></a>Kendte problemer

Der er et kendt problem, hvor der vises en fejlmeddelelse, når du forsøger at publicere en Power BI Desktop-rapport, som allerede er publiceret. Scenariet er som følger.

1. Anna har et datasæt, der er publiceret i Power BI-tjenesten, og hvor RLS er konfigureret.

1. Anna opdaterer rapporten i Power BI Desktop og publicerer den igen.

1. Anna modtager en fejl.

**Midlertidig løsning:** Udgiv Power BI Desktop-filen igen vha. Power BI-tjenesten, indtil problemet er løst. Det kan du gøre ved at vælge **Hent data** > **Filer**.
