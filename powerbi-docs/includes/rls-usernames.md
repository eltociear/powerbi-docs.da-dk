---
ms.openlocfilehash: 3e89344ef1298864b485f465b28c56397a7e1511
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "61193684"
---
## <a name="using-the-username-or-userprincipalname-dax-function"></a>Brug af DAX-funktionen username() eller userprincipalname()
Du kan benytte DAX-funktionerne *username()* eller *userprincipalname()* i dit datasæt. Du kan bruge dem i udtryk i Power BI Desktop. Når du publicerer din model, bruges det i Power BI-tjenesten.

I Power BI Desktop returnerer *username()* en bruger i formatet *DOMÆNE\bruger*, og *userprincipalname()* returnerer en bruger i formatet <em>user@contoso.com</em>.

I Power BI-tjenesten returnerer både *username()* og *userprincipalname()* brugerens hovednavn (UPN). Dette ligner en mailadresse.

