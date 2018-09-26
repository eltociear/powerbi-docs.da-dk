---
title: Rapporteditoren... Få en introduktion
description: Rapporteditoren... Få en introduktion.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 9ce4d09e20fe02ff0552045e307f9d63aa834bd3
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187576"
---
# <a name="the-report-editortake-a-tour"></a>Rapporteditoren... Få en introduktion
## <a name="editing-reports-in-power-bi-service-and-power-bi-desktop"></a>Redigering af rapporter i Power BI-tjenesten og Power BI Desktop
Rapporteditoren i Power BI-tjenesten og rapporteditoren i Power BI Desktop ligner hinanden meget. Videoen viser rapporteditoren i Power BI Desktop, og denne artikel viser rapporteditoren i Power BI-tjenesten. 

## <a name="the-difference-between-report-creators-and-report-consumers"></a>Forskellen mellem *oprettere* og *forbrugere* af rapporter
Muligheden for at oprette og redigere en rapport er begrænset til rapportejere (dvs. *oprettere*). Hvis du *forbruger* en rapport, der er blevet delt med dig, vil du stadig kunne åbne og interagere med rapporten i Power BI-tjenesten vha. [Kun læsevisning](consumer/end-user-reading-view.md), men alle de robuste og omfattende funktioner er ikke tilgængelige for rapportopretteren.  

Hvis du vil vide mere om læsevisning i forbindelse med rapporter, skal du se under [Læsevisning og redigeringsvisning i Power BI-tjenesten](consumer/end-user-reading-view.md) 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

I Power BI-tjenesten er *rapporteditoren* kun tilgængelig i [Redigeringsvisning](consumer/end-user-reading-view.md). Du skal være rapportejer eller rapportopretter for at åbne en rapport i Redigeringsvisning.

Power BI-rapporteditoren består af 3 afsnit:  

1. Ruderne **Felter**, **Visualiseringer** og **Filtre**
2. øverste navigationslinjer    
3. rapportcanvas     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Rapporteditorens ruder
![Power BI-rapporteditor](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Du kan se 3 ruder, når du åbner en rapport første gang: Visualiseringer, Filtre og Felter. Ruderne til venstre, Visualiseringer og Filtre, styrer, hvordan dine visualiseringer ser ud – type, farver, filtrering, formatering.  Og ruden til højre, Felter, administrerer de underliggende data, der bruges i visualiseringerne. 

Det indhold, der vises i rapporteditoren, varierer i forhold til valg, du foretager på rapportcanvasset.  Når du for eksempel vælger et individuelt visuelt element. 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>Øverst i ruden Visualisering identificeres den type visuelle element, der bruges. I dette eksempel et grupperet søjlediagram.<br><br></li> <li>Nederst i ruden Visualisering (du skal muligvis rulle ned) vises de felter, der bruges i det visuelle element. Dette diagram bruger FiscalMonth, DistrictManager og Total Sales Variance. <br><br></li><li>Ruden Filtre (du skal muligvis rulle ned) viser alle de filtre, der er anvendt. <br><br></li><li>Ruden Felter indeholder de tilgængelige tabeller, og hvis du udvider en tabels navn, de felter, der udgør tabellen. Med gul skrifttype ved du, at mindst ét felt fra denne tabel bruges i visualiseringen.<br><br></li><li>![malerrulleikon](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png) Vælg malerrulleikonet for at vise formateringsruden for den valgte visualisering.<br><br></li><li>![forstørrelsesglasikon](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png) Vælg forstørrelsesglasikonet for at få vist ruden Analystics.</ul> |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>Ruden visualiseringer (oppefra og ned)
![toppen af ruden Visualiseringer](media/service-the-report-editor-take-a-tour/selectviz.png)

Her er stedet, hvor du vælger en visualiseringstype. De små billeder kaldes *skabeloner*. I billedet herover er det grupperede søjlediagram valgt. Hvis du ikke vælger en visualiseringstype først, men i stedet begynder at opbygge en visualisering ved at vælge felter, vælger Power BI visualiseringstypen for dig. Du kan bevare Power BI's valg eller ændre typen ved at vælge en anden skabelon. Skift så mange gange, det er nødvendigt for at finde den visualiseringstype, der bedst repræsenterer dine data.

### <a name="manage-the-fields-used-in-your-visual"></a>Administrer de felter, der bruges i det visuelle element.
![midten af ruden Visualiseringer](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

De buckets (også kaldet *wells*), der er vist i denne rude, varierer afhængigt af, hvilken type visualisering du har valgt.  Hvis du for eksempel har valgt et søjlediagram, kan du se buckets for: Værdi, Akse og Forklaring. Når du vælger et felt eller trækker det over på canvasset, føjer Power BI dette felt til en af disse buckets.  Du kan også trække felter fra listen Felter direkte til buckets.  Nogle buckets er begrænset til visse datatyper.  For eksempel accepterer **Værdier** ikke felter, der ikke er numeriske. Så hvis du trækker et felt for **medarbejdernavn** til bucket'en **Værdier**, ændrer Power BI det til **antal medarbejdernavn**.

### <a name="remove-a-field"></a>Fjern et felt
Vælg **X** til højre for feltnavnet for at fjerne et felt fra visualiseringen.

![Fjern Lagertype fra Forklaring](media/service-the-report-editor-take-a-tour/deletefield.png)

Du kan finde flere oplysninger i [Føj visualiseringer til en Power BI-rapport](visuals/power-bi-report-add-visualizations-i.md)

### <a name="format-your-visuals"></a>Formatér dine visuelle elementer
Vælg ikonet med malerullen for at åbne ruden Formatér. Den tilgængelige indstilling afhænger af den valgte type visualisering.

![Ruden Formatering](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Formateringsmulighederne er næsten uendelige.  Udforsk selv for at få mere for at vide, eller gå til disse artikler:

* [Tilpas visualiseringstitel, -baggrund og -forklaring](visuals/power-bi-visualization-customize-title-background-and-legend.md)
* [Farveformatering](visuals/service-getting-started-with-color-formatting-and-axis-properties.md)
* [Tilpas egenskaber for x- og y-akse](visuals/power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Føj analyser til din visualiseringer
Vælg forstørrelsesglasikonet for at få vist ruden Analystics. Den tilgængelige indstilling afhænger af den valgte type visualisering.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Med ruden Analytics i Power BI-tjenesten kan du føje dynamiske referencelinjer til visuelle elementer og give fokus på vigtige tendenser eller indsigt. Du kan finde flere oplysninger i [Ruden Analytics i Power BI-tjenesten](service-analytics-pane.md) eller [Ruden Analytics i Power BI Desktop](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>Ruden Filtre
Brug ruden Filtre til at få vist, angive og redigere faste filtre til dine rapporter på side-, rapport-, detaljeadgangs- og visualiseringsniveau. Ja, du kan udføre ad hoc-filtrering på rapportsider og visualiseringer ved at vælge elementer i visualiseringerne eller ved at anvende værktøjer, f.eks. udsnitsværktøjer, men når du bruger ruden Filtre, gemmes filtertilstanden i rapporten. 

Ruden Filtre indeholder en af fire effektive funktioner – muligheden for at filtrere ved hjælp af et felt, ***der er ikke allerede bruges i en af visualiseringerne i rapporten***. Lad mig forklare. Når du opretter en rapportside, føjer Power BI automatisk alle de felter, du bruger i dine visualiseringer, til filterområdet i ruden Filtre på visualiseringsniveau.  Men hvis du vil angive en visualisering, en side, en detaljeadgang eller et rapportfilter vha. et felt, der ikke bruges i en visualisering i øjeblikket, skal du bare trække det til en filterbucket.   

![Ruden Filtre](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Du kan finde flere oplysninger under [Føj et filter til en rapport](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>Ruden Felter
Ruden Felter indeholder de tabeller og felter, der findes i dine data og er tilgængelige for dig, så du kan bruge dem til at oprette visualiseringer.

|  |  |
| --- | --- |
| ![ruden Felter](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Træk et felt til siden for at starte en ny visualisering.  Du kan også trække et felt til en eksisterende visualisering for at føje feltet til den pågældende visualisering.<br><br></li> <li>Når du markerer afkrydsningsfeltet ud for et felt, føjer Power BI dette felt til den aktive (eller nye) visualisering. Og den beslutter også, hvilken bucket dette felt skal placeres i.  Skal feltet for eksempel bruges som en forklaring, akse eller værdi? Power BI gætter på bedste vis, og du kan om nødvendigt flytte det fra denne bucket til en anden. <br><br></li><li>Uanset hvad, føjes hvert enkelt felt til ruden Visualiseringer i rapporteditoren.</li></ul> |

**BEMÆRK**! Hvis du bruger Power BI Desktop, har du også muligheder for at vise/skjule felter, tilføje beregninger osv.

### <a name="what-do-the-field-icons-mean"></a>Hvad betyder feltikonerne?
* **∑-aggregeringer** En aggregering er en numerisk værdi, der for eksempel skal lægges sammen eller gennemsnitsberegnes. Aggregeringer importeres med dataene (der er defineret i den datamodel, som din rapport er baseret på).
  Du kan finde flere oplysninger i [Aggregeringer i Power BI-rapporter](service-aggregates.md).
* ![lommeregnerikon](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png) **Beregnede målinger (også kaldet beregnede felter)**  
   Hvert beregnet felt har sin egen hard-coded formel. Du kan ikke ændre beregningen – hvis det f.eks. er en sum, kan det kun være en sum. Yderligere oplysninger finder du ved at læse [Om målinger](desktop-measures.md)
* ![Entydigt felt-ikon](media/service-the-report-editor-take-a-tour/icon.png) **Entydige felter**  
   Felter med dette ikon blev importeret fra Excel og er indstillet til at vise alle værdier, selvom de har dublerede værdier. Dine data kan for eksempel have to poster for personer med navnet 'John Smith', og hver enkelt behandles som entydig – de lægges ikke sammen.  
* **![Geografiikon](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png) Geografifelter**  
   Placeringsfelter kan bruges til at oprette kortvisualiseringer. 
* **![Hierarkiikon](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Hierarki**  
   Vælg pilen for at få vist de felter, der udgør hierarkiet. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Den øverste navigationslinje
De handlinger, der er tilgængelige fra øverste navigationslinje, er mange, og der tilføjes hele tiden nye handlinger. Brug indholdsfortegnelsen eller søgefeltet i dokumentationen til Power BI for at få oplysninger om en bestemt handling.

## <a name="3-the-report-canvas"></a>3. Rapportcanvasset
Rapportcanvasset er det sted, dit arbejde vises. Når du bruger ruderne Felter, Filtre og Visualiseringer til at oprette visuelle elementer, bygges og vises de på dit rapportcanvas. Hver fane nederst på canvasset repræsenterer en side i rapporten. Vælg en fane for at åbne siden. 

## <a name="next-steps"></a>Næste trin:
[Opret en rapport](service-report-create-new.md)

Læs mere om rapporter i [Power BI-tjenesten](consumer/end-user-reports.md), [Power BI Desktop](desktop-report-view.md) og [Power BI – Mobil](consumer/mobile/mobile-apps-view-phone-report.md).

[Power BI – Grundlæggende begreber](consumer/end-user-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

