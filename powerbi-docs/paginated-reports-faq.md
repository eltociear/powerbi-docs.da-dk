---
title: 'Sideinddelte rapporter i Power BI: Ofte stillede spørgsmål'
description: I denne artikel finder du svar på ofte stillede spørgsmål om sideinddelte rapporter. Disse rapporter indeholder megen formatering og er perfekt pixeleret output, der er optimeret til udskrivning eller generering af PDF.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: overview
ms.date: 09/04/2019
ms.openlocfilehash: 2be953c31ba3090e83e58f8e5626bb83e249556e
ms.sourcegitcommit: 09ee1b4697aad84d8f4c9421015d7e4dbd3cf25f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/04/2019
ms.locfileid: "70302702"
---
# <a name="paginated-reports-in-power-bi-faq"></a>Sideinddelte rapporter i Power BI: Ofte stillede spørgsmål 

I denne artikel finder du svar på ofte stillede spørgsmål om sideinddelte rapporter. Disse rapporter indeholder megen formatering og er perfekt pixeleret output, der er optimeret til udskrivning eller generering af PDF. De kaldes "sideinddelte", fordi de er formateret til at passe godt på flere sider. Sideinddelte rapporter er baseret på RDL-rapportteknologien i SQL Server Reporting Services. 

I denne artikel finde du svar på mange almindelige spørgsmål, som folk har om sideinddelte rapporter i Power BI Premium, og om Report Builder, som er et separat værktøj til oprettelse af sideinddelte rapporter. Du skal bruge en Power BI Pro-licens for at publicere en rapport i tjenesten. Du kan publicere og dele sideinddelte rapporter i Mit arbejdsområde eller i apparbejdsområder, så længe arbejdsområdet er placeret i en Power BI Premium-kapacitet. 

## <a name="administration"></a>Administration

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Hvilken størrelse Premium-kapacitet for sideinddelte rapporter skal jeg bruge?

Arbejdsbelastningen for sideinddelte rapporter er tilgængelig på P1-P3 SKU'er.  Du kan også bruge den med A4 – A6 SKU'er til integrerings- eller test/dev-scenarier.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Hvad er den maksimale hukommelsestærskel, jeg kan angive, for sideinddelte rapporter i min kapacitet?

Du må bruge op til 100 % af hukommelsen til denne arbejdsbelastning.

### <a name="how-does-user-access-work-for-paginated-reports"></a>Hvordan fungerer brugeradgang til sideinddelte rapporter?

Brugeradgang til sideinddelte rapporter er det samme som brugeradgang til alt andet indhold i Power BI-tjenesten 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Hvordan slår jeg arbejdsbelastningen for mine sideinddelte rapporter til/fra?

Administratoren af kapacitet kan aktivere eller deaktivere arbejdsbelastningen for sideinddelte rapporter på siden med administratorportalen for kapacitet.  Som standard er arbejdsbelastningen slået til for alle nye kapaciteter, du opretter.  

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

Ja, overvågning er tilgængelig som en ny fane med de samme relevante oplysninger, som du har til dine Power BI-datasæt.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Skal jeg have en Pro-licens for at oprette og publicere sideinddelte rapporter?

Du kan uploade sideinddelte rapporter til Mit arbejdsområde uden en Pro-licens, hvis den er i en Premium-kapacitet.  For andre arbejdsområder skal du have en Pro-licens for at oprette og publicere indhold til dem. Vi anbefaler, at du henter og bruger Power BI Report Builder selv uden en Pro-licens, men du kan ikke publicere de sideinddelte rapporter, du opretter, uden den. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Hvad nu hvis jeg har en sideinddelt rapport i et arbejdsområde, og arbejdsbelastningen for sideinddelte rapporter er slået fra?

Du får vist en fejlmeddelelse, og du kan ikke få vist rapporten, før arbejdsbelastningen er slået til igen. Du kan stadig slette rapporten fra arbejdsområdet.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>Hvad er standardhukommelsen for hver af de Premium SKU'er, der understøttes for sideinddelte rapporter?

Standardhukommelsen for hver Premium SKU for sideinddelte rapporter er:

- **P1/A4**: 20 % som standard, minimum 10 %
- **P2/A5**: 20 % som standard, minimum 5 %
- **P3/A6**: 20 % som standard, minimum 2,5 %

## <a name="general"></a>Generelt

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Hvornår skal jeg bruge en sideinddelt rapport i forhold til en Power BI-rapport?

Sideinddelte rapporter er bedst til scenarier, hvor der kræves megen formatering og perfekt pixeleret output, der er optimeret til udskrivning eller generering af PDF.  Et driftsregnskab er et godt eksempel på den type rapport, du sandsynligvis ville oprette som en sideinddelt rapport.  

Power BI-rapporter er optimeret til udforskning og interaktivitet.  En salgsrapport, hvor forskellige sælgere vil opdele dataene i den samme rapport for deres specifikke område/branche/kunde og se, hvordan tallene ændres, vil fungere bedst som en Power BI-rapport.

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Ifølge dokumentationen er Power BI Report Builder det foretrukne værktøj til oprettelse. Kan jeg oprette sideinddelte rapporter i SQL Server Data Tools til Power BI?

Ja, men Power BI-tjenesten giver dig kun mulighed for at uploade et enkelt element ad gangen, så mange af de scenarier, forfattere bruger med SQL Server Data Tools (SSDT), understøttes endnu ikke. Du kan se en komplet [liste over ikke-understøttede funktioner](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) senere i disse Ofte stillede spørgsmål.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Hvilke versioner af Report Builder understøttes?

Vi har for nylig udgivet Power BI Report Builder som det primære værktøj til oprettelse af sideinddelte rapporter i Power BI-tjenesten. Installér [Power BI Report Builder fra Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=2086513).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Hvordan flytter jeg eksisterende rapporter, som jeg har gemt i SQL Server Reporting Services, til Power BI?

Du skal downloade rapporten fra serveren og derefter uploade den til Power BI via portalen.  Der er intet overførselsværktøj tilgængeligt på nuværende tidspunkt, men vi ser på at oprette et, når den offentlige prøveversion er gennemført, og vi har fået det rette niveau af funktionsparitet mellem produkterne.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Kan jeg åbne rapporter og publicere direkte i tjenesten?

Ja. Vi har for nylig tilføjet understøttelse af åbning af rapporter og publicering af dem direkte i tjenesten fra Power BI Report Builder.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Hvilke funktioner for sideinddelte rapporter i SSRS understøttes endnu ikke i Power BI?

Sideinddelte rapporter understøtter i øjeblikket ikke følgende elementer:

- Delte datakilder
- Delte datasæt
- Underrapporter
- Detaljeadgang og klikfrekvens til andre rapporter
- Linkede rapporter
- Lag i Bing-kort
- Brugerdefinerede skrifttyper

Du får vist en fejlmeddelelse, hvis du forsøger at uploade en fil, som indeholder en ikke-understøttet funktion i Power BI-tjenesten – med undtagelse af slå til/fra og sortering.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Hvilke datakilder understøttes i øjeblikket for sideinddelte rapporter?

Vi understøtter følgende datakilde – 

- Power BI-datasæt (via enkeltlogon (SSO))
- Azure Analysis Services (via enkeltlogon (SSO) og oAuth)
- Azure SQL Data Warehouse
- Azure SQL Database (brugernavn/adgangskode, SSO og oAuth)
- SQL Server*
- SSAS-modeller (SQL Server Analysis Services) i tabelformat (DAX) og multidimensionale (MDX) SSAS-modeller* 
- Oracle* 
- Teradata* 

* kræver gatewayen i det lokale miljø.

Når du åbner SSAS gennem gatewayen, skal den bruger, hvis legitimationsoplysninger er gemt, have administratorrettigheder i SSAS for at kunne arbejde via denne Gateway.

### <a name="what-authentication-methods-do-you-support"></a>Hvilke godkendelsesmetoder understøttes?

Vi understøtter SSO til Azure Analysis Services, Azure SQL Database og Power BI-datakilder.  Vi understøtter også OAuth til Azure SQL Database og Azure Analysis Services.  For alle andre datakilder skal du i øjeblikket gemme et brugernavn og en adgangskode sammen med datakilden på portalen eller i gatewayen.  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Kan jeg bruge et Power BI-datasæt som en datakilde til min sideinddelte rapport?

Ja, vi understøtter Power BI-datasæt som datakilder for dine sideinddelte rapporter.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Kan jeg bruge gemte procedurer via denne gateway?

Du kan bruge en gemt procedure via gatewayen, men du ser måske problemer i bestemte scenarier, hvis den gemte procedure har parametre.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Hvilke eksportformater er tilgængelige for min rapport i Power BI-tjenesten?

Du kan eksportere til Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, .CSV, XML og MHTML.

### <a name="can-i-print-paginated-reports"></a>Kan jeg udskrive sideinddelte rapporter?

Ja, udskrivning er tilgængelig for sideinddelte rapporter, herunder en ny og forbedret oplevelse af Vis udskrift. 

### <a name="are-e-mail-subscriptions-available-for-paginated-reports"></a>Er mailabonnementer tilgængelige for sideinddelte rapporter?

Ja, mailabonnementer understøttes fuldt ud for sideinddelte rapporter og omfatter understøttelse af seks forskellige filformater og parameterværdier.

### <a name="can-i-run-custom-code-in-my-report"></a>Kan jeg køre brugerdefineret kode i min rapport?

Ja, vi understøtter muligheden for at køre kode i dine rapporter, ligesom du kan i SSRS.

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Kan jeg bruge Power BI Embedded til at integrere mine sideinddelte rapporter i en app, jeg er vært for?

SaaS-integration understøttes allerede. PaaS-integration understøttes ikke i øjeblikket.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Kan jeg få detaljeadgang fra en Power BI-rapport til en sideinddelt rapport?

Ja, dette kan gøres ved at bruge URL-parametre sammen med sideinddelte rapporter.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Kan jeg dele indhold i min sideinddelte rapport via en Power BI-app?

Ja, sideinddelte rapporter understøttes og kan implementeres med apps fra både v1- og v2-arbejdsområder. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Vil andre rapportspecifikke funktioner i Power BI, f.eks. fastgørelse af rapportfelter til dashboards, fungere med sideinddelte rapporter?

Vi har planer om, at rapporterne skal understøtte de samme overordnede scenarier i tjenesten så meget som muligt.  Selvom værktøjet til at oprette dem er forskelligt, er det, set fra en brugers synspunkt, ideelt set blot endnu en rapport på deres liste på portalen. De er ligeglade med, hvordan den blev oprettet, så længe de kan gøre det, de har brug for.  Et godt eksempel på denne funktionsparitet er understøttelsen af planlagte kommentarer. Selvom selve funktionen muligvis fungerer en smule anderledes for hver rapporttype, vil du kunne bruge kommentarer til begge.

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>Er der planer om et overførselsværktøj, så SSRS-kunder kan flytte deres eksisterende rapporter og aktiver til Power BI?

Vi evaluerer mulighederne for at tillade, at indhold flyttes til Power BI automatisk, men det bliver ikke tilgængeligt indtil efter versionen, der er offentligt tilgængelig.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Er der et kontrolelement til rapportfremviser for sideinddelte rapporter i Power BI-tjenesten?

Nej, kontrolelementet til rapportfremviser er i øjeblikket ikke tilgængeligt.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Kan man søge efter sideinddelte rapporter fra den nye Hjem-oplevelse i Power BI-tjenesten?

Ja, du kan nu søge efter dine sideinddelte rapporter fra Hjem.  Du kan også se dem i andre dele af den nye Hjem-oplevelse.

## <a name="next-steps"></a>Næste trin

- [Installér Power BI Report Builder fra Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=2086513)
- [Selvstudium: Opret en sideinddelt rapport](paginated-reports-quickstart-aw.md)
