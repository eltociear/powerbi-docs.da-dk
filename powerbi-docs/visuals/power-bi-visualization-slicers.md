---
title: Selvstudium – Udsnit i Power BI
description: Udsnitsværktøjer i Power BI
author: v-thepet
ms.reviewer: ''
featuredvideoid: zIZPA0UrJyA
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 10/22/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 808f27b94e53d5acf351772ef304f9cc69215007
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880816"
---
# <a name="slicers-in-power-bi"></a>Udsnitsværktøjer i Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Du vil gerne give rapportlæserne mulighed for at se de overordnede salgstal, men samtidig fremhæve resultaterne for individuelle distriktsledere (District Manager) og forskellige tidsperioder. Du kan oprette separate rapporter eller diagrammer til sammenligning, eller du kan bruge udsnit. Et udsnit er en alternativ metode til filtrering, som begrænser den del af datasættet, der vises i andre visualiseringer i en rapport. 

I dette selvstudium bruges det gratis [eksempel på detailhandelsanalyse](../sample-retail-analysis.md) til at gennemgå, hvordan du opretter, formaterer og bruger liste- og datointervaludsnit. Mor dig med at opdage måder, du kan formatere og bruge udsnit på. 

![udsnit](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Hvornår man bruger et udsnit
Udsnit er et fantastisk valg, når du vil:

* vise ofte brugte eller vigtige filtre på rapportlærredet af hensyn til lettere adgang
* gøre det nemmere at se den aktuelle filtrerede tilstand uden at skulle åbne en rulleliste 
* filtrere efter kolonner, der ikke er behov for, og som er skjult i datatabeller
* oprette mere fokuserede rapporter ved at placere udsnit ved siden af vigtige visualiseringer.

Der er følgende begrænsninger for udsnit i Power BI:

- Udsnit understøtter ikke inputfelter.
- Detaljeret visning understøttes ikke for udsnit.


## <a name="create-slicers"></a>Opret udsnit

**Opret et nyt udsnit for at filtrere data efter District Manager**

I dette selvstudium bruges [PBIX-filen med eksemplet Detailhandelsanalyse](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Vælg **Fil** > **Åbn** i øverste venstre afsnit af menulinjen
   
2. Find din kopi af **PBIX-filen med eksemplet Detailhandelsanalyse**

1. Åbn **PBIX-filen med eksemplet Detailhandelsanalyse** i rapportvisning ![ikon for skærmbillede af rapportvisning.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Markér ![Skærmbillede af den gule fane.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) for at tilføje en ny side.

2. Uden at have markeret noget på lærredet skal du på siden Oversigt vælge ikonet **Udsnit** ![udsnitsikonet](media/power-bi-visualization-slicers/slicer-icon.png) i ruden **Visualiseringer** for at oprette et nyt udsnit. 
3. Med det nye udsnit markeret skal du vælge **Distrikt** > **DM** i ruden Felter for at udfylde udsnittet. Det nye udsnit er en liste med afkrydsningsfelter ud for navnene. 
    
    ![nyt udsnit](media/power-bi-visualization-slicers/power-bi-new-slicer.png)
    
4. Tilpas størrelsen på udsnittet, og træk udsnittet og andre elementet på lærredet for at gøre plads til udsnittet. Bemærk, at elementerne i udsnittet bliver afskåret, hvis du gør udsnittet for lille. 
5. Vælg navne på udsnittene, og bemærk, hvordan det påvirker de øvrige visualiseringer på siden. Vælg navnene igen for at fjerne markeringen af dem, og hold **Ctrl** nede for at markere mere end ét navn. Hvis du markerer alle navnene, vil det have samme effekt som ikke at markere nogen af dem. 

6. Du kan også vælge malerrulleikonet for at formatere udsnittet. Der er simpelthen for mange muligheder til at kunne beskrive dem alle her. Så eksperimentér, og opret et udsnit, der fungerer for dig. I eksemplerne herunder bruges en vandret retning i det første udsnit, og der bruges farvede baggrunde til elementerne. Det andet udsnit er lodret, og teksten er i stedet farvet for at give et mere standardudseende.

   ![nyt udsnit](media/power-bi-visualization-slicers/power-bi-filter-examples.png)
>[!TIP]
>Listeudsnitselementer sorteres som standard i stigende rækkefølge. Hvis du i stedet vil ændre sorteringsrækkefølgen til faldende, skal du vælge ellipsen ( **...** ) i øverste højre hjørne af udsnittet og vælge **Sortér faldende**.

**Sådan opretter du et nyt udsnit for at filtrere data efter datointerval**

1. Uden at have markeret noget på lærredet skal du vælge rullelisten **Butik** i ruden Felter og trække **Åbningsdato** til brønden **Værdier** i ruden Visualiseringer for at oprette en ny visualisering.
2. Med den nye visualisering markeret skal du vælge ikonet **Udsnit** for at konvertere den nye visualisering til et udsnit. Dette udsnit er en skyder med det angivne datointerval.
    
    ![nyt intervaludsnit](media/power-bi-visualization-slicers/power-bi-date-slicer.png)

    
4. Tilpas størrelsen på udsnittet, og træk udsnittet og andre elementet på lærredet for at gøre plads til udsnittet. Vær opmærksom på, at udsnittets størrelse tilpasses, når du tilpasser størrelsen på udsnittet, men hvis udsnittet bliver for lille, skjules udsnittet, og datoerne vil være beskåret. 
4. Vælg et andet datointerval på skyderen, vælg et datofelt for at skrive en værdi, eller brug en pop op-kalender for at gør det nemt at vælge nøjagtige datoer. Bemærk, hvordan det påvirker de øvrige visualiseringer på siden.
    
    >[!NOTE]
    >Numeriske data og data af typen dato/klokkeslæt kan oprettet udsnit med skydere som standard. Fra og med Power BI-opdateringen i februar 2018 vil skyderen med heltalsintervaller nu fastgøre til heltalsværdier og ikke vise decimaler. 


5. Hvis du vil ændre udsnitstypen, skal du markere udsnittet, pege på det øverste højre hjørne af udsnittet for at få vist en rulleliste og vælge en af de andre indstillinger, for eksempel **Liste** eller **Før**. Bemærk, hvordan udsnittets udseende og indstillingerne ændres. 
 
    ![nyt intervaludsnit](media/power-bi-visualization-slicers/power-bi-between-slicer.png)


Hvis du vil vide mere om, hvordan du opretter udsnit med datointervaller eller talintervaller, skal du se følgende video og se [Brug udsnittet til talintervaller i Power BI Desktop](../desktop-slicer-numeric-range.md).
   > [!NOTE]
   > I denne video bruges en ældre version af Power BI Desktop.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe> 

## <a name="control-which-page-visuals-are-affected-by-slicers"></a>Styr, hvilke visualiseringer på siden der påvirkes af udsnit
Som standard påvirker udsnit på rapportsider alle andre visualiseringer på den samme side – også hinanden. Når du vælger værdier på de liste- og datoudsnit,du har oprettet, kan du se ændringerne i de andre visualiseringer. De filtrerede data er skæringspunktet for de værdier, der er valgt i begge udsnit. 

Du kan bruge **Visuelle interaktioner** til at forhindre, at nogle visualiseringer på siden bliver påvirket. På siden **Oversigt** viser diagrammet "Total Sales Variance by FiscalMonth and District Manager" de overordnede sammenlignelige data for District Managers efter måned, som du vil vise hele tiden. Du kan bruge **Visuelle interaktioner** for at forhindre, at valg i udsnit filtrerer dette diagram. 

1. Med udsnittet District Manager på siden **Månedligt salg for distrikt** markeret:
    - I Power BI Desktop skal du vælge menuen **Formater** under **Visuelle værktøjer** og vælge **Rediger interaktioner**.
   
   Kontrolelementerne til filtrering ![kontrolelementer til filtrering](media/power-bi-visualization-slicers/filter-controls.png) vises over alle andre visualiseringer på siden. Alle ikonerne under **Filter** er valgt til at starte med.
   
2. Vælg ikonet **Ingen** over diagrammet **Total Sales Variance by FiscalMonth and District Manager** for at forhindre, at udsnittet filtrerer diagrammet. 
3. Vælg udsnittet **Måned**, og vælg igen ikonet **Ingen** over diagrammet **Total Sales Variance by FiscalMonth and District Manager** for at forhindre, at udsnittet filtrerer diagrammet. Når du vælger navne og datointervaller i udsnittet, vil diagrammet Total Sales Variance by FiscalMonth and District Manager nu forblive uændret. 

Se [Visuelle interaktioner i en Power BI-rapport](../service-reports-visual-interactions.md) for at få flere oplysninger om redigering af interaktioner.

## <a name="sync-and-use-slicers-on-other-pages"></a>Synkroniser og brug udsnit på andre sider
Fra og med opdateringen af Power BI i februar 2018 kan du synkronisere et udsnit og bruge det på en hvilken som helst side i en rapport. 

I den aktuelle rapport på siden **Månedligt salg for distrikt** er der også et udsnit af typen **District Manager**, men hvad nu hvis vi også gerne vil have dette udsnit på siden **Oversigt**? Siden **Nye butikker** har også et udsnit, men det indeholder kun oplysninger om **Butiksnavn**. Ved hjælp af ruden **Synkroniser udsnit** kan vi synkronisere udsnittet **District Manager** til disse sider, så markeringer af udsnit på en hvilken som helst side påvirker visualiseringerne på alle tre sider.

1. I menuen **Vis** skal du vælge **Synkroniser udsnit** i Power BI Desktop.

    ![synkroniser udsnit](media/power-bi-visualization-slicers/power-bi-slicer-view-sync.png)

1.  Ruden **Synkroniser udsnit** vises mellem ruderne **Filtre** og **Visualiseringer**.  

    ![synkroniser udsnit](media/power-bi-visualization-slicers/power-bi-slicer-sync-pane.png)

1. På siden **Månedligt salg for distrikt** skal du vælge udsnittet **District Manager**. 
    
    ![synkroniser udsnit](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
3. I kolonnen **Synkroniser** skal du vælge siden **Nye butikker** og siden **Oversigt** for at synkronisere udsnittet **Månedligt salg for distrikt** til disse sider. 
    
3. I kolonnen **Synlig** skal du vælge siden **Nye butikker** og siden **Oversigt**. Ruden **Synkroniser udsnit** burde nu ligne billedet herunder:

    ![synkroniser udsnit](media/power-bi-visualization-slicers/power-bi-sync-slicer-finished.png)

1. Se, hvordan synkronisering af slideren påvirker de andre sider. På siden **District Monthly Sales** viser udsnittet **District Manager** nu de samme valg som den på siden **Oversigt**. På siden **New Stores** vil valgene i udsnittet **District Manager** påvirke, hvilke valg der er tilgængelige i udsnittet **Store Name**. 
    
    >[!TIP]
    >Selvom udsnittet vises på de synkroniserede sider med samme størrelse og placering som på den oprindelige side, kan du flytte dem, ændre deres størrelse og formatere dem uafhængigt på de enkelte sider. 

>[!NOTE]
>Hvis du synkroniserer et udsnit til en side, men ikke gør det synligt på siden, vil udsnitsvalgene på de andre sider stadig filtrere dataene på siden.
 
## <a name="format-slicers"></a>Formatér udsnit
Der findes forskellige indstillinger til formatering afhængigt af udsnitstypen. Hvis du bruger retningen **Vandret**, layoutet **Dynamisk** og **elementfarver**, kan du oprette knapper eller felter i stedet for almindelige listeelementer og få elementer i udsnit til at tilpasse størrelse, så de passer til forskellige skærmstørrelser og layout.  

1. Med udsnittet **District Manager** markeret på en vilkårlig side skal du i ruden **Visualiseringer** vælge ikonet **Formatér** ![ikonet formatér](media/power-bi-visualization-slicers/power-bi-paintroller.png) for at få vist kontrolelementerne til formatering. 
    
    ![formatering](media/power-bi-visualization-slicers/3-format.png)
    
2. Klik på pilene i rullelisten ud for hver kategori for at få vist og redigere indstillingerne. 

### <a name="general-options"></a>Generelle indstillinger
1. Vælg rød under **Konturfarve**, og ret **Konturtykkelse** til "2". Dermed angives konturens farve og tykkelse eller understregning for overskrifter og elementer, når det aktiveres. 
2. Under **Retning** er **Lodret** valgt som standard. Vælg **Vandret** for at få et udsnit med vandret arrangerede felter eller knapper, og rul med pilene for at få adgang til elementer, der ikke vises på skyderen.
    
    ![vandret](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Slå layoutet **Dynamisk** til for at ændre størrelsen på og placeringen af udsnitselementerne efter visningsskærm og udsnitsstørrelse. For listeudsnit er dynamisk layout kun tilgængeligt i vandret format, og det forhindrer, at elementer afskæres på små skærme. For udsnit med intervalskydere vil dynamisk formatering ændre formatet for skyderen og give mere fleksible muligheder for tilpasning af størrelsen. Begge typer udsnit bliver filterikoner ved meget små størrelser. 
    
    ![dynamisk](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Ændringer af Dynamisk layout kan tilsidesætte særlig formatering af overskrifter og elementer, som du har angivet. 
    
4. Angiv skyderens placering og størrelse med tal under **X-placering**, **Y-placering**, **Bredde** og **Højde**, eller flyt og tilpas størrelsen på udsnittet direkte på lærredet. Afprøv forskellige størrelser på og placering af elementer, og se, hvordan dynamisk formatering ændres derefter.  

    ![vandrette knapper](media/power-bi-visualization-slicers/6-buttons.png)

Se [Opret et dynamisk udsnit, som du kan ændre størrelsen på, i Power BI](../power-bi-slicer-filter-responsive.md) for at få flere oplysninger om horisontal retning og dynamisk layout.

### <a name="selection-controls-options-list-slicers-only"></a>Indstillinger for Kontrolelementer til markering (angiv kun udsnit)
1. **Vis Vælg alle** er som standard slået **Fra**. Slå den **til** for at føje elementet **Vælg alle** til udsnittet, så du vælge eller fravælge alle elementer, når du skifter mellem indstillingerne. Når alle elementer er valgt, fravælger du et element ved at klikke eller trykke på det, hvilket aktiverer filtret af typen "er ikke". 
    
    ![vælg alle](media/power-bi-visualization-slicers/7-select-all.png)
    
2. **Vælg én** er som standard slået **til**. Når du klikker eller trykker på hvert element, vælger du det, og når du holder **Ctrl** nede, mens du klikker eller trykker, vælger du flere elementer. Slå **Vælg én** **fra** for at muliggøre valg af flere elementer uden at skulle holde **Ctrl** nede. Når du klikker eller trykker på hvert element igen, fravælger du det. 

### <a name="title-options"></a>Titelindstillinger
**Titler** er som standard slået **Til**, så navnet på datafeltet vises øverst i udsnittet. 
1. Formatér titelteksten for at gøre **skriftfarven** rød samt angive **tekststørrelsen** til 14 pkt., centreret **Justering** og **Skrifttypeserien** til Arial Black. 


### <a name="item-options-list-slicers-only"></a>Indstillinger for element (kun listeudsnit)
1. Formatér elementernes tekst og baggrund for at angive **skriftfarven** til sort, **baggrunden** til lys rød, **tekststørrelsen** til 10 pkt. og **skrifttypen** til Arial. 
2. Vælg **Ramme** under **Kontur** for at tegne en kant omkring hvert element med den størrelse og farve, som du har angivet under **Generelle indstillinger**. 
    
    ![formateret](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Med **Retning > Vandret** vises den valgte tekst og de valgte baggrundsfarver for fravalgte elementer, mens systemstandarderne bruges for valgte elementer, hvilket normalt er sort baggrund med hvid tekst.
    >- Med **Retning > Lodret** vises de angivne farver altid for elementerne, og afkrydsningsfelterne er altid sorte, når de er markeret. 

### <a name="datenumeric-inputs-and-slider-options-range-slider-slicers-only"></a>Dato/numerisk input og indstillinger for skyder (kun for udsnit med intervalskyder)
- Indstillingerne for dato/numerisk input er de samme som indstillingerne for **Element** for listeudsnit, men der findes ikke **Kontur** og understregning.
- Med indstillingerne for skyderen kan du angive farven på intervalskyderen, eller du kan slå skyderen **fra** og kun bruge numerisk input.

### <a name="other-formatting-options"></a>Andre formateringsindstillinger
De andre formateringsindstillinger er som standard slået fra. Når de er slået **til**: 
- **Baggrund:** Føjer en baggrundsfarve til hele udsnittet og angiver gennemsigtigheden.
- **Lås højde-bredde-forhold:** Bevarer formen af udsnittet, hvis størrelsen tilpasses.
- **Kant:** Tilføjer en kant på 1 pixel rundt om udsnittet og angiver farven på den. (Denne kant er forskellig fra og ikke påvirket af de generelle indstillinger for Kontur). 

## <a name="next-steps"></a>Næste trin
[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Tabeller i Power BI](power-bi-visualization-tables.md)

