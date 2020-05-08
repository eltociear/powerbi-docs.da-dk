---
ms.openlocfilehash: cd0696b44e285119193059304c89cfa04c755771
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "71409355"
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

**Spørgsmål:** Der er allerede defineret sikkerhedsroller for min datakilde (f.eks. SQL Server-roller eller SAP BW-roller). Hvad er relationen mellem disse og sikkerhed på rækkeniveau?  
**Svar:** Svaret afhænger af, om du importerer data eller bruger DirectQuery. Hvis du importerer data til dit Power BI-datasæt, bruges sikkerhedsrollerne i din datakilde ikke. I dette tilfælde skal du definere sikkerhed på rækkeniveau for at gennemtvinge sikkerhedsregler for de brugere, der opretter forbindelse i Power BI. Hvis du bruger DirectQuery, bruges sikkerhedsrollerne i din datakilde. Når en bruger åbner en rapport, sender Power BI en forespørgsel til den underliggende datakilde, som anvender sikkerhedsregler for dataene på baggrund af brugerens legitimationsoplysninger.
