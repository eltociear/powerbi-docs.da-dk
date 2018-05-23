---
title: Opret pakker med skabelonindhold i Power BI
description: Oprettelse af pakke med skabelonindhold
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: f3f3343122857cbf06c0004d2a3e5e5247f07e48
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="author-template-content-packs-in-power-bi"></a>Opret pakker med skabelonindhold i Power BI
Til oprettelse af en pakke med skabelonindhold bruges Power BI Desktop og PowerBI.com. Der er fire komponenter i din indholdspakke:

* Forespørgsler gør det muligt at [oprette forbindelse](../desktop-connect-to-data.md) og [transformere](../desktop-query-overview.md) data samt definere [parametre](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/)  
* Datamodel til at oprette [relationer](../desktop-create-and-manage-relationships.md), [målinger](../desktop-measures.md) og forbedringer af spørgsmål og svar  
* [Sider](../desktop-report-view.md) i rapporter omfatter visuelle elementer og filtre, der giver indsigt i dine data  
* [Dashboard](../service-dashboards.md) og [felter](../service-dashboard-create.md) giver et overblik over den indsigt, der er inkluderet  

Du kender hver enkelt del som eksisterende funktioner i Power BI. Når du opretter en indholdspakke, er der flere ting, der bør overvejes for hvert aspekt. Du kan finde flere oplysninger om dette i de enkelte afsnit nedenfor.

<a name="queries"></a>

## <a name="queries"></a>Forespørgsler
I forbindelse med pakker med skabelonindhold bruges forespørgsler, der er udviklet i Power BI Desktop, til at oprette forbindelse til datakilden og importere data. Disse forespørgsler skal returnere et ensartet skema, og understøttes med henblik på planlagt dataopdatering (direkte forespørgsel understøttes ikke).

Pakker med skabelonindhold understøtter kun én datakilde pr. indholdspakke, så vær omhyggelig, når du definerer dine forespørgsler. En enkelt datakilde defineres som en kilde, der kræver samme godkendelse. Du kan foretage flere API-kald i forskellige forespørgsler, hvis alle kald er til det samme API-slutpunkt og bruger den samme godkendelse. Power BI-indholdspakker understøtter ikke flere kilder, der kræver forskellige godkendelser.

### <a name="connect-to-your-api"></a>Opret forbindelse til din API
For at kunne komme i gang skal du oprette forbindelse til din API fra Power BI Desktop, så du kan begynde at oprette dine forespørgsler.

Du kan bruge de dataconnectorer i Power BI Desktop, der er klar til brug, til at oprette forbindelse til din API. Du kan bruge Web Data Connector (Hent Data -> Web) til at oprette forbindelse til din Rest API eller OData-connectoren (Hent Data -> OData-feed) for at oprette forbindelse til dit OData-feed. Bemærk, at disse connectorer kun er klar til brug, hvis din API understøtter basisgodkendelse.

> [!NOTE]
> Hvis din API bruger andre godkendelsestyper, som f.eks. OAuth 2.0 eller internat-API-nøgle, skal du udvikle din egen dataconnector, så Power BI Desktop kan oprette forbindelse til og godkendes til din API. Du kan få flere oplysninger om, hvordan du udvikler din egen dataconnector til indholdspakken i dokumentationen til dataconnectorer [her](https://aka.ms/DataConnectors). 
> 
> 

### <a name="consider-the-source"></a>Tag højde for kilden
Forespørgsler definerer de data, der skal medtages i datamodellen. Afhængigt af størrelsen af dit system bør disse forespørgsler også inkludere filtre for at sikre, at dine kunder arbejder med en håndterbar størrelse, der passer til dit forretningsscenarie.

Power BI-indholdspakker kan udføre flere forespørgsler parallelt og for flere brugere samtidig.  Planlæg din strategi for begrænsning og samtidighed, og spørg os, hvordan du kan gøre din indholdspakke fejltolerant.

### <a name="schema-enforcement"></a>Håndhævelse af skema
Kontrollér, at dine forespørgsler er robuste i forhold til ændringer i systemet. Ændringer i skemaer ved opdatering kan ødelægge modellen. Hvis kilden kunne returnere resultatet null/mangler skema for nogle forespørgsler, bør du overveje at returnere en tom tabel eller aktivere en tilpasset fejlmeddelelse, der er relevant for din bruger.

### <a name="parameters"></a>Parametre
[Parametre](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) i Power BI Desktop giver brugerne mulighed for at angive inputværdier, der tilpasser de data, som brugeren har hentet. Overvej parametrene fra starten, så du undgår at skulle lave tingene om, når du har investeret tid på at oprette detaljerede forespørgsler eller rapporter.

> [!NOTE]
> Pakker med skabelonindhold understøtter i øjeblikket kun tekstparametre. Andre parametertyper kan bruges i udviklingsfasen, men under [test](template-content-pack-testing.md#templates) vil alle værdier, der angives af brugerne, være konstantværdier.
> 
> 

### <a name="additional-query-tips"></a>Flere tip til forespørgsler
* Kontrollér, at alle kolonner er skrevet korrekt  
* Kolonner har informative navne (se spørgsmål og svar)  
* Overvej at bruge funktioner eller forespørgsler til delt logik  
* Niveau for beskyttelse af personlige oplysninger understøttes ikke i tjenesten i øjeblikket – hvis du får vist en prompt om niveau for beskyttelse af personlige oplysninger, skal du muligvis omskrive forespørgslen, så der bruges relative stier  

## <a name="data-model"></a>Datamodel
En datamodel, der er korrekt defineret, sikrer, at dine kunder nemt og intuitivt kan interagere med indholdspakken. Opret datamodellen i Power BI Desktop.

> [!NOTE]
> Meget af den grundlæggende modellering (indtastning, kolonnenavne) bør udføres i [forespørgslerne](#queries).
> 
> 

### <a name="qa"></a>Spørgsmål og svar
Modelleringen har også indflydelse på, i hvor høj grad spørgsmål og svar kan levere resultater til dine kunder. Sørg for at føje synonymer til ofte anvendte kolonner, og at dine kolonner navngives korrekt i [forespørgslerne](#queries).

### <a name="additional-data-model-tips"></a>Flere tip til datamodeller
* Der er anvendt formatering til alle værdikolonner
    >[!NOTE]
    >Der skal anvendes typer i forespørgslen.  
* Der er anvendt formatering til alle målinger  
* Der er angivet standardopsummering. Specielt "Opsummer ikke", når det er relevant (f.eks. til entydige værdier)  
* Datakategori er angivet, når det er relevant  
* Relationer er angivet efter behov  

## <a name="reports"></a>Rapporter
Rapportsider tilbyder yderligere indsigt i de data, der er medtaget i din indholdspakke. Brug siderne i rapporterne til at besvare de vigtige forretningsspørgsmål, som din indholdspakke prøver at håndtere. Opret rapporten ved hjælp af Power BI Desktop.

> [!NOTE]
> En indholdspakke kan kun indeholde én rapport; udnyt fordelene ved de forskellige sider til at forklare bestemte dele af dit scenarie.
> 
> 

### <a name="additional-report-tips"></a>Flere tip til rapporter
* Brug mere end ét visuelt element pr. side til krydsfiltrering  
* Juster de visuelle elementer omhyggeligt (ingen overlapning)  
* Siden er angivet til tilstanden "4:3" eller "16:9" for layout  
* Alle de viste aggregeringer giver mening numerisk (gennemsnit, entydige værdier)  
* Udsnit giver rationelle resultater  
* Logo findes som minimum i den øverste rapport  
* Elementer er i videst muligt omfang holdt i klientens farveskema  

<a name="dashboard"></a>

## <a name="dashboard"></a>Dashboard
Dashboardet er det primære interaktionspunkt med indholdspakken til dine kunder. Den bør indeholde en oversigt over det indhold, der er inkluderet, specielt vigtige målepunkter til dit forretningsscenarie.

Når du vil oprette et dashboard til din pakke med skabelonindhold, skal du blot overføre din PBIX via Hent data > Filer eller publicere direkte fra Power BI Desktop.

> [!NOTE]
> Pakker med skabelonindhold kræver i øjeblikket en enkelt rapport og et enkelt datasæt pr. indholdspakke. Fastgør ikke indhold fra flere rapporter/datasæt i dashboardet, der bruges i indholdspakken.
> 
> 

### <a name="additional-dashboard-tips"></a>Flere tip til dashboard
* Bevar det samme tema i forbindelse med fastgørelse, så felterne i dashboardet er ensartede  
* Fastgør et logo til temaet, så forbrugerne ved, hvor pakken er fra  
* Det anbefalede layout til arbejde med de fleste skærmopløsninger er en bredde på 5 til 6 små felter  
* Alle felter i dashboardet skal have relevante titler/undertitler  
* Du kan overveje grupperinger i dashboardet til forskellige scenarier enten lodret eller vandret  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>Oversigt over begrænsninger
Som angivet i afsnittene ovenfor er der i øjeblikket en række begrænsninger for pakker med skabelonindhold:  

| Understøttet | *Ikke understøttet* |
| --- | --- |
| Datasæt, der er oprettet i PBI Desktop |*Datasæt fra andre indholdspakker eller input, f.eks. Excel-filer* |
| Datakilde, der understøttes for planlagt dataopdatering i cloud |*Direkte forespørgsel eller forbindelser i det lokale miljø understøttes ikke* |
| Forespørgsler, der returnerer ensartet skema eller fejl, hvor det er relevant |*Dynamiske eller brugerdefinerede skemaer* |
| Én datakilde pr. datasæt |*Flere datakilder, f.eks. miks eller URL-adresser, der registreres som flere datakilder* |
| Parametre af typen tekst |*Andre parametertyper (f.eks. dato) eller "liste over tilladte værdier"* |
| Et dashboard, én rapport og ét datasæt |*Flere dashboards, rapporter eller datasæt* |

## <a name="next-step"></a>Næste trin
[Test af indholdspakke og indsendelse](template-content-pack-testing.md)

