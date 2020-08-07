---
title: Samarbejd i Microsoft Teams med Power BI
description: Du kan nemt dele og samarbejde om interaktivt Power BI-indhold i Microsoft Teams-kanaler og -chats.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 07/31/2020
ms.openlocfilehash: 01e5b470e0beb189d64da18785a17e771bcaf59b
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478032"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Samarbejd i Microsoft Teams med Power BI

I takt med at en distribueret og ekstern arbejdsstyrke bliver normen, anvender stadig flere organisationer Microsoft Teams til at holde medarbejderne opdateret. Power BI giver flere muligheder for at dele og samarbejde om interaktivt Power BI-indhold i Microsoft Teams-kanaler og -chats. 

- Med den opdaterede **Power BI**-fane til Microsoft Teams kan du [integrere interaktive rapporter i Microsoft Teams](service-embed-report-microsoft-teams.md)-kanaler og -chats. Fanen **Power BI** hjælper dine kolleger med at finde dit teams data og drøfte dataene i dit teams kanaler. 
- Vi opretter et [linkeksempel](service-teams-link-preview.md), når du indsætter et link til dine rapporter, dashboards og apps i Microsoft Teams-meddelelsesfeltet. Linkeksemplet viser oplysninger om linket. 
- Brug [Del i Teams](service-share-report-teams.md), når du får vist rapporter og dashboards i Power BI-tjenesten, til hurtigt at starte samtaler i Teams.
 
:::image type="content" source="media/service-collaborate-microsoft-teams/power-bi-embed-teams-report.png" alt-text="Skærmbillede af en Power BI-rapport, der er integreret i en Teams-kanal.":::

## <a name="requirements"></a>Krav

For at Power BI kan fungere i Microsoft Teams, skal du overordnet sørge for følgende:

- At brugerne har en Power BI Pro-licens, eller at rapporten er indeholdt i en [Power BI Premium-kapacitet (EM- eller P-SKU)](../admin/service-premium-what-is.md) med en Power BI-licens.
- At brugerne er logget på Power BI-tjenesten for at aktivere deres Power BI-licens.
- At brugerne opfylder kravene til at bruge **Power BI**-fanen til Microsoft Teams.

## <a name="grant-access-to-reports"></a>Giv adgang til rapporter

Integrering af en rapport i Microsoft Teams eller afsendelse af et link til et element giver ikke automatisk brugerne tilladelse til at få vist rapporten. Du skal [give brugerne tilladelse til at få vist rapporten i Power BI](service-share-dashboards.md). Du kan bruge en Microsoft 365-gruppe til dit team for at gøre det nemmere.

> [!IMPORTANT]
> Sørg for at gennemse, hvem der kan få vist rapporten, i Power BI-tjenesten, og giv adgang til dem, der er ikke angivet.

Du kan f.eks. sikre, at alle i et team har adgang til rapporter, ved at placere rapporterne i et enkelt arbejdsområde og give Microsoft 365-gruppen for dit team adgang til det.

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

- Power BI understøtter ikke de samme oversatte sprog som Microsoft Teams. Derfor ser du muligvis ikke den korrekte oversættelse i den integrerede rapport.
- Power BI-dashboards kan ikke integreres i **Power BI**-fanen til Microsoft Teams.
- Brugere uden en Power BI-licens eller en adgangstilladelse til rapporten, får vist meddelelsen "Indholdet er ikke tilgængeligt".
- Du har muligvis problemer med dette, hvis du bruger Internet Explorer 10. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- [URL-filtre](service-url-filters.md) understøttes ikke med **Power BI**-fanen til Microsoft Teams.
- Den nye **Power BI**-fane ikke tilgængelig i de nationale cloudmiljøer. Der er muligvis en ældre version tilgængelig, som ikke understøtter den nye arbejdsområdeoplevelse eller rapporter i Power BI-apps.
- Når du har gemt fanen, kan du ikke ændre navnet på fanen under fanen Indstillinger. Du kan bruge funktionen **Omdøb** for at ændre navnet.
- Enkeltlogon understøttes ikke for tjenesten til linkeksempler.
- Linkeksempler fungerer ikke i forbindelse med mødechat eller private kanaler.

## <a name="next-steps"></a>Næste trin

- [Integrer Power BI-indhold i Microsoft Teams](service-embed-report-microsoft-teams.md)
- [Få vist et eksempel på et Power BI-link i Microsoft Teams](service-teams-link-preview.md)
- [Del direkte i Teams fra Power BI-tjenesten](service-share-report-teams.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/).
