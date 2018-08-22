---
title: Power BI-ydeevne – bedste praksis
description: Denne artikel indeholder en vejledning i at oprette hurtige og pålidelige rapporter i Power BI
author: MarkMcGeeAtAquent
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: kfile
LocalizationGroup: Reports
ms.openlocfilehash: 2e8888679f36b64a6fc5956a9ca10dc3d07dce1a
ms.sourcegitcommit: 8b2ae15eb0e39cce29f3bf466ab7768f3f7c7815
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2018
ms.locfileid: "40256910"
---
# <a name="power-bi-performance-best-practices"></a>Power BI-ydeevne – bedste praksis 
Denne artikel giver vejledning i at oprette hurtige og pålidelige rapporter i Power BI.  

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Brug filtre for kun at vise de mest nødvendige visuelle elementer i rapporter 

Jo flere data et visuelt element skal vise, jo langsommere er indlæsningen af det pågældende visuelle element. Dette princip kan synes indlysende, men glemmes dog let. Et eksempel: Lad os antage, at du har et stort datasæt. Oven i det opretter du en rapport med en tabel af tabellen. Slutbrugere benytter udsnitsværktøj på siden for at få adgang til de ønskede rækker – de er typisk kun interesserede i et fåtal af rækker.

En hyppig fejl er, at standardvisningen af tabellen er ufiltreret – dvs. af samtlige 100M+ rækker. Dataene til disse rækker skal indlæses i hukommelsen og dekomprimeres ved hver opdatering. Dette belaster hukommelsen enormt. Løsningen: reducer det maksimale antal elementer, som tabellen viser, ved hjælp af filteret "Top N". Det maksimale antal elementer kan være meget større, end brugeren har brug for, f.eks. 10.000. Som et resultat heraf er slutbrugerens oplevelse uændret, men rapportens brug af hukommelsen faldt med flere ordrers størrelse, og ydeevnen blev forbedret tilsvarende.

En tilsvarende tilgang til ovenstående anbefales stærkt til alle visuelle elementer på dine rapporter. Stil dig selv spørgsmålet, om alle dataene i dette visuelle element er nødvendige. Kan mængden af de viste data i det visuelle element på nogen måde begrænses via filtrering uden stort set at påvirke slutbrugerens oplevelse? Bemærk, at især tabeller kan være meget dyre. 
 
## <a name="limit-visuals-on-report-pages"></a>Begræns visuelle elementer på rapportsider 
Ovenstående gælder tilsvarende for antallet af visuelle elementer på en relevant rapport. Det anbefales kraftigt, at du begrænser antallet af visuelle elementer på en relevant rapport til det mest nødvendige. Detaljeadgangssider kan med stor fordel bruges til at få vist yderligere detaljer uden at proppe yderligere visuelle elementer ind i rapporten.  
 
## <a name="optimize-your-model"></a>Optimer din model 
Et par bedste praksisser: 
 
- Ubrugte tabeller eller kolonner skal fjernes, hvis det er muligt. 
- Undgå adskilte optællinger på felter med høj kardinalitet – dvs. millioner af entydige værdier.  
- Tag forholdsregler mod felter med unødvendig præcision og høj kardinalitet. Du kan f.eks. opdele særdeles unikke datatime-værdier i særskilte kolonner – f.eks. måned, år, dato osv. Eller, hvor det er muligt, benytte afrunding af højpræcisionsfelter for at reducere kardinalitet – (f.eks. 13.29889 -> 13,3). 
- Brug heltal i stedet for strenge, hvor det er muligt. 
- Vær forsigtig med DAX-funktioner, som skal teste hver række i en tabel – f.eks. RANKX – i værste fald kan disse funktioner øge kørsels- og hukommelseskrav eksponentielt, hvilket giver lineære forøgelser af tabelstørrelsen. 
- Når der oprettes forbindelse til datakilder via DirectQuery, bør du overveje at indeksere kolonner, der ofte filtreres eller opdeles igen – dette vil forbedre rapportens svartid væsentligt.  
 

Se [DirectQuery i SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) for at få mere vejledning i at optimere datakilder til DirectQuery. 
 
## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>DirectQuery og Direkte forbindelse: få indsigt i underliggende datakilders ydeevne 

I situationer med DirectQuery eller direkte forbindelse – når brugere besøger en Power BI-rapport, så sender Power BI forespørgsler i realtid til den underliggende datakilde. Når datakilden returnerer med forespørgselsdataene, så gengives rapporten. Som et resultat heraf afhænger din rapports ydeevne i disse tilfælde hovedsageligt af den underliggende datakildes ydeevne.

I denne situation er det vigtigt at have forståelse for din underliggende datakildes ydeevne. Forskellige datakilder har forskellige værktøjer til forståelse af forespørgslers ydeevne. SQL Server og Azure SQL omfatter eksempelvis Query Store, som henter en oversigt over forespørgsler og deres kørselsstatistik.

Du kan bruge tommelfingerreglen om, at når du implementerer Power BI-rapporter, der er baseret på DirectQuery og direkte forbindelse, så kan du prøve at gøre som dine slutbrugere i Power BI Desktop. Hvis rapporten er lang tid om at indlæse i Power BI Desktop, så vil den næsten helt sikkert også være lang tid om at indlæse i dine slutbrugeres tjeneste. 
 
## <a name="directquery-best-practices"></a>DirectQuery – bedste praksis 
I følgende afsnit beskrives generelle bedste praksisser for oprettelse af forbindelse via DirectQuery.
  
### <a name="db-design-guidance"></a>Vejledning i DB-design 
- Skub beregnede kolonner og målinger til kilden, når det er muligt – jo tættere de er på kilden, jo større er chancen for forbedret ydeevne. 
- Optimer! Forstå afviklingsplanerne for dine forespørgsler, føj indekser til hyppigt filtrerede kolonner osv. 

### <a name="modelling-guidance"></a>Vejledning i udformning 
- Begynd i Power BI Desktop. 
- Undgå komplekse forespørgsler i Forespørgselseditoren. 
- Brug ikke relativ datofiltrering i Forespørgselseditoren.  
- Hold dig indledningsvist til simple målinger, og øg så kompleksitet lidt efter lidt. 
- Undgå relationer på beregnede kolonner og entydige id-kolonner. 
- Prøv at indstille "Antag referentiel integritet" på relationer – i mange tilfælde kan dette forbedre forespørgslens ydeevne væsentligt.  

### <a name="general"></a>Generelt 
- Anvend først filtre. 
- Overvej at slå interaktion mellem visuelle elementer fra – dette vil reducere forespørgselsbelastningen, når brugere benytter tværgående fremhævning. 
- Begræns antallet af visuelle elementer og data pr. visuelle elementer, som beskrevet ovenfor. 
- Aktivering af sikkerhed på rækkeniveau, kan det medføre betydelige ændringer i ydeevne. Sørg for at afprøve de forskellige sikkerhedsroller på rækkeniveau, som dine brugere antager. 
- Bemærk, at der gennemtvinges timeout på forespørgselsniveau af tjenesten for at sikre, at forespørgsler, der har kørt i lang tid, ikke kan monopolisere systemressourcer. Forespørgsler, der tager længere tid end 225 sekunder, får timeout og resulterer i en fejl på visualiseringsniveau. 

## <a name="understanding-dashboards-and-query-caches"></a>Forstå dashboards og forespørgselscacher 
Visuelle elementer, der er fastgjort til dashboards, håndteres af forespørgselscachen, når dashboardet indlæses. Omvendt, når du besøger en rapport, så oprettes forespørgslerne ad hoc til datakilden – En Power BI-tjeneste (i tilfælde af import) eller datakilden, du angiver (i tilfælde af DirectQuery eller direkte forbindelse).  
 
> [!NOTE]
> Når du fastgør direkte rapportfliser til et dashboard, håndteres de ikke af forespørgselscachen – i stedet fungerer de som rapporter, og afgiver forespørgsler til back-end-kerner ad hoc. 
 

Som navnet antyder sikrer modtagelse af data fra forespørgselscachen en bedre og mere ensartet ydeevne end at afhænge af datakilden. Én måde at drage fordel af denne funktionalitet på er ved at gøre dashboards til den første landingsside for dine brugere. Fastgør ofte brugte og hyppigt anvendte visuelle elementer til dashboardene. På denne måde bliver dashboards et praktisk "første forsvarsværk", som leverer konsekvent ydelse med mindre belastning af kapaciteten. Brugerne kan stadig klikke sig gennem rapporten for at gå ned i detaljerne.  
 

Bemærk, at for DirectQuery og direkte forbindelse, så opdateres denne forespørgselscache periodisk ved at forespørge om datakilden. Dette sker som standard hver time, men kan konfigureres i datasættets indstillinger. Hver forespørgselscacheopdatering sender forespørgsler til den underliggende datakilde om at opdatere cachen. Antallet af forespørgsler, der oprettes, afhænger af antallet af visuelle elementer, der er fastgjort til dashboards, der afhænger af den pågældende datakilde. Bemærk, at hvis sikkerhed på rækkeniveau er aktiveret, så genereres forespørgsler for hver særskilte sikkerhedskontekst. Hvis du f.eks. har to forskellige roller, som brugerne falder ind under, med to forskellige visninger af data, så oprettes der to sæt af forespørgsler under opdatering af forespørgselscachen. 
 
## <a name="understand-custom-visual-performance"></a>Forstå brugerdefinerede visuelle elementers ydeevne 
Sørg for at gennemprøve hvert brugerdefinerede visuelle element for at sikre høj ydeevne. Brugerdefinerede visuelle elementer med dårlig optimering kan påvirke hele rapportens ydeevne negativt. 
 
## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>Gå i dybden med forespørgslers ydeevne med SQL Profiler og Power BI Desktop

For at dykke længere ned i, hvilke visuelle elementer der optager mest tid og ressourcer, så kan du forbinde SQL Profiler til Power BI Desktop for at få et fuldt overblik over forespørgslers ydeevne.

> [!NOTE]
> Power BI Desktop understøtter, at der oprettes forbindelse til en port til diagnosticering. Med porten til diagnosticering kan andre værktøjer oprette forbindelse til og udføre sporing til diagnosticering. *Det understøttes ikke at ændre modellen! Ændringer i modellen vil muligvis beskadige data eller medføre tab af data.*

Følg nedenstående anvisninger:
  
1. **Installér SQL Server Profiler, og kør Power BI Desktop** 

   SQL Server Profiler fås som del af SQL Server Management Studio. 
 
2. **Fastlæg hvilken port, der bruges af Power BI Desktop** 

   Kør kommandoprompten eller PowerShell med administratorrettigheder, og brug netstat til at finde den port, der bruger Power BI Desktop til analysering:

   `> netstat -b -n` 

   Outputtet bør være en liste over programmer, og deres åbne porte, f.eks.:  

   TCP    [::1]:55786            [::1]:55830            OPRETTET 

   [msmdsrv.exe] 

   Søg efter porten, der bruges af msmdsrv.exe, og udskriv til senere brug. I dette tilfælde kan du bruge port 55786. 
3. **Forbind SQL Server Profiler til Power BI Desktop** 

   - Start SQL Server Profiler fra **Start**-menuen 
   - **Filer** > **Ny sporing** 
   - Servertype: Analysetjenester 
   - Servernavn: localhost: [portnummeret findes ovenfor] 
   - Vælg **Kør** på den næste skærm 
   - Nu er SQL Profiler dynamisk og profilerer aktivt forespørgslerne, som Power BI Desktop sender. 
   - Når forespørgslerne udføres, kan du se deres respektive varigheder og CPU-tider – disse oplysninger kan du bruge til at fastlægge, hvilke forespørgsler der er flaskehalse.  

Du kan identificere de forespørgsler, der bruger den længste CPU-tid, som igen er sandsynlige flaskehalse for ydeevnen, via SQL Profiler. De visuelle elementer, som udfører disse forespørgsler, bør derefter være fokuspunkt for fortsat optimering. 

## <a name="gateway-best-practices"></a>Gateway – bedste praksisser 

Datagatewayen i det lokale miljø er et fantastisk værktøj til at forbinde Power BI tjenesten med dataene i dit lokale miljø. Men samtidig kan dårlig planlægning gøre, at den bliver en flaskehals for rapporters ydeevne. Dette er tilfældet for DirectQuery-/direkte forbindelse-datasæt, hvor alle forespørgsler og forespørgselssvar passerer igennem gatewayen. Nedenfor nævnes nogle bedste praksisser til sikring af højtydende gateways: 
 
- **Brug Enterprise-tilstand**, i modsætning til personlig tilstand. 
- **Anbefalede hardwarespecifikationer for gatewayen** – 8 CPU-kerner, 16 GB RAM. 
- **Konfigurer overvågning** – konfigurer overvågning af ydeevnen på gatewaymaskinen for at se, om gatewayen er ved at blive overbelastet og en flaskehals. Du kan finde flere oplysninger i [Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md).
- **Skaler op eller skaler ud** – Hvis gatewayen rent faktisk er ved at blive en flaskehals, så bør du overveje at skalere op (dvs. at flytte gatewayen til en stærkere maskine med mere CPU og RAM) eller skalere ud (f.eks. fordele datasæt til forskellige gateways). 
- **Separat import vs. DirectQuery** – hvis du skalerer ud, skal du overveje at adskille gatewayene, der er ansvarlige for import i forhold til dem, der er ansvarlige for DirectQuery. 
 
## <a name="network-latency"></a>Netværksventetid 
Netværksventetid kan påvirke rapporters ydeevne ved at øge den tid, der kræves for anmodninger om at oprette forbindelse til Power BI-tjenesten, og for at svarene leveres. Lejere i Power BI tildeles et bestemt område. Du kan få vist din lejers "hjemmeområde" ved at gå til powerbi.com og vælge **?** øverst til højre og derefter **Om Power BI**. Når brugere fra en lejer tilgår Power BI-tjenesten, så føres vedkommendes anmodninger altid til dette område. Når anmodninger når Power BI-tjenesten, sender tjenesten muligvis flere anmodninger endnu – f.eks. til den underliggende datakilde eller gatewayen – som også er underlagt netværksventetid. 

Funktioner som f.eks. [Azure Speed Test](http://azurespeedtest.azurewebsites.net/) kan give en praj om netværksventetiden mellem klienten og Azure-området. Generelt bør du begrænse indvirkningen af netværksventetider ved at stræbe efter at holde datakilder, gateways og din Power BI-klynge så tæt på hinanden som muligt. Hvis netværksventetid er et problem, kan du prøve at finde gateways og datakilder, der ligger tættere på din Power BI-klynge ved at placere dem på virtuelle maskiner. 

Hvis du yderligere vil afhjælpe netværksventetid, bør du overveje at bruge [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/), som er i stand til at oprette hurtigere og mere pålidelige netværksforbindelser mellem dine klienter og Azure-datacentre. 

## <a name="next-steps"></a>Næste trin
- [Planlægning af en installation af Power BI Enterprise](https://aka.ms/pbienterprisedeploy) med komplette retningslinjer for Power BI-installationer i stor skala 
- [DirectQuery i SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) 
- [[YouTube] Oprettelse af hurtige og pålidelige rapporter i Power BI](https://www.youtube.com/watch?v=GhiJABR7XX0) 
- [[YouTube] Power BI Enterprise-installationer](https://www.youtube.com/watch?v=K-zEWICvICM)  
 
 
