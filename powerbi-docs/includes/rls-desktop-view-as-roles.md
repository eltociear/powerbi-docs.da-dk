---
ms.openlocfilehash: 8dc488a47ac2b5b4e7980b7404b2722b1120b6ab
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464350"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Valider rollerne i Power BI Desktop
Når du har oprettet dine roller, kan du teste resultaterne af rollerne i Power BI Desktop.

1. Vælg **Vis som roller** på fanen **Udformning**. 

    ![Vælg Vis som roller](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    Vinduet **Vis som roller** vises, hvor du kan få vist de roller, som du har oprettet.

    ![Vinduet Vis som roller](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Vælg en rolle, du har oprettet, og vælg derefter **OK** for at anvende rollen. 

   Rapporterne gengiver de data, der er relevante for rollen.

4. Du kan også vælge **Anden bruger** og angive en specifik bruger. 

    ![Vælg en anden bruger](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

   Det er bedst at angive brugerens hovednavn, da det er det navn, som Power BI-tjenesten og Power BI-rapportserver bruger.

   I Power BI Desktop viser **Anden bruger** kun forskellige resultater, hvis du bruger dynamisk sikkerhed baseret på dine DAX-udtryk. 

5. Vælg **OK**. 

   Rapporten gengives baseret på det, som brugeren kan se.



