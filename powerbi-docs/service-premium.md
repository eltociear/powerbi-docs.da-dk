---
title: Hvad er Microsoft Power BI Premium?
description: Power BI Premium er dedikeret kapacitet for din organisation eller dit team og giver dig mere pålidelig ydeevne og større datamængder, uden at du skal købe licenser pr. bruger.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/21/2018
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: cbfee8034639a65517f9adc57cc95dd1271e6044
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025436"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Hvad er Microsoft Power BI Premium?

Microsoft Power BI Premium indeholder ressourcer, der er dedikeret til at køre Power BI-tjenesten for din organisation. Det giver dig mere pålidelig ydeevne og gør det muligt at have større datamængder. Premium giver også mulighed for omfattende distribution af indhold, uden at du skal købe Pro-licenser pr. bruger til forbrugere af indhold. Du kan finde oplysninger om køb under [Sådan køber du Power BI Premium](service-admin-premium-purchase.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="premium-capacity-and-shared-capacity"></a>Premium-kapacitet og delt kapacitet

Du drager fordel af Power BI Premium ved at tildele arbejdsområder til en *Premium-kapacitet*. Premium-kapacitet er en dedikeret ressource for din organisation. Arbejdsområder, der ikke er knyttet til en Premium-kapacitet, indgår i en *delt kapacitet*. Med en delt kapacitet kan dine arbejdsbelastninger køre på databehandlingsressourcer, der deles med andre kunder.

På følgende billede vises relationen mellem Premium-kapacitet og delt kapacitet ved at bruge virksomheden Contoso som et eksempel.

![Illustration af Power BI Premium](media/service-premium/premium-chart.png)

| Område | Beskrivelse |
| --- | --- |
| **(1)** Elementer i en Premium-kapacitet | <ul><li>Adgang til apparbejdsområder (som medlemmer eller administratorer) og publicering af apps kræver en Power BI Pro-licens.<li>Deling af en app kræver en Pro-licens, men det gør forbrug af en app ikke.<li>Alle dashboardmodtagere, uanset hvilken licens de er tildelt, kan sætte databeskeder.<li>REST-API'er til integration anvender en tjenestekonto med en Pro-licens i stedet for en brugerkonto.</ul> |
| **(2)** Mit arbejdsområde i delt kapacitet | <ul><li>Både deling og brug af en app kræver en Pro-licens.</ul> |
| **(3)** Apparbejdsområder i delt kapacitet | <ul><li>Enhver brug af app kræver en Pro-licens.</ul>|
| | |

Power BI pålægger flere grænser for individuelle brugere i delt kapacitet for at sikre kvaliteten af oplevelsen for alle brugere. Dit arbejdsområde er som standard i delt kapacitet, herunder dit personlige *Mit arbejdsområde* og apparbejdsområder.

I følgende tabel ses en oversigt over forskellene mellem delt kapacitet og Premium-kapacitet.

|  | Delt kapacitet | Power BI Premium-kapacitet |
| --- | --- | --- |
| **Opdateringshastighed** |8/dag |48/dag |
| **Isolering med dedikeret hardware** |![Ikke tilgængelig](media/service-premium/not-available.png) |![Tilgængelig](media/service-premium/available.png) |
| **Enterprise Distribution til** _**alle brugere**_ | | |
| Apps og deling |![Ikke tilgængelig](media/service-premium/not-available.png) |![Tilgængelig](media/service-premium/available.png) |
| Integreret API og kontrolelementer |![Ikke tilgængelig](media/service-premium/not-available.png) |![Tilgængelig](media/service-premium/available.png)<sup>2</sup> |
| **Publicer Power BI-rapporter i det lokale miljø** |![Ikke tilgængelig](media/service-premium/not-available.png) |![Tilgængelig](media/service-premium/available.png) |
| | | |

*<sup>1</sup> Se [Funktioner efter licenstype](service-features-license-type.md) for at få flere oplysninger.*  
*<sup>2</sup> Fremtidige forbedringer i Power BI Premium.*

Hvis du vil vide mere om tildeling af arbejdsområder til en Premium-kapacitet, skal du se [Administrer Power BI Premium](service-admin-premium-manage.md).

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium-kapacitetsnoder

Power BI Premium er tilgængelig i nodekonfigurationer med andre v-kerne-kapaciteter. Du kan finde flere oplysninger om specifikke SKU-tilbud og omkostninger under [Priser på Power BI](https://powerbi.microsoft.com/pricing/). Der findes også en [omkostningsberegner](https://powerbi.microsoft.com/calculator/). Du kan finde oplysninger om planlægning af integreret analysekapacitet i [Hvidbog om planlægning af en Power BI Enterprise-installation](https://aka.ms/pbienterprisedeploy). Opsummering:

* P-noder kan bruges til integrerede installationer eller tjenesteinstallationer.

* EM-noder kan kun bruges til integrerede installationer. EM-noder har ikke adgang til Premium-funktioner, f.eks. deling af apps med brugere, der ikke har en Power BI Pro-licens.

>[!NOTE]
>Links i denne tabel kan kun fungere korrekt for brugere, der har rollen Global Office 365-administrator. Andre får vist fejlmeddelelsen 404.

| Kapacitetsnode | V-kerner i alt<br/>*(Backend + frontend)* | Backend-v-kerner | Frontend-v-kerner | Grænser for DirectQuery/liveforbindelser | Maks. antal sidegengivelser med størst belastning | Tilgængelighed |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (for hver måned)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 v-kerne |0,5 v-kerner, 2,5 GB RAM |0,5 v-kerner |3.75 pr. sekund |150-300 |Tilgængelig |
| [EM2 (for hver måned)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 v-kerner |1 v-kerne, 5 GB RAM |1 v-kerne |7.5 pr. sekund |301-600 |Tilgængelig |
| [EM3 (for hver måned)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 v-kerner |2 v-kerner, 10 GB RAM |2 v-kerner | |601-1.200 |Tilgængelig |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 v-kerner |4 v-kerner, 25 GB RAM |4 v-kerner |30 pr. sekund |1.201-2.400 |Tilgængelig ([månedsabonnement](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) findes også) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 v-kerner |8 v-kerner, 50 GB RAM |8 v-kerner |60 pr. sekund |2.401-4.800 |Tilgængelig |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 v-kerner |16 v-kerner, 100 GB RAM |16 v-kerner |120 pr. sekund |4.801-9.600 |Tilgængelig |
| | | | | | | |

* Frontend-v-kernerne er ansvarlige for webtjenesten, dashboardet og dokumentstyringen af rapporter, administration af adgangsrettigheder, planlægning, API'er, uploads og downloads og generelt alt, hvad der er relateret til brugeroplevelsen.

* Backend-v-kernerne er ansvarlige for det tunge arbejde: behandling af forespørgsler, cachestyring, kørsel af R-servere, dataopdatering, behandling på naturligt sprog, feeds i realtid og gengivelse af rapporter og billeder på serversiden. Med backend-v-kernerne er der også reserveret en bestemt mængde hukommelse. Det er især vigtigt at have tilstrækkelig hukommelse i forbindelse med store datamodeller eller med et stort antal aktive datasæt.

## <a name="workloads-in-premium-capacity"></a>Arbejdsbelastninger i Premium-kapacitet

Tænk på en arbejdsbelastning i Power BI som en af de mange tjenester, du kan vise til brugere. Som standard understøtter kapaciteter for **Power BI Premium** og **Power BI Embedded** kun den arbejdsbelastning, der er knyttet til Power BI-forespørgsler, som kører i clouden.

Vi tilbyder nu understøttelse af yderligere to arbejdsbelastninger: **Sideinddelte rapporter** og **Dataflow**. Du aktiverer disse arbejdsbelastninger på Power BI-administrationsportalen eller via Power BI REST-API'en. Du kan også angive den maksimale hukommelse, som de enkelte arbejdsbelastninger kan forbruge, og dermed styre, hvordan de forskellige arbejdsbelastninger påvirker hinanden. Du kan finde flere oplysninger under [Konfigurer arbejdsbelastninger](service-admin-premium-manage.md#configure-workloads).

### <a name="default-memory-settings"></a>Standardindstillinger for hukommelse

I følgende tabeller vises standard- og minimumværdierne for hukommelse baseret på de forskellige [kapacitetsnoder](#premium-capacity-nodes), der er tilgængelige. Hukommelse allokeres dynamisk til dataflow, men den allokeres statisk til sideinddelte rapporter. Du kan finde flere oplysninger i næste afsnit [Overvejelser i forbindelse med sideinddelte rapporter](#considerations-for-paginated-reports).

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office-SKU'er til SaaS-scenarier (Software som en service)

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Sideinddelte rapporter | I/T | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| Dataflow | 20 % som standard, minimum 8 %  | 20 % som standard, minimum 4 %  | 20 % som standard, minimum 2 % | 20 % som standard, minimum 1 %  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure-SKU'er til PaaS-scenarier (Platform as a Service)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Sideinddelte rapporter | I/T                      | I/T                      | I/T                     | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| Dataflow         | 27 % som standard, minimum 27 % | 20 % som standard, minimum 16 % | 20 % som standard, minimum 8 % | 20 % som standard, minimum 4 %  | 20 % som standard, minimum 2 % | 20 % som standard, minimum 1 %   |

### <a name="considerations-for-paginated-reports"></a>Overvejelser i forbindelse med sideinddelte rapporter

Hvis du bruger arbejdsbelastningen for sideinddelte rapporter, skal du være opmærksom på følgende punkter.

* **Hukommelsesallokering i sideinddelte rapporter**: I sideinddelte rapporter kan du køre din egen kode, når du gengiver en rapport (f.eks. når du ændrer tekstfarven dynamisk baseret på indhold). Derfor sikrer vi Power BI Premium-kapacitet ved at køre sideinddelte rapporter i et inkluderet område i kapaciteten. Vi kan tildele den maksimale hukommelse, du angiver, til dette område, uanset om arbejdsbelastningen er aktiv eller ej. Hvis du bruger Power BI-rapporter eller -dataflow i den samme egenskab, skal du sørge for, at du har angivet hukommelsen lavt nok til sideinddelte rapporter, så det ikke påvirker andre arbejdsbelastninger.

* **Sideinddelte rapporter er ikke tilgængelige**: I sjældne tilfælde kan arbejdsbelastningen i sideinddelte rapporter blive utilgængelige. I dette tilfælde viser arbejdsbelastningen en fejltilstand på administrationsportalen, og brugere får vist timeout for gengivelse af rapporter. Du kan afhjælpe dette problem ved at deaktivere arbejdsbelastningen og derefter aktivere den igen.

## <a name="power-bi-report-server"></a>Power BI-rapportserver

Power BI Premium giver også mulighed for at køre Power BI-rapportserver i det lokale miljø i din organisation. Du kan finde flere oplysninger i [Introduktion til Power BI-rapportserver](report-server/get-started.md).

## <a name="next-steps"></a>Næste trin

[Ofte stillede spørgsmål om Power BI Premium](service-premium-faq.md)
[Sådan køber du Power BI Premium](service-admin-premium-purchase.md)
[Administration af Power BI Premium](service-admin-premium-manage.md)
[Whitepaper om Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
[Whitepaper om planlægning af en Power BI Enterprise-udrulning](https://aka.ms/pbienterprisedeploy)
[Administrering af Power BI i din organisation](service-admin-administering-power-bi-in-your-organization.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
