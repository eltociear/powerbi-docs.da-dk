---
title: Føj et filter til en rapport i redigeringsvisning
description: Føj et sidefilter, visualiseringsfilter eller rapportfilter til en rapport i Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 328c8ab2e236f0ddc0c5116c1f76d343999193ab
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157373"
---
# <a name="add-a-filter-to-a-report-in-editing-view"></a>Føj et filter til en rapport i redigeringsvisning

I denne artikel forklares det, hvordan du føjer et sidefilter, visualiseringsfilter, rapportfilter eller detaljeadgangsfilter til en rapport i Power BI. Eksemplerne i denne artikel er i Power BI-tjenesten. Trinnene er stort set de samme i Power BI Desktop.

**Vidste du det?** Power BI indeholder en ny filtreringsoplevelse, der i øjeblikket findes som en prøveversion. Læs mere om [den nye filtreringsoplevelse i Power BI-rapporter](power-bi-report-filter-preview.md).

## <a name="filters-in-editing-view-or-reading-view"></a>Filtre i redigeringsvisning eller læsevisning
Du kan interagere med rapporter i to forskellige visninger: læsevisning og redigeringsvisning. Hvilke filterfunktioner der er tilgængelige, afhænger af, hvilken visning du arbejder i. Læs alt [om filtre og fremhævning i Power BI-rapporter](power-bi-reports-filters-and-highlighting.md) for at få mere at vide.

I denne artikel beskrives det, hvordan du opretter filtre i **redigeringsvisning**  til rapporter.  Du kan finde flere oplysninger om filtre i læsevisning i afsnittet om [brug af filtre i læsevisning](consumer/end-user-reading-view.md).

## <a name="filter-types-in-the-filters-pane"></a>Filtertyper i ruden Filtre
Uanset om du bruger Desktop-versionen eller Power BI-tjenesten, vises ruden Filtre i højre side af rapportcanvasset. Hvis ruden Filtre ikke er vist, skal du vælge ikonet ">"øverst til højre for at udvide den.

Der findes fire typer filtre: **sidefilter**, **visual-filter**, **detaljeadgangsfilter** og **rapportfilter**.

![ruden filtre i læsevisning](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

Da filtre *bevares*, når du navigerer væk fra rapporten, bevarer Power BI de ændringer, som du foretager i filtre, udsnit og andre datavisninger. Du kan derfor fortsætte, hvor du slap, når du vender tilbage til rapporten. Hvis du ikke vil bevare dine filterændringer, skal du vælge **Nulstil til standard** på den øverste menulinje.

![knappen faste filtre](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-visual"></a>Tilføj et filter i en visual
Du kan føje et filter til en bestemt visual på to forskellige måder (også kaldet et "visualfilter"). 

* Filtrer et felt, der allerede bruges i den pågældende visual.
* Identificer et felt, der ikke allerede bruges i den pågældende visual, og føj dette felt direkte til bucket'en **Filtre på visualiseringsniveau**.

Denne procedure anvender i øvrigt Retail Analysis-eksemplet, hvis du gerne vil downloade den og følge med. Download [Retail Analysis-eksemplet](sample-retail-analysis.md).

### <a name="filter-the-fields-in-the-visual"></a>Filtrer felterne i denne visual


1. Åbn din [rapport i redigeringsvisning](service-the-report-editor-take-a-tour.md).
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Åbn ruden Visualizations and Filters (Visualiseringer og filtre) og ruden Felter (hvis de ikke allerede er åbne).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Vælg først en visualisering for at aktivere den. Alle felter, der bruges af det visuelle element, findes i ruden **Felter** og er desuden angivet i ruden **Filtre** under overskriften **Filtre på visualiseringsniveau**.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Herefter føjer vi et filter til et felt, der allerede bruges i visualiseringen. 
   
    Rul ned til området **Filtre på visualiseringsniveau**, og brug pilen til at udvide det felt, du vil filtrere efter. I dette eksempel filtrerer vi efter **StoreNumberName**.
     
    ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
    
    Angiv et af kontrolelementerne **Basic**, **Advanced** eller **Top N**. I dette eksempel søger vi efter **cha** i Grundlæggende filtrering og vælger de fem butikker.
     
    ![](media/power-bi-report-add-filter/power-bi-search-filter.png) 
   
    Visualiseringen ændres for at afspejle det nye filter. Hvis du gemmer din rapport med filteret, kan rapportlæsere se den visual, der filtreres fra starten, og interagere med filteret i læsevisning og markere eller fjerne markering af værdier.
     
    ![](media/power-bi-report-add-filter/power-bi-search-visual-filter-results.png)

### <a name="filter-with-a-field-thats-not-in-the-visual"></a>Filtrer med et felt, der ikke er i den pågældende visual

Nu skal vi føje et nyt felt til vores visual som et filter på visualiseringsniveau.
   
1. Vælg i ruden Felter det felt, du vil tilføje som et nyt filter på visualiseringsniveau, og træk det til **området Filtre på visualiseringsniveau**.  I dette eksempel trækker vi **District Manager** til bucket'en **Filtre på visualiseringsniveau**, søger efter **an** og vælger de tre chefer. 
     
    ![](media/power-bi-report-add-filter/power-bi-search-add-visual-filter.png)

    Bemærk, at **District Manager** *ikke* føjes til selve visualiseringen. Visualiseringen består stadig af **StoreNumberName** som akse og **This Year Sales** som værdi.  
     
    ![](media/power-bi-report-add-filter/power-bi-visualization.png)

    Og selve visualiseringen filtreres nu, så kun disse chefers omsætning dette år for de angivne butikker vises.
     
    ![](media/power-bi-report-add-filter/power-bi-search-visual-filter-results-2.png)

    Hvis du gemmer din rapport med filteret, kan rapportlæsere interagere med filteret **District Manager** i læsevisning og markere eller fjerne markering af værdier.

## <a name="add-a-filter-to-an-entire-page"></a>Føj et filter til en hel side

Du kan også føje et filter til en hel side (et sidevisningsfilter)
1. Åbn din [rapport i redigeringsvisning](service-the-report-editor-take-a-tour.md).
2. Åbn ruden Visualizations and Filters (Visualiseringer og filtre) og ruden Felter (hvis de ikke allerede er åbne).
3. Vælg i ruden Felter det felt, du vil tilføje som et nyt filter på sideniveau, og træk det til **området Filtre på sideniveau**.  
4. Vælg de værdier, du vil filtrere efter, og angiv enten kontrolelementet **Basic** eller **Advanced**.
   
   Al visualisering på siden, der påvirkes af dette filter, tegnes igen, så ændringen afspejles. 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

    Hvis du gemmer din rapport med filteret, kan rapportlæsere interagere med filteret i læsevisning og markere eller fjerne markering af værdier.

## <a name="add-a-drillthrough-filter"></a>Tilføj et filter til detaljeadgang
Med detaljeadgang i Power BI-tjenesten og Power BI Desktop kan du oprette en *destination* på en rapportside, som fokuserer på en bestemt enhed – f.eks. en leverandør, en kunde eller en producent. Nu kan brugere via andre rapportsider højreklikke på et datapunkt for denne enhed og opnå detaljeadgang til den fokuserede side.

### <a name="create-a-drillthrough-filter"></a>Opret et filter til detaljeadgang
Følg med ved at åbne eksemplet på kunderentabilitet i redigeringsvisning. Antag, at du vil have en side med fokus på overordnede forretningsområder.   

1. Føj en ny side til rapporten, og kald den **Team Executive**. Denne side bliver *destinationen* for detaljeadgang.
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
1. Åbn din [rapport i redigeringsvisning](service-the-report-editor-take-a-tour.md).
2. Åbn ruden Visualizations and Filters (Visualiseringer og filtre) og ruden Felter (hvis de ikke allerede er åbne).
3. Vælg i ruden Felter det felt, du vil tilføje som et nyt filter på rapporteringsniveau, og træk det til området **Filtre på rapporteringsniveau**.  
4. Vælg de værdier, du vil filtrere.

    De visuelle elementer på den aktive side og på alle sider i rapporten ændres for at afspejle det nye filter. Hvis du gemmer din rapport med filteret, kan rapportlæsere interagere med filteret i læsevisning og markere eller fjerne markering af værdier.

1. Vælg tilbage-pilen for at vende tilbage til den forrige rapportside.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

- Der er situationer, hvor dit filter på visualiseringsniveau og dit filter på sideniveau kan returnere forskellige resultater.  Hvis du f.eks. tilføjer et filter på visualiseringsniveau, filtrerer Power BI de samlede resultater.  Standardsammenlægningen er Sum, men du kan [ændre sammenlægningstypen](service-aggregates.md).  

    Hvis du derefter tilføjer et filter på sideniveau, filtrerer Power BI uden sammenlægning.  Der samles ikke, fordi en side kan have mange visualiseringer, som hver især kan gøre brug af forskellige sammenlægningstyper.  Filteret anvendes derfor til hver enkelt datarække.

- Hvis du ikke får vist ruden Felter, skal du sikre dig, at du er i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md) for rapporten    
- Hvis du har foretaget mange ændringer af filtrene, og du vil vende tilbage til de indstillinger, som rapportens forfatter har angivet, skal du vælge **Nulstil til standard** på den øverste menulinje.

## <a name="next-steps"></a>Næste trin
[Få en præsentation af ruden Rapportfiltre](consumer/end-user-report-filter.md)

[Filtre og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md)

[Arbejd med filtre og fremhævning i læsevisning for en rapport](consumer/end-user-reading-view.md)

[Rediger, hvordan visuals i rapporter krydsfiltrerer og krydsfremhæver hinanden](consumer/end-user-interactions.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

