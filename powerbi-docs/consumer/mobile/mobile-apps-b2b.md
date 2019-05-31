---
title: Få vist Power BI-indhold som en ekstern gæstebruger (Azure AD B2B)
description: Brug Power BI-mobilapps til at få vist indhold, der er delt med dig fra eksterne organisation.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/27/2019
ms.author: mshenhav
ms.openlocfilehash: a15da4349ce97e34c8321909abc862e424b2839c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61338645"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>Få vist Power BI-indhold, der deles med dig fra en ekstern organisation

Powerbi kan integreres med Azure Active Directory business-to-business (Azure AD B2B) til at tillade sikker distribution af Power BI-indhold til gæstebrugere uden for din organisation. Og eksterne gæstebrugere kan bruge Power BI-mobilappen til at få adgang til denne Power BI-indhold, der er delt med vedkommende. 


Gælder for:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-telefon](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tablet](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhones |iPad-tablets |Android-telefoner |Android-tablets |

## <a name="accessing-shared-content"></a>Adgang til delt indhold

**Først skal bruge du en anden person i en ekstern organisation at dele et element med dig.** Når nogen [deler et element med dig](../../service-share-dashboards.md), enten fra den samme organisation eller fra en ekstern organisation, modtager du en mail med et link til det delt element. Følger linket i den mobile enhed, åbner Power BI-mobilappen. Hvis appen genkender, at elementet blev delt fra en ekstern organisation, at appen opretter forbindelse til organisationen med din identitet. Appen indlæser derefter alle elementer, der blev delt med dig fra denne organisation.

![Åbner Powerbi delt element fra mail ](./media/mobile-apps-b2b/mobile-b2b-open-item-email.png)

> [!NOTE]
> Hvis dette er det første element, der er delt med dig som en ekstern gæstebruger, skal du gøre krav på invitationen i en browser. Du kan ikke gøre krav på invitationen i Power BI-appen.

Så længe du har forbindelse til en ekstern organisation, der vises en sort-header i appen. Denne header angiver, at du ikke har forbindelse til din startside organisation. For at oprette forbindelse tilbage til din startside organisation, at afslutte fra gæstetilstand.

![Power BI gæst bruger header](./media/mobile-apps-b2b/mobile-b2b-exit-home.png)

Selvom du skal have et link til Power BI-artefakt til at oprette forbindelse til en ekstern organisation, når du skifter din app, kan du få adgang til alle elementer, der er delt med dig (ikke kun på det element, som du har åbnet fra mailen). Gå til menuen for at få vist alle elementer, du kan få adgang til i den eksterne organisation, og vælg **delt med mig**. Under **Apps** du finder apps, du kan også bruge.

![Power BI-appmenuen som eksterne gæstebruger](./media/mobile-apps-b2b/mobile-b2b-menu.png)

## <a name="limitations"></a>Begrænsninger

- Betinget adgang og andre Intune-politikker, understøttes ikke i Azure AD B2B og i Power BI – mobil. Det betyder, at appen gennemtvinger kun startside organisationens politikker, hvis de findes.
- Push-beskeder, der modtages fra webstedet startside organisation (selv når brugeren er tilsluttet som gæst til en ekstern organisation). Åbne beskeden igen opretter forbindelse mellem appen til brugerens startside organisation websted.
- Hvis brugeren lukker appen, når genåbnes på, at appen opretter automatisk forbindelse til brugerens startside organisation.
- Når du har forbindelse til en ekstern organisation, der har deaktiveret visse handlinger: favorit elementer, databeskeder, kommentarer og deling.
- Offlinedata er ikke tilgængelig, mens forbindelse til en ekstern organisation.
- Hvis du har appen firmaportal, der er installeret på din enhed, skal derefter din enhed være tilmeldt.
