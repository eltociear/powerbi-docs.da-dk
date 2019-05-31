---
title: Find Power BI-brugere, der er logget på
description: Hvis du er administrator af lejere, og du vil se, hvem der har logget på Power BI, kan du bruge rapporter om adgang og forbrug af Azure Active Directory til at skabe synlighed.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e513607dd89aee15f10145cf62bd461621cc12c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906715"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Find Power BI-brugere, der er logget på

Hvis du er administrator af lejere, og du vil se, hvem der har logget på Power BI, Brug den [Azure Active Directory-adgang og forbrug rapporter](/azure/active-directory/reports-monitoring/concept-sign-ins) til at skabe synlighed.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Den **logonaktivitet** rapport indeholder nyttige oplysninger, men det ikke identificere typen licens hver bruger har. Brug Microsoft 365 Administration til at få vist licenser.

## <a name="requirements"></a>Krav

Alle brugere (herunder personer, der ikke er administratorer) kan se en rapport over deres egne logon, men du skal opfylde følgende krav for at få vist en rapport for alle brugere.

* Din lejer skal have en Azure Active Directory Premium-licens, der er knyttet til den.

* Du skal være i en af følgende roller: Global administrator, Sikkerhedsadministrator eller Sikkerhedslæser.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Brug Azure Portal til at få vist logon

Følg disse trin for at få vist logonaktivitet.

1. På **Azure Portal** skal du vælge **Azure Active Directory**.

1. Under **Overvågning** skal du vælge **Logon**.
   
    ![Skærmbillede af Brugergrænsefladen i Azure med Azure Active Directory og logonaktivitet indstillinger fremhævet.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Filtrer programmet efter enten **Microsoft Power BI** eller **Power BI Gateway**, og vælg **Anvend**.

    **Microsoft Power BI** filtre til logonaktivitet relateret til tjenesten, mens **Power BI Gateway** filtre til logonaktivitet specifikke for datagatewayen i det lokale miljø.
   
    ![Skærmbillede af filteret login med feltet programmer, der er fremhævet.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Eksportér dataene

Du kan [hente en rapport, der logon](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) i en af to formater: en CSV-fil eller en JSON-fil.

![Skærmbillede af knappen Hent.](media/service-admin-access-usage/download-sign-in-data-csv.png)

Øverst i den **logonaktivitet** rapporten, vælge **Download** , og vælg derefter en af følgende indstillinger:

* **CSV** at downloade en CSV-fil for de data, der i øjeblikket er filtreret.

* **JSON** at downloade en JSON-fil for de data, der i øjeblikket er filtreret.

## <a name="data-retention"></a>Dataopbevaring

Relaterede logondata er tilgængelige i op til 30 dage. Du kan finde flere oplysninger, i [politikker til opbevaring af Azure Active Directory-rapport](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Næste trin

[Brug af overvågning i din organisation](service-admin-auditing.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)