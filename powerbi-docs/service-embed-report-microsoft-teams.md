---
title: Integrer rapport ved hjælp af Power BI-fanen til Microsoft Teams
description: Med fanen Power BI til Microsoft Teams kan du nemt integrere interaktive rapporter i kanaler og chats.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 01/31/2020
ms.openlocfilehash: fb4846a777dda4787e1ed0be7de869367a616ea5
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/21/2020
ms.locfileid: "77530481"
---
# <a name="embed-report-with-the-power-bi-tab-for-microsoft-teams"></a>Integrer rapport ved hjælp af Power BI-fanen til Microsoft teams

Med den opdaterede Power BI-fane til Microsoft Teams kan du nemt integrere interaktive rapporter i Microsoft Teams-kanaler og -chats.

Brug Power BI-fanen til Microsoft Teams til at hjælpe dine kolleger med at finde de data, som dit team bruger, og til at diskutere dataene i dine teamkanaler.

## <a name="requirements"></a>Krav

Der er følgende forudsætninger, for at **Power BI-fanen til Microsoft Teams** kan fungere:

- En Power BI Pro-licens, eller at rapporten er indeholdt i en [Power BI Premium-kapacitet (EM- eller P-SKU)](service-premium-what-is.md) med en Power BI-licens.
- Power BI-fanen til Microsoft Teams.
- Brugeren skal logge på Power BI-tjenesten for at aktivere sin Power BI-licens for at kunne bruge rapporten.
- Brugeren skal have tilladelse til at få vist rapporten.

## <a name="embed-your-report"></a>Integrer din rapport
Hvis du vil integrere din rapport i en Microsoft Teams-kanal eller -chat, skal du tilføje den som beskrevet nedenfor.

1. Åbn den ønskede kanal eller chat i Microsoft Teams, og vælg ikonet **+**.

    ![Føj en fane til en kanal eller chat](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

2. Vælg Power BI-fanen.

    ![Liste over Microsoft Teams-faner, der viser Power BI](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

3. Du kan benytte indstillingerne til at vælge en rapport fra et arbejdsområde, fra Delt med mig eller fra en Power BI-app

    ![Indstillinger for Power BI-fanen til Microsoft Teams](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

4. Fanenavnet opdateres automatisk, så det passer til rapportnavnet, men du kan ændre det. 

5. Tryk på **Gem**.

## <a name="supported-reports"></a>Understøttede rapporter

Fanen gør det muligt at integrere følgende rapporter:

- Interaktive og sideinddelte rapporter
- Rapporter i Mit arbejdsområde, i den nye arbejdsområdeoplevelse og i klassiske arbejdsområder
- Rapporter i Power BI-mobilapps


## <a name="grant-access-to-reports"></a>Giv adgang til rapporter

Integrering af en rapport i Microsoft Teams giver ikke automatisk brugerne tilladelse til at få vist rapporten. Du skal [give brugerne tilladelse til at få vist rapporten i Power BI](service-share-dashboards.md). Du kan bruge en Office 365-gruppe for dit team for at gøre det nemmere. 

> [!IMPORTANT]
> Sørg for at gennemse, hvem der kan få vist rapporten, i Power BI-tjenesten, og giv adgang til dem, der er ikke angivet.

Du kan f.eks. sikre, at alle i dit team har adgang til rapporter, som du integrerer, ved at placere dem i et enkelt arbejdsområde i Power BI og give Office 365-gruppen for dit team adgang til arbejdsområdet.

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

- Power BI understøtter ikke de samme oversatte sprog som Microsoft Teams. Derfor ser du muligvis ikke den korrekte oversættelse i den integrerede rapport.
- Power BI-dashboards kan ikke integreres i Power BI-fanen til Microsoft Teams.
- En bruger uden en Power BI-licens eller en tilladelse til rapporten, får vist meddelelsen "Indholdet er ikke tilgængeligt".
- Der kan opstå tekniske problemer, hvis du bruger Internet Explorer 10. <!--You can look at the [browsers support for Power BI](consumer/end-user-browsers.md) and for [Office 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- [URL-filtre](service-url-filters.md) understøttes ikke med Power BI-fanen til Microsoft Teams.
- Den nye Power BI-fane er ikke tilgængelig i nationale clouds. En ældre version, som ikke understøtter den nye arbejdsområdeoplevelse eller rapporter i Power BI-apps, kan være tilgængelig. 
- Når fanen er gemt, kan fanenavnet ikke ændres via indstillingerne for fanen. Du kan bruge funktionen til omdøbning for at ændre navnet.

## <a name="next-steps"></a>Næste trin
- [Del et dashboard med kolleger og andre](service-share-dashboards.md)  
- [Opret og distribuer en app i Power BI](service-create-distribute-apps.md)  
- [Hvad er Power BI Premium?](service-premium-what-is.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
