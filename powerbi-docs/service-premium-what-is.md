---
title: Hvad er Microsoft Power BI Premium?
description: Power BI Premium indeholder dedikeret kapacitet for din organisation, der giver dig mere pålidelig ydeevne og større datamængder, uden at du skal købe licenser pr. bruger.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/22/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e5ffa624bf69cf470aade076c80ac37028a55456
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565271"
---
# <a name="what-is-power-bi-premium"></a>Hvad er Power BI Premium?

Power BI Premium indeholder ressourcer, der er dedikeret og forbedret for at køre Power BI-tjenesten for din organisation. Eksempel:

- Større skala og ydeevne
- Fleksibilitet til at licensere af kapacitet
- Samle selvbetjening og virksomheder
- Udvid i det lokale miljø BI med Power BI Report Server
- Understøttelse af dataplacering efter område (Multi-geografisk)
- Del data med nogen uden at købe en licens til pr. bruger

I denne artikel er ikke beregnet til at levere dybtgående oplysninger om alle funktioner i Power BI Premium – faktisk, den berører lige overflade. Hvor det er nødvendigt, leveres links til flere artikler med mere detaljerede oplysninger.

## <a name="subscriptions-and-licensing"></a>Abonnementer og licenser

Power BI Premium er et Office 365-abonnement på lejerniveau, der er tilgængeligt i to SKU-serier (lagerenheder):

- **EM** SKU'er (EM1-EM3) til at integrere, der kræver en årlig forpligtelse, faktureres månedligt.
- **P** SKU'er (P1-P3) til integrering og enterprise-funktioner, der kræver en månedlig eller årlig forpligtelse, faktureret månedsvis og indeholder en licens til at installere Power BI Report Server i det lokale miljø.

Der er en alternativ metode til at købe en **Azure Power BI Embedded** -abonnement, som har en enkelt **A** (A1-A6) SKU-serien til integrering og test kapacitet kun formål. Alle varenumre levere v-kerner for at oprette kapaciteter, men er begrænset til at integrere med mindre skalering EM-SKU'er. EM1, EM2, A1 og A2 SKU'er med færre end fire v-kerner, kan ikke køre på dedikeret infrastruktur.

Meget af hvad der er beskrevet er også relevant for A-SKU'er, mens der er i fokus i denne artikel på de P-varenumre. I modsætning til SKU'erne for Premium-abonnementet kræver Azure-SKU'er ingen tidsmæssig binding og faktureres på timebasis. De leverer fuld elasticitet, hvilket gør det muligt at skalere op og ned, afbryde midlertidigt, genoptage og slette. 

Azure Power BI Embedded er stort set uden for området i denne artikel, men det er beskrevet i den [test tilgange](service-premium-capacity-optimize.md#testing-approaches) afsnit af optimering af Premium-kapaciteter artiklen som en praktisk og økonomisk mulighed for at teste og måle arbejdsbelastninger. Hvis du vil vide mere om Azure-SKU'er, se [Azure Power BI Embedded-dokumentation](https://azure.microsoft.com/services/power-bi-embedded/).

### <a name="purchasing"></a>Køb

Power BI Premium-abonnementer købes af administratorer i Microsoft 365 Administration. Specifikt kan kun Office 365 globale administratorer eller fakturering administratorer købe SKU'er. Når du har købt, lejeren, modtager et tilsvarende antal v-kerner til at tildele til kapaciteter, kendt som *gruppering af v-kerner*. Køb af en P3-SKU giver f.eks. lejeren 32 v-kerner. Hvis du vil vide mere, kan du se [Sådan køber du Power BI Premium](service-admin-premium-purchase.md).

## <a name="dedicated-capacities"></a>Dedikeret kapacitet

Med Power BI Premium, får du *dedikerede kapaciteter*. I modsætning til en delt kapacitet, hvor arbejdsbelastninger kører på databehandlingsressourcer, der deles med andre kunder, er en dedikeret kapacitet til eksklusive brug af en organisation. Det er isoleret med dedikeret databehandlingsressourcer, som en pålidelig og konsekvent ydeevne for hostede indhold. 

Der er placeret arbejdsområder i kapaciteter. Hver bruger af Power BI har et personligt arbejdsområde, der er kendt som **Mit arbejdsområde**. Flere arbejdsområder kan oprettes for at muliggøre samarbejde og udrulning, og disse kaldes **Apparbejdsområder**. Arbejdsområder, herunder personlige arbejdsområder, der som standard oprettes i den delte kapacitet. Når du har Premium-kapaciteter, kan både mine arbejdsområder og App-arbejdsområder tildeles til Premium-kapaciteter.

### <a name="capacity-nodes"></a>Kapacitet noder

Som beskrevet i den [abonnementer og licenser](#subscriptions-and-licensing) afsnit, der er to Power BI Premium SKU-serier: **EM** og **P**. Alle Power BI Premium-SKU'er fås som kapacitet *noder*, der hver repræsenterer en fast mængde ressourcer, der består af processor, hukommelse og lager. Hver SKU har operational grænser for antallet af forbindelser for DirectQuery og direkte forbindelse pr. sekund, ud over ressourcer, og antallet af parallelle model opdateres.

Behandling opnås ved et angivet antal v-kerner, der er ligeligt fordelt mellem backend og frontend.

**Backend-v-kernerne** er ansvarlige for det tunge arbejde i Power BI, herunder behandling af forespørgsler, cachestyring, kørsel af R-servere, modelopdatering, behandling på naturligt sprog (Spørgsmål og svar) og gengivelse af rapporter og billeder på serversiden. Backend-v-kerner tildeles en fast mængde hukommelse, der primært bruges til at hoste modeller, også kendt som aktive datasæt.

**Frontend-v-kerner** er ansvarlige for webtjenesten, dashboardet og dokumentstyring af, administration af adgangsrettigheder, planlægning, API'er, uploads og downloads og generelt oplevelser for alt relateret til brugeren.

Storage er indstillet til **100 TB pr. node kapacitet**.

Ressourcer og grænserne for hver Premium-SKU (og equivalently størrelse A SKU) er beskrevet i følgende tabel:

| Kapacitetsnoder | V-kerner i alt | Backend-v-kerner | RAM (GB) | Frontend-v-kerner | DirectQuery/direkte forbindelse (pr. sek.) | Parallel opdatering af modeller |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3,75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7,5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

### <a name="capacity-workloads"></a>Kapacitet arbejdsbelastninger

Kapacitetarbejdsbelastninger er tjenester, som gøres tilgængelige for brugere. Understøtter kun en datasæt arbejdsbelastning, der er knyttet til Power BI-forespørgsler, der kører som standard Premium og Azure-kapaciteter. Arbejdsbyrden datasæt kan ikke deaktiveres. Yderligere arbejdsbelastninger kan aktiveres for [AI (Cognitive Services)](https://powerbi.microsoft.com/blog/easy-access-to-ai-in-power-bi-preview/), [Dataflows](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium), og [sideinddelte rapporter](paginated-reports-save-to-power-bi-service.md). Disse arbejdsbelastninger, der understøttes i Premium-abonnementer. 

Hver ekstra arbejdsbyrde giver mulighed for konfiguration af den maksimale hukommelse (som en procentdel af samlede tilgængelige hukommelse), der kan bruges af arbejdsbelastningen. Standardværdier for maksimumhukommelse bestemmes af SKU. Du kan maksimere din kapacitet tilgængelige ressourcer ved at aktivere disse yderligere arbejdsbelastninger, når de bruges. Og du kan ændre hukommelse indstillinger kun, når du har bestemt standardindstillingerne ikke opfylder dine krav til kapacitet ressource. Arbejdsbelastninger kan være aktiveret og konfigureret til en kapacitet ved kapacitetsadministratorer ved hjælp af **kapacitetsindstillinger** i den [administrationsportalen](service-admin-portal.md) eller ved hjælp af den [kapaciteter REST API'er](https://docs.microsoft.com/rest/api/power-bi/capacities).  

![Aktivér arbejdsbelastninger](media/service-admin-premium-workloads/admin-portal-workloads.png)

Hvis du vil vide mere, kan du se [konfigurere arbejdsbelastninger i Premium-kapacitet](service-admin-premium-workloads.md). 

### <a name="how-capacities-function"></a>Hvordan kapaciteter funktion

I hele tiden, Power BI-tjenesten gør det bedste ud af kapacitet ressourcer under anvendte grænser for kapaciteten, der ikke overstiger.

Kapacitet handlinger er klassificeret som enten *interaktive* eller *baggrunden*. Interaktive handlinger omfatter gengivelse af anmodninger og svare på Brugerinteraktioner (filtrering, spørgsmål og svar-forespørgsel, osv.). Generelt er import model forespørgsel hukommelse ressourcekrævende, mens forespørge modeller for DirectQuery og direkte forbindelse er CPU-intensive. Handlinger i baggrunden omfatter opdateringer af dataflows og importmodeller samt cachelagring af dashboardforespørgsler.

Det er vigtigt at forstå, interaktive handlinger, der altid er prioriteret ud over handlinger i baggrunden til at sikre den bedste mulige brugeroplevelse. Hvis der ikke er tilstrækkelige ressourcer, føjes handlinger i baggrunden til en kø for at blive behandlet, når ressourcerne frigøres. Handlinger i baggrunden, f.eks. datasæt opdateres, kan være stoppet midt i en proces med Power BI-tjenesten og føjes til en kø.

Importér modeller skal være fuldt indlæses i hukommelsen, så de kan sendes en forespørgsel eller opdateres. Power BI-tjenesten administrerer hukommelse forbrug ved hjælp af avancerede algoritmer for at sikre maksimal anvendelse af tilgængelig hukommelse, og kan medføre yderligere bekræftelse kapacitet: Mens det er muligt med en kapacitet til at gemme mange import-modeller (op til 100 TB pr. Premium-kapacitet), når deres kombinerede disklager overskrider den understøttede hukommelse (og hukommelseskrav er påkrævet til forespørgsler og opdatering), kan derefter de alle ikke indlæses i hukommelsen på på samme tid.

Importér modeller er derfor indlæses i og fjernet fra hukommelsen i henhold til forbrug. En model af import er indlæst, når den er forespurgt (interaktive operation) og endnu ikke i hukommelsen, eller når den er opdateres (handling i baggrunden).

Fjernelse af en model fra hukommelsen er kendt som *hård*. Det er en handling, som Power BI kan udføre hurtigt afhængigt af størrelsen på modellerne. Hvis kapaciteten ikke oplever noget pres på hukommelsen, indlæses modellerne i hukommelsen og forbliver der. Men, når der er ikke tilstrækkelig hukommelse til at indlæse en model, Power BI-tjenesten skal først Frigør hukommelse. Det Frigør hukommelse ved at registrere modeller, der er blevet inaktiv ved at anmode modeller, som ikke har været anvendt i de sidste tre minutter \[ [1](#endnote-1)\], og fjerner dem derefter. Hvis der ikke er nogen inaktive modeller at fjerne, forsøger Power BI-tjenesten at fjerne modeller, der er indlæst til handlinger i baggrunden. Sidste udvej, efter 30 sekunder mislykkede forsøg \[ [1](#endnote-1)\], er ikke interaktive handlingen. I dette tilfælde er rapporten brugeren besked om fejl med et forslag til at prøve igen om et øjeblik. I nogle tilfælde kan modeller blev fjernet fra hukommelsen pga. service operations.

Det er vigtigt at fremhæve, at datasættet hård er en normale og forventede funktionsmåde. Den har til formål at maksimere forbruget af hukommelse ved at indlæse og fjerne modeller, hvis størrelse tilsammen kan overskride den tilgængelige hukommelse. Dette er tilsigtet og helt åbenlyst for rapportbrugerne. Høje fjernelsesrater betyder ikke nødvendigvis, at kapaciteten har fået tildelt utilstrækkelige ressourcer. De kan dog blive et problem, hvis svartiden for forespørgsler eller opdateringer bliver påvirket af de høje fjernelsesrater.

Opdateringer af import modeller er altid hukommelsestunge som modeller, der skal indlæses i hukommelsen. Der kræves yderligere hukommelse til behandling. En fuld opdatering kan bruge ca. dobbelt så meget hukommelse, der kræves af modellen. Dette sikrer, at modellen kan forespørges, selv når der behandles, fordi sendes forespørgsler til den eksisterende model, før opdateringen er fuldført, og de nye data til modellen er tilgængelig. Trinvis opdatering kræver mindre hukommelse og kunne fuldføre hurtigere, og så kan reducere væsentligt pres på kapacitet ressourcer. Opdateringer kan også være CPU-krævende for modeller, især dem med komplekse Power-transformationer eller beregnede tabeller/kolonner, som er komplekse eller baseret på store tabeller.

Opdateringer, som f.eks. forespørgsler, kræver, at modellen indlæses i hukommelsen. Hvis der ikke er tilstrækkelig hukommelse, vil Power BI-tjenesten forsøge at udsætte inaktive modeller, og hvis det ikke er muligt (da alle modeller er aktive), sættes opdateringsjobbet i kø. Opdateringer er typisk CPU-intensive endnu mere så end forespørgsler. Der er derfor kapacitetsbegrænsninger for antallet af samtidige opdateringer, der er angivet til 1,5 gange antallet af backend-v-kerner, rundet op. Hvis der er for mange samtidige opdateringer, sættes en planlagt opdatering i kø. Når disse situationer opstår, tager det længere tid at fuldføre opdateringen. Opdateres efter behov f.eks dem, der udløses af en bruger anmoder om eller et API-kald forsøger igen tre gange \[ [1](#endnote-1)\]. Hvis der stadig er ikke tilstrækkelige ressourcer, mislykkes derefter opdateringen.

Afsnit noter:   
<a name="endnote-1"></a>\[1\] kan ændres.

### <a name="regional-support"></a>Lokal support

Når du opretter en ny kapacitet, Office 365 globale administratorer og administratorer af Power BI-tjenesten kan angive findes et område, hvor arbejdsområder, der er tildelt til kapaciteten. Dette er kendt som **Multi-Geo**. Med Multi-Geo kan organisationer opfylde krav til dataplacering ved at implementere indhold i datacentre i et bestemt område, selvom det er forskelligt fra det område, som er placeret på Office 365-abonnement. Hvis du vil vide mere, kan du se [Multi-Geo-support til Power BI Premium](service-admin-premium-multi-geo.md).

### <a name="capacity-management"></a>Kapacitetsadministration

Administration af Premium-kapaciteter omfatter oprettelse eller sletning af kapaciteter tildele administratorer tildeling af arbejdsområder, og konfiguration af arbejdsbelastninger, overvågning og foretage justeringer til at optimere ydeevnen kapacitet. 

Office 365 globale administratorer og administratorer af Power BI-tjenesten kan oprette Premium-kapaciteter fra tilgængelige v-kerner, eller rediger eksisterende Premium-kapaciteter. Når der oprettes en kapacitet, der er angivet kapacitetsstørrelse og geografiske område, og tildeles mindst én kapacitetsadministrator. 

Når der oprettes kapaciteter, de fleste administrative opgaver er udført i den [administrationsportalen](service-admin-portal.md).

![Administrationsportal](media/service-premium-what-is/premium-admin-portal.png)

Kapacitetsadministratorer kan tildele arbejdsområder til kapaciteten, Administrer brugertilladelser og Tildel andre administratorer. Kapacitetsadministratorer kan også konfigurere arbejdsbelastninger, justere hukommelse intervaller, og om nødvendigt genstarte en kapacitet, nulstilling af handlinger i tilfælde af en overbelastning af kapacitet.

![Administrationsportal](media/service-premium-what-is/premium-admin-portal-mgmt.png)

Kapacitetsadministratorer kan også sikre dig en kapacitet, der kører uden problemer. De kan overvåge kapacitet health højre i administrationsportalen eller ved hjælp af appen målepunkter for Premium-kapacitet.

Hvis du vil vide mere om oprettelse af kapaciteter, tildele administratorer og tildeling af arbejdsområder, se [administration af Premium-kapaciteter](service-premium-capacity-manage.md). Hvis du vil vide mere om roller, se [administratorroller, der er relateret til Power BI](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi).

### <a name="monitoring"></a>Overvågning

Overvågning af Premium-kapaciteter giver administratorer en forståelse af, hvordan klarer kapaciteter. Kapaciteter kan overvåges ved hjælp af administrationsportalen og [Power BI Premium-kapacitet målepunkter app](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics).

Overvågning i portalen giver et hurtigt overblik på højt niveau målepunkter, der angiver belastninger, der er placeret, og de ressourcer, der bruges af din kapacitet, udregner gennemsnittet, for de seneste syv dage. 

![Administrationsportal](media/service-premium-what-is/premium-admin-portal-health.png)

Den **Power BI Premium-kapacitet målepunkter** app indeholder de mest detaljerede oplysninger i, hvordan klarer din kapaciteter. Appen giver et overordnet dashboard og mere detaljerede rapporter.

![Appdashboardet Målepunkter](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Du kan klikke på en metriske celle for at åbne en dybtgående rapport fra appens dashboard. Rapporter giver detaljeret målepunkter og filterfunktion til detailudledning på de vigtigste oplysninger du har brug at holde dine kapaciteter, der kører korrekt.

![Periodiske spidsbelastninger af forespørgselsventetider indikerer en potentiel CPU-mætning](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Få, mere at vide om overvågning af kapaciteter se [overvågning i Power BI-administrationsportalen](service-admin-premium-monitor-portal.md) og [overvågning med Power BI Premium-kapacitet målepunkter appen](service-admin-premium-monitor-capacity.md).

### <a name="optimizing-capacities"></a>Optimering af kapaciteter

Gør det bedste ud af dine kapaciteter er afgørende for at forsikre brugerne får ydeevnen, og du får mest muligt ud af din investering i Premium. Ved at overvåge vigtige målepunkter, kan administratorer afgøre, hvordan de bedst at foretage fejlfinding af flaskehalse og nødvendige handle. Hvis du vil vide mere, kan du se [optimering af Premium-kapaciteter](service-premium-capacity-optimize.md) og [Premium-kapacitet scenarier](service-premium-capacity-scenarios.md).

### <a name="capacities-rest-apis"></a>Kapaciteter REST-API'er

Power BI REST-API'er, der indeholder en samling af [kapaciteter API'er](https://docs.microsoft.com/rest/api/power-bi/capacities). Med API'er, kan administratorer programmeringsmæssigt administrere mange aspekter af dit Premium-kapaciteter, herunder aktivering og deaktivering af arbejdsbelastninger, tildeling af arbejdsområder til en kapacitet og meget mere.

## <a name="large-datasets"></a>Store datasæt

Afhængigt af SKU, Power BI Premium understøtter Power BI Desktop (.pbix) modelfiler op til maksimalt **10 GB** størrelse. Når du er indlæst, kan modellen derefter publiceres til et arbejdsområde, der er tildelt til en Premium-kapacitet. Datasættet kan derefter opdateres til op til **12 GB** størrelse.

### <a name="size-considerations"></a>Overvejelser i forbindelse med størrelse

Store modeller kan være ressourcekrævende. Du skal have mindst en P1-SKU for nogen modeller, der er større end 1 GB. Selvom udgivelse af store modeller til arbejdsområder understøttes af A-SKU'er op til A3 kunne arbejde, opdatere dem vil ikke.

I nedenstående tabel beskrives de anbefalede SKU'er til forskellige .pbix-størrelser:

   |SKU  |.pbix-størrelse   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3, P4, P5    | op til 10 GB   |

Power BI Embedded A4-SKU'en er lig med P1-SKU'en, A5-SKU'en = P2 og A6-SKU'en = P3. Bemærk, at hvis du udgiver store modeller til A- og EM-SKU'er, kan det returnere fejl, der ikke er specifikke for størrelsesbegrænsningen af modellen i den delte kapacitet. Opdateringsfejl for store modeller i A- og EM-SKU'er skyldes sandsynligvis timeout. 

Dine .pbix-filer repræsenterer data i en *stærkt komprimeret tilstand*. Data udvides sandsynligvis flere gange, når de indlæses i hukommelsen, og herfra vil de sikkert blive udvidet gentagne gange under dataopdatering.

Planlagt opdatering af store datasæt kan tage lang tid og være ressourcekrævende. Det er vigtigt, at du ikke planlægge for mange overlappende opdateringer. Det anbefales [trinvis opdatering](service-premium-incremental-refresh.md) er konfigureret, fordi det er hurtigere og mere pålidelige, og forbruger færre ressourcer.

Den første rapportindlæsning af store datasæt kan tage lang tid, hvis det er et stykke tid siden, det sidste datasæt blev brugt. En linje for længere rapportindlæsninger viser indlæsningens status.

Mens hukommelse pr. forespørgsel og tidsbegrænsninger er meget større i Premium-kapacitet, kan det anbefales, at du bruger filtre og udsnit for at vise kun det mest nødvendige visuelle elementer.

## <a name="incremental-refresh"></a>Trinvis opdatering

Trinvis opdatering giver en uundværlig del af at have og vedligeholdelse af store datasæt i Power BI Premium. Trinvis opdatering har mange fordele, f.eks, opdateringer er hurtigere, fordi kun data, der har ændret skal opdateres. Opdateringer er mere pålidelige, fordi det er ikke nødvendigt at vedligeholde langvarige forbindelser til svingende datakilder. Ressourceforbrug er reduceret, fordi mindre data til at opdatere reducerer overordnede forbruget af hukommelse og andre ressourcer. Politikker for trinvis opdatering, der er defineret i **Power BI Desktop**, og anvendes, når der udgives til et arbejdsområde i Premium-kapacitet. 

![Detaljer om opdatering](media/service-premium-incremental-refresh/refresh-details.png)

Hvis du vil vide mere, kan du se [trinvis opdatering i Power BI Premium](service-premium-incremental-refresh.md).

## <a name="paginated-reports"></a>Sideinddelte rapporter

Sideinddelte rapporter, der understøttes på P1-P3 og A4_A6 SKU'er, er baseret på teknologi i Report Definition Language (RDL) i SQL Server Reporting Services. Mens baseret på RDL-teknologi, er det ikke den samme som Power BI Report Server, som er en kan downloades reporting platform, som du kan installere i det lokale miljø, også inkluderet i Power BI Premium. Sideinddelte rapporter er formateret til at passe godt i en side, der kan udskrives eller delt. Data vises i en tabel, selvom tabellen strækker sig over flere sider. Ved hjælp af den gratis [ **Power BI Report Builder** ](https://go.microsoft.com/fwlink/?linkid=2086513) Windows Desktop-programmet, brugere forfatter sideinddelte rapporter og publicere dem til tjenesten.

Paginated rapporter er i Power BI Premium, en arbejdsbelastning, der skal være aktiveret for en kapacitet ved hjælp af administrationsportalen. Kapacitetsadministratorer kan aktivere og derefter angive mængden hukommelse, som en procentdel af den kapacitet, overordnede hukommelsesressourcer. Premium kører i modsætning til andre typer arbejdsbelastninger, sideinddelte rapporter i en opbevaret plads i kapaciteten. Uanset om arbejdsbelastningen er aktiv, bruges den maksimale hukommelse, der er angivet for dette område. Standarden er 20%. 

Hvis du vil vide mere, kan du se [sideinddelte rapporter i Power BI Premium](paginated-reports-report-builder-power-bi.md). Hvis du vil vide mere om aktivering af Paginated rapporter arbejdsbyrden, se [konfigurere arbejdsbelastninger](service-admin-premium-workloads.md).

## <a name="power-bi-report-server"></a>Power BI-rapportserver
 
Power BI Report Server inkluderet med med Power BI Premium, som er en *i det lokale miljø* rapportserver med en webportal. Du kan opbygge din BI miljø i det lokale miljø og distribuere rapporter bag din organisations firewall. Rapportserver giver brugerne adgang til omfattende interaktiv og enterprise-funktionalitet til rapportering af SQL Server Reporting Services. Brugere kan udforske visuelle data og hurtigt finde mønstre for at træffe bedre, hurtigere beslutninger. Report Server indeholder styring på dine egne betingelser. Hvis tid, der kommer, og når Power BI Report Server nemt at overføre til cloudmiljøet, hvor din organisation kan drage fuld nytte af alle funktioner i Power BI Premium.

Hvis du vil vide mere, kan du se [Power BI Report Server](report-server/get-started.md).

## <a name="unlimited-content-sharing"></a>Ubegrænset indholdsdeling

Med Premium, alle, uanset om de er i eller uden for din organisation kan få vist dine Power BI-indhold, herunder sideinddelte og interaktive rapporter uden at købe individuelle licenser. 

![Deling af indhold](media/service-premium-what-is/premium-sharing.png)

Premium giver mulighed for omfattende distribution af indhold af Pro-brugere uden at der kræves en Pro-licenser til modtagere, der kan få vist indholdet. Pro-licenser er påkrævet for oprettere af indhold. Oprettere oprette forbindelse til datakilder, modeldata, og oprette rapporter og dashboards, der er pakket som arbejdsområde apps. 

Hvis du vil vide mere, kan du se [Power BI-licenser](service-admin-licensing-organization.md).

## <a name="tool-connectivity-preview"></a>Værktøjet forbindelse (prøveversion)

Under hjelmen?, virksomheden dokumenterede Microsoft **Analysis Services Vertipaq-programmet** driver Power BI-datasæt. Analysis Services leverer programmering og klientprogram og værktøj understøtter via klientbiblioteker og API'er, der understøtter åbne standarder XMLA-protokollen. Datasæt i Power BI Premium understøtter i øjeblikket *skrivebeskyttet* handlinger fra Microsoft og tredjeparter klientprogrammer og værktøjer via **XMLA-slutpunkter**. 

Microsoft-værktøjer som SQL Server Management Studio og SQL Server Profiler og tredjeparts-apps, f.eks DAX-Studio og programmer til visualisering, kan oprette forbindelse til og forespørge gratis eller prisbillige datasæt ved hjælp af XMLA, DAX, MDX, Dmv'er og spor hændelser. 

![SSMS](media/service-premium-what-is/connect-tools-ssms-dax.png)

Hvis du vil vide mere, kan du se [Opret forbindelse til datasæt med klientprogrammer og værktøjer](service-premium-connect-tools.md).

## <a name="acknowledgements"></a>Godkendelser

Peter Myers, Data Platform MVP og uafhængige BI-ekspert med [bitvis løsninger](https://www.bitwisesolutions.com.au/), og Microsoft Power BI Customer Advisory Team (CAT) er større bidragydere til denne artikel.

## <a name="next-steps"></a>Næste trin

> [!div class="nextstepaction"]
> [Administration af Premium-kapaciteter](service-premium-capacity-manage.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

||||||
