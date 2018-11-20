---
title: 'Sideinddelte rapporter i Power BI: Ofte stillede spørgsmål (prøveversion)'
description: I denne artikel finder du svar på ofte stillede spørgsmål om sideinddelte rapporter. Disse rapporter indeholder megen formatering og er perfekt pixeleret output, der er optimeret til udskrivning eller generering af PDF.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 0ddf95563c52af135ac7ae4fe71aeddcd2ce7313
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/07/2018
ms.locfileid: "51267275"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Sideinddelte rapporter i Power BI: Ofte stillede spørgsmål (prøveversion)

I denne artikel finder du svar på ofte stillede spørgsmål om sideinddelte rapporter. Disse rapporter indeholder megen formatering og er perfekt pixeleret output, der er optimeret til udskrivning eller generering af PDF. De kaldes "sideinddelte", fordi de er formateret til at passe godt på flere sider. Sideinddelte rapporter er baseret på RDL-rapportteknologien i SQL Server Reporting Services. 

I denne artikel finde du svar på mange almindelige spørgsmål, som folk har om sideinddelte rapporter i Power BI Premium, og om Report Builder, som er et separat værktøj til oprettelse af sideinddelte rapporter. Du skal bruge en Power BI Pro-licens for at publicere en rapport i tjenesten. Du kan publicere og dele sideinddelte rapporter i Mit arbejdsområde eller i apparbejdsområder, så længe arbejdsområdet er placeret i en Power BI Premium-kapacitet. 

## <a name="administration"></a>Administration

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Hvilken størrelse Premium-kapacitet for sideinddelte rapporter skal jeg bruge?

Arbejdsbelastningen for sideinddelte rapporter er tilgængelig på P1-P3 SKU'er som en offentlig prøveversion.  Du kan også bruge den til dev/test-scenarier med A4-A6 SKU'er.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Hvad er den maksimale hukommelsestærskel, jeg kan angive, for sideinddelte rapporter i min kapacitet?

I øjeblikket kan du kun reservere 50 % af hukommelsen til denne arbejdsbelastning. 

### <a name="how-does-user-access-work-for-paginated-reports"></a>Hvordan fungerer brugeradgang til sideinddelte rapporter?

Brugeradgang til sideinddelte rapporter er det samme som brugeradgang til alt andet indhold i Power BI-tjenesten 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Hvordan slår jeg arbejdsbelastningen for mine sideinddelte rapporter til/fra?

Administratoren af kapacitet kan aktivere eller deaktivere arbejdsbelastningen for sideinddelte rapporter på siden med administratorportalen for kapacitet.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Hvordan overvåger jeg forbrug af sideinddelte rapporter i min lejer?

Office 365-overvågningslogge indeholder detaljerede oplysninger om forbrug af denne rapporttype under følgende hændelser: 

- Vis Power BI-rapport
- Slet Power BI-rapport
- Opret Power BI-rapport
- Downloadet Power BI-rapport

Feltet ReportType har værdien "PaginatedReport" for at identificere sideinddelte rapporter i modsætning til Power BI-rapporter.

Desuden indeholder overvågningsloggene følgende hændelser for sideinddelte rapporter:

- Bundne Power BI-datasæt til gateway
- Udforsk Power BI-datakilde
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Kan jeg overvåge denne arbejdsbelastning via appen til overvågning af Premium-kapacitet?

Ikke endnu. Overvågning bliver tilgængelig som en offentlig prøveversion som en ny fane i den eksisterende rapport med samme relevante oplysninger, du har for dine Power BI-datasæt.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Skal jeg have en Pro-licens for at oprette og publicere sideinddelte rapporter?

Ja. Du kan ikke uploade rapporter til arbejdsområdet uden en Pro-licens. Du kan downloade og prøve Report Builder uden Pro-licensen, men du kan ikke publicere de sideinddelte rapporter, du opretter. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Hvad nu hvis jeg har en sideinddelt rapport i et arbejdsområde, og arbejdsbelastningen for sideinddelte rapporter er slået fra?

Du får vist en fejlmeddelelse, og du kan ikke få vist rapporten, før arbejdsbelastningen er slået til igen. Du kan stadig slette rapporten fra arbejdsområdet.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>Hvad er standardhukommelsen for hver af de Premium SKU'er, der understøttes for sideinddelte rapporter?

Standardhukommelsen for hver Premium SKU for sideinddelte rapporter er:

- **P1/A4**: 20 % som standard; minimum 10 %
- **P2/A5**: 10 % som standard; minimum 5 %
- **P3/A6**: 5 % som standard; minimum 2,5 %

## <a name="general"></a>Generelt

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Hvornår skal jeg bruge en sideinddelt rapport i forhold til en Power BI-rapport?

Sideinddelte rapporter er bedst til scenarier, hvor der kræves megen formatering og perfekt pixeleret output, der er optimeret til udskrivning eller generering af PDF.  Et driftsregnskab er et godt eksempel på den type rapport, du sandsynligvis ville oprette som en sideinddelt rapport.  

Power BI-rapporter er optimeret til udforskning og interaktivitet.  En salgsrapport, hvor forskellige sælgere vil opdele dataene i den samme rapport for deres specifikke område/branche/kunde og se, hvordan tallene ændres, vil fungere bedst som en Power BI-rapport.

### <a name="the-documentation-says-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Ifølge dokumentationen er Report Builder det foretrukne værktøj til oprettelse. Kan jeg oprette sideinddelte rapporter i SQL Server Data Tools til Power BI?

Ja, men Power BI-tjenesten giver dig kun mulighed for at uploade et enkelt element ad gangen, så mange af de scenarier, forfattere bruger med SQL Server Data Tools (SSDT), understøttes endnu ikke. Du kan se en komplet [liste over ikke-understøttede funktioner](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) senere i disse Ofte stillede spørgsmål.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Hvilke versioner af Report Builder understøttes?

Brug den nyeste version af SQL Server 2016 Report Builder til at udarbejde og publicere dine rapporter i Power BI-tjenesten. Installér [Report Builder fra Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Hvordan flytter jeg eksisterende rapporter, som jeg har gemt i SQL Server Reporting Services, til Power BI?

Du skal downloade rapporten fra serveren og derefter uploade den til Power BI via portalen.  Der er intet overførselsværktøj tilgængeligt på nuværende tidspunkt, men vi ser på at oprette et, når den offentlige prøveversion er gennemført, og vi har fået det rette niveau af funktionsparitet mellem produkterne.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Kan jeg åbne rapporter og publicere direkte i tjenesten?

Ikke på nuværende tidspunkt. Vi tilføjer understøttelse af åbning af rapporter og publicering af dem direkte i tjenesten fra Report Builder på et tidspunkt, ligesom du kan med Power BI Desktop.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Hvilke funktioner for sideinddelte rapporter i SSRS understøttes endnu ikke i Power BI?

Sideinddelte rapporter understøtter i øjeblikket ikke følgende elementer:

- Delte datakilder
- Delte datasæt
- Underrapporter
- Handlinger for klikfrekvens og detaljeadgang
- Linkede rapporter
- Bogmærker
- Lag i Bing-kort
- Brugerdefinerede skrifttyper
- Skjulte parametre

Slå til/fra og interaktiv sortering er endnu ikke i produktion, men de forventes at blive det snart.    

Du får vist en fejlmeddelelse, hvis du forsøger at uploade en fil, som indeholder en ikke-understøttet funktion i Power BI-tjenesten – med undtagelse af slå til/fra og sortering.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Hvilke datakilder understøttes i øjeblikket for sideinddelte rapporter?

Vi understøtter Azure SQL Database samt SQL Server- og SQL Server Analysis Services-tabelmodeller (SSAS) ved hjælp af gatewayen i det lokale miljø. Vi understøtter i øjeblikket ikke flerdimensionelle SSAS-modeller (MDX).

Når du åbner SSAS gennem gatewayen, skal den bruger, hvis legitimationsoplysninger er gemt, have administratorrettigheder i SSAS for at kunne arbejde via denne Gateway.

### <a name="what-authentication-methods-do-you-support"></a>Hvilke godkendelsesmetoder understøttes?

I øjeblikket skal du gemme et brugernavn og en adgangskode med datakilden på portalen eller i gatewayen.  Yderligere godkendelsesmetoder til understøttelse af ting som sikkerhed på rækkeniveau kommer senere i prøveversionen.

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Kan jeg bruge et Power BI-datasæt som en datakilde til min sideinddelte rapport?

Ikke endnu, men denne understøttelse er planlagt til at komme snart.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Kan jeg bruge gemte procedurer via denne gateway?

Du kan bruge en gemt procedure via gatewayen, men ikke hvis den gemte procedure indeholder parametre.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Hvilke eksportformater er tilgængelige for min rapport i Power BI-tjenesten?

Du kan eksportere til Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, .CSV, XML og MHTML.

### <a name="can-i-print-paginated-reports"></a>Kan jeg udskrive sideinddelte rapporter?

I øjeblikket kan du eksportere til PDF og udskrive filen. Udskrivning direkte fra en sideinddelt rapport bliver snart tilgængelig. 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>Er mailabonnementer tilgængelige for sideinddelte rapporter?

Nej, mailabonnementer kommer senere.

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>Hvilke funktioner fra SSRS understøttes i Power BI-tjenesten?

Vores plan er at levere en så tæt paritet mellem de to produkter som muligt.  Der er visse ting ved SSRS og Power BI, som nok ikke vil give mening at prøve at ændre for at få det til at passe til eksisterende SSRS-mønstre, f.eks. de forskellige tilladelsesmodeller i Power BI, men vi kigger efter feedback fra kunder og partnere for at kunne træffe den slags beslutninger.

### <a name="can-i-run-custom-code-in-my-report"></a>Kan jeg køre brugerdefineret kode i min rapport?

Ja, vi understøtter muligheden for at køre kode i dine rapporter, ligesom du kan i SSRS.

### <a name="does-this-mean-ssrs-is-going-away"></a>Betyder det, at SSRS forsvinder?

Overhovedet ikke.  Dette nye tilbud giver kunderne en cloudbaseret mulighed for deres sideinddelte rapporter.  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Kan jeg bruge Power BI Embedded til at integrere mine sideinddelte rapporter i en app, jeg er vært for?

Vi har planer om at understøtte dette scenarie med eksisterende Power BI-API'er, men vi har endnu ikke en tidsramme for, hvornår dette scenarie vil være tilgængeligt.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Kan jeg få detaljeadgang fra en Power BI-rapport til en sideinddelt rapport?

Ikke endnu, men vi har helt sikkert planer om at understøtter dette scenarie.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Kan jeg dele indhold i min sideinddelte rapport via en Power BI-app?

I øjeblikket kan du dele individuelle sideinddelte rapporter med andre brugere via delingshandlingen på portalen. Vi understøtter endnu ikke deling i en app, men det forventer vi at gøre snart. Der er også delingsknappen på værktøjslinjen.

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Vil andre rapportspecifikke funktioner i Power BI, f.eks. fastgørelse af rapportfelter til dashboards, fungere med sideinddelte rapporter?

Vi har planer om, at rapporterne skal understøtte de samme overordnede scenarier i tjenesten så meget som muligt.  Selvom værktøjet til at oprette dem er forskelligt, er det, set fra en brugers synspunkt, ideelt set blot endnu en rapport på deres liste på portalen. De er ligeglade med, hvordan den blev oprettet, så længe de kan gøre det, de har brug for.  Et godt eksempel på denne funktionsparitet er understøttelsen af planlagte kommentarer. Selvom selve funktionen muligvis fungerer en smule anderledes for hver rapporttype, vil du kunne bruge kommentarer til begge.

### <a name="are-you-planning-to-create-a-new-authoring-tool-for-paginated-reports-in-the-power-bi-service--we-cant-do-everything-we-need-to-with-report-builder-today"></a>Er der planer om at oprette et nyt værktøj til oprettelse af sideinddelte rapporter i Power BI-tjenesten?  Vi kan endnu ikke gøre alt det, vi gerne vil med Report Builder.

Vi undersøger stadig forskellige muligheder for at få de bedste værktøjer, men du kan være sikker på, at vi vil understøtte funktioner som ALM, brugerdefinerede udvidelser og andre funktioner, der ellers kun er inkluderet i et af værktøjerne til oprettelse til SSRS. 

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>Er der planer om et overførselsværktøj, så SSRS-kunder kan flytte deres eksisterende rapporter og aktiver til Power BI?

Ja, men ikke før kernesættet af understøttede funktioner i Power BI-tjenesten er fuldført.

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>Kommer jeg nogensinde til at kunne oprette både sideinddelte rapporter og Power BI-rapporter i et enkelt værktøj til oprettelse?

Vi har i øjeblikket ingen planer om et enkelt værktøj til oprettelse, men vi undersøger forskellige måder, hvorpå vi potentielt kan distribuere værktøjerne til oprettelse samlet som en enkelt BI-pakke i stedet for at skulle have forskellige downloads/branding.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Er der et kontrolelement til rapportfremviser for sideinddelte rapporter i Power BI-tjenesten?

Nej, kontrolelementet til rapportfremviser er i øjeblikket ikke tilgængeligt.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Kan man søge efter sideinddelte rapporter fra den nye Hjem-oplevelse i Power BI-tjenesten?

Nej, du kan i øjeblikket ikke søge efter dine sideinddelte rapporter fra Hjem.  Du kan dog se dem i andre dele af den nye Hjem-oplevelse.

## <a name="next-steps"></a>Næste trin

- [Installér Report Builder fra Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613)
- [Selvstudium: Opret en sideinddelt rapport](paginated-reports-quickstart-aw.md)