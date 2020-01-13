---
title: Køb og tildel Power BI Pro-licenser
description: Få mere at vide om, hvordan du køber og tildeler Power BI Pro-licenser, så dine brugere kan få adgang til indhold og samarbejde med kolleger i Power BI-tjenesten.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: quickstart
ms.date: 12/18/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 01eb30857b0b76f96e7e18115d92fb1d68dbef0c
ms.sourcegitcommit: 02b05932a119527f255e1eacc745a257044e392f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/19/2019
ms.locfileid: "75223840"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Køb og tildel Power BI Pro-brugerlicenser

Power BI Pro er en individuel brugerlicens, der giver brugerne mulighed for at læse og interagere med rapporter og dashboards, som andre brugere har publiceret i Power BI-tjenesten, og for at dele indhold og samarbejde med andre Power BI Pro-brugere. Det er kun brugere med en Power BI Pro-brugerlicens, der kan publicere eller dele indhold med andre brugere eller bruge indhold, der er oprettet af andre brugere, medmindre indholdet er hostet i en Power BI Premium-kapacitet. Du kan finde flere oplysninger under _Sammenligning af Power BI-funktioner_ i afsnittet [Power BI-priser](https://powerbi.microsoft.com/pricing/).

## <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Køb og tildel Power BI Pro-brugerlicenser

Denne artikel indeholder en forklaring på, hvordan du køber Power BI Pro-brugerlicenser via Microsoft 365 Administration. Den indeholder også en forklaring på to indstillinger, som administratorer kan bruge til at tildele disse licenser til individuelle brugere: via Microsoft 365 Administration og via Azure Portal (vælg én indstilling).

### <a name="prerequisites"></a>Forudsætninger

Hvis du vil købe og tildele licenser via Microsoft 365 Administration, skal du være medlem af rollen **[Global administrator eller Faktureringsadministrator](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** i Microsoft 365.

Du skal være ejer af det Azure-abonnement, som Power BI bruger til opslag i Azure Active Directory, for at tildele licenser via Azure Portal.

### <a name="purchase-licenses-in-microsoft-365"></a>Køb licenser i Microsoft 365

Følg disse trin for at købe Power BI Pro-licenser via Microsoft 365 Administration:

1. Åbn [Microsoft 365 Administration](https://portal.office.com/adminportal/home#/homepage).

2. Vælg **Fakturering** i navigationsruden, og vælg derefter **Abonnementer**.

3. Vælg **Tilføj abonnementer** i øverste højre hjørne på siden **Abonnementer**.

4. Find det ønskede abonnement:

    - Vælg **Office 365 Enterprise E5** under **Enterprise Suite**.

    - Vælg **Power BI Pro** under **Andre planer**.

5. Hold musemarkøren over ellipsen **(…)** for det ønskede abonnement, og vælg **Køb nu**.

6. Vælg **Betal en gang om måneden** eller **Betal for et helt år** afhængigt af dine ønsker.

7. Angiv det ønskede antal licenser under **Hvor mange brugere ønsker du?** , og vælg derefter **Gå til kassen** for at gennemføre transaktionen.

8. Kontrollér, at abonnementet nu vises på siden **Abonnementer**.

9. Hvis du vil tilføje flere licenser efter det første køb, skal du vælge **Power BI Pro** på siden **Abonnementer** og derefter vælge **Skift antal licenser**.

### <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Tildel licenser via Microsoft 365 Administration

Du kan finde flere oplysninger om tildeling af licenser i Microsoft 365 Administration under [Tildel licenser til brugere](/office365/admin/manage/assign-licenses-to-users).

For gæstebrugere skal du se [Tildel licenser til brugere på siden Licenser](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page). Før du tildeler Pro-licenser til gæstebrugere, skal du kontakte din Microsoft-kontorepræsentant for at sikre, at du overholder vilkårene i din aftale med Microsoft.

### <a name="assign-licenses-in-the-azure-portal"></a>Tildel licenser via Azure Portal

Benyt følgende fremgangsmåde for at tildele Power BI Pro-licenser til individuelle brugerkonti:

1. Åbn [Azure-portalen](https://portal.azure.com/).

2. Søg efter og vælg **Azure Active Directory**.

3. Under **Azure Active Directory** skal du vælge **Licenser**.

4. Vælg **Alle produkter** under **Licenser**, og vælg derefter **Power BI Pro** for at få vist en liste over brugere med licens.

5. Vælg **Tildel** for at føje en Power BI Pro-licens til en brugerkonto.

## <a name="next-steps"></a>Næste trin

Nu, hvor du har tildelt licenser, kan du få mere at vide om Power BI Pro.

[Power BI-licenser i din organisation](service-admin-licensing-organization.md)

[Find Power BI-brugere, der er logget på](service-admin-access-usage.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
