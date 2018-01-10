---
title: "Føj en visualisering, side eller detaljeadgang eller et rapportfilter til en rapport"
description: "Føj et sidefilter, visualiseringsfilter eller rapportfilter til en rapport i Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: bd358b8e986313ba665326de0ff2722e0113554d
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2018
---
# <a name="add-a-filter-to-a-power-bi-report-in-editing-view"></a>Føj et filter til en rapport i Power Bi (i redigeringsvisning)
> [!TIP]
> Det anbefales, at du først læser [Om filtre og markering i Power BI-rapporter](power-bi-reports-filters-and-highlighting.md).
> 
> 

## <a name="what-is-the-difference-between-report-filters-in-editing-view-versus-reading-view"></a>Hvad er forskellen mellem rapportfiltrene i redigeringsvisning i forhold til læsevisning?
Du kan interagere med rapporter i to forskellige tilstande: [Læsevisning](service-reading-view-and-editing-view.md) og [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md).  Og de filterfunktioner, der er tilgængelige, afhænger af hvilken tilstand du arbejder i.

* Du kan tilføje rapport- og sidefiltre samt visualiseringsfiltre i redigeringsvisning. Når du gemmer rapporten, gemmes filtrene sammen med den. Personer, der ser på rapporten i læsevisning, kan arbejde med de filtre, som du har tilføjet, men ikke gemme deres ændringer.
* I læsevisning kan du arbejde med alle filtre til rapporter, sider og visualiseringer, der allerede findes i rapporten, men du kan ikke gemme dine filterændringer.

> [!NOTE]
> I denne artikel beskrives det, hvordan du opretter filtre i **redigeringsvisning**  til rapporter.  Du kan finde flere oplysninger om filtre i læsevisning i afsnittet om [brug af filtre i læsevisning](service-reading-view-and-editing-view.md).
> 
> 

## <a name="visual-filters-page-filters-drillthrough-filters-and-report-filters"></a>Visuelle filtre, sidefiltre, filtre til detaljeadgang og rapportfiltre
Et **sidefilter** gælder for alle visuelle elementer på rapportsiden. Et **visuelt filter** gælder for et enkelt visuelt element på rapportsiden. Og et **rapportfilter** gælder for alle sider i rapporten.

![](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

## <a name="add-a-filter-to-a-specific-visualization-aka-visual-filter"></a>Føj et filter til en bestemt visualisering (også kaldet visuelt filter)
Der er to måder, du kan gøre dette på: 

* Ved at filtrere et felt, der allerede bruges i visualiseringen
* ved at identificere et felt, der ikke allerede bruges i visualiseringen, og føje dette felt direkte til bucket'en **Filtre på visualiseringsniveau**.

### <a name="by-filtering-the-fields-already-in-the-visualization"></a>Ved at filtrere felterne der allerede findes i visualiseringen
1. Åbn din [rapport i redigeringsvisning](service-reading-view-and-editing-view.md).
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Åbn ruden Visualizations and Filters (Visualiseringer og filtre) og ruden Felter (hvis de ikke allerede er åbne).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Vælg først en visualisering for at aktivere den. Alle felter, der bruges af det visuelle element, er identificeret i ruden **Felter** og også angivet i ruden **Filtre** under overskriften **Filtre på visualiseringsniveau**.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Herefter skal du føje et filter til et felt, der er allerede bruges i visualiseringen. 
   
   * Rul ned til området **Filtre på visualiseringsniveau**, og brug pilen til at udvide det felt, du vil filtrere efter. I dette eksempel skal vi filtrere **StoreNumberName**
     
      ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
   * Angiv et af kontrolelementerne **Basic**, **Advanced** eller **Top N** (se [Sådan bruger du rapportfiltre](power-bi-how-to-report-filter.md)). I dette eksempel vælger vi filtreringen Basic og markerer tallene 10, 11, 15 og 18.
     
      ![](media/power-bi-report-add-filter/power-bi-basic-filters.png) 
   * Visualiseringen ændres for at afspejle det nye filter. Hvis du gemmer din rapport med filteret, kan rapportlæsere interagere med filteret i læsevisning og markere eller fjerne markering af værdier.
     
      ![](media/power-bi-report-add-filter/power-bi-filter-effect.png)
5. Nu skal vi føje et helt nyt felt som et filter på visualiseringsniveau til vores visualisering.
   
   * Vælg i ruden Felter det felt, du vil tilføje som et nyt filter på visualiseringsniveau, og træk det til **området Filtre på visualiseringsniveau**.  I dette eksempel skal vi trække **District Manager** (Distriktchef) til bucket'en **Filtre på visualiseringsniveau** og kun vælge Andrew Ma. 
     
      ![](media/power-bi-report-add-filter/power-bi-andrew.png)
   * Bemærk, at **District Manager** *ikke* føjes til selve visualiseringen. Visualiseringen består stadig af **StoreNumberName** som akse og **This Year Sales** som værdi.  
     
      ![](media/power-bi-report-add-filter/power-bi-visualization.png)
   * Og selve visualiseringen filtreres nu, så kun Andrew's salg for året for de angivne butikker vises.
     
     ![](media/power-bi-report-add-filter/power-bi-filtered-andrew.png)

## <a name="add-a-filter-to-an-entire-page-aka-page-view-filter"></a>Føj et filter til en hel side (også kaldet sidevisningsfilter)
1. Åbn din [rapport i redigeringsvisning](service-reading-view-and-editing-view.md).
2. Åbn ruden Visualizations and Filters (Visualiseringer og filtre) og ruden Felter (hvis de ikke allerede er åbne).
3. Vælg i ruden Felter det felt, du vil tilføje som et nyt filter på sideniveau, og træk det til **området Filtre på sideniveau**.  
4. Vælg de værdier, du vil filtrere efter, og angiv enten kontrolelementet **Basic** eller **Advanced** (se [Sådan bruger du rapportfiltre](power-bi-how-to-report-filter.md)).
   
   Al visualisering på siden, der er påvirket af dette filter, tegnes igen, så ændringen afspejles. 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

Hvis du gemmer din rapport med filteret, kan rapportlæsere interagere med filteret i læsevisning og markere eller fjerne markering af værdier.

## <a name="add-a-drillthrough-filter"></a>Tilføj et filter til detaljeadgang
Med detaljeadgang i Power BI-tjenesten og Power BI Desktop kan du oprette en *destination* på en rapportside, som fokuserer på en bestemt enhed – f.eks. en leverandør, en kunde eller en producent. Nu kan brugere via andre rapportsider højreklikke på et datapunkt for denne enhed og opnå detaljeadgang til den fokuserede side.

### <a name="create-a-drillthrough-filter"></a>Opret et filter til detaljeadgang
Følg med ved at åbne eksemplet på kunderentabilitet i redigeringsvisning. Antag, at du vil have en side med fokus på overordnede forretningsområder.   

1. Føj en ny side til rapporten, og kald den **Team Executive**. Dette bliver siden med *destinationen*, der er detaljeadgang til.
2. Tilføj visualiseringer, der sporer vigtige målepunkter for teamets overordnede forretningsområder.    
3. Føj desuden **Executive > Executive Name** til filtrene til detaljeadgang.    
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Bemærk, at Power BI føjer en tilbage-pil til rapportsiden.  Når tilbage-pilen vælges, returneres brugere til den *oprindelige* rapportside – den side, de var placeret på, da de valgte detaljeadgang. Tilbage-pil fungerer kun i læsevisning.
   
     ![](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Brug filteret til detaljeadgang
Lad os se, hvordan filteret til detaljeadgang fungerer.

1. Start på rapportsiden **Team Scorecard**.    
2. Antag, at du er Andrew Ma, og at du vil have vist rapportsiden Team Executive filtreret udelukkende efter dine data.  Højreklik i områdediagrammet øverst til venstre på et vilkårligt grønt datapunkt for at åbne menupunktet Detaljeadgang.
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. Vælg **Detaljeadgang > Team Executive** for at få detaljeadgang til rapportsiden med navnet **Team Executive**. Siden filtreres, så den viser oplysninger om det datapunkt, du har højreklikket fra, i dette tilfælde Andrew Ma. Det er kun det felt, der er i Detaljeadgang-filtrene, der sendes videre til rapportsiden med detaljeadgang.  
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-filter-to-an-entire-report-aka-report-filter"></a>Føj et filter til hele rapporten (også kaldet rapportfilter)
1. Åbn din [rapport i redigeringsvisning](service-reading-view-and-editing-view.md).
2. Åbn ruden Visualizations and Filters (Visualiseringer og filtre) og ruden Felter (hvis de ikke allerede er åbne).
3. Vælg i ruden Felter det felt, du vil tilføje som et nyt filter på rapporteringsniveau, og træk det til området **Filtre på rapporteringsniveau**.  
4. Vælg de værdier, du vil filtrere efter (se [Sådan bruger du rapportfiltre](power-bi-how-to-report-filter.md)).

De visuelle elementer på den aktive side og på alle sider i rapporten ændres for at afspejle det nye filter. Hvis du gemmer din rapport med filteret, kan rapportlæsere interagere med filteret i læsevisning og markere eller fjerne markering af værdier.

1. Vælg tilbage-pilen for at vende tilbage til den forrige rapportside.

## <a name="troubleshooting"></a>Fejlfinding
### <a name="why-your-visual-level-filter-and-page-level-filter-may-return-different-results"></a>Derfor kan dit filter på visualiseringsniveau og dit filter på sideniveau returnere forskellige resultater
Når du tilføjer et filter på visualiseringsniveau, filtrerer Power BI ud fra de sammenlagte resultater.  Standardsammenlægningen er Sum, men du kan [ændre sammenlægningstypen](service-aggregates.md).  

Når du tilføjer et filter på sideniveau, filtrerer Power BI uden sammenlægning.  Grunden til dette er, at en side kan have mange visuelle elementer, som hver især kan gøre brug af forskellige sammenlægningstyper.  Filteret anvendes derfor til hver enkelt datarække.

Hvis du ikke får vist ruden Felter, skal du sikre dig, at du er i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md) for rapporten

## <a name="next-steps"></a>Næste trin
 [Sådan bruger du rapportfiltre](power-bi-how-to-report-filter.md)

  [Filtre og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md)

[Arbejd med filtre og fremhævning i læsevisning for en rapport](service-reading-view-and-editing-view.md)

[Rediger, hvordan visualiseringer i rapporter krydsfiltrerer og krydsfremhæver hinanden](service-reports-visual-interactions.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

