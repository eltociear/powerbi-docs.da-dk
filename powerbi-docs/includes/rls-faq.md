---
ms.openlocfilehash: 0592cb7ef076f8094aca565d955cc238b2181068
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560975"
---
## <a name="faq"></a>Ofte stillede spørgsmål
**Spørgsmål:** Hvad hvis jeg på et tidligere tidspunkt har oprettet roller og regler for et datasæt i Power BI-tjenesten? Vil de stadig virke, hvis jeg ikke gør noget?  
**Svar:** Nej, visualiseringer vil ikke blive gengivet korrekt. Du skal genoprette rollerne og reglerne i Power BI Desktop og derefter publicere dem til Power BI-tjenesten.

**Spørgsmål:** Kan jeg oprette disse roller til Analysis Services-datakilder?  
**Svar:** Det kan du, hvis du importerede dataene til Power BI Desktop. Hvis bruger en dynamisk forbindelse, kan du ikke konfigurere RLS i Power BI-tjenesten. Dette defineres i Analysis Services-modellen i det lokale miljø.

**Spørgsmål:** Kan jeg bruge sikkerhed på rækkeniveau til at begrænse, hvilke kolonner eller målinger brugerne har adgang til?  
**Svar:** Nej, hvis en bruger har adgang til en bestemt række data, kan vedkommende se alle kolonner med data for den række.

**Spørgsmål:** Vil sikkerhed på rækkeniveau lade mig skjule detaljerede data, men samtidig give adgang til de data, der er opsummeret i visualiseringer?  
**Svar:** Nej. Du beskytter individuelle rækker, men brugerne kan altid se enten detaljer eller de opsummerede data.

