---
title: Opret ArcGIS-kort fra ESRI i Power BI
description: 'Opret et ArcGIS-kort fra ESRI i Power BI '
author: mihart
manager: kvivek
ms.reviewer: lukaszp
featuredvideoid: EKVvOZmxg9s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 87a8333c89f2682640649e757984c6b02e10c3a8
ms.sourcegitcommit: 0687908938e4c3b68401fd511ec1c28fb54ddeb3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2019
ms.locfileid: "71691275"
---
# <a name="arcgis-maps-in-power-bi-desktop-by-esri"></a>ArcGIS-kort i Power BI Desktop fra Esri

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Dette selvstudium er skrevet fra den person, der opretter et ArcGIS korts synspunkt. Når en opretter deler et ArcGIS-kort med en kollega, kan den pågældende kollega få vist og interagere med kortet, men ikke gemme ændringer. Du kan få mere at vide om visning af et ArcGIS-kort under [Interaktion med ArcGIS-kort](power-bi-visualizations-arcgis.md).

Kombinationen af ArcGIS-kort og Power BI tager kort til et helt nyt niveau, som involverer mere end præsentation af punkter på et kort. Du kan vælge mellem grundlæggende kort, placeringstyper, temaer, symboltypografier og referencelag til at oprette fantastiske informative kortvisualiseringer. Kombinationen af autoritative datalag på et kort med rumlige analyser giver en bedre forståelse af dataene i visualiseringen.

 Du kan ikke oprette et ArcGIS-kort på en mobilenhed, men du kan få det vist og interagere med det. Se [Interaktion med ArcGIS-kort](power-bi-visualizations-arcgis.md).

> [!TIP]
> GIS står for Geographic Information Systems.


Nedenstående eksempel bruger et mørkegråt canvas til at vise det regionale salg som et termisk kort i forhold til et demografisk lag for medianen for den disponible indtægt i 2016. Som du kan se, hvis du læser videre, tilbyder ArcGIS-kort næsten ubegrænsede kortmuligheder, demografiske data og endnu mere overbevisende kortvisualiseringer, så du kan fremvise dine data på den bedst mulige måde.

![indledende billede af arcgis](media/power-bi-visualization-arcgis/power-bi-intro-arcgis.png)

> [!TIP]
> Besøg [Esris side på Power BI](https://www.esri.com/powerbi) for at se de mange eksempler og læse anbefalinger. Og se derefter Esris [side med introduktion til ArcGIS Maps for Power BI](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm).

## <a name="user-consent"></a>Brugerens samtykke
ArcGIS Maps til Power BI leveres af Esri (www.esri.com). Din brug af ArcGIS Maps for Power BI er omfattet af Esris vilkår og politik for beskyttelse af personlige oplysninger. Power BI-brugere, der gerne vil bruge ArcGIS-kort til visuelle elementer i Power BI, skal acceptere dialogboksen til samtykke.

**Ressourcer**

[Vilkår](https://go.microsoft.com/fwlink/?LinkID=826322)

[Politik for beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?LinkID=826323)

[Produktsiden med ArcGIS Maps for Power BI](https://www.esri.com/powerbi)

<br/>


### <a name="enable-the-arcgis-map-in-power-bi-desktop-apppowerbicom"></a>Aktivér ArcGIS-kortet ***i Power BI Desktop (app.powerbi.com)***
I dette selvstudium bruges [PBIX-filen med eksemplet Detailhandelsanalyse](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix
). Sådan aktiveres **ArcGIS Maps for Power BI**:

1. Vælg **Fil** \> **Åbn** i øverste venstre afsnit af menulinjen
   
2. Find **PBIX-filen med eksemplet Detailhandelsanalyse**, som er gemt på din lokale maskine.

1. Åbn **Retail Analysis Sample** i rapportvisningen ![Skærmbillede af ikonet for rapportvisning.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Markér ![Skærmbillede af den gule fane.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) for at tilføje en ny side.

   
3. Vælg ikonet for ArcGIS Maps for Power BI i ruden Visualiseringer.
   
    ![ruden visualiseringer til arcGIS-kort](media/power-bi-visualization-arcgis/power-bi-viz-pane.png)
4. Power BI føjer en tom ArcGIS-kortskabelon til rapportcanvasset.
   
   ![pladsholder for arcgis-visualisering](media/power-bi-visualization-arcgis/power-bi-esri-placeholder2new.png)

<br/>

## <a name="create-an-arcgis-map-visual"></a>Opret en ArcGIS-kortvisualisering
Se, hvordan Will opretter forskellige ArcGIS-kortvisualiseringer, og følg derefter trinnene nedenfor for at prøve det selv ved hjælp af [PBIX-filen med eksemplet Detailhandelsanalyse](../sample-datasets.md).
   > [!NOTE]
   > I denne video bruges en ældre version af Power BI Desktop.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/EKVvOZmxg9s" frameborder="0" allowfullscreen></iframe>

1. Træk et datafelt fra ruden **Fields** (Felter) til filsættet **Location** (Placering) eller **Latitude** (Breddegrad) og/eller **Longitude** (Længdegrad). I dette eksempel bruger vi **Store > City**.
   
   > [!NOTE]
   > ArcGIS Maps for Power BI registrerer automatisk, hvis de felter, som du har valgt, bedst kan ses som en figur eller et punkt på et kort. Du kan tilpasse standarden i indstillingerne (se nedenfor).
   > 
   > 
   
    ![ruden arcgis-felter](media/power-bi-visualization-arcgis/power-bi-fields-pane3new.png)

3. Fra feltet **Fields** (Felter) skal du trække en måling til filsættet **Size** (Størrelse) for at justere, hvordan dataene vises. I dette eksempel bruger vi **Sales > Last Year Sales**.
   
    ![visualisering med esri-punktkort](media/power-bi-visualization-arcgis/power-bi-esri-point-map-size2new.png)

## <a name="settings-and-formatting-for-arcgis-maps"></a>Indstillinger og formatering for ArcGIS-kort
Sådan får du adgang til formateringsfunktionerne i **ArcGIS Maps for Power BI**:

1. Få adgang til yderligere funktioner ved at vælge ellipsen i øverste højre hjørne af visualiseringen og vælge **Rediger**.
   
   ![ruden rediger arcgis](media/power-bi-visualization-arcgis/power-bi-edit2.png)
   
   De tilgængelige funktioner vises øverst i visualiseringen. Der åbnes en opgaverude for hver funktion, når den er blevet valgt, med mere detaljerede indstillinger.<br/>
   
   ![ruden esri-funktioner](media/power-bi-visualization-arcgis/power-bi-esri-features-new.png)
   
   > [!NOTE]
   > Du kan finde flere oplysninger om indstillingerne og funktionerne i den **detaljerede dokumentation** nedenfor.
   > 
   > 


<br/>

## <a name="detailed-documentation"></a>Detaljeret dokumentation
**Esri** leverer [omfattende dokumentation](https://go.microsoft.com/fwlink/?LinkID=828772) om funktionssættet i **ArcGIS Maps for Power BI**.

## <a name="features-overview"></a>Oversigt over funktioner
### <a name="base-maps"></a>Grundlæggende kort
Der findes fire grundlæggende kort: Dark Gray Canvas, Light Gray Canvas, OpenStreetMap og Streets.  Streets er ArcGIS' grundlæggende standardkort.

Hvis du vil anvende et grundlæggende kort, skal du vælge det i opgaveruden.

![visualisering med esri-basiskort](media/power-bi-visualization-arcgis/power-bi-esri-base-maps-new.png)

### <a name="location-type"></a>Placeringstype
ArgGIS Maps for Power BI finder automatisk den bedste måde at vise data på et kort på. Den vælger fra Points (Punkter) eller Boundaries (Grænser). Indstillingerne for placeringstype giver dig mulighed for at tilpasse disse valg.

![eksempel på esri-placeringstyper](media/power-bi-visualization-arcgis/power-bi-esri-location-types-new.png)

**Boundaries** (Grænser) fungerer kun, hvis dine data indeholder geografiske standardværdier. Esri finder automatisk ud af, hvilken figur der skal vises på kortet. Geografiske standardværdier omfatter lande, områder, postnumre osv. Men på samme måde som med geokodning registrerer Power BI muligvis ikke, om feltet skal være en grænse som standard, eller også indeholder tjenesten ikke en grænse for dine data.  

### <a name="map-theme"></a>Korttema
Der findes fire korttemaer. Temaerne Location Only (Kun placering) og Size (Størrelse) vælges automatisk på baggrund af de felter, du knyttede til filsættet **Size** (Størrelse) i ruden med Power BI-felter. Vi bruger i øjeblikket **Størrelse**, så lad os skifte til **Termisk kort**. Husk blot på at deaktivere **Termisk kort**, før du fortsætter med det næste trin.  

![eksempel på esri-korttema](media/power-bi-visualization-arcgis/power-bi-esri-map-theme-new.png)

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
Symboltypografier giver dig mulighed for at finjustere, hvordan data vises på kortet. Symboltypografier er kontekstafhængige og er baseret på den valgte placeringstype og det valgte korttema. I nedenstående eksempel vises korttypen, der er angivet til **Størrelse**, og flere justeringer af gennemsigtighed, typografi og størrelse. 

![eksempel på typografi af esri-symbol](media/power-bi-visualization-arcgis/power-bi-esri-symbol-style-new.png)

### <a name="pins"></a>Nåle
Fremhæv datapunkter på kortet ved at tilføje nåle.  

1. Vælg fanen **Pins** (Nåle).
2. Skriv nøgleord (f.eks adresser, steder og interessepunkter) i søgefeltet, og vælg på rullelisten. Der vises et symbol på kortet, og kortet zoomer automatisk ind på placeringen. Søgeresultater gemmes som placeringskort i ruden Pins (Knappenåle). Du kan gemme op til 10 placeringskort.
   
   ![eksempel på knappenål på arcgis-kort](media/power-bi-visualization-arcgis/power-bi-pin-arcgis-newer.png)
3. Power BI føjer en knappenål til den pågældende placering, og du kan ændre farven på knappenålen.
   
   ![eksempel på farve på knappenål](media/power-bi-visualization-arcgis/power-bi-pin-color-new.png)
4. Tilføj og slet knappenåle.
   
   ![eksempel på tilføjelse og sletning af knappenål](media/power-bi-visualization-arcgis/power-bi-pin3.png)

### <a name="drive-time"></a>Køretid
I ruden Drive time (Køretid) kan du vælge en placering og derefter angive, hvilken anden kortfunktion der er inden for en bestemt radius eller køretid.  
    ![eksempel på kørselstid](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

1. Vælg fanen **Drive time** (Køretid), og vælg værktøjet til valg af et eller flere elementer. Vælg knappenålen for Washington D.C.

   ![eksempel på valg af en enkelt knappenål](media/power-bi-visualization-arcgis/power-bi-esri-single-select.png)
   
   > [!TIP]
   > Det er lettere at vælge en placering, hvis du zoomer ind på kortet (ved hjælp af +-ikonet).
   > 
   > 
2. Lad os sige, at du skal til Washington D.C. i et par dage og gerne vil finde ud af, hvilke butikker der ligger inden for en rimelig køreafstand. Angiv søgeområdet til **Radius** og Distance (Afstand) til **50** mil, og vælg OK.    
   
    ![radius af kørselstid](media/power-bi-visualization-arcgis/power-bi-esri-drive-time-radius.png)

3. Radiussen vises i lilla. Vælg et vilkårligt sted for at få vist detaljer om det. Du kan eventuelt formatere radiussen ved at ændre farve og rammekontur.
   
    ![eksempel på radiusformat med farve og kontur](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

### <a name="reference-layer"></a>Referencelag
#### <a name="reference-layer---demographics"></a>Referencelag – demografi
ArcGIS Maps for Power BI indeholder en række demografiske lag, der hjælper med at kontekstualisere data fra Power BI.

1. Vælg fanen **Reference layer** (Referencelag), og vælg **Demographics** (Demografi).
2. Der er et afkrydsningsfelt ud for hvert lag, der er angivet. Markér afkrydsningsfeltet for at føje laget til kortet.  Vi har tilføjet den gennemsnitlige husstandsindkomst i dette eksempel.<br/>
   
    ![eksempel på demografisk referencelag](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-demographic.png)
3. Hvert lag er også interaktivt. På samme måde som du kan pege på en boble for at få vist detaljer, kan du klikke på et skraveret område på kortet for at få vist detaljer.<br/>
   
    ![eksempel på oplysninger om referencelag](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-details.png)

#### <a name="reference-layer---arcgis"></a>Referencelag – ArcGIS
ArcGIS Online giver virksomheder mulighed for at publicere offentlige webkort. Desuden leverer Esri et sæt overvågede webkort via Living Atlas. Under fanen ArcGIS kan du søge efter alle offentlige webkort eller Living Atlas-kort og føje dem til kortet som referencelag.

1. Vælg fanen **Reference layer** (Referencelag), og vælg **ArcGIS**.
2. Skriv søgeord, og vælg derefter et kortlag. I dette eksempel har vi valgt USA Congressional districts.
   
    ![eksempel på esri-demografi](media/power-bi-visualization-arcgis/power-bi-reference-details.png)
3. Hvis du vil have vist detaljerne, skal du vælge et skraveret område for at åbne *Vælg fra referencelag*: Brug markeringsværktøjet til referencelag til at vælge grænser eller objekter på referencelaget.

<br/>

## <a name="selecting-data-points"></a>Valg af datapunkter
ArcGIS Maps for Power BI tillader fem markeringstilstande, der hjælper dig med at vælge data præcist og hurtigt.

Skift markeringstilstanden ved at holde markøren over ikonet for det enkelte markeringsværktøj, som vist på nedenstående billede. Derved udvides den skjulte linje også, så der vises yderligere værktøjer:

![esri-markeringsværktøj](media/power-bi-visualization-arcgis/power-bi-esri-selection-tools2.png)

Hvert værktøj har en unik rolle, så du kan vælge dine data: 

![enkelt esri-markering](media/power-bi-visualization-arcgis/power-bi-esri-selection-single2.png) Vælg individuelle datapunkter.

![lysramme for esri-markering](media/power-bi-visualization-arcgis/power-bi-esri-selection-marquee2.png) Der tegnes et rektangel på kortet, og de indeholdte datapunkter markeres.

![referencelag for esri-markering](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-layer2.png) Tillader, at grænser eller polygoner i referencelag kan bruges til at vælge indeholdte datapunkter.

![bufferlag for esri-markering](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-buffer.png) Giver dig mulighed for at vælge data ved hjælp af et bufferlag.

![lignende markering i esri-markering](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-similar.png) Giver dig mulighed for at vælge datapunkter, der ligner hinanden.

> [!NOTE]
> Du kan maksimalt vælge 250 datapunkter ad gangen.
> 
> 

<br/>

## <a name="getting-help"></a>Få hjælp
**Esri** leverer [omfattende dokumentation](https://go.microsoft.com/fwlink/?LinkID=828772) om funktionssættet i **ArcGIS Maps for Power BI**.

Du kan stille spørgsmål, finde de seneste oplysninger, rapportere problemer og finde svar i Power BI [community'ets tråd om **ArcGIS Maps for Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771).

Hvis du har et forslag til en forbedring, kan du sende den til [Power BI's ideliste](https://ideas.powerbi.com).

<br/>

## <a name="managing-use-of-arcgis-maps-for-power-bi-within-your-organization"></a>Administration af brugen af ArcGIS Maps for Power BI i din organisation
Power BI giver brugere, lejeradministratorer og IT-administratorer mulighed for at administrere, om ArcGIS Maps for Power BI skal bruges eller ej. Nedenfor kan du se de trin, som hver rolle kan udføre for at administrere brugen af ArcGis Maps. 

### <a name="user-options"></a>Brugerindstillinger
I Power BI Desktop kan brugerne stoppe med at benytte ArcGIS Maps for Power BI ved at deaktivere funktionen under sikkerhedsfanen i **Fil** > **Indstillinger** og derefter vælge **Indstillinger** > **Sikkerhed**. Når ArcGIS Maps er deaktiveret, indlæses den ikke som standard.

![eksempel på dialogboksen sikkerhed i desktop](media/power-bi-visualization-arcgis/power-bi-desktop-security-dialog2.png)

### <a name="tenant-admin-options"></a>Indstillinger for lejeradministrator
I PowerBI.com kan lejeradministratorer forhindre, at alle lejerbruger benytter ArcGIS Maps for Power BI ved at deaktivere indstillingen under **Indstillinger** > **Administrationsportal** > **Lejerindstillinger**. Når det sker, vises ArcGIS Maps for Power BI-ikonet ikke længere i ruden med visualiseringer i Power BI.

![eksempel på arcGIS-administrationsportal](media/power-bi-visualization-arcgis/power-bi-arcgis-admin-portal2.png)

### <a name="it-administrator-options"></a>Indstillinger for IT-administrator
Power BI Desktop understøtter brug af **Gruppepolitik** til at deaktivere ArcGIS Maps for Power BI på tværs af de computere, der er udrullet i en organisation.

<table>
<tr><th>Attribut</th><th>Værdi</th>
</tr>
<tr>
<td>key</td>
<td>Software\Policies\Microsoft\Power BI Desktop&lt;/td&gt;
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

**Hvordan fungerer ArcGIS Maps til Power BI?**
ArcGIS Maps til Power BI leveres af Esri (www.esri.com). Din brug af ArcGIS Maps til Power BI er omfattet af Esris [vilkår](https://go.microsoft.com/fwlink/?LinkID=8263222) og [politik om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?LinkID=826323). Power BI-brugere, der gerne vil bruge ArcGIS-kort til visuelle elementer i Power BI, skal acceptere i dialogboksen til samtykke (se under Brugersamtykke for at få flere oplysninger).  Brug af Esris ArcGIS Maps til Power BI er underlagt Esris Vilkår og Politik om beskyttelse af personlige oplysninger, der også er linket til i dialogboksen til samtykke. Hver enkelt bruger skal samtykke, før de kan bruge ArcGIS Maps til Power BI første gang. Når brugeren accepterer samtykket, sendes data, der er bundet til visualiseringen til Esris tjenester i hvert fald i forbindelse med geo-kodning. Det vil sige, at placeringsoplysninger transformeres til oplysninger om længdegrad og breddegrad, der kan vises på et kort. Du skal antage, at alle data, der er bundet til datavisualiseringen kan sendes til Esris tjenester. Esri leverer tjenester, såsom kort, afstandsanalyse, geo-kodning osv. ArcGIS Maps til Power BI-visualiseringen interagerer med disse tjenester vha. en SSL-forbindelse, der beskyttes af et certifikat, som leveres og vedligeholdes af Esri. Du kan få flere oplysninger om ArcGIS Maps til Power BI på Esris [produktside for ArcGIS Maps til Power BI](https://www.esri.com/powerbi).

Når en bruger tilmelder sig et Plus-abonnement, der tilbydes af Esri, via ArcGIS Maps til Power BI, indgår vedkommende i en direkte relation med Esri. Power BI sender ikke personlige oplysninger om brugeren til Esri. Brugeren logger på og angiver, at vedkommende har tillid til et AAD-program, der leveres af Esri, vha. sit eget AAS-id. På denne måde deler brugeren sine personlige oplysninger direkte med Esri. Når brugeren føjer Plus-indhold til en ArcGIS Maps til Power BI-visualisering, skal andre Power BI-brugere også have et Plus-abonnement fra Esri for at kunne se eller redigere det pågældende indhold. 

Hvis du har tekniske spørgsmål om, hvordan Esris ArcGIS Maps til Power BI fungerer, skal du kontakte Esri via deres supportwebsted.

**Hvilke data sendes til Esri?**
Du kan læse om, hvilke data der overføres til Esri, i deres [dokumentation](https://doc.arcgis.com/en/maps-for-powerbi/get-started/data-transfer.htm).

**Er der omkostninger forbundet med brugen af ArcGIS Maps for Power BI?**

ArcGIS Maps for Power BI er tilgængelig for alle Power BI-brugere uden meromkostninger. Det er en komponent, der leveres af **Esri**, og din brug er underlagt **Esris** vilkår og beskyttelse af personlige oplysninger, som nævnt tidligere i denne artikel.

**Jeg får vist en fejlmeddelelse i Power BI Desktop om, at min cache er fuld**

Dette er en fejl, der er ved at blive behandlet.  I mellemtiden skal du slette filer på denne placering for at rydde cachen: C:\Users\\AppData\Local\Microsoft\Power BI Desktop\CEF og derefter genstarte Power BI.

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

