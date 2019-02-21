---
title: Tip til udarbejdelse af skabelonprogrammer i Power BI (prøveversion)
description: Tip til udarbejdelse af forespørgsler, datamodeller, rapporter og dashboards for at skabe gode skabelonprogrammer
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/05/2019
ms.author: maggies
ms.openlocfilehash: 282638c7c1c8a60ee93292602766d63fd0fe436e
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249582"
---
# <a name="tips-for-authoring-template-apps-in-power-bi-preview"></a>Tip til udarbejdelse af skabelonprogrammer i Power BI (prøveversion)

Når du [udarbejder dit skabelonprogram](service-template-apps-create.md) i Power BI, er en del af det logistikken til oprettelse af arbejdsområdet, test af det og produktion. Men en anden vigtige del er naturligvis at udarbejde rapporten og dashboardet. Vi kan opdele processen for udarbejdelse i fire primære komponenter. Når du arbejder på disse komponenter, hjælper det dig med at oprette det bedst mulige skabelonprogram:

* Med **forespørgsler** kan du [oprette forbindelse til](desktop-connect-to-data.md) og [transformere](desktop-query-overview.md) dataene samt definere [parametre](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/). 
* I **datamodellen** opretter du [relationer](desktop-create-and-manage-relationships.md), [målinger](desktop-measures.md) og forbedringer af Spørgsmål og svar.  
* **[Rapportsider](desktop-report-view.md)** indeholder visualiseringer og filtre, som kan hjælpe med at give indsigt i dine data.  
* **[Dashboards](consumer/end-user-dashboards.md)** og [felter](service-dashboard-create.md) hjælper med at give et overblik over den inkluderede indsigt.  

Du kender hver enkelt del som eksisterende funktioner i Power BI. Når du udarbejder et skabelonprogram, er der flere ting, du bør overveje for hver enkelt del. Du kan finde flere oplysninger under de enkelte afsnit herunder.

<a name="queries"></a>

## <a name="queries"></a>Forespørgsler
I forbindelse med skabelonprogrammer bruges forespørgsler, der er udviklet i Power BI Desktop, til at oprette forbindelse til datakilden og importere data. Disse forespørgsler skal returnere et ensartet skema, og de understøttes med henblik på planlagt dataopdatering (DirectQuery understøttes ikke).

### <a name="connect-to-your-api"></a>Opret forbindelse til din API
Du kommer i gang ved at oprette forbindelse til din API fra Power BI Desktop, så du kan begynde at udarbejde dine forespørgsler.

Du kan bruge de dataconnectorer i Power BI Desktop, der er klar til brug, til at oprette forbindelse til din API. Du kan bruge Web Data Connector (Hent Data -> Web) til at oprette forbindelse til din Rest API eller OData-connectoren (Hent Data -> OData-feed) for at oprette forbindelse til dit OData-feed. Disse connectorer er kun klar til brug, hvis din API understøtter grundlæggende godkendelse.

> [!NOTE]
> Hvis din API bruger andre godkendelsestyper, f.eks. OAuth 2.0 eller Web API-nøgle, skal du udvikle din egen dataconnector, så Power BI Desktop kan oprette forbindelse til og godkendes til din API. Du kan få flere oplysninger om, hvordan du udvikler din egen dataconnector til skabelonprogrammet i [dokumentationen til dataconnectorer](https://aka.ms/DataConnectors). 
>
>

### <a name="consider-the-source"></a>Tag højde for kilden
Forespørgsler definerer de data, der inkluderes i datamodellen. Afhængigt af størrelsen af dit system bør disse forespørgsler også inkludere filtre for at sikre, at dine kunder arbejder med en håndterbar størrelse, der passer til dit forretningsscenarie.

Power BI-skabelonprogrammer kan udføre flere forespørgsler parallelt og for flere brugere samtidigt.  Planlæg din strategi for begrænsning og samtidighed, og spørg os, hvordan du kan gøre dit skabelonprogram fejltolerant.

### <a name="schema-enforcement"></a>Håndhævelse af skema
Kontrollér, at dine forespørgsler er robuste i forhold til ændringer i systemet. Ændringer i skemaer ved opdatering kan ødelægge modellen. Hvis kilden kunne returnere resultatet null eller mangler skema for nogle forespørgsler, bør du overveje at returnere en tom tabel eller en meningsfuld brugerdefineret fejlmeddelelse.

### <a name="parameters"></a>Parametre
[Parametre](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) i Power BI Desktop giver brugerne mulighed for at angive inputværdier, der tilpasser de data, som brugeren har hentet. Overvej parametrene fra starten, så du undgår at skulle lave tingene om, efter du har brugt tid på at oprette detaljerede forespørgsler eller rapporter.

> [!NOTE]
> Skabelonprogrammer understøtter alle parametre, undtagen Any og Binary.
>

### <a name="additional-query-tips"></a>Flere tip til forespørgsler

* Kontrollér, at alle kolonner er skrevet korrekt.
* Kolonner har informative navne (se [Spørgsmål og svar](#qa)).  
* Overvej at bruge funktioner eller forespørgsler til delt logik.  
* Niveauer for beskyttelse af personlige oplysninger understøttes i øjeblikket ikke i tjenesten. Hvis du får vist en prompt om niveauer for beskyttelse af personlige oplysninger, skal du muligvis omskrive forespørgslen til at bruge relative stier.  

## <a name="data-models"></a>Datamodeller

En veldefineret datamodel sikrer, at dine kunder nemt og intuitivt kan interagere med skabelonprogrammet. Opret datamodellen i Power BI Desktop.

> [!NOTE]
> Du bør udføre meget af den grundlæggende udformning (indtastning, kolonnenavne) i [forespørgslerne](#queries).
>


### <a name="qa"></a>Spørgsmål og svar
Udformningen har også indflydelse på, i hvor høj grad Spørgsmål og svar kan levere resultater til dine kunder. Sørg for at føje synonymer til ofte anvendte kolonner, og at du har navngivet dine kolonner korrekt i [forespørgslerne](#queries).

### <a name="additional-data-model-tips"></a>Flere tip til datamodeller

Sørg for, at du har gjort følgende:
* Anvendt formatering på alle værdikolonner. Anvendt typer i forespørgslen.  
* Anvendt formatering på alle målinger. 
* Angivet standardopsummering. Specielt "Opsummer ikke", når det er relevant (f.eks. til entydige værdier).  
* Angivet datakategori, når det er relevant.  
* Angivet relationer efter behov.  

## <a name="reports"></a>Rapporter
Med rapportsider får du yderligere indsigt i de data, der er inkluderet i dit skabelonprogram. Brug siderne i rapporterne til at besvare de vigtigste forretningsspørgsmål, som dit skabelonprogram prøver at håndtere. Opret rapporten ved hjælp af Power BI Desktop.

> [!NOTE]
> Du kan kun inkludere én rapport i et skabelonprogram, så udnyt fordelene ved de forskellige sider til at forklare bestemte dele af dit scenarie.
>
>

### <a name="additional-report-tips"></a>Flere tip til rapporter

* Brug mere end én visualisering pr. side, så du kan bruge krydsfiltrering.  
* Juster visualiseringerne omhyggeligt (ingen overlapning).  
* Siden er angivet til tilstanden "4:3" eller "16:9" for layout.  
* Alle de viste sammenlægninger giver mening numerisk (gennemsnit, entydige værdier).  
* Udsnit giver rationelle resultater.  
* Logo findes som minimum øverst i rapporten.  
* Elementer er i videst muligt omfang holdt i klientens farveskema.  

<a name="dashboard"></a>

## <a name="dashboards"></a>Dashboards
Dine kunder bruger primært dashboardet til at interagere med dit skabelonprogram. Den bør indeholde en oversigt over det indhold, der er inkluderet, specielt vigtige målepunkter til dit forretningsscenarie.

Når du vil oprette et dashboard for dit skabelonprogram, skal du blot uploade din PBIX via Hent data > Filer eller udgive direkte fra Power BI Desktop.

> [!NOTE]
> Skabelonprogrammer kræver i øjeblikket en enkelt rapport og et enkelt datasæt pr. skabelonprogram. Fastgør ikke indhold fra flere rapporter/datasæt på dashboardet, der bruges i skabelonprogrammet.
>
>

### <a name="additional-dashboard-tips"></a>Flere tip til dashboard

* Bevar det samme tema, når du fastgør, så felterne på dashboardet er ensartede.  
* Fastgør et logo til temaet, så brugerne ved, hvor pakken er fra.  
* Det anbefalede layout, når du arbejder med de fleste skærmopløsninger, er en bredde på 5-6 små felter.  
* Alle dashboardfelter skal have relevante titler/undertitler.  
* Overvej at anvende grupperinger på dashboardet til forskellige scenarier enten lodret eller vandret.  

## <a name="known-limitations"></a>Kendte begrænsninger

| Udvalgt | Kendt begrænsning |
|---------|---------|
|Indhold:  Datasæt   | Nøjagtigt ét datasæt skal være til stede. Der tillades kun datasæt, som er udarbejdet i Power BI Desktop (.pbix-filer). <br>Understøttes ikke: Datasæt fra andre skabelonprogrammer, datasæt på tværs af arbejdsområder, sideinddelte rapporter (.rdl-filer), Excel-projektmapper |
|Indhold: Rapporter     | Op til én rapport    |
| Indhold: Dashboards | Op til ét dashboard, der ikke er tomt <br>Understøttes ikke: Felter i realtid (med andre ord, så understøttes PushDataset eller pubnub ikke) |
| Indhold: Dataflow | Understøttes ikke: Dataflow |
| Indhold fra filer | Der tillades kun PBIX-filer. <br>Understøttes ikke: .rdl-filer (sideinddelte rapporter), Excel-projektmapper   |
| Datakilder | Der tillades datakilder, som understøttes for planlagt dataopdatering i cloudmiljøet. <br>Understøttes ikke: <br>DirectQuery <br>Direkte forbindelser (ingen Azure AS) <br>Datakilder i det lokale miljø (personlige gateways og virksomhedsgateways understøttes ikke) <br>Realtid (PushDataset understøttes ikke) <br>Sammensatte modeller |
| Datasæt: på tværs af arbejdsområde | Datasæt på tværs af arbejdsområder er ikke tilladt  |
| Indhold: Dashboards | Felter i realtid tillades ikke (med andre ord, så understøttes PushDataset eller pubnub ikke) |
| Forespørgselsparametre | Understøttes ikke: Parametre af typen "Any" eller "Binary" blokerer opdateringshandlinger for datasæt |
| Brugerdefinerede visualiseringer | Der understøttes kun offentligt tilgængelige visualiseringer. [Brugerdefinerede visualiseringer til virksomheder](power-bi-custom-visuals-organization.md) understøttes ikke |

## <a name="next-steps"></a>Næste trin

[Hvad er Power BI-skabelonprogrammer? (prøveversion)](service-template-apps-overview.md)
