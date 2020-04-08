---
ms.openlocfilehash: 26f4b82301915524b65d9d2d6b39d61b54ed0321
ms.sourcegitcommit: 8eeb784fd46321680367ac913ef976aeedaa7766
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/03/2020
ms.locfileid: "80621581"
---
Tjeneste principalen er en godkendelsesmetode, der kan bruges til at lade et Microsoft Azure AD-program få adgang indhold og API'er i Power BI-tjenesten.

Når du opretter en Azure Active Directory-app, oprettes der et [tjenesteprincipalobjekt](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Tjenesteprincipalobjektet, der også blot kaldes *tjenesteprincipal*, gør det muligt for Microsoft Azure AD at godkende din app. Når appen er godkendt, kan den få adgang til Microsoft Azure AD-lejerressourcer.

For at kunne godkende skal tjenesteprincipalen bruge Microsoft Azure AD-appens *program-id* og et af følgende:
* Programhemmelighed
* Certifikat