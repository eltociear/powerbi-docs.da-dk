---
title: Hvad er Microsoft Power BI Premium?
description: Power BI Premium er dedikeret kapacitet for din organisation eller dit team og giver dig mere pålidelig ydeevne og større datamængder, uden at du skal købe licenser pr. bruger.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/28/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: cb9280f47f1f2d28ce6fabda2dbc173fbdc837ac
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226129"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Hvad er Microsoft Power BI Premium?

> [!NOTE]
> Denne artikel opdateres i øjeblikket for at beskrive nye funktioner, give flere detaljer og forbedre læsbarheden. Se de nyeste oplysninger i [Udrulning og administration af Power BI Premium-kapaciteter](whitepaper-powerbi-premium-deployment.md).

Power BI Premium indeholder ressourcer, der er dedikeret til at køre Power BI-tjenesten for din organisation. Det giver dig mere pålidelig ydeevne og gør det muligt at have større datamængder. Premium giver også mulighed for omfattende distribution af indhold, uden at du skal købe Pro-licenser pr. bruger til forbrugere af indhold.  

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

I følgende tabel ses en oversigt over forskellene mellem delt kapacitet og Premium-kapacitet:

|  | Delt kapacitet | Power BI Premium-kapacitet |
| --- | --- | --- |
| **Opdateringshastighed** |8/dag |48/dag |
| Isolering med dedikeret hardware |![Ikke tilgængelig](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Distribution i virksomheden til *alle brugere* | | |
| Apps og deling |![Ikke tilgængelig](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Integreret API og kontrolelementer |![Ikke tilgængelig](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Publicer Power BI-rapporter i det lokale miljø |![Ikke tilgængelig](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> Fremtidige forbedringer i Power BI Premium.



### <a name="premium-capacity-nodes"></a>Premium-kapacitetsnoder

Power BI Premium er tilgængelig i nodekonfigurationer med andre v-kerne-kapaciteter. Du kan finde flere oplysninger om specifikke SKU-tilbud og omkostninger under [Priser på Power BI](https://powerbi.microsoft.com/pricing/). Der findes også en [omkostningsberegner](https://powerbi.microsoft.com/calculator/). Du kan finde oplysninger om planlægning af integreret analysekapacitet i [Hvidbog om planlægning af en Power BI Enterprise-installation](https://aka.ms/pbienterprisedeploy). Opsummering:

* P-noder kan bruges til integrerede installationer eller tjenesteinstallationer.

* EM-noder kan kun bruges til integrerede installationer. EM-noder har ikke adgang til Premium-funktioner, f.eks. deling af apps med brugere, der ikke har en Power BI Pro-licens.

| Kapacitetsnode | V-kerner i alt<br/>*(Back-end + front-end)*  | Virtuelle back end-kerner <sup>[1](#fn1)</sup> | Virtuelle front end-kerner <sup>[2](#fn2)</sup> | Grænser for DirectQuery/liveforbindelser | Maks. antal samtidige opdateringer |  Tilgængelighed
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1 (månedsvis) |1 v-kerne |0,5 v-kerner, 2,5 GB RAM |0,5 v-kerner |3.75 pr. sekund |  1 | Tilgængelig |
| EM2 (månedsvis) |2 v-kerner |1 v-kerne, 5 GB RAM |1 v-kerne |7.5 pr. sekund |  2 | Tilgængelig |
| EM3 (månedsvis) |4 v-kerner |2 v-kerner, 10 GB RAM |2 v-kerner | | 3 |  Tilgængelig |
| P1 |8 v-kerner |4 v-kerner, 25 GB RAM |4 v-kerner |30 pr. sekund | 6 | Tilgængelig (månedsvis er også tilgængeligt) |
| P2 |16 v-kerner |8 v-kerner, 50 GB RAM |8 v-kerner |60 pr. sekund | 12 | Tilgængelig |
| P3 |32 v-kerner |16 v-kerner, 100 GB RAM |16 v-kerner |120 pr. sekund | 24 | Tilgængelig |
| | | | | | | |

<a name="fn1">1</a>: Virtuelle front end-kerner er ansvarlige for webtjenesten. Det kan f.eks. være administration af dashboard og rapportdokumenter, administration af adgangsrettigheder, planlægning, API'er, uploads og downloads og generelt alt, der er relateret til brugeroplevelsen. 

<a name="fn2">2</a>: Virtuelle back end-kerner er ansvarlige for det tunge arbejde, f.eks. behandling af forespørgsler, administration af cache, kørsel af R-servere, dataopdatering, behandling på naturligt sprog, feeds i realtid og gengivelse af rapporter og billeder på serversiden. Med backend-v-kernerne er der også reserveret en bestemt mængde hukommelse. Det er især vigtigt at have tilstrækkelig hukommelse i forbindelse med store datamodeller eller med et stort antal aktive datasæt.

## <a name="workloads-in-premium-capacity"></a>Arbejdsbelastninger i Premium-kapacitet

Som standard understøtter kapaciteter for **Power BI Premium** og **Power BI Embedded** kun den arbejdsbelastning, der er knyttet til Power BI-forespørgsler, som kører i clouden. Premium understøtter også yderligere arbejdsbelastninger for **Kunstig intelligens**, **Dataflow** og **Sideinddelte rapporter**. Du aktiverer disse arbejdsbelastninger på Power BI-administrationsportalen eller via Power BI REST-API'en. Du kan også angive den maksimale hukommelse, som de enkelte arbejdsbelastninger kan forbruge, og dermed styre, hvordan de forskellige arbejdsbelastninger påvirker hinanden. Du kan få mere at vide ved at se [Konfigurer arbejdsbelastninger](service-admin-premium-workloads.md).

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

Hvis arbejdsbelastningen for sideinddelte rapporter bruges, skal du huske på, at sideinddelte rapporter giver dig mulighed for at køre din egen kode, når du gengiver en rapport (f.eks. når du ændrer tekstfarven dynamisk baseret på indhold). Derfor sikrer vi Power BI Premium-kapacitet ved at køre sideinddelte rapporter i et inkluderet område i kapaciteten. Vi kan tildele den maksimale hukommelse, du angiver, til dette område, uanset om arbejdsbelastningen er aktiv eller ej. Hvis du bruger Power BI-rapporter eller -dataflow i den samme egenskab, skal du sørge for, at du har angivet hukommelsen lavt nok til sideinddelte rapporter, så det ikke påvirker andre arbejdsbelastninger.

I sjældne tilfælde kan arbejdsbelastningen i sideinddelte rapporter blive utilgængelige. I dette tilfælde viser arbejdsbelastningen en fejltilstand på administrationsportalen, og brugere får vist timeout for gengivelse af rapporter. Du kan afhjælpe dette problem ved at deaktivere arbejdsbelastningen og derefter aktivere den igen.

## <a name="power-bi-report-server"></a>Power BI-rapportserver

Power BI Premium giver også mulighed for at køre Power BI-rapportserver i det lokale miljø i din organisation. Du kan finde flere oplysninger i [Introduktion til Power BI-rapportserver](report-server/get-started.md).

## <a name="next-steps"></a>Næste trin

[Udrulning og administration af Power BI Premium-kapaciteter](whitepaper-powerbi-premium-deployment.md)   
[Sådan køber du Power BI Premium](service-admin-premium-purchase.md)   
[Ofte stillede spørgsmål til Power BI Premium](service-premium-faq.md)   



Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
