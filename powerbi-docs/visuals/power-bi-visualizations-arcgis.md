---
title: Interaktion med et ArcGIS-kort, som er blevet delt med dig
description: Brug af ArcGIS Map til Power BI-visualisering i læsevisning som rapportbruger
author: mihart
ms.reviewer: willt, lukasz
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 05/06/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a95e9cd889bdf42ba703649cbc475f587fb1482b
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237804"
---
# <a name="interact-with-arcgis-maps-in-power-bi"></a>Interager med ArcGIS-kort i Power BI

[!INCLUDE[consumer-appliesto-yyyn](../includes/consumer-appliesto-yyyn.md)]    

Dette emne skrives af en person, der bruger et ArcGIS-kort i Power BI-tjenesten, på Desktop eller på mobil. Når en designer deler et ArcGIS-kort til Power BI-visualiseringer med dig, er der mange måder, du kan interagere med visualiseringen på.  Du kan få mere at vide om, hvordan du opretter et ArcGIS-kort, i [ArcGIS-kort efter Esri-selvstudium](../visuals/power-bi-visualization-arcgis.md).

> [!NOTE]
> Når du deler din rapport med en Power BI-kollega, kræves det, at I begge har individuelle Power BI Pro-licenser, eller at rapporten er gemt i en Premium-kapacitet. Se [deling af rapporter](../collaborate-share/service-share-reports.md).

Kombinationen af ArcGIS-kort og Power BI tager kort til et helt nyt niveau, som involverer mere end præsentation af punkter på et kort. Rapportdesignere starter med et kort og føjer lag af demografiske data til kortet. Kombinationen af disse placeringsbaserede datalag (f.eks. folketællingsdata) på et kort med rumlige analyser giver en bedre forståelse af dataene i visualiseringerne.

> [!TIP]
> GIS står for Geographic Information System.
> 

Dette ArcGIS-kort til Power BI-visualiseringer viser sidste års salg efter by, og der bruges et lag med et gadebaseret kort og et lag med den gennemsnitlige husstandsindkomst. Kortet indeholder to nåle (rød og gul) og én køretidsradius (i lilla).

![ArcGIS-kort, der viser USA med bobler, nåle og køretid](media/power-bi-visualizations-arcgis/power-bi-arcgis-esri.png)

> [!TIP]
> Besøg [Esris side på Power BI](https://www.esri.com/powerbi) for at se de mange eksempler og læse anbefalinger. Se derefter Esris [side med introduktion til ArcGIS Maps for Power BI](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm).
> 
> 

## <a name="user-consent"></a>Brugerens samtykke

Første gang, en kollega deler et ArcGIS-kort med dig, vises der en samtykkebesked i Power BI. ArcGIS Maps for Power BI leveres af Esri (https://www.esri.com) og din brug af ArcGIS Maps for Power BI er underlagt Esris vilkår og politik for beskyttelse af personlige oplysninger). Power BI-brugere, der gerne vil bruge ArcGIS-kort til visuelle elementer i Power BI, skal acceptere i dialogboksen til samtykke.


## <a name="understand-the-layers"></a>Om lagene

En ArcGIS Maps for Power BI-visualisering kan indeholde flere forskellige typer lag af demografiske placeringsoplysninger.

### <a name="base-maps"></a>Grundlæggende kort

Hver ArcGIS Maps for Power BI-visualisering starter med et grundlæggende kort. Tænk på det grundlæggende kort som lærredet til dataene. Et grundlæggende kort kan være et mørkt eller lyst lærred i en grundfarve

![grundlæggende kort i koksgrå](media/power-bi-visualizations-arcgis/power-bi-basemap-dark.png) 

eller et lærred med oplysning om gader og transportmuligheder. 

![grundlæggende kort i koksgrå](media/power-bi-visualizations-arcgis/power-bi-streets-basemap.png)  

Det grundlæggende kort anvendes på hele lærredet. Når du panorerer og zoomer, opdateres kortet. Zoom ind for at se mere detaljerede oplysninger om gader og transportmuligheder. Panorer fra ét kontinent til et andet – niveauet af detaljer forbliver det samme. Her har vi panoreret fra Porto til Beijing.

![grundlæggende kort med gader](media/power-bi-visualizations-arcgis/power-bi-basemap-pan.png)  

### <a name="reference-layers"></a>Referencelag

En *rapportdesigner* kan tilføje ét referencelag. Referencelagene hostes af Esri og giver et ekstra lag af demografiske oplysninger om en placering. Nedenstående eksempel har et referencelag for befolkningstæthed. Mørkere farver repræsenterer en højere tæthed.

![kort over Orlando-området, der viser befolkningstætheden](media/power-bi-visualizations-arcgis/power-bi-reference.png)  

### <a name="infographics"></a>Infografik

En *rapportdesigner* kan tilføje mange infografiklag. Infografik er hurtige visuelle indikatorer, der vises langs højre side af visualiseringslærredet. Infografik hostes af Esri og giver et ekstra lag af demografiske oplysninger om en placering. I eksemplet nedenfor er der anvendt tre infografikker. De vises ikke på selve kortet, men på kort langs højre side af lærredet. Infografikkortene opdateres, når du zoomer, panorerer og vælger områder på kortet.

![kort over Orlando-området, hvor der er zoomet ind, og infografikkort langs højre side af lærredet](media/power-bi-visualizations-arcgis/power-bi-infographics.png)  

### <a name="pins"></a>Nåle

Nåle repræsenterer præcise placeringer, f. eks. en by eller en adresse. Nogle gange bruger *rapportdesignere* nåle med køretidsradius. I dette eksempel vises butikker i en radius af 50 miles fra Charlotte i North Carolina.


![Køretid rundt om Charlotte, NC](media/power-bi-visualizations-arcgis/power-bi-drive-times.png) 


## <a name="interact-with-an-arcgis-maps-for-power-bi-visual"></a>Interager med en ArcGIS Maps til en Power BI-visualisering
Hvilke funktioner, der er tilgængelige for dig, afhænger af, hvordan rapporten blev delt med dig og din Power BI-kontotype. Kontakt systemadministratoren, hvis du har spørgsmål. ArcGIS Maps for Power BI-visualiseringer fungerer på stort set samme måde som andre visualiseringer i en rapport. Du vil kunne [vise de data, der bruges til at oprette visualiseringen](../consumer/end-user-show-data.md), se kortet i [fokustilstand og fuldskærmsvisning](../consumer/end-user-focus.md), [tilføje kommentarer](../consumer/end-user-comment.md), [interagere med de filtre](../consumer/end-user-report-filter.md), der er angivet af *rapportdesigneren* og meget mere. ArcGIS-visualiseringer kan filtreres på tværs af andre visualiseringer på rapportsiden og omvendt.

Hold musemarkøren hen over placeringer på det grundlæggende kort (f. eks. en boble) for at få vist værktøjstip. Du kan også bruge ArcGIS-markeringsværktøjerne til visualiseringer for at få vist yderligere værktøjstip og for at foretage bestemte valg på det grundlæggende kort eller i referencelaget.  

### <a name="selection-tools"></a>Markeringsværktøjer

ArcGIS Maps for Power BI har fem markeringstilstande. Du kan maksimalt vælge 250 datapunkter ad gangen.

![Skærmbillede af alle tre markeringsværktøjer](media/power-bi-visualizations-arcgis/power-bi-esri-selection-tools.png)

#### <a name="the-single-select-tool"></a>Værktøjet til et enkelt valg

![skærmbillede af værktøjet til enkelt valg](media/power-bi-visualizations-arcgis/power-bi-esri-selection-single2.png) 

Vælg et datapunkt, en boble, en nål eller et enkelt datapunkt i referencelaget. Power BI viser et værktøjstip med oplysninger om din markering. Enkelt valg filtrerer på tværs af de andre visualiseringer på rapportsiden, afhængigt af din markering, og opdaterer infografikkortene for det valgte område. 

Her har vi markeret et brunt bobledatapunkt på det grundlæggende kort. Power BI:
- fremhæver vores valg,
- viser et værktøjstip for datapunktet, 
- opdaterer infografikkortene, så der kun vises data for din markering, og
- fremhæver på tværs af søjlediagrammet.

![Skærmbillede af værktøjstip til brun boble](media/power-bi-visualizations-arcgis/power-bi-single-selects.png)

Hvis kortet har et referencelag, vises der oplysninger i et værktøjstip, når du markerer en placering. Her har vi valgt Seneca County, og du kan se de data fra referencelaget (befolkningstæthed), som *rapportdesigneren* har føjet til kortet. I dette eksempel omfatter vores datapunkt to forskellige amter, så der er to sider i værktøjstippet. Der er et diagram på hver side. Vælg en søjle i diagrammet for at få vist flere oplysninger. 

![Skærmbillede af værktøjstip til Seneca County](media/power-bi-visualizations-arcgis/power-bi-single-select-ref.png)

> [!TIP]
  > Nogle gange kan du reducere antallet af sider i værktøjstippet ved at zoome ind for at vælge en bestemt placering.  Hvis der er overlappende placeringer, kan Power BI vise dig mere end ét 1 værktøjstip ad gangen. Klik på pilen for at flytte mellem værktøjstippene
  > 
  > ![Værktøjstip, der viser tre sider](media/power-bi-visualizations-arcgis/power-bi-3-screens.png)

#### <a name="the-multi-select-tool"></a>Værktøjet til flere valg

![værktøj til flere valg](media/power-bi-visualizations-arcgis/power-bi-esri-selection-marquee2.png) 

Der tegnes et rektangel på kortet, og de indeholdte datapunkter markeres. Du kan bruge CTRL til at vælge mere end ét rektangulært område. Flere valg opdaterer infografikkortene for det valgte område og fremhæver på tværs af de andre visualiseringer på rapportsiden, afhængigt af din markering.

![værktøj til flere valg](media/power-bi-visualizations-arcgis/power-bi-multi-select.png) 

#### <a name="the-reference-layer-tool"></a>Værktøjet til referencelag

![tredje valgværktøj til grænser](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference-layer2.png) 

Tillader, at grænser eller polygoner i referencelag kan bruges til at vælge indeholdte datapunkter. Det er svært at se, men der er en gul kontur i referencelaget. I modsætning til værktøjet til et enkelt valg får vi ikke vist et værktøjstip. I stedet får vi vist data om de datapunkter, der er placeret inden for grænserne for den pågældende kontur. I dette eksempel indeholder vores markering et datapunkt – det er for en Lindseys-butik i Winston Salem.

![referencemarkeringsværktøj](media/power-bi-visualizations-arcgis/power-bi-ref-tool.png) 

#### <a name="the-buffer-tool"></a>Bufferværktøjet

![fjerde markeringsværktøj til buffere](media/power-bi-visualizations-arcgis/power-bi-esri-selection-4.png) 

Tillader markering af datapunkter ved hjælp af et bufferlag. Du kan f. eks. bruge dette værktøj til at vælge en køretidsradius og fortsætte med at interagere med resten af rapporten. Køretidsradiussen forbliver aktiv, og infografikkortene afspejler stadig køretidsradiussen, men hvis du markerer andre datapunkter på kortet, filtreres de andre visualiseringer på rapportsiden.

![buffermarkeringsværktøj](media/power-bi-visualizations-arcgis/power-bi-buffer.png) 

#### <a name="the-find-similar-tool"></a>Værktøjet Find lignende

![femte markeringsværktøj til ligheder](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference5.png) 

Giver dig mulighed for at finde placeringer med lignende attributter. Du starter med at markere et eller flere interessepunkter, eller referenceplaceringer, og derefter definerer du op til fem dimensioner, som du vil bruge i analysen. Find lignende beregner derefter de 10 placeringer på kortet, der mest ligner de referenceplaceringer, du har angivet. Du kan derefter bruge infografikkortene til at se de demografiske oplysninger omkring de enkelte resultater og oprette køretidsområder for at få en fornemmelse af, hvad der er inden for køreafstand fra de enkelte placeringer. Du kan også bruge værktøjet Find lignende til at filtrere din rapport og få mere indsigt. Allervigtigst er dog, at alle beregninger sker lokalt på din maskine, så du kan være sikker på, at dine fortrolige data forbliver beskyttet.


## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
ArcGIS-kort til Power BI er tilgængeligt i følgende tjenester og programmer:

|Tjeneste/app  |Tilgængelighed  |
|---------|---------|
|Power BI Desktop     |     Ja    |
|Power BI-tjenesten (app.powerbi.com)     |    Ja     |
|Power BI-mobilapps     |  Ja      |
|Power BI publiceret til internettet     |  Nej       |
|Power BI Embedded     |     Nej    |
|Integration af Power BI-tjenesten (PowerBI.com)  | Nej |


## <a name="how-do-arcgis-maps-for-power-bi-work-together"></a>Hvordan fungerer ArcGIS Maps for Power BI?
ArcGIS Maps for Power BI leveres af Esri (https://www.esri.com). Din brug af ArcGIS Maps til Power BI er omfattet af Esris [vilkår](https://go.microsoft.com/fwlink/?LinkID=8263222) og [politik om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?LinkID=826323). Power BI-brugere, der gerne vil bruge ArcGIS-kort til visuelle elementer i Power BI, skal acceptere i dialogboksen til samtykke (se under Brugersamtykke for at få flere oplysninger).  Brug af Esris ArcGIS Maps til Power BI er underlagt Esris vilkår og politik om beskyttelse af personlige oplysninger, der også er linket til i dialogboksen til samtykke. Hver enkelt bruger skal samtykke, før de kan bruge ArcGIS Maps til Power BI første gang. Når brugeren accepterer samtykket, sendes data, der er bundet til visualiseringen til Esris tjenester i hvert fald i forbindelse med geo-kodning. Det vil sige, at placeringsoplysninger transformeres til oplysninger om længdegrad og breddegrad, der kan vises på et kort. Du skal antage, at alle data, der er bundet til datavisualiseringen kan sendes til Esris tjenester. Esri leverer tjenester, såsom kort, afstandsanalyse, geo-kodning osv. ArcGIS Maps til Power BI-visualiseringen interagerer med disse tjenester vha. en SSL-forbindelse, der beskyttes af et certifikat, som leveres og vedligeholdes af Esri. Du kan få flere oplysninger om ArcGIS Maps til Power BI på Esris [produktside for ArcGIS Maps til Power BI](https://www.esri.com/powerbi).

### <a name="power-bi-plus"></a>Power BI Plus

![Vælg plustegnet for at tilmelde dig, eller log på](media/power-bi-visualizations-arcgis/power-bi-plus.png)

Når en bruger tilmelder sig et Plus-abonnement, der tilbydes af Esri, via ArcGIS Maps for Power BI, indgår vedkommende i en direkte relation med Esri. Power BI sender ikke personlige oplysninger om brugeren til Esri. Brugeren logger på og angiver, at vedkommende har tillid til et AAD-program, der leveres af Esri, vha. sit eget AAS-id. På denne måde deler brugeren sine personlige oplysninger direkte med Esri. Når brugeren føjer Plus-indhold til en ArcGIS Maps til Power BI-visualisering, skal de kolleger, der vil se eller redigere visualiseringen også have et Plus-abonnement fra Esri. 

Hvis du har tekniske spørgsmål om, hvordan Esris ArcGIS Maps til Power BI fungerer, skal du kontakte Esri via deres supportwebsted.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

**ArcGIS-kortet vises ikke**    
I tjenester eller programmer, hvor ArcGIS Maps for Power BI ikke er tilgængelig, vises visualiseringen som en tom visualisering med Power BI-logoet.

**Jeg kan ikke se alle mine oplysninger på kortet**    
Når du udfører geokodning af breddegrad/længdegrad på kortet, vises der op til 30.000 datapunkter. Når du udfører geokodning af datapunkter, f.eks. postnumre eller postadresser, er det kun de første 15.000 datapunkter, der geokodes. Geokodning af stednavne eller lande er ikke underlagt grænsen på 1500 adresser.

**Er der omkostninger forbundet med brugen af ArcGIS Maps for Power BI?**

ArcGIS Maps for Power BI er tilgængelig for alle Power BI-brugere uden meromkostninger. Det er en komponent, der leveres af **Esri**, og din brug er underlagt **Esris** vilkår og beskyttelse af personlige oplysninger, som nævnt tidligere i denne artikel. Hvis du abonnerer på ArcGIS **Plus**, skal du betale et gebyr.

**Jeg får vist en fejlmeddelelse om, at min cache er fuld**

Dette er en fejl, der er ved at blive løst.  Vælg i mellemtiden det link, der vises i fejlmeddelelsen, for at få vejledning til, hvordan du rydder Power BI-cachen.

**Kan jeg få vist mine ArcGIS-kort offline?**

Nej, Power BI skal bruge en netværksforbindelse for at vise kortene.

## <a name="next-steps"></a>Næste trin
Få hjælp: **Esri** leverer [omfattende dokumentation](https://go.microsoft.com/fwlink/?LinkID=828772) om funktionssættet i **ArcGIS Maps for Power BI**.

Du kan stille spørgsmål, finde de seneste oplysninger, rapportere problemer og finde svar i Power BI [community'ets tråd om **ArcGIS Maps for Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771).


[Produktsiden med ArcGIS Maps for Power BI](https://www.esri.com/powerbi)
