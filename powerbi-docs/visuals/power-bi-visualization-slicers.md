---
title: Udsnitsværktøjer i Power BI
description: Et Power BI-udsnit er en alternativ metode til filtrering, som begrænser den del af datasættet, der vises i andre visualiseringer i en rapport.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 04/06/2020
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: cba1a79f0089fd17b69d6babf93c8a5d4b08bd6a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85234808"
---
# <a name="slicers-in-power-bi"></a>Udsnitsværktøjer i Power BI

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Du kan f.eks. give rapportlæserne mulighed for at se de overordnede salgstal, men samtidig fremhæve resultaterne for individuelle distriktschefer og forskellige tidsperioder. Du kan oprette separate rapporter eller diagrammer til sammenligning. Du kan også bruge *udsnitsværktøjer*. Et udsnit er en alternativ metode til filtrering, som begrænser den del af datasættet, der vises i andre visualiseringer i en rapport. 

![Animation af udsnit](media/power-bi-visualization-slicers/slicer2.gif)

I denne artikel gennemgås, hvordan du opretter og formaterer et grundlæggende udsnitsværktøj ved hjælp af det gratis [eksempel på en detailhandelsanalyse](../create-reports/sample-retail-analysis.md). Det gennemgås også, hvordan du kan styre, hvilke visualiseringer der påvirkes af et udsnitsværktøj, og hvordan du synkroniserer med udsnitsværktøjer på andre sider. Her er nogle andre artikler, der indeholder fremgangsmåder til, hvordan du opretter bestemte typer udsnitsværktøjer:

- [Udsnitsværktøjer til numerisk område](../create-reports/desktop-slicer-numeric-range.md).
- [Udsnitsværktøjer til relative datoudsnit](desktop-slicer-filter-date-range.md).
- Dynamiske [udsnitsværktøjer, hvis størrelse kan ændres](../create-reports/power-bi-slicer-filter-responsive.md).
- [Hierarkiske udsnitsværktøjer](../create-reports/power-bi-slicer-hierarchy-multiple-fields.md) med flere felter.

## <a name="when-to-use-a-slicer"></a>Hvornår man bruger et udsnit
Udsnit er et fantastisk valg, når du vil:

* vise almindeligt anvendte eller vigtige filtre på rapportlærredet for at få lettere adgang.
* gøre det nemmere at se den aktuelle filtrerede tilstand uden at skulle åbne en rulleliste 
* filtrere efter kolonner, der ikke er behov for, og som er skjult i datatabeller
* oprette mere fokuserede rapporter ved at placere udsnit ved siden af vigtige visualiseringer.

Power BI-udsnitsværktøjer understøtter ikke:

- Inputfelter
- Detailudledning

## <a name="create-a-slicer"></a>Opret et udsnit

Dette udsnitsværktøj filtrerer data efter distriktschef. Hvis du vil følge med i denne fremgangsmåde, kan du downloade eksempelfilen [PBIX-eksempel på detailhandelsanalyse](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Åbn Power BI Desktop, og vælg **Filer** > **Åbn**.
   
1. Gå til filen **Retail Analysis sample PBIX.pbix**, og vælg derefter **Åbn**.

1. I ruden til venstre skal du vælge ikonet **Rapport**![Ikonet Rapport](media/power-bi-visualization-kpi/power-bi-report-view.png) for at åbne filen i rapportvisning.

1. Uden at have markeret noget på rapportlærredet skal du på siden **Oversigt** vælge ikonet **Udsnit**![Ikonet Udsnit](media/power-bi-visualization-slicers/slicer-icon.png) i ruden **Visualiseringer** for at oprette et nyt udsnit. 

1. Med det nye udsnit markeret skal du vælge **Distrikt** > **DM** i ruden **Felter** for at udfylde udsnittet. 

    Det nye udsnit er nu udfyldt med en liste over distriktschefernes navne og deres markeringsfelter.
    
    ![Udsnit, der er udfyldt med distriktschefers navne](media/power-bi-visualization-slicers/power-bi-new-slicer.png)
    
1. Tilpas størrelsen på og træk elementerne på lærredet for at gøre plads til udsnittet. Bemærk, at hvis du ændrer størrelsen på udsnittet, så det bliver for lille, afskæres elementerne. 

1. Vælg navne på udsnittene, og bemærk, hvordan det påvirker de øvrige visualiseringer på siden. Vælg navnene igen for at fjerne markeringen af dem, eller hold **Ctrl** nede for at markere mere end ét navn. Hvis du markerer alle navnene, vil det have samme effekt som ikke at markere nogen af dem. 

1. Du kan også vælge **Format** (ikonet med malerrullen) i ruden **Visualiseringer** for at formatere dit udsnit. 

   Der er for mange muligheder til at kunne beskrive dem alle her. Eksperimentér, og opret et udsnit, der fungerer for dig. På følgende billede er retningen vandret i det første udsnit, og der bruges farvede baggrunde til elementerne. I det andet udsnit er retningen lodret, og der bruges farvet tekst, så du får et mere standardiseret udseende.

   ![Formateret udsnit](media/power-bi-visualization-slicers/power-bi-filter-examples.png)

   >[!TIP]
   >Udsnitslisteelementer sorteres som standard i stigende rækkefølge. Hvis du i stedet vil ændre sorteringsrækkefølgen til faldende, skal du vælge ellipsen ( **...** ) i øverste højre hjørne af udsnittet og vælge **Sortér faldende**.

## <a name="control-which-page-visuals-are-affected-by-slicers"></a>Styr, hvilke visualiseringer på siden der påvirkes af udsnit
Som standard påvirker udsnit på rapportsider alle andre visualiseringer på den samme side – også hinanden. Når du vælger værdier i de liste- og datoudsnit, du har oprettet, kan du se ændringerne i de andre visualiseringer. De filtrerede data er skæringspunktet for de værdier, der er valgt i begge udsnit. 

Brug visuelle interaktioner til at forhindre, at nogle visualiseringer på siden bliver påvirket. På siden **Oversigt** viser diagrammet **Total Sales Variance by FiscalMonth and District Manager** de overordnede sammenlignelige data for distriktschefer efter måned, som du vil vise hele tiden. Brug visuelle interaktioner for at forhindre, at valg i udsnit filtrerer dette diagram. 

1. Gå til siden **Oversigt** i rapporten, og vælg derefter det **DM**-udsnit, du har oprettet tidligere.

1. I Power BI Desktop-menuen skal du vælge **Formatér** under **Visuelle værktøjer** og derefter vælge **Rediger interaktioner**.
   
   Kontrolelementer til filtrering ![Kontrolelementer til filtrering](media/power-bi-visualization-slicers/filter-controls.png), der hver især har et **filter** og indstillingen **Ingen**, vises over alle de visuelle elementer på siden. Indstillingen **Filter** er valgt på forhånd for alle kontrolelementerne.
   
1. Vælg indstillingen **Ingen** i kontrolelementet til filtrering over diagrammet **Total Sales Variance by FiscalMonth and District Manager** for at forhindre, at **DM**-udsnittet filtrerer diagrammet. 

1. Vælg udsnittet **OpenDate**, og vælg derefter **Ingen** over diagrammet **Total Sales Variance by FiscalMonth and District Manager** for at forhindre, at dette udsnit filtrerer diagrammet. 

   Når du vælger navne og datoområder i udsnittet, vil diagrammet **Total Sales Variance by FiscalMonth and District Manager** nu forblive uændret.

Du kan finde flere oplysninger om redigering af interaktioner under [Rediger, hvordan visualiseringer interagerer i en Power BI-rapport](../create-reports/service-reports-visual-interactions.md).

## <a name="sync-and-use-slicers-on-other-pages"></a>Synkroniser og brug udsnit på andre sider
Fra og med opdateringen af Power BI i februar 2018 kan du synkronisere et udsnit og bruge det på en hvilken som helst side i en rapport. 

I den aktuelle rapport på siden **Månedligt salg for distrikt** er der et udsnit af typen **District Manager**, men hvad nu hvis vi også gerne vil have dette udsnit på siden **Nye butikker**? Siden **Nye butikker** har et udsnit, men det indeholder kun oplysninger om **Butiksnavn**. Ved hjælp af ruden **Synkroniser udsnit** kan du synkronisere udsnittet **District Manager** med disse sider, så markeringer af udsnit på en hvilken som helst side påvirker visualiseringerne på alle tre sider.

1. I menuen **Vis** i Power BI Desktop skal du vælge **Synkroniser udsnit**.

    ![Synkroniser valgte udsnit](media/power-bi-visualization-slicers/power-bi-slicer-view-sync.png)

    Ruden **Synkroniser udsnit** vises mellem ruderne **Filtre** og **Visualiseringer**.

    ![Ruden Synkroniser udsnit](media/power-bi-visualization-slicers/power-bi-slicer-sync-pane.png)

1. På siden **Månedligt salg for distrikt** i rapporten skal du vælge udsnittet **District Manager**. 

    Da du allerede har oprettet udsnittet **District Manager** (**DM**) på siden **Oversigt**, vises ruden **Synkroniser udsnit** på følgende måde:
    
    ![Synkroniser udsnittet Månedligt salg pr. distrikt](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
1. I kolonnen **Synkroniser** i ruden **Synkroniser udsnit** skal du vælge siderne **Oversigt**, **Månedligt salg pr. distrikt** og **Nye butikker**. 

    Dette valg medfører, at udsnittet **Månedligt salg pr. distrikt** synkroniseres på tværs af disse tre sider. 
    
1. I kolonnen **Synlig** i ruden **Synkroniser udsnit** skal du vælge siden **Nye butikker**. 

    Dette valg medfører, at udsnittet **Månedligt salg pr. distrikt** er synligt på disse tre sider. Ruden **Synkroniser udsnit** vises nu på følgende måde:

    ![Vælg sider i Synkroniser udsnit](media/power-bi-visualization-slicers/power-bi-sync-slicer-finished.png)

1. Se, hvordan synkronisering af slideren påvirker de andre sider. På siden **District Monthly Sales** skal du lægge mærke til, at udsnittet **District Manager** nu viser de samme valg som dem på siden **Oversigt**. På siden **Nye butikker** er udsnittet **District Manager** nu synligt, og valgene påvirker, hvilke valg der er synlige i udsnittet **Store Name**. 
    
    >[!TIP]
    >Selvom udsnittet vises på de synkroniserede sider med samme størrelse og placering som på den oprindelige side, kan du flytte dem, ændre deres størrelse og formatere dem uafhængigt på de enkelte sider. 

    >[!NOTE]
    >Hvis du synkroniserer et udsnit med en side, men ikke gør det synligt på siden, vil udsnitsvalgene på de andre sider stadig filtrere dataene på siden.
 
## <a name="filtering-slicers"></a>Filtrering af udsnitsværktøjer
Du kan anvende filtre på visualiseringsniveau på udsnit for at reducere listen over værdier, der vises i udsnittet. Du kan f.eks. filtrere tomme værdier fra et listeudsnit eller filtrere bestemte datoer fra et intervaludsnit. Når du gør det, påvirker det kun *de værdier, der vises i udsnittet* og ikke *det filter, udsnittet anvender for andre visualiseringer*, når du foretager et valg. Lad os f.eks. sige, at du anvender et filter på et intervaludsnit, så det kun er bestemte datoer, der vises. Valget for udsnittet viser kun de første og sidste datoer fra området, men du vil stadig kunne se andre datoer i dine andre visualiseringer. Når du har ændret det valgte område i udsnittet, kan du se, at de andre visualiseringer opdateres. Hvis du rydder udsnittet, vises alle datoer igen.

Se [Filtertyper](../create-reports/power-bi-report-filter-types.md) for at få flere oplysninger om filtre på visualiseringsniveau.

## <a name="format-slicers"></a>Formatér udsnit
Der findes forskellige indstillinger til formatering afhængigt af udsnitstypen. Hvis du bruger retningen **Vandret**, layoutet **Dynamisk** og **elementfarver**, kan du oprette knapper eller felter i stedet for almindelige listeelementer og få elementer i udsnit til at tilpasse størrelse, så de passer til forskellige skærmstørrelser og layout.  

1. Med udsnittet **District Manager** markeret på en vilkårlig side skal du i ruden **Visualiseringer** vælge ikonet **Formatér**![Ikonet Formatér](media/power-bi-visualization-slicers/power-bi-paintroller.png) for at få vist kontrolelementerne til formatering. 
    
    ![Valg af formatering](media/power-bi-visualization-slicers/3-format.png)
    
1. Klik på pilene i rullelisten ud for hver kategori for at få vist og redigere indstillingerne. 

### <a name="general-options"></a>Generelle indstillinger
1. Under **Format** skal du vælge **Generelt**, vælge en rød farve under **Konturfarve** og derefter ændre **Konturtykkelse** til *2*. 

    Denne indstilling ændrer konturens farve og tykkelse eller understregning for overskrifter og elementer.

1. Under **Retning** er **Lodret** valgt som standard. Vælg **Vandret** for at få et udsnit med vandret arrangerede felter eller knapper, og rul med pilene for at få adgang til elementer, der ikke vises på skyderen.
    
    ![Generelle valg](media/power-bi-visualization-slicers/4-horizontal.png)
    
1. Slå layoutet **Dynamisk** **til** for at ændre størrelsen på og placeringen af udsnitselementerne efter visningsskærm og udsnitsstørrelse. 

    For listeudsnit forhindrer dynamisk layout, at elementer afskæres på små skærme. Det er kun tilgængeligt i vandrette retninger. For udsnit med intervalskydere vil dynamisk formatering ændre formatet for skyderen og give mere fleksible muligheder for tilpasning af størrelsen. Begge typer udsnit ændres til filterikoner ved små størrelser.
    
    ![Angiv dynamisk layout](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Ændringer af dynamisk layout kan tilsidesætte særlig formatering af overskrifter og elementer, som du har angivet. 
    
1. Under **X-placering**, **Y-placering**, **Bredde** og **Højde** skal du angive skyderens placering og størrelse med tal eller flytte og tilpasse størrelsen på udsnittet direkte på lærredet. 

    Afprøv forskellige størrelser på og placering af elementer, og se, hvordan dynamisk formatering ændres derefter. Disse indstillinger er kun tilgængelige, når du vælger vandrette retninger. 

    ![Indstillinger for vandrette retninger](media/power-bi-visualization-slicers/6-buttons.png)

Du kan finde flere oplysninger om vandrette retninger og dynamisk layout under [Opret et dynamisk udsnitsværktøj, som du kan ændre størrelsen på i Power BI](../create-reports/power-bi-slicer-filter-responsive.md).

### <a name="selection-controls-options-list-slicers-only"></a>Indstillinger for Kontrolelementer til markering (angiv kun udsnit)
1. Under **Kontrolelementer til markering** skal du slå **Vis indstillingen "Vælg alle"** **til** for at føje et **Vælg alle**-element til udsnittet. 

    **Vis indstillingen "Vælg alle"** er som standard slået **fra**. Når denne indstilling er aktiveret, vælges eller fravælges alle elementer, når den slås til eller fra. Hvis du vælger alle elementer og fravælger et element, fravælges det og gør det muligt at anvende et filter af typen *is-not*.
    
    ![Kontrolelementer til markering](media/power-bi-visualization-slicers/7-select-all.png)
    
1. Slå **Vælg én** **fra** for at gøre det muligt at vælge flere elementer uden at skulle holde **Ctrl** nede. 

    **Vælg én** er som standard slået **til**. Når du markerer et element, vælges det, og hvis du holder **Ctrl** nede, vælges der flere elementer. Når du vælger et element igen, fravælger du det.

### <a name="title-options"></a>Titelindstillinger
**Titel** er som standard slået **til**. Dette valg viser datafeltets navn øverst i udsnittet. 
- I denne artikel skal du formatere titelteksten på følgende måde: 
   - **Skriftfarve**: rød
   - **Tekststørrelse**: **14 pt**
   - **Justering**: **Centrer**
   - **Skrifttypefamilie**: **Arial Black**


### <a name="items-options-list-slicers-only"></a>Indstillinger for elementer (kun listeudsnit)
1. Formater indstillingerne **Elementer** på følgende måde:
    - **Skriftfarve**: sort
    - **Baggrund**: lys rød
    - **Tekststørrelse**: **10 pt**
    - **Skrifttypefamilie**: **Arial**
 
1. Vælg **Ramme** under **Kontur** for at tegne en kant omkring hvert element med den størrelse og farve, som du har angivet under **Generelle indstillinger**. 
    
    ![Indstillinger for rammekontur](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Når **Generelt** > **Retning** > **Vandret** er valgt, vises den valgte tekst og de valgte baggrundsfarver for fravalgte elementer, mens systemstandarderne bruges for valgte elementer, hvilket normalt er sort baggrund med hvid tekst.
    >- Når **Generelt** > **Retning > Lodret** er valgt, vises de valgte farver altid for elementerne, og afkrydsningsfelterne er altid sorte, når de er markeret. 

### <a name="datenumeric-inputs-and-slider-options-range-slider-slicers-only"></a>Dato/numerisk input og indstillinger for skyder (kun for udsnit med intervalskyder)
- For listeudsnit er indstillingerne for dato/numerisk input de samme som indstillingerne for **Element**, men der er ingen indstillinger for kontur eller understregning.
- Med indstillingerne for **skyderen** kan du angive farven på intervalskyderen, eller du kan slå skyderen **fra** og kun bruge numerisk input.

### <a name="other-formatting-options"></a>Andre formateringsindstillinger
De andre formateringsindstillinger er som standard slået **fra**. Slå disse indstillinger **til** for at styre dem: 
- **Baggrund**: Føj en baggrundsfarve til udsnittet, og angiv gennemsigtigheden.
- **Lås højde-bredde-forhold**: Bevarer formen af udsnittet, hvis størrelsen tilpasses.
- **Kant**: Tilføjer en kant rundt om udsnittet og angiver farven på den. Denne udsnitskant er særskilt og ikke påvirket af indstillingerne under **Generelt**. 

## <a name="next-steps"></a>Næste trin
Du kan få flere oplysninger i følgende artikler:

- [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

- [Tabeller i Power BI](power-bi-visualization-tables.md)
