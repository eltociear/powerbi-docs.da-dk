---
title: Udsnit i Power BI (selvstudium)
description: 'Selvstudium: Udsnit i Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Udsnit i Power BI (selvstudium)
En vicedirektør i salg vil gerne kunne se flere målepunkter for hele divisionen og for hver enkelt distriktschef. Vedkommende kunne oprette en separat rapport for hver chef eller bruge et udsnit. Et udsnit begrænser den del af datasættet, der vises i andre visualiseringer i en rapport. Udsnit er en alternativ måde at filtrere på.

I dette selvstudium bruges det gratis [Eksempel på detailhandelsanalyse](sample-retail-analysis.md) i gennemgangen af, hvordan du opretter og formaterer et udsnit, og hvordan du bruger det til at filtrere en rapport. Mor dig med at opdage måder, du kan formatere og bruge udsnit på. 

![Udsnit](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Hvornår bruger man et udsnit
Udsnit er et fantastisk valg, når du vil:

* vise ofte brugte eller vigtige filtre på rapportcanvasset af hensyn til lettere adgang
* gøre det nemmere at se den aktuelle filtrerede tilstand uden at skulle åbne en rulleliste 
* filtrere efter kolonner, der ikke er behov for, og som er skjult i datatabeller
* oprette mere fokuserede rapporter ved at placere udsnit ved siden af vigtige visualiseringer.

Der er følgende begrænsninger for udsnit i Power BI:

- Udsnit understøtter ikke inputfelter.
- Udsnit kan ikke fastgøres til et dashboard.
- Detaljeret visning understøttes ikke for udsnit.
- Udsnit understøtter ikke filtre på visualiseringsniveau.

## <a name="create-a-slicer"></a>Opret et udsnit

I dette selvstudium bruges et listeudsnit. Numeriske data og data af typen dato/klokkeslæt kan have intervaludsnit. Se [Brug det numeriske intervaludsnit i Power BI Desktop](desktop-slicer-numeric-range.md) eller følgende video for at få flere oplysninger om, hvordan du opretter og bruger intervaludsnit.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. Åbn [detailhandelsanalysen](sample-retail-analysis.md) i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md) i Power BI Desktop eller Power BI tjenesten, og [tilføj en ny rapportside](power-bi-report-add-page.md).
2. Vælg **Distriktschef** i ruden Felter under Distrikt for at oprette en ny visualisering.
    
    ![nyt diagram](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. Vælg ikonet **Udsnit** ![ikonet Udsnit](media/power-bi-visualization-slicers/slicer-icon.png) i ruden Visualiseringer for at konvertere den nye visualisering til et udsnit. 
    
    ![konvertér til udsnit](media/power-bi-visualization-slicers/2-slicer.png)

Du kan også vælge ikonet Udsnit for at oprette et nyt udsnit og derefter vælge eller trække et datafelt ind i boksen Felt for at udfylde det.

>[!TIP]
>Du kan sortere elementer i listeudsnit efter dataværdier. Hvis du vil sortere elementerne i udsnittet i omvendt alfabetisk rækkefølge, skal du vælge ellipserne (...) i øverste højre hjørne af udsnittet og derefter vælge **Sortér efter distriktschef**. Indstillingen er som standard sat til alfabetisk rækkefølge, men du kan ændre mellem alfabetisk og omvendt alfabetisk rækkefølge. 

## <a name="format-the-slicer"></a>Formatér udsnittet
Anvend visuel formatering på udsnittet Distriktschef.
1. Markér udsnittet, og vælg ikonet Formatér ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) i ruden Visualiseringer for at få vist kontrolelementerne til formatering. 
    
    ![formatering](media/power-bi-visualization-slicers/3-format.png)
    
2. Klik på pilene i rullelisten ud for hver kategori for at få vist og redigere indstillingerne. 

### <a name="general-options"></a>Generelle indstillinger
1. Vælg rød under **Konturfarve**, og ret **Konturtykkelse** til "2". Dermed angives konturens farve og tykkelse eller understregning for overskrifter og elementer, når det aktiveres. 
2. Under Retning er Vertikal valgt som standard, hvilket medfører et vertikalt listeudsnit med afkrydsningsfelter foran elementerne. Vælg **Horisontal** for at oprette et udsnit med elementer, der er arrangeret horisontalt. Den horisontale retning kan medføre forskelligt layout af tekst, knapper eller felter, afhængigt af størrelsen og formen på udsnittet samt formateringen af elementer. 
    
    ![horisontal](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Slå **Dynamisk** layout til, hvilket ændrer størrelsen og layoutet af horisontale elementer i udsnittet, så de passer til størrelsen og formen på udsnittet. Hvis udsnittet er meget lille, bliver det et filterikon. 
    
    ![dynamisk](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Ændringer af Dynamisk layout kan tilsidesætte særlig formatering af overskrifter og elementer, som du har angivet. 
    
4. Angiv placeringen og størrelsen på udsnittet med numerisk præcision under **X-placering**, **Y-placering**, **Bredde** og **Højde**, eller flyt og tilpas størrelsen på udsnittet direkte på canvasset for at få forskellige størrelser på elementerne og forskelligt layout, f.eks. horisontale rækker af knapper. 

    ![horisontale knapper](media/power-bi-visualization-slicers/6-buttons.png)

Se [Opret et dynamisk udsnit, som du kan ændre størrelsen på, i Power BI](power-bi-slicer-filter-responsive.md) for at få flere oplysninger om horisontal retning og dynamisk formatering.

### <a name="selection-controls-options"></a>Indstillinger for Kontrolelementer til markering
1. Vis "Vælg alle" er som standard slået fra. Slå den **til** for at føje elementet Vælg alle til udsnittet, så du vælge eller fravælge alle elementer, når du skifter mellem indstillingerne. Når alle elementer er valgt, fravælger du et element ved at klikke på det, hvilket aktiverer filtret af typen "er ikke". 
    
    ![vælg alle](media/power-bi-visualization-slicers/7-select-all.png)
    
2. Vælg én er som standard slået til. Når du klikker på hvert element, vælger du det, og når du holder Ctrl-tasten nede, mens du klikker, vælger du flere elementer. Slå Vælg én **fra** for at muliggøre valg af flere elementer uden at skulle holde Ctrl-tasten nede. Når du klikker på hvert element igen, fravælger du det. 

### <a name="header-options"></a>Indstillinger for overskrifter
Overskrifter er som standard slået til, så datafeltnavnet vises øverst i udsnittet. 
1. Formatér teksten i overskriften for at angive **skriftfarven** til rød, **tekststørrelsen** til 14 pkt. og **skrifttypen** til Arial Black. 
2. Vælg **Kun knap** under Kontur for at oprette en understregning med den størrelse og farve, som du har angivet under Generelle indstillinger. 

### <a name="item-options"></a>Indstillinger for elementer
1. Formatér elementernes tekst og baggrund for at angive **skriftfarven** til sort, **baggrunden** til lys rød, **tekststørrelsen** til 10 pkt. og **skrifttypen** til Arial. 
2. Vælg **Ramme** under Kontur for at tegne en kant omkring hvert element med den størrelse og farve, som du har angivet under Generelle indstillinger. 
    
    ![formateret](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Med Vandret retning vises den valgte tekst og de valgte baggrundsfarver for fravalgte elementer, mens systemstandarderne bruges for valgte elementer, hvilket normalt er sort baggrund med hvid tekst. 
    >- Med Lodret retning vises de angivne farver altid for elementerne, og afkrydsningsfelterne er altid sorte, når de er markeret. 

### <a name="other-formatting-options"></a>Andre formateringsindstillinger
De andre formateringsindstillinger er som standard slået fra. Når de er slået **til**: 
- **Titel:** Tilføjer og formaterer en titel (udover og uafhængigt af overskriften) øverst i udsnittet. 
- **Baggrund:** Tilføjer en baggrundsfarve på hele udsnittet og angiver gennemsigtigheden.
- **Lås højde-bredde-forhold:** Bevarer formen af udsnittet, hvis størrelsen tilpasses.
- **Kant:** Tilføjer en kant på 1 pixel rundt om udsnittet og angiver farven på den. (Denne kant er forskellig fra og ikke påvirket af de generelle indstillinger for Kontur). 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>Synkroniser og brug udsnittet på andre sider
Fra og med opdateringen af Power BI i februar 2018 kan du synkronisere et udsnit og bruge det på en hvilken som helst side i en rapport. 
1. Når du har valgt udsnittet Distriktschef i menuen Vis, skal du vælge **Synkroniser udsnit** i Power BI Desktop eller slå **ruden Synkroniser udsnit** til i Power BI tjenesten. Ruden Synkroniser udsnit vises. 
    
    ![synkroniser udsnit](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. I den første kolonne skal du vælge **Oversigt** og alle andre sider, som du vil synkronisere udsnittet med. Du kan også klikke på **Føj til alle** for at synkronisere udsnittet med alle rapportsider.  
3. I den næste kolonne skal du vælge **Oversigt** og alle andre sider, som du vil have vist udsnittet på. 
4. Skift til siden **Oversigt**, og bemærk udsnittet og dets effekt på de andre visualiseringer på siderne. 
    - Foretag og fjern forskellige valg for elementer, og bemærk, hvordan de andre visualiseringer på siden ændres tilsvarende. Valg for elementer på en hvilken som helst side afspejles på alle synkroniserede sider.
    - Ret udsnittets størrelse, form, placering og/eller formatering på siden Oversigt. Formateringen af udsnittet på andre synkroniserede sider ændres ikke. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>Styr, hvilke visualiseringer på siden der påvirkes af udsnittet
Et udsnit på en rapportside påvirker som standard alle andre visualiseringer på den pågældende side. Brug **Visuelle interaktioner** til at forhindre, at nogle visualiseringer på siden bliver påvirket.

1. Gør følgende på siden **Oversigt** med udsnittet markeret:
    - Klik på menuen Formatér under Visuelle værktøjer i Power BI Desktop, og vælg **Rediger interaktioner**.
    - Fold rullelisten **Visuelle interaktioner** ud på menulinjen, og slå **Rediger interaktioner** til. 
    
    Kontrolelementer til filtrering vises over alle de andre visualiseringer på siden. ![kontrolelementer til filtrering](media/power-bi-visualization-slicers/filter-controls.png)
    
2. Vælg ikonet **Ingen** over en visualisering, så filtreres det ikke sammen med udsnittet. Vælg ikonet **Filtrer** for at filtrere visualiseringen sammen med udsnittet igen. 

Se [Visuelle interaktioner i en Power BI rapport](service-reports-visual-interactions.md) for at få flere oplysninger om redigering af interaktioner.

## <a name="next-steps"></a>Næste trin
[Prøv det – det er gratis!](https://powerbi.com/)

Har du ideer til at forbedre Power BI? [Send en ide](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

[Føj en visualisering til en rapport](power-bi-report-add-visualizations-i.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

