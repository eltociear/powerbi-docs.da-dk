---
title: Visualiseringstyper i Power BI til forbrugere
description: Visualiseringstyper i Power BI-tjenesten
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 02/21/2019
ms.author: mihart
LocalizationGroup: Consumer
ms.openlocfilehash: ea86970565717d5dae8db865a65765f2c8245bad
ms.sourcegitcommit: a054782370dec56d49bb205ee10b7e2018f22693
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/22/2019
ms.locfileid: "56662382"
---
# <a name="visualization-types-in-power-bi"></a>Visualiseringstyper i Power BI
Du finder visualiseringer i rapporter, på dashboards, i apps og under Spørgsmål og svar. Nogle af disse visualiseringstyper medfølger Power BI som en del af pakken, og nogle er *brugerdefinerede visualiseringer*. Brugerdefinerede visualiseringer oprettes uden for Power BI og på en måde, der gør det muligt for *rapportdesignere* at føje dem til rapporter, dashboards og apps i Power BI. 

Denne artikel indeholder en oversigt over de visualiseringer, der medfølger Power BI som en del pakken.  Disse visualiseringstyper er dem, du oftest vil støde på. 

> [!NOTE]
> Du kan få mere at vide om brugerdefinerede visualiseringer ved at søge efter dem i afsnittet **Power BI-visualiseringer** i [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals). For hver enkelt visualisering finder du en beskrivelse, forfatteroplysninger og enten skærmbilleder eller en video. 

## <a name="list-of-visualizations-available-in-power-bi"></a>Liste over de visualiseringer, der er tilgængelige i Power BI
Du finder alle disse visualiseringer i apps, på dashboards, i rapporter og [angivet under Spørgsmål og svar](#qna) i Power BI. Hvis du vil vide mere om, hvordan du interagerer med visualiseringer, skal du se [Interager med visualiseringer i rapporter, på dashboards og i programmer](end-user-visualizations.md)

### <a name="area-charts-basic-layered-and-stacked"></a>Områdediagrammer: Grundlæggende (lagdelte) og stablede
![områdediagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/basicareamapsmall.png)

Det grundlæggende områdediagram er baseret på kurvediagrammet med området mellem aksen og kurven udfyldt. Områdediagrammer fremhæver omfanget af ændringer over tid og kan bruges til at fremhæve den samlede værdi på tværs af en udvikling. Data, som repræsenterer indtjening over tid, kan f.eks. afbildes i et områdediagram for at fremhæve den samlede indtjening.

### <a name="bar-and-column-charts"></a>Liggende søjlediagrammer og søjlediagrammer
![søjlediagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_bar.png)

 ![liggende søjlediagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_col.png)

Liggende søjlediagrammer er standarden for at finde en specifik værdi på tværs af en række kategorier.

### <a name="cards-single-number"></a>Kort: Enkelt tal
![kort med enkelt tal](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_card.png)

Kort med et enkelt tal viser et enkelt faktum, dvs. et enkelt datapunkt. Nogle gange er et enkelt tal det vigtigste, du vil finde frem til på dit Power BI-dashboard eller i din Power BI-rapport som f.eks. salg i alt, markedsandel fra år til år eller salgsmuligheder i alt.  

### <a name="cards-multi-row"></a>Kort: Med flere rækker
![Kort med flere rækker](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/multi-row-card.png)

Kort med flere rækker viser et eller flere datapunkter; én pr. række.


### <a name="combo-charts"></a>Kombinationsdiagrammer
![kombinationsdiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/combosmall.png)

I et kombinationsdiagram kombineres et søjlediagram og et kurvediagram. Ved at kombinere disse to diagrammer kan du hurtigere sammenligne dine data. Kombinationsdiagrammer kan have en eller to Y-akser, så sørg for at se nøje efter. 

Kombinationsdiagrammer er et fantastisk valg i følgende tilfælde:
- Når du har et kurvediagram og et søjlediagram med den samme X-akse.
- til at sammenligne flere målinger med forskellige værdiområder
- til at illustrere sammenhængen mellem to målinger i én visualisering
- Til at kontrollere, om en måling opfylder målet, der er defineret af en anden måling
- til at spare plads på lærredet.

### <a name="doughnut-charts"></a>Kransediagrammer
![kransediagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/donutsmall.png)

Kransediagrammer ligner cirkeldiagrammer.  De viser relationen mellem dele og en helhed. Den eneste forskel er, at centreret i det er tomt og giver plads til en etiket eller et ikon.

### <a name="funnel-charts"></a>Tragtformede diagrammer
![tragtformet diagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_funnel.png)

Tragtformede diagrammer hjælper med at visualisere en proces med faser og elementer, der flyder sekventielt fra den ene fase til den næste.  Et eksempel er en salgsproces, der starter med kundeemner og ender med køb.

F.eks. et tragtformet salgsdiagram, der sporer kunder gennem forskellige faser: Kundeemne > Kvalificeret kundeemne > Kundeemne > Kontrakt > Luk. I korte træk afspejler tragtens form tilstanden af den proces, du holder øje med.
De enkelte faser i tragten repræsenterer en procentdel af det samlede antal. Så i de fleste tilfælde vil et tragtformet diagram være formet som en tragt – hvor det første trin er det største, og hvor hvert efterfølgende trin bliver mindre end det foregående. En pæreformet tragt er også nyttig – det kan bruges til at identificere et problem i processen. Det første trin i fasen, "indgangsfasen", er dog typisk det største.

Tragtformede diagrammer er et fantastisk valg i følgende tilfælde:
- Når dataene er fortløbende og dækker over mindst fire faser.
- Når antallet af "elementer" i den første fase forventes at være større end antallet i den sidste fase.
- Til at beregne potentiale (omsætning/salg/handler/osv.) efter fase.
- Til at beregne og holde øje med gennemførelsesfrekvens og fastholdelsesrate.
- Til at vise flaskehalse i en lineær proces.
- Til at holde øje med arbejdsprocessen i forbindelse med indkøbskurv.
- Til at holde øje med statussen på og succesen af reklame-/marketingkampagner vha. klikfrekvensen.

### <a name="gauge-charts"></a>Målerdiagrammer
![målerdiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/gauge_m.png)

Et radialt målerdiagram har en cirkulær bue og viser en enkelt værdis status i forhold til et mål/en KPI. Målet, eller målværdien, er repræsenteret med en streg (nål). Statussen mod målet repræsenteres med en skygge. Den værdi, der repræsenterer statussen, vises med fed i buen. Alle de mulige værdier er fordelt langs buen fra minimumværdien (længst til venstre) til maksimumværdien (længst til højre).

I eksemplet ovenfor spores det gennemsnitlige salg pr. måned for salgsteamet hos en bilforhandler. Målet er 140, hvilket repræsenteres med den sorte nål. Det mindst mulige salg er 0, og vi har angivet maksimum til 200. Den blå farve viser, at vi i øjeblikket er på 120 salg i denne måned. Der er heldigvis stadig en uge til at nå målet.

Radiale målere er fantastiske til:
- at vise statussen mod et mål
- repræsentere en percentilmåling, f.eks. KPI
- vise tilstanden for en enkelt måling
- vise oplysninger, der er hurtige at skimme og forstå.

 ### <a name="key-influencers-chart"></a>Diagram over nøglepersoner med indflydelse
![nøgleperson med indflydelse](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-influencer.png)

Et diagram over nøglepersoner med indflydelse viser de største bidragydere for et valgt resultat eller en valgt værdi.

Nøglepersoner med indflydelse er et godt valg til at hjælpe dig med at forstå de faktorer, der påvirker en nøglemetrikværdi. Det kan eksempelvis være, *hvad der har indflydelse på, at kunderne afgiver ordre nummer to *, eller* hvorfor salget var så højt sidste år i juni*. 

### <a name="kpis"></a>KPI'er
![KPI](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-kpi.png)

Et nøgletal (KPI) er en visuel ledetråd, der viser fremgangen mod et målbart mål. 

KPI'er er et godt valg:
- til at måle fremgang (hvad er jeg foran eller bagefter med?)
- til at måle afstanden til et mål (hvor langt foran eller bagefter er jeg?)

### <a name="line-charts"></a>Kurvediagrammer
![kurvediagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_line.png)

Kurvediagrammer fremhæver den overordnede form af en hel serie af værdier som regel over tid.

### <a name="maps-basic-maps"></a>Kort: Basiskort
![basiskort](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi-nancy_viz_map.png)

Brug et basiskort til at knytte både kategoriinddelte og kvantitative oplysninger til spatiale placeringer.

### <a name="maps-arcgis-maps"></a>Kort: ArcGIS-kort
![ArcGis-kort](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-esri-map-theme2.png)

Kombinationen af ArcGIS-kort og Power BI tager kort til et helt nyt niveau, som involverer mere end præsentation af punkter på et kort. De tilgængelige indstillinger til grundlæggende kort, placeringstyper, temaer, symboltypografier og referencelag opretter fantastiske informative kortvisualiseringer. Kombinationen af autoritative datalag på et kort (f.eks. census-data) med rumlige analyser giver en bedre forståelse af dataene i visualiseringen.

### <a name="maps-filled-maps-choropleth"></a>Kort: Kartogrammer (Choropleth)
![Kartogram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_filledmap.png)

Et udfyldt kort bruger skygger eller toner eller mønstre til at vise, hvordan en værdi varierer i forhold på tværs af et geografisk område eller en region. Fremvis hurtigt disse relative forskelle med skygger, der går fra lys (mindre-hyppige/lavere) til mørk (mere-hyppige/mere).

### <a name="maps-shape-maps"></a>Kort: Figurkort
![figurkort](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-shape-map2.png)

Med figurkort sammenlignes områder på et kort ved hjælp af farve. I modsætning til visualiseringen M/kort kan der på figurkort ikke vises præcise geografiske placeringer af datapunkter på et kort. I stedet er dets primære formål at vise relative sammenligninger mellem områder på et kort ved at give dem forskellige farver.

### <a name="matrix"></a>Matrix
![matrix](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/matrix.png)

Matrixvisualiseringen er en type tabelvisualisering (se "Tabel" herunder), som understøtter et trinvist layout. Rapportdesignere inkluderer ofte matricer i rapporter og på dashboards, så brugerne kan vælge et eller flere elementer (rækker, kolonner, celler) i matrixen til tværgående fremhævning af andre visualiseringer på en rapportside.  

### <a name="pie-charts"></a>Cirkeldiagrammer
![cirkeldiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_pie.png)

I cirkeldiagrammer vises relationen mellem dele og en helhed. 

### <a name="ribbon-chart"></a>Bånddiagram
![bånddiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-ribbon.png)

I bånddiagrammer vises, hvilken datakategori der har den højeste placering (største værdi). Bånddiagrammer er effektive til at vise ændringer af placeringer, hvor den højeste placering (værdi) altid vises øverst for hver tidsperiode.

### <a name="scatter-bubble-and-dot-plot-charts"></a>Punktdiagrammer, boblediagrammer og prikdiagrammer


Et punktdiagram har altid to værdiakser for at vise ét sæt numeriske data langs en vandret akse og et andet sæt numeriske værdier langs en lodret akse. Diagrammet viser punkter ved skæringspunktet for en numerisk x- og y-værdi og kombinerer disse værdier i enkelte datapunkter. Disse datapunkter kan være fordelt jævnt eller ujævnt på tværs af den vandrette akse afhængigt af dataene.

![boblediagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_bubble.png)

Et boblediagram erstatter datapunkter med bobler, hvor boblestørrelsen repræsenterer en yderligere dimension af dataene.

Et prikdiagram svarer til et boblediagram og et punktdiagram, bortset fra at der plottes numeriske eller kategoriske data langs X-aksen.

### <a name="scatter-high-density"></a>Punktdiagram – høj tæthed
![punktdiagram med høj tæthed](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/density-scatter.png)

Stikprøver af data med høj tæthed tages pr. definition for at kunne oprette visualiseringer forholdsvist hurtigt og bruge disse visualiseringer interaktivt. Ved stikprøvetagning med høj tæthed bruges en algoritme, der fjerner overlappende punkter og sikrer, at alle punkter i datasættet repræsenteres i visualiseringen. Der afbildes ikke blot en repræsentativ stikprøve af dataene.  

Dette sikrer den bedste kombination af svartid, repræsentation og tydelig bevarelse af vigtige punkter i det samlede datasæt.

### <a name="slicers"></a>Udsnit
![udsnit](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_slicer.png)

Et udsnit er et separat diagram, der kan bruges til at filtrere de andre visualiseringer på siden. Udsnit kommer i mange forskellige formater (kategori, område, dato osv.) og kan formateres til kun at tillade valg af én, mange eller alle tilgængelige værdier. 

Udsnit er et fantastisk valg til at:
- vise almindeligt anvendte eller vigtige filtre på rapportlærredet af hensyn til lettere adgang
- gøre det nemmere at se den aktuelle filtrerede tilstand uden at skulle åbne en rulleliste
- filtrere efter kolonner, der ikke er behov for, og som er skjult i datatabeller
- oprette mere fokuserede rapporter ved at placere udsnit ved siden af vigtige visualiseringer.

### <a name="standalone-images"></a>Separate billeder
![separate billeder](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_image.png)

Et separat billede er en grafik, der er blevet føjet til en rapport eller et dashboard. 


### <a name="tables"></a>Tabeller
![tabeldiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/tabletype.png)

En tabel er et gitter, der indeholder relaterede data i logiske serier af rækker og kolonner. Den kan også indeholde overskrifter og en række til totaler. Tabeller fungerer godt med kvantitative sammenligninger, hvor du får vist mange værdier for en enkelt kategori. I denne tabel vises f.eks. fem forskellige målinger for Kategori.

Tabeller er et godt valg til at:
- Se og sammenligne detaljerede data og nøjagtige værdier (i stedet for visuelle repræsentationer).
- Se data i tabelformat.
- Se numeriske data efter kategorier.

### <a name="treemaps"></a>Træstrukturer
![træstrukturdiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_tree.png)

Træstrukturer er diagrammer med farvede rektangler, hvor størrelsen repræsenterer værdien.  De kan være hierarkiske, hvor rektangler er indlejret i de primære rektangler. Pladsen inde i hvert rektangel er allokeret ud fra den værdi, der måles. Og rektanglerne er arrangeret efter størrelse fra øverst til venstre (størst) til nederst til højre (mindst).

Træstrukturer er et godt valg:
- til at vise store mængder hierarkiske data
- når et liggende søjlediagram ikke kan håndtere det store antal værdier effektivt
- til at vise proportionerne mellem de enkelte dele og en helhed
- til at vise fordelingsmønsteret for målingen på tværs af hvert niveau af kategorier i hierarkiet
- til at vise attributter ved hjælp af størrelse og farvekodning
- til at identificere mønstre, udenforliggende værdier, de vigtigste bidragsydere samt undtagelser.

### <a name="waterfall-charts"></a>Vandfaldsdiagrammer
![vandfaldsdiagram](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/waterfallsmall.png)

Et vandfaldsdiagram viser en løbende total som værdier, der tilføjes eller trækkes fra. Det er nyttigt for at forstå, hvordan en indledende værdi (f.eks, årets resultat) påvirkes af en række positive og negative ændringer.

Kolonnerne er farvekodet, så du hurtigt kan se stigninger og fald. Kolonnerne med den indledende og endelige værdi starter ofte på den vandrette akse, mens de mellemliggende værdier er flydende kolonner. Vandfaldsdiagrammer kaldes også brodiagrammer på grund af deres "udseende".

Vandfaldsdiagrammer er et godt valg:
- når du har ændringer til målingen på tværs af tidsserier eller forskellige kategorier
- til overvågning af overordnede ændringer, der bidrager til den samlede værdi
- til afbildning af årets resultatet for virksomhed vha. visning af flere omsætningskilder og opnåelse af det samlede resultat.
- til illustration af antal medarbejdere ved årets start og slutning
- til visualisering af, hvor mange penge du tjener og bruger hver måned, samt den løbende kontobalance.

## <a name="tell-qa-which-visualization-to-use"></a>Fortæl Spørgsmål og svar, hvilken visualisering der skal bruges
Når du skriver forespørgsler i naturligt sprog med Spørgsmål og svar i Power BI, kan du angive visualiseringstypen i din forespørgsel.  Eksempel:

"***salg efter område som trækort***"

![Spørgsmål og svar-session](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/qatreemap.png)

## <a name="next-steps"></a>Næste trin
[Interager med visualiseringer i rapporter, på dashboards og i programmer](end-user-visualizations.md)    
[Den rette visuelle reference fra sqlbi.com](http://www.sqlbi.com/wp-content/uploads/videotrainings/dashboarddesign/visuals-reference-may2017-A3.pdf)