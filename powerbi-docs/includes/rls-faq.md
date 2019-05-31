---
ms.openlocfilehash: b05b5b0b5212f39b9b47cb63e2fc8522fff2f8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61193683"
---
## <a name="faq"></a>Ofte stillede spørgsmål
**Spørgsmål:** Hvad nu hvis jeg tidligere har oprettet roller og regler for et datasæt i Power BI-tjenesten? Vil de stadig virke, hvis jeg ikke gør noget?  
**Svar:** Nej. Visualiseringer gengives ikke korrekt. Du skal genoprette rollerne og reglerne i Power BI Desktop og derefter publicere dem til Power BI-tjenesten.

**Spørgsmål:** Kan jeg oprette disse roller til Analysis Services-datakilder?  
**Svar:** Det kan du, hvis du importerede dataene til Power BI Desktop. Hvis bruger en dynamisk forbindelse, kan du ikke konfigurere RLS i Power BI-tjenesten. Dette defineres i Analysis Services-modellen i det lokale miljø.

**Spørgsmål:** Kan jeg bruge sikkerhed på rækkeniveau til at begrænse, hvilke kolonner eller målinger brugerne har adgang til?  
**Svar:** Nej. Hvis en bruger har adgang til en bestemt række data, kan vedkommende se alle kolonner med data for den række.

**Spørgsmål:** Vil sikkerhed på rækkeniveau lade mig skjule detaljerede data, men samtidig give adgang til de data, der er opsummeret i visualiseringer?  
**Svar:** Nej. Du beskytter individuelle rækker, men brugerne kan altid se enten detaljer eller de opsummerede data.

