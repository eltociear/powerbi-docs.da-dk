---
title: Administrer Microsoft Power BI Premium-kapaciteter
description: I denne artikel beskrives administrationsopgaver til Power BI Premium-kapaciteter.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e4bb907e12d3c0b07408f069d9b238599756e8e0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565231"
---
# <a name="managing-premium-capacities"></a>Administration af Premium-kapaciteter

Administration af Power BI Premium omfatter oprettelse, administration og overvågning af Premium-kapaciteter.

## <a name="creating-and-managing-capacities"></a>Oprettelse og administration af kapaciteter

Den **kapacitetsindstillinger** side i Power BI-administrationsportalen vises antallet af v-kerner, der er købt og Premium-kapaciteter. Siden, kan Office 365 globale administratorer eller Power BI-tjenesteadministratorer til at oprette Premium-kapaciteter fra tilgængelige v-kerner, eller at ændre eksisterende Premium-kapaciteter.

Når du opretter en Premium-kapacitet, er administratorer nødvendige for at definere:

- Kapacitetsnavn (entydigt i lejeren).
- Kapacitet admin(s).
- Kapacitetsstørrelse.
- Område for dataopbevaring.

Der skal være udpeget mindst én kapacitetsadministrator. Brugere, der er udpeget som kapacitetsadministratorer, kan:

- Du kan tildele arbejdsområder til kapaciteten.
- Administrer brugertilladelser til at tilføje flere Kapacitetsadministratorer eller brugere med tildelingstilladelser (for at aktivere dem til at tildele arbejdsområder til kapaciteten).
- Administrer arbejdsbelastninger, hvis du vil konfigurere maksimumhukommelse forbrug for sideinddelte rapporter og dataflows arbejdsbelastninger.
- Genstarte kapaciteten, til at nulstille alle handlinger på grund af en overbelastning af systemet.

Kapacitetsadministratorer ikke adgang til indhold i arbejdsområdet, medmindre det udtrykkeligt er tildelt i arbejdsområdet tilladelser. De også har ikke adgang til alle områder af Power BI-administrator (medmindre det udtrykkeligt er tildelt) som f.eks forbrugsdata, overvågningslogger eller lejerindstillinger. Kapacitetsadministratorer har heller ikke tilladelse til at konfigurere nye kapaciteter eller skalere eksisterende kapaciteter. Administratorer, der er tildelt på grundlag af kapacitet pr., at sikre, at de kan kun få vist og administrere kapaciteter, som de er tildelt.

Kapacitetsstørrelse er valgt en tilgængelig listen over SKU-indstillinger, som er begrænset af antallet af tilgængelige v-kerner i puljen. Det er muligt at oprette flere kapaciteter fra den gruppe, som kan købes fra en eller flere købt SKU'er. En P3-SKU (32 v-kerner) kan f.eks. bruges til at oprette tre kapaciteter: én P2 (16 v-kerner) og to P1 (2 x 8 v-kerner). Forbedret ydeevne og skalering kan opnås ved at oprette mindre størrelser kapaciteter, som beskrevet i den [optimering af Premium-kapaciteter](service-premium-capacity-optimize.md) artikel. På følgende billede vises et eksempel på opsætning for den fiktive virksomhed Contoso bestående af fem Premium-kapaciteter (3 x P1 og 2 x P3), som hver især indeholder apparbejdsområder og flere arbejdsområder i en delt kapacitet.

![Et eksempel på opsætning for den fiktive virksomhed Contoso](media/service-premium-capacity-manage/contoso-organization-example.png)

En Premium-kapacitet, der kan tildeles til et andet område end den lokale område af Power BI-lejeren, kendt som multi-geografiske område. Multi-geo giver administrative kontrol over, hvilke datacentre i defineres geografiske områder, der er placeret i din Power BI-indhold. En multi-geo-installation kommer til sin ret i forbindelse med overholdelse af angivne standarder i store virksomheder eller regeringer, fremfor i forbindelse med ydeevne og skalering. Indlæsning af rapporter og dashboards omfatter stadig anmodninger til det lokale område for metadata. Hvis du vil vide mere, kan du se [Multi-Geo-support til Power BI Premium](service-admin-premium-multi-geo.md).

Administratorer af Power BI-tjenesten og globale Office 365-administratorer kan redigere Premium-kapaciteter. De kan:

- Rediger kapacitetsstørrelse til at skalere op eller ned ressourcer.
- Tilføj eller fjern Kapacitetsadministratorer.
- Tilføje eller fjerne brugere, der har tilladelser til tildeling af.
- Tilføj eller fjern yderligere arbejdsbelastninger.
- Rediger områder.

Tildelingstilladelser er påkrævede for at kunne tildele et arbejdsområde til en bestemt Premium-kapacitet. Tilladelserne, der kan tildeles til hele organisationen, specifikke brugere eller grupper.

Premium-kapaciteter understøtter som standard kun de arbejdsbelastninger, der er tilknyttet kørende Power BI-forespørgsler. Premium-kapaciteter understøtter også yderligere arbejdsbelastninger: **AI (Cognitive Services)** , **sideinddelte rapporter**, og **Dataflows**. Hver arbejdsbelastning kræver, at den maksimale hukommelse (som en procentdel af den samlede tilgængelige hukommelse), der kan bruges af arbejdsbelastningen, konfigureres. Det er vigtigt at forstå, at øge maksimumhukommelse allokeringer kan påvirke antallet af aktive modeller, der kan være vært for og gennemløbet af opdateringer. 

Hukommelsen allokeres dynamisk at dataflows, men statisk er allokeret til sideinddelte rapporter. Årsagen til statisk allokering af den maksimale hukommelse er, at sideinddelte rapporter kører i et sikret område i kapaciteten. Man bør konfigurere hukommelse til sideinddelte rapporter med omhu, da det reducerer den tilgængelige hukommelse til indlæsning af modeller. Hvis du vil vide mere, kan du se de [standardindstillinger hukommelse](service-admin-premium-workloads.md#default-memory-settings).

Hvis du sletter en Premium-kapacitet er muligt, og resultere ikke i sletning af dets arbejdsområder og indhold. I stedet, flyttes den tildelte arbejdsområder til delt kapacitet. Når Premium-kapacitet er oprettet i et andet område, flyttes arbejdsområdet til delt kapacitet i det lokale område.

### <a name="assigning-workspaces-to-capacities"></a>Tildeling af arbejdsområder til kapaciteter

Arbejdsområder kan tildeles til en Premium-kapacitet i Power BI-administrationsportalen eller til et apparbejdsområde, i den **arbejdsområde** rude.

Kapacitetsadministratorer, samt Office 365 globale administratorer eller Power BI-tjenesteadministratorer, kan massetildele arbejdsområder i Power BI-administrationsportalen. Massetildelingen kan gælde for:

- **Arbejdsområder efter brugere** – alle arbejdsområder, der ejes af disse brugere, herunder personlige arbejdsområder, der er tildelt til Premium-kapacitet. Dette omfatter omfordeling af arbejdsområder, når de er allerede tildelt til en anden premiumkapacitet. Herudover tildeles brugerne også tilladelser til arbejdsområdetildelinger.

- **Specifikke arbejdsområder**
- **Hele organisationens arbejdsområder** – alle arbejdsområder, herunder personlige arbejdsområder, der er tildelt til Premium-kapacitet. Alle aktuelle og fremtidige brugere tildeles tilladelser til tildeling af arbejdsområde. Denne fremgangsmåde anbefales ikke. En mere målrettede fremgangsmåde foretrækkes.

Et arbejdsområde kan føjes til en Premium-kapacitet ved hjælp af ruden **Arbejdsområde**, hvis brugeren både er arbejdsområdeadministrator og har tildelingstilladelser.

![Brug af ruden Arbejdsområde til at tildele et arbejdsområde til en Premium-kapacitet](media/service-premium-capacity-manage/assign-workspace-capacity.png)

Arbejdsområdeadministratorer kan fjerne et arbejdsområde fra en kapacitet (til delt kapacitet) uden at have tildelingstilladelser. Fjernelse af arbejdsområder fra dedikerede kapaciteter flytter effektivt arbejdsområdet til en delt kapacitet. Bemærk, at det kan have negative konsekvenser at fjerne et arbejdsområde fra en Premium-kapacitet, da delt indhold f.eks. kan blive utilgængeligt for brugere med en Power BI Free-licens, eller en planlagt opdatering kan blive suspenderet, når brugerne når det tilladte forbrug, der er understøttet af delte kapaciteter.

I Power BI-tjenesten er et arbejdsområde, der er tildelt til en Premium-kapacitet, markeret med et rombeikon ud for navnet på arbejdsområdet.

![Identifikation af et arbejdsområde, der er tildelt til en Premium-kapacitet](media/service-premium-capacity-manage/premium-diamond-icon.png)

## <a name="monitoring-capacities"></a>Overvågning af kapaciteter

Overvågning af Premium-kapaciteter giver administratorer en forståelse af, hvordan kapaciteterne kører. Kapaciteter kan overvåges ved hjælp af Power BI-administrationsportalen eller **Power BI Premium-kapacitet målepunkter** app (Power BI).

### <a name="power-bi-admin-portal"></a>Power BI-administrationsportal

I administrationsportalen for hver kapacitet har den **Health** fanen giver en oversigt over målepunkter for kapaciteten, og hver aktiveret arbejdsbelastninger. Målepunkter viser et gennemsnit over de seneste syv dage.  

Målepunkter er akkumuleret af alle arbejdsbelastninger, der er aktiveret på niveauet kapacitet. der findes følgende målepunkter:

- **CPU-forbruget** -giver Gennemsnitlig CPU-forbruget som en procentdel af samlede tilgængelige CPU for kapaciteten.  
- **Brug af hukommelse** -giver gennemsnit hukommelsesforbrug (i GB) som en total af tilgængelig hukommelse for kapaciteten. 

For hver aktiveret arbejdsbelastning, er udnyttelse for CPU og hukommelse angivet, samt et antal arbejdsbelastning specifikke målepunkter. For eksempel for Dataflow arbejdsbyrde, **Samlet antal** viser samlet opdateringer for hver dataflowet, og **gennemsnitlige varighed** viser den gennemsnitlige varighed af opdatering til dataflowet.

![Under fanen kapacitet tilstand i portalen](media/service-premium-capacity-manage/admin-portal-health-dataflows.png)

Hvis du vil vide mere om alle tilgængelige målepunkter for hver enkelt arbejdsbelastning, se [overvåge kapaciteter i administrationsportalen](service-admin-premium-monitor-portal.md).

Overvågning funktionaliteten i Power BI-administrationsportalen er designet til at give et overblik over vigtige kapacitet målepunkter. Finde mere detaljerede overvågning, anbefales det, du bruger den **Power BI Premium-kapacitet målepunkter** app.

### <a name="power-bi-premium-capacity-metrics-app"></a>Appen Power BI Premium Capacity Metrics

Den [Power BI Premium-kapacitet målepunkter app](https://appsource.microsoft.com/product/power-bi/pbi_pcmm.pbi-premiumcapacitymonitoring?tab=Overview) er en Power BI-app, der er tilgængelig for kapacitetsadministratorer og er installeret som enhver anden Power BI-app. Den indeholder et dashboard og en rapport.

![Appen Power BI Premium Capacity Metrics](media/service-premium-capacity-manage/capacity-metrics-app.png)

Når appen åbnes, indlæses dashboardet og viser de mange felter, der udtrykker en samlet visning over alle de kapaciteter, som brugeren er kapacitetsadministrator for. Dashboardlayoutet indeholder fem vigtigste afsnit:

- **Oversigt over** -appversion, antal kapaciteter og arbejdsområder
- **Oversigt over system** -hukommelse og CPU-målepunkter
- **Oversigt over datasæt** – antallet af datasæt, DQ/LC, opdatering og målepunkter for forespørgsel
- **Oversigt over dataflowet** – antallet af dataflows og metrikværdier, datasæt
- **Sideinddelt rapportoversigt** – Opdater, og se målinger

Den underliggende rapport, hvorfra dashboardfelterne er fastgjort, kan opnås ved at klikke på en hvilken som helst dashboard-felt. Den giver et mere detaljeret overblik over hvert af dashboardafsnittene og understøtter interaktiv filtrering. 

Du kan filtrere ved at angive udsnit efter datointerval, kapacitet, arbejdsområde og arbejdsbelastning (rapport, datasæt, dataflow) og ved at vælge elementer i rapportvisualiseringer for at filtrere på tværs af rapportsiden. Tværgående filtrering er en effektiv teknik til at indsnævre til bestemte tidsperioder, kapaciteter, arbejdsområder, datasæt, osv., og det kan være meget nyttigt, når du diagnosticerer den underliggende årsag.

Detaljerede oplysninger om dashboardet og rapporten målinger i appen, [Monitor Premium-kapaciteter med appen](service-admin-premium-monitor-capacity.md).

### <a name="interpreting-metrics"></a>Fortolkning af målepunkter

Målepunkter skal overvåges for at oprette en grundlæggende forståelse af ressourceforbruget og arbejdsbelastningsaktiviteterne. Hvis kapaciteten bliver langsom, er det vigtigt at forstå, hvilke målepunkter der skal overvåges og de konklusioner, du kan drage.

Ideelt set bør forespørgsler være fuldført inden for et sekund for at levere dynamiske oplevelser til rapportbrugerne og muliggøre et højere gennemløb af forespørgsler. Det er som regel mindre væsentligt, når processer i baggrunden – herunder opdateringer – tager længere tid at fuldføre.

Langsomme rapporter kan generelt være en indikation af en overbebyrdet kapacitet. Når rapporter ikke indlæses, er det en indikation af en overbebyrdet kapacitet. I begge situationer kan hovedårsagen henføres til flere forskellige faktorer, herunder:

- **Mislykkede forespørgsler** angiver i høj grad en belastning af hukommelsen, og at en model ikke kunne indlæses i hukommelsen. Power BI-tjenesten vil forsøge at indlæse en model i 30 sekunder, før der opstår en fejl.

- **Overdrevne ventetider for forespørgsler** kan skyldes flere forskellige årsager:
  - Behovet for Power BI-tjenesten til først fjerne eller-modellerne og derefter indlæse modellen skal-be – forespørges (tilbagekaldelse, højere datasæt hård alene ikke takster angivelse af kapacitet stress, medmindre ledsages af længe forespørgslen ventetider, der angiver hukommelsesudskiftning).
  - Indlæsning af modellen gange (især ventetid til at indlæse en stor model i hukommelse).
  - Lange kørende forespørgsler.
  - For mange LC\DQ forbindelser (overskrider grænser for datakapacitet).
  - CPU-mætning.
  - Komplekse report Designer med et stort antal visualiseringer på en side (tilbagekaldelse, at hver visual er en forespørgsel).

- **Lange varigheder af forespørgsler** kan indikere, at modeldesignet ikke er optimeret, især når flere datasæt er aktive i en kapacitet, og kun ét datasæt genererer lange varigheder af forespørgsler. Dette tyder på, at kapaciteten ikke har tilstrækkeligt med ressourcer, og at det pågældende datasæt ikke er optimalt eller blot langsomt. Lange forespørgsler kan være problematiske, da de kan blokere adgang til ressourcer, der kræves af andre processer.
- **Opdater lange ventetider** angive utilstrækkelig hukommelse på grund af mange aktive modeller, der bruger for meget hukommelse, eller (grænser overstiger parallel opdatering), en problematiske opdatering blokerer andre opdateres.

En mere detaljeret beskrivelse af, hvordan du bruger målepunkter, der er beskrevet i den [optimering af Premium-kapaciteter](service-premium-capacity-optimize.md) artikel.

## <a name="acknowledgements"></a>Godkendelser

I denne artikel er skrevet af Peter Myers, Data Platform MVP og uafhængige BI-ekspert med [bitvis løsninger](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Næste trin

> [!div class="nextstepaction"]
> [Optimering af Premium-kapaciteter](service-premium-capacity-optimize.md)   
> [!div class="nextstepaction"]
> [Konfigurer arbejdsprocesser i en Premium-kapacitet](service-admin-premium-workloads.md)   

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

||||||
