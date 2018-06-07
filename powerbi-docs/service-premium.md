---
title: Power BI Premium – hvad er det?
description: Power BI Premium er dedikeret kapacitet for din organisation eller dit team og giver dig mere pålidelig ydeevne og større datamængder, uden at du skal købe licenser pr. bruger.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2018
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: 980aa830e38e49613b54ad473ef23eb7eac78ed2
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34722787"
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium – hvad er det?
Power BI Premium indeholder ressourcer, der er dedikeret til at køre Power BI-tjenesten for din organisation eller dit team og giver dig en mere pålidelig ydeevne og større datamængder. Premium giver også mulighed for omfattende distribution af indhold, uden at du skal købe licenser pr. bruger til fremvisere.

Du kan drage fordel af Power BI Premium ved at tildele arbejdsområder til en Premium-kapacitet. *Premium-kapacitet* er en dedikeret ressource for din organisation. Arbejdsområder, der ikke er knyttet til en Premium-kapacitet, vil være i en delt kapacitet.

*Delt kapacitet* er oplevelsen, du er vant til med Power BI, hvor dine arbejdsbelastninger kører på databehandlingsressourcer, der deles med andre kunder. Der er pålagt flere grænser for individuelle brugere i delt kapacitet for at sikre kvaliteten af oplevelsen for alle brugere.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Kapacitetsniveauer
Der er to kapacitetstyper i Power BI. Delt kapacitet og Power BI Premium-kapacitet. Her kan du se, hvad forskellen er mellem dem.

|  | Delt kapacitet | Power BI Premium-kapacitet |
| --- | --- | --- |
| **Opdateringshastighed** |8/dag |Ikke begrænset |
| **Isolering med dedikeret hardware** |![](media/service-premium/not-available.png "Ikke tilgængelig") |![](media/service-premium/available.png "Tilgængelig") |
| **Enterprise Distribution til** ***alle brugere*** | | |
| Apps |![](media/service-premium/not-available.png "Ikke tilgængelig") |![](media/service-premium/available.png "Tilgængelig")<sup>1</sup> |
| Integreret API og kontrolelementer |![](media/service-premium/not-available.png "Ikke tilgængelig") |![](media/service-premium/available.png "Tilgængelig")<sup>2</sup> |
| **Publicer Power BI-rapporter i det lokale miljø** |![](media/service-premium/not-available.png "Ikke tilgængelig") |![](media/service-premium/available.png "Tilgængelig") |

*<sup>1</sup> Gratis brugerforbrug i apps omfatter visning af indhold i web og mobil ved hjælp af Spørgsmål og svar, Hurtig indsigt, Cortana, eksport til CSV, Excel og PowerPoint. Der kræves en Pro-licens til andre aktiviteter, der ikke er angivet, f.eks. oprettelse af rapporter baseret på delte datasæt og Analysér i Excel. Få mere at vide om funktionaliteten i [den gratis version af Power BI sammenlignet med Pro-versionen](service-free-vs-pro.md).*  
*<sup>2</sup> Fremtidige forbedringer i Power BI Premium efter GA.*

### <a name="premium-capacity"></a>Premium-kapacitet
Hvis du vil bruge en Power BI Premium-kapacitet, skal du tildele et arbejdsområde til en kapacitet. Du kan finde flere oplysninger om, hvordan du tildeler et arbejdsområde til en Premium-kapacitet, under [Administrer Power BI Premium](service-admin-premium-manage.md).

Når et arbejdsområde bakkes op af Premium-kapacitet, kan du udnytte fordelene ved Power BI Premium.

* Planlagte opdateringer: Brugere var tidligere begrænset til 8x om dagen ved planlægning af opdateringer med importerede modeller. Denne begrænsning fjernes for datasæt i Premium-arbejdsområder. Dette gælder ikke for indstillingerne for planlagt opdatering af cache til DirectQuery. De forbliver uændret mellem Premium- og delt kapacitet.
* Isolering med dedikeret hardware – som den delte kapacitet fungerer, kan rapporternes og dashboardenes ydeevne blive påvirket af andre arbejdsbelastningers ressourcekrav i kapaciteten, til trods for vores sikkerhedsforanstaltninger mod det. Premium leverer omvendt mere ensartet, pålidelig ydeevne for dine arbejdsbelastninger ved at isolere det fra ikke-relaterede arbejdsbelastninger.

Hvis en app bakkes op af Premium-kapacitet (dvs. den blev publiceret fra et apparbejdsområde, som i øjeblikket er tildelt til Premium), kan den publicerede app derefter anvendes af alle brugere i din organisation, uanset den licens de er tildelt. Det betyder, at selv brugere af den gratis Power BI kan bruge disse apps, der er publiceret.

### <a name="shared-capacity"></a>Delt kapacitet
Som standard vil dit arbejdsområde være i delt kapacitet. Dette omfatter dit personlige *Mit arbejdsområde* sammen med apparbejdsområder. En delt kapacitet er oplevelsen, du er vant til med Power BI, hvor dine arbejdsbelastninger kører på databehandlingsressourcer, der deles med andre kunder.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium-kapacitetsnoder
Power BI Premium er tilgængelig i nodekonfigurationer med andre v-kerne-kapaciteter. Du kan finde flere oplysninger om specifikke SKU-tilbud og priser under [Priser på Power BI](https://powerbi.microsoft.com/pricing/). Der findes også en [omkostningsberegner](https://powerbi.microsoft.com/calculator/). Du kan finde oplysninger om planlægning af integreret analysekapacitet i [Hvidbog om planlægning af en Power BI Enterprise-installation](https://aka.ms/pbienterprisedeploy).

* P-noder kan bruges til integrerede installationer eller tjenesteinstallationer
* EM-noder kan kun bruges til integrerede installationer
* EM1 og EM2 

>[!NOTE]
>Links i denne tabel kan kun fungere korrekt for brugere, der er globale Office 365-administratorer – andre får vist fejlmeddelelsen 404. 

| Kapacitetsnode | V-kerner i alt<br/>*(Backend + frontend)* | Backend-v-kerner | Frontend-v-kerner | Grænser for DirectQuery/liveforbindelser | Maks. antal sidegengivelser med størst belastning | Tilgængelighed |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (for hver måned)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 v-kerne |,5 v-kerner 2,5 GB RAM |,5 v-kerner |3.75 pr. sekund |150-300 |Tilgængelig |
| [EM2 (for hver måned)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 v-kerner |1 v-kerne, 5 GB RAM |1 v-kerne |7.5 pr. sekund |301-600 |Tilgængelig |
| [EM3 (for hver måned)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 v-kerner |2 v-kerner, 10 GB RAM |2 v-kerner | |601-1.200 |Tilgængelig |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 v-kerner |4 v-kerner, 25 GB RAM |4 v-kerner |30 pr. sekund |1.201-2.400 |Tilgængelig ([månedsabonnement](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) findes også) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 v-kerner |8 v-kerner, 50 GB RAM |8 v-kerner |60 pr. sekund |2.401-4.800 |Tilgængelig |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 v-kerner |16 v-kerner, 100 GB RAM |16 v-kerner |120 pr. sekund |4.801-9.600 |Tilgængelig |

* Frontend-v-kernerne er ansvarlige for webtjenesten, dashboardet og dokumentstyringen af rapporter, administration af adgangsrettigheder, planlægning, API'er, uploads og downloads og generelt alt, hvad der er relateret til brugeroplevelsen.
* Backend-v-kernerne er ansvarlige for det tunge arbejde: behandling af forespørgsler, cachestyring, kørsel af R-servere, dataopdatering, behandling på naturligt sprog, feeds i realtid og gengivelse af rapporter og billeder på serversiden. Med backend-v-kernerne er der også reserveret en bestemt mængde hukommelse. Det er især vigtigt at have tilstrækkelig hukommelse i forbindelse med store datamodeller eller med et stort antal aktive datasæt.

## <a name="power-bi-report-server"></a>Power BI Report Server
Power BI Premium omfatter retten til at køre Power BI Report Server i det lokale miljø. Du kan finde flere oplysninger i [Kom i gang med Power BI Report Server](report-server/get-started.md).

## <a name="next-steps"></a>Næste trin
[Ofte stillede spørgsmål til Power BI Premium](service-premium-faq.md)  
[Produktbemærkninger til Power BI Premium](service-premium-release-notes.md)  
[Sådan køber du Power BI Premium](service-admin-premium-purchase.md)  
[Administrer Power BI Premium](service-admin-premium-manage.md)  
[Hvidbog om Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Hvidbog om planlægning af en Power BI Enterprise-installation](https://aka.ms/pbienterprisedeploy)  
[Administrer Power BI i din virksomhed](service-admin-administering-power-bi-in-your-organization.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

