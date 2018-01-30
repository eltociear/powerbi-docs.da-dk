---
title: Opret ArcGIS-kort fra ESRI i Power BI (selvstudium)
description: 'Opret et ArcGIS-kort fra ESRI i Power BI '
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: EKVvOZmxg9s
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/04/2018
ms.author: mihart
ms.openlocfilehash: a1f424229a05b7f4b5507100287719f8d4cac005
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2018
---
# <a name="arcgis-maps-in-power-bi-service-and-power-bi-desktop-by-esri"></a>ArcGIS-kort i Power BI-tjenesten og Power BI Desktop fra Esri
Dette selvstudium er skrevet fra den person, der opretter et ArcGIS korts synspunkt. Når en opretter deler et ArcGIS-kort med en kollega, kan den pågældende kollega få vist og interagere med kortet, men ikke gemme ændringer. Du kan få mere at vide om visning af et ArcGIS-kort under [Interaktion med ArcGIS-kort](power-bi-visualizations-arcgis.md).

Kombinationen af ArcGIS-kort og Power BI tager kort til et helt nyt niveau, som involverer mere end præsentation af punkter på et kort. Du kan vælge mellem grundlæggende kort, placeringstyper, temaer, symboltypografier og referencelag til at oprette fantastiske informative kortvisualiseringer. Kombinationen af autoritative datalag på et kort med rumlige analyser giver en bedre forståelse af dataene i visualiseringen.

 Du kan ikke oprette et ArcGIS-kort på en mobilenhed, men du kan få det vist og interagere med det. Se [Interaktion med ArcGIS-kort](power-bi-visualizations-arcgis.md).

> [!TIP]
> GIS står for Geographic Information Science (Geografisk informationsvidenskab).


Nedenstående eksempel bruger et mørkegråt canvas til at vise det regionale salg som et termisk kort i forhold til et demografisk lag for medianen for den disponible indtægt i 2016. Som du kan se, hvis du læser videre, tilbyder ArcGIS-kort næsten ubegrænsede kortmuligheder, demografiske data og endnu mere overbevisende kortvisualiseringer, så du kan fremvise dine data på den bedst mulige måde.

![](media/power-bi-visualization-arcgis/power-bi-intro-arcgis.png)

> [!TIP]
> Besøg [Esris side på Power BI](https://www.esri.com/powerbi) for at se de mange eksempler og læse anbefalinger. Og se derefter Esris [side med introduktion til ArcGIS Maps for Power BI](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm).

## <a name="user-consent"></a>Brugerens samtykke
ArcGIS Maps for Power BI leveres af [Esri](https://www.esri.com). Din brug af ArcGIS Maps for Power BI er omfattet af Esris vilkår og politik for beskyttelse af personlige oplysninger. Power BI-brugere, der gerne vil bruge ArcGIS-kort til visuelle elementer i Power BI, skal acceptere dialogboksen til samtykke.

**Ressourcer**

[Vilkår](https://go.microsoft.com/fwlink/?LinkID=826322)

[Politik for beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?LinkID=826323)

[Produktsiden med ArcGIS Maps for Power BI](https://www.esri.com/powerbi)

<br/>

## <a name="enable-arcgis-map"></a>Aktivér ArcGIS-kort
ArcGIS-kort er i øjeblikket tilgængelige i Power BI-tjenesten, Power BI Desktop og Power BI – Mobil. Artiklen indeholder instruktioner til tjenesten og til Desktop.

### <a name="enable-the-arcgis-map-in-power-bi-service-apppowerbicom"></a>Aktivér ArcGIS-kortet ***i Power BI-tjenesten (app.powerbi.com)***
I dette selvstudium benyttes [eksemplet Retail Analysis](sample-retail-analysis.md). Sådan aktiveres **ArcGIS Maps for Power BI**:

1. Vælg tandhjulsikonet i den øverste højre del af menulinjen, og åbn **Settings** (Indstillinger).
   
    ![](media/power-bi-visualization-arcgis/power-bi-settings.png)
2. Markér afkrydsningsfeltet **ArcGIS Maps for Power BI** (ArcGIS-kort til Power BI). Du skal genstarte Power BI, når du har markeret indstillingen.
   
    ![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)
3. Åbn en rapport i [redigeringstilstand](service-reading-view-and-editing-view.md), og vælg ikonet for ArcGIS Maps for Power BI i ruden Visualiseringer.
   
    ![](media/power-bi-visualization-arcgis/power-bi-viz-pane2.png)
4. Power BI føjer en tom ArcGIS-kortskabelon til rapportcanvasset.
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-placeholder2new.png)

<br/>

## <a name="create-an-arcgis-map-visual"></a>Opret en ArcGIS-kortvisualisering
Se, hvordan Will opretter et par forskellige ArcGIS-kortvisualiseringer, og benyt derefter fremgangsmåden nedenfor til at prøve det selv ved hjælp af [eksemplet Retail Analysis](sample-datasets.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/EKVvOZmxg9s" frameborder="0" allowfullscreen></iframe>

1. Træk et datafelt fra ruden **Fields** (Felter) til filsættet **Location** (Placering) eller **Latitude** (Breddegrad) og/eller **Longitude** (Længdegrad). I dette eksempel bruger vi **Store > City**.
   
   > [!NOTE]
   > ArcGIS Maps for Power BI registrerer automatisk, hvis de felter, som du har valgt, bedst kan ses som en figur eller et punkt på et kort. Du kan tilpasse standarden i indstillingerne (se nedenfor).
   > 
   > 
   
    ![](media/power-bi-visualization-arcgis/power-bi-fields-pane3new.png)
2. Konvertér visualiseringen til et ArcGIS-kort ved at vælge skabelonen i ruden Visualiseringer![](media/power-bi-visualization-arcgis/power-bi-arcgis-template.png).
3. Fra feltet **Fields** (Felter) skal du trække en måling til filsættet **Size** (Størrelse) for at justere, hvordan dataene vises. I dette eksempel bruger vi **Sales > Last Year Sales**.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-point-map-size2new.png)

## <a name="settings-and-formatting-for-arcgis-maps"></a>Indstillinger og formatering for ArcGIS-kort
Sådan får du adgang til formateringsfunktionerne i **ArcGIS Maps for Power BI**:

1. Få adgang til yderligere funktioner ved at vælge ellipsen i øverste højre hjørne af visualiseringen og vælge **Edit** (Rediger).
   
   ![](media/power-bi-visualization-arcgis/power-bi-edit2.png)
   
   De tilgængelige funktioner vises øverst i visualiseringen. Der åbnes en opgaverude for hver funktion, når den er blevet valgt, med mere detaljerede indstillinger.<br/>
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-features-new.png)
   
   > [!NOTE]
   > Du kan finde flere oplysninger om indstillingerne og funktionerne i den **detaljerede dokumentation** nedenfor.
   > 
   > 
2. Du vender tilbage til rapporten ved at vælge **Back to Report** (Tilbage til rapporten) i det øverste venstre hjørne af rapportcanvasset.

<br/>

## <a name="detailed-documentation"></a>Detaljeret dokumentation
**Esri** leverer [omfattende dokumentation](https://go.microsoft.com/fwlink/?LinkID=828772) om funktionssættet i **ArcGIS Maps for Power BI**.

## <a name="features-overview"></a>Oversigt over funktioner
### <a name="base-maps"></a>Grundlæggende kort
Der er fire grundlæggende kort: Dark Gray Canvas, Light Gray Canvas, OpenStreetMap og Streets.  Streets er ArcGIS' grundlæggende standardkort.

Hvis du vil anvende et grundlæggende kort, skal du vælge det i opgaveruden.

![](media/power-bi-visualization-arcgis/power-bi-esri-base-maps-new.png)

### <a name="location-type"></a>Placeringstype
ArgGIS Maps for Power BI finder automatisk den bedste måde at vise data på et kort på. Den vælger fra Points (Punkter) eller Boundaries (Grænser). Indstillingerne for placeringstype giver dig mulighed for at tilpasse disse valg.

![](media/power-bi-visualization-arcgis/power-bi-esri-location-types-new.png)

**Boundaries** (Grænser) fungerer kun, hvis dine data indeholder geografiske standardværdier. Esri finder automatisk ud af, hvilken figur der skal vises på kortet. Geografiske standardværdier omfatter lande, områder, postnumre osv. Men på samme måde som med geokodning registrerer Power BI muligvis ikke, om feltet skal være en grænse som standard, eller også indeholder tjenesten ikke en grænse for dine data.  

### <a name="map-theme"></a>Korttema
Der findes fire korttemaer. Temaerne Location Only (Kun placering) og Size (Størrelse) vælges automatisk på baggrund af de felter, du knyttede til filsættet **Size** (Størrelse) i ruden med Power BI-felter. Vi bruger i øjeblikket **Size** (Størrelse), så lad os ændre det til **Heat map** (Termisk kort).  

![](media/power-bi-visualization-arcgis/power-bi-esri-map-theme-new.png)

<table>
<tr><th>Tema</th><th>Beskrivelse</th>
<tr>
<td>Location Only (Kun placering)</td>
<td>Placerer datapunkter eller udfyldte grænser på kortet på baggrund af indstillingerne i Location Type (Placeringstype).</td>
</tr>
<tr>
<td>Heat Map (Termisk kort)</td>
<td>Viser en afbildning af intensiteten af data på kortet.</td>
</tr>
<tr>
<td>Size (Størrelse)</td>
<td>Placerer datapunkter på kortet, hvis størrelse afhænger af værdien i størrelsesdatasættet i ruden med felter.</td>
</tr>
<tr>
<td>Clustering</td>
<td>Placerer antallet af datapunkter i områder på kortet. </td>
</tr>
</table>


### <a name="symbol-style"></a>Symboltypografi
Symboltypografier giver dig mulighed for at finjustere, hvordan data vises på kortet. Symboltypografier er kontekstafhængige og er baseret på den valgte placeringstype og det valgte korttema. Nedenstående eksempel viser placeringstypen, der er angivet til **Size** (Størrelse), og flere justeringer af gennemsigtighed, typografi og størrelse.

![](media/power-bi-visualization-arcgis/power-bi-esri-symbol-style-new.png)

### <a name="pins"></a>Nåle
Fremhæv datapunkter på kortet ved at tilføje nåle.  

1. Vælg fanen **Pins** (Nåle).
2. Skriv nøgleord (f.eks adresser, steder og interessepunkter) i søgefeltet, og vælg på rullelisten. Der vises et symbol på kortet, og kortet zoomer automatisk ind på placeringen. Søgeresultater gemmes som placeringskort i ruden Pins (Knappenåle). Du kan gemme op til 10 placeringskort.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-arcgis-newer.png)
3. Power BI føjer en knappenål til den pågældende placering, og du kan ændre farven på knappenålen.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-color-new.png)
4. Tilføj og slet knappenåle.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin3.png)

### <a name="drive-time"></a>Drive time (Køretid)
I ruden Drive time (Køretid) kan du vælge en placering og derefter angive, hvilken anden kortfunktion der er inden for en bestemt radius eller køretid.  
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

1. Vælg fanen **Drive time** (Køretid), og vælg værktøjet til valg af et eller flere elementer. Vælg knappenålen for Washington D.C.
    ![](media/power-bi-visualization-arcgis/power-bi-esri-single-select.png)
   
   > [!TIP]
   > Det er lettere at vælge en placering, hvis du zoomer ind på kortet (ved hjælp af +-ikonet).
   > 
   > 
2. Lad os sige, at du skal til Washington D.C. i et par dage og gerne vil finde ud af, hvilke butikker der ligger inden for en rimelig køreafstand. Angiv søgeområdet til **Radius** og Distance (Afstand) til **50** mil, og vælg OK.    
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time-radius.png)
3. Radiussen vises i lilla. Vælg et vilkårligt sted for at få vist detaljer om det. Du kan eventuelt formatere radiussen ved at ændre farve og rammekontur.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

### <a name="reference-layer"></a>Referencelag
#### <a name="reference-layer---demographics"></a>Referencelag – demografi
ArcGIS Maps for Power BI indeholder en række demografiske lag, der hjælper med at kontekstualisere data fra Power BI.

1. Vælg fanen **Reference layer** (Referencelag), og vælg **Demographics** (Demografi).
2. Der er et afkrydsningsfelt ud for hvert lag, der er angivet. Markér afkrydsningsfeltet for at føje laget til kortet.  Vi har tilføjet den gennemsnitlige husstandsindkomst i dette eksempel.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-demographic.png)
3. Hvert lag er også interaktivt. På samme måde som du kan pege på en boble for at få vist detaljer, kan du klikke på et skraveret område på kortet for at få vist detaljer.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-details.png)

#### <a name="reference-layer---arcgis"></a>Referencelag – ArcGIS
ArcGIS Online giver virksomheder mulighed for at publicere offentlige webkort. Desuden leverer Esri et sæt overvågede webkort via Living Atlas. Under fanen ArcGIS kan du søge efter alle offentlige webkort eller Living Atlas-kort og føje dem til kortet som referencelag.

1. Vælg fanen **Reference layer** (Referencelag), og vælg **ArcGIS**.
2. Skriv søgeord, og vælg derefter et kortlag. I dette eksempel har vi valgt USA Congressional districts.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-demographics-esri2-new.png)
3. Hvis du vil have vist detaljerede oplysninger, skal du markere et skraveret område for at åbne *Select from reference layer* (Vælg fra referencelag): Brug markeringsværktøjet for referencelag til at vælge grænser eller objekter på referencelaget.

<br/>

## <a name="selecting-data-points"></a>Valg af datapunkter
ArcGIS Maps for Power BI har tre markeringstilstande.

Rediger markeringstilstanden ved at vælge:

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-single2.png) Vælg individuelle datapunkter.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-marquee2.png) Tegner et rektangel på kortet og markerer de indeholdte datapunkter.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-layer2.png) Muliggør, at grænser eller polygoner i referencelag kan bruges til at vælge indeholdte datapunkter.

> [!NOTE]
> Du kan maks. vælge 250 datapunkter ad gangen.
> 
> 

<br/>

## <a name="getting-help"></a>Få hjælp
**Esri** leverer [omfattende dokumentation](https://go.microsoft.com/fwlink/?LinkID=828772) om funktionssættet i **ArcGIS Maps for Power BI**.

Du kan stille spørgsmål, finde de seneste oplysninger, rapportere problemer og finde svar i Power BI [community'ets tråd om **ArcGIS Maps for Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771).

Hvis du har et forslag til en forbedring, kan du sende den til [Power BI's ideliste](https://ideas.powerbi.com).

<br/>

## <a name="managing-use-of-arcgis-maps-for-power-bi-within-your-organization"></a>Administration af brugen af ArcGIS Maps for Power BI i din organisation
Power BI giver brugere, lejeradministratorer og IT-administratorer mulighed for at administrere, om ArcGIS Maps for Power BI skal bruges eller ej.

**Brugerindstillingerne** i Power BI Desktop – brugerne kan stoppe med at benytte ArcGIS Maps for Power BI ved at deaktivere funktionen under sikkerhedsfanen i **Options** (Indstillinger). Når ArcGIS Maps er deaktiveret, indlæses den ikke som standard.

![](media/power-bi-visualization-arcgis/power-bi-desktop-security-dialog2.png)

I Power BI-tjenesten kan brugerne stoppe med at bruge ArcGIS Maps for Power BI ved at deaktivere funktionen på fanen ArcGIS Maps for Power BI i User Settings (Brugerindstillinger). Når ArcGIS Maps er deaktiveret, indlæses den ikke som standard.

![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)

**Indstillinger for lejeradministratorer** I PowerBI.com kan lejeradministratorer forhindre, at alle lejerbruger benytter ArcGIS Maps for Power BI ved at deaktivere funktionen. Når det sker, vises ArcGIS Maps for Power BI-ikonet ikke længere i ruden med visualiseringer i Power BI.

![](media/power-bi-visualization-arcgis/power-bi-arcgis-admin-portal2.png)

**Indstillinger for IT-administratorer** Power BI Desktop understøtter ved hjælp af **Gruppepolitik** deaktivering af ArcGIS Maps for Power BI på tværs af de computere, der er installeret i en organisation.

<table>
<tr><th>Attribut</th><th>Værdi</th>
</tr>
<tr>
<td>key</td>
<td>Software\Policies\Microsoft\Power BI Desktop\</td>
</tr>
<tr>
<td>valueName</td>
<td>EnableArcGISMaps</td>
</tr>
</table>

En værdi på 1 (decimal) aktiverer ArcGIS Maps for Power BI.

En værdi på 0 (decimal) deaktiverer ArcGIS Maps for Power BI.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
ArcGIS-kort til Power BI er tilgængeligt i følgende tjenester og programmer:

<table>
<tr><th>Tjeneste/app</th><th>Tilgængelighed</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>Ja</td>
</tr>
<tr>
<td>Power BI-tjeneste (PowerBI.com)</td>
<td>Ja</td>
</tr>
<tr>
<td>Power BI-mobilapps</td>
<td>Ja</td>
</tr>
<tr>
<td>Power BI publiceret til internettet</td>
<td>Nej</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>Nej</td>
</tr>
<tr>
<td>Integration af Power BI-tjenesten (PowerBI.com)</td>
<td>Nej</td>
</tr>
</table>

I tjenester eller programmer, hvor ArcGIS Maps for Power BI ikke er tilgængelig, vises visualiseringen som en tom visualisering med Power BI-logoet.

Når adresser geokodes, er det kun de første 1500 adresse, der geokodes. Geokodning af stednavne eller lande er ikke underlagt grænsen på 1500 adresser.

<br/>

**Er der omkostninger forbundet med brugen af ArcGIS Maps for Power BI?**

ArcGIS Maps for Power BI er tilgængelig for alle Power BI-brugere uden meromkostninger. Det er en komponent, der leveres af **Esri**, og din brug er underlagt **Esris** vilkår og beskyttelse af personlige oplysninger, som nævnt tidligere i denne artikel.

**Jeg får vist en fejlmeddelelse i Power BI Desktop om, at min cache er fuld**

Dette er en fejl, der er ved at blive behandlet.  I mellemtiden kan du prøve at rydde cachen ved at slette filer på denne placering: C:\Users\\AppData\Local\Microsoft\Power BI Desktop\CEF og derefter genstarte Power BI.

**Understøtter ArcGIS Maps for Power BI Esri Shapefiles?**

ArcGIS Maps for Power BI registrerer automatisk standardgrænser som lande/områder, stater/provinser og postnumre. Hvis du vil angive dine egne figurer, kan du gøre det ved hjælp [figurkort til Power BI Desktop (prøveversion)](desktop-shape-map.md).

**Kan jeg få vist mine ArcGIS-kort offline?**

Nej, Power BI skal bruge en netværksforbindelse for at vise kortene.

**Kan jeg oprette forbindelse til min ArcGIS Online-konto fra Power BI?**

Ikke endnu. [Stem på denne ide](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/9154765-arcgis-geodatabases), og vi sender dig en mail, når vi begynder at arbejde på denne funktion.  

## <a name="next-steps"></a>Næste trin
[Interaktion med ArcGIS-kort, som er blevet delt med dig](power-bi-visualizations-arcgis.md)

[Blogindlæg annoncerer tilgængeligheden af ArcGIS Maps for Power BI](https://powerbi.microsoft.com/blog/announcing-arcgis-maps-for-power-bi-by-esri-preview/)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
