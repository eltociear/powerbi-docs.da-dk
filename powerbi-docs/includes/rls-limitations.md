---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 01/31/2020
ms.author: davidi
ms.openlocfilehash: 912b0213c328c623e7881f7f30fe7d67f6d889b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83274625"
---
## <a name="limitations"></a>Begrænsninger

De aktuelle begrænsninger for sikkerhed på rækkeniveau i cloudmodeller er følgende:

* Hvis du tidligere har defineret roller og regler i Power BI-tjenesten, skal du genoprette dem i Power BI Desktop.

* Du kan kun definere RLS for de datasæt, der er oprettet ved hjælp af Power BI Desktop. Hvis du vil aktivere RLS for de datasæt, der er oprettet i Excel, skal du først konvertere dine filer til PBIX-filer (Power BI Desktop). [Få mere at vide](../connect-data/desktop-import-excel-workbooks.md).

* Det er kun Import- og DirectQuery-forbindelser, der understøttes. Dynamiske forbindelser til Analysis Services skal håndteres i modellen i det lokale miljø.

## <a name="known-issues"></a>Kendte problemer

Der er et kendt problem, hvor der vises en fejlmeddelelse, når du forsøger at publicere en Power BI Desktop-rapport, som allerede er publiceret. Scenariet er som følger:

1. Anna har et datasæt, der er publiceret i Power BI-tjenesten, og hvor RLS er konfigureret.

1. Anna opdaterer rapporten i Power BI Desktop og publicerer den igen.

1. Anna modtager en fejl.

**Midlertidig løsning:** Publicer Power BI Desktop-filen igen vha. Power BI-tjenesten, indtil problemet er løst. Det kan du gøre ved at vælge **Hent data** > **Filer**.

