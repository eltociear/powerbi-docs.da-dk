---
title: Integrer rapporter i Microsoft Teams
description: Med fanen Power BI til Microsoft Teams kan du nemt integrere interaktive rapporter i kanaler og chats.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 04/27/2020
ms.openlocfilehash: 7034bd544ee9c14dd5f32df9335faefd4221e4ac
ms.sourcegitcommit: 250242fd6346b60b0eda7a314944363c0bacaca8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/20/2020
ms.locfileid: "83693901"
---
# <a name="embed-reports-in-microsoft-teams-with-the-power-bi-tab"></a>Integrer rapporter i Microsoft Teams ved hjælp af Power BI-fanen

Med den opdaterede Power BI-fane til Microsoft Teams kan du nemt integrere interaktive rapporter i Microsoft Teams-kanaler og -chats. Brug Power BI-fanen til Microsoft Teams til at hjælpe dine kolleger med at finde de data, som dit team bruger, og til at diskutere dataene i dine teamkanaler.  Når du indsætter et link til dine rapporter, dashboards og apps i Microsoft Teams-meddelelsesfeltet, viser linkeksemplet oplysninger om elementerne. Brugerne kan nemmere forstå, hvilket element de kommer til, når de vælger linket.

## <a name="requirements"></a>Krav

Du kan sikre, at **Power BI-fanen til Microsoft Teams** fungerer, ved at sørge for:

- At brugerne har en Power BI Pro-licens, eller at rapporten er indeholdt i en [Power BI Premium-kapacitet (EM- eller P-SKU)](../admin/service-premium-what-is.md) med en Power BI-licens.
- Microsoft Teams har en Power BI-fane.
- Brugerne er logget på Power BI-tjenesten for at aktivere deres Power BI-licens, så de kan bruge rapporten.
- Hvis du vil tilføje en rapport i Microsoft Teams via Power BI-fanen, skal du mindst have rollen som Seer i det arbejdsområde, der hoster rapporten. Se [Roller i de nye arbejdsområder](service-new-workspaces.md#roles-in-the-new-workspaces) for at få oplysninger om de forskellige roller.
- Brugerne skal have tilladelse til at få vist rapporten, før de kan se den under Power BI-fanen i Microsoft Teams.

Hvis **linkeksempler** skal kunne fungere, skal du også sikre, at:
- Brugerne opfylder kravene til at bruge Power BI-fanen til Microsoft Teams.
- Brugerne er logget på Power BI-tjenesten. 


## <a name="embed-your-report"></a>Integrer din rapport

Hvis du vil integrere din rapport i en Microsoft Teams-kanal eller -chat, skal du benytte denne fremgangsmåde.

1. Åbn en kanal eller chat i Microsoft Teams, og vælg ikonet **+** .

    ![Føj en fane til en kanal eller chat](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

2. Vælg Power BI-fanen.

    ![Liste over Microsoft Teams-faner, der viser Power BI](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

3. Du kan benytte indstillingerne til at vælge en rapport fra et arbejdsområde fra Delt med mig eller fra en Power BI-app.

    ![Indstillinger for Power BI-fanen til Microsoft Teams](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

4. Fanenavnet opdateres automatisk, så det passer til rapportnavnet, men du kan ændre det. 

5. Tryk på **Gem**.

## <a name="supported-reports-for-embedding-the-power-bi-tab"></a>Understøttede rapporter til integrering af Power BI-fanen
Du kan integrere følgende typer rapporter på Power BI-fanen:

- Interaktive og sideinddelte rapporter.
- Rapporter i Mit arbejdsområde, i den nye arbejdsområdeoplevelse og i klassiske arbejdsområder.
- Rapporter i Power BI-apps.

## <a name="get-a-link-preview"></a>Få et linkeksempel

Følg disse trin for at få et linkeksempel af indhold i Power BI-tjenesten.

1. Kopiér et link til en rapport, et dashboard eller en app i Power BI-tjenesten. Du kan f.eks. kopiere linket fra browserens adresselinje.

2. Indsæt linket i meddelelsesfeltet i Microsoft Teams. Log på tjenesten til linkeksempler, hvis du bliver bedt om det. Det kan være nødvendigt at vente et par sekunder på, at linkeksemplet indlæses.

    ![Log på Power BI Bot](media/service-embed-report-microsoft-teams/service-teams-link-preview-sign-in-needed.png)

3. Det grundlæggende linkeksempel vises, når du er logget på.

    ![Grundlæggende linkeksempel](media/service-embed-report-microsoft-teams/service-teams-link-preview-basic.png)

4. Vælg udvidelsesikonet for at få vist kortet med en detaljeret eksempelvisning.

    ![Ikonet Udvid](media/service-embed-report-microsoft-teams/service-teams-link-preview-expand-icon.png)

5. Kortet med et detaljeret linkeksempel viser linket og de relevante handlingsknapper

    ![Kort med detaljeret linkeksempel](media/service-embed-report-microsoft-teams/service-teams-link-preview-nice-card.png)

6. Send meddelelsen.



## <a name="grant-access-to-reports"></a>Giv adgang til rapporter

Integrering af en rapport i Microsoft Teams eller afsendelse af et link til et element giver ikke automatisk brugerne tilladelse til at få vist rapporten. Du skal [give brugerne tilladelse til at få vist rapporten i Power BI](service-share-dashboards.md). Du kan bruge en Microsoft 365-gruppe for dit team for at gøre det nemmere.

> [!IMPORTANT]
> Sørg for at gennemse, hvem der kan få vist rapporten, i Power BI-tjenesten, og giv adgang til dem, der er ikke angivet.

Du kan f.eks. sikre, at alle i dit team har adgang til rapporter, ved at placere rapporterne i et enkelt arbejdsområde i Power BI og give Microsoft 365-gruppen for dit team adgang til arbejdsområdet.

## <a name="link-previews"></a>Linkeksempler 

Der er angivet linkeksempler for følgende elementer i Power BI:
- Rapporter
- Dashboards
- Apps

Tjenesten til linkeksempler kræver, at brugerne logger på. Hvis du vil logge af, skal du vælge Power BI-ikonet nederst i meddelelsesfeltet og derefter vælge Log af.

## <a name="start-a-conversation"></a>Start en samtale

Når du føjer en Power BI-rapportfane til Teams, opretter Teams automatisk en fanesamtale til rapporten. 

- Vælg **Vis fanesamtale** i øverste højre hjørne.

    ![Ikon for Vis fanesamtale](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-icon.png)

    Den første kommentar er et link til rapporten. Alle i den pågældende Teams-kanal kan se og diskutere rapporten i samtalen.

    ![Fanesamtale](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-tab.png)

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

- Power BI understøtter ikke de samme oversatte sprog som Microsoft Teams. Derfor ser du muligvis ikke den korrekte oversættelse i den integrerede rapport.
- Power BI-dashboards kan ikke integreres i Power BI-fanen til Microsoft Teams.
- Brugere uden en Power BI-licens eller en tilladelse til rapporten, får vist meddelelsen "Indholdet er ikke tilgængeligt".
- Der kan opstå tekniske problemer, hvis du bruger Internet Explorer 10. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- [URL-filtre](service-url-filters.md) understøttes ikke med Power BI-fanen til Microsoft Teams.
- I de nationale cloudmiljøer er den nye Power BI-fane ikke tilgængelig. Der er muligvis en ældre version tilgængelig, som ikke understøtter den nye arbejdsområdeoplevelse eller rapporter i Power BI-apps. 
- Når du har gemt fanen, kan du ikke ændre navnet på fanen under fanen Indstillinger. Du kan bruge funktionen til omdøbning for at ændre navnet.
- Enkeltlogon understøttes ikke for tjenesten til linkeksempler.
- Linkeksempler fungerer ikke i forbindelse med mødechat eller private kanaler.

## <a name="next-steps"></a>Næste trin
- [Del et dashboard med kolleger og andre](service-share-dashboards.md)  
- [Opret og distribuer en app i Power BI](service-create-distribute-apps.md)  
- [Hvad er Power BI Premium?](../admin/service-premium-what-is.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
