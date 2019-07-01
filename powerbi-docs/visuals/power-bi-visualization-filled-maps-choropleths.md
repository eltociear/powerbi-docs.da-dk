---
title: Udfyldte kort (Choropleths) i Power BI
description: Dokumentation om oprettelse af udfyldte kort (Choropleths) i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/19/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0123d8123170cfa78b3d13a55ed2f367af0447ae
ms.sourcegitcommit: 90aa7ea5fcc7cf0fd7f6c3c1efeff5f27e8ef0dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/20/2019
ms.locfileid: "67299325"
---
# <a name="filled-maps-choropleths-in-power-bi"></a>Udfyldte kort (Choropleths) i Power BI
Et udfyldt kort bruger skygger eller toner eller mønstre til at vise, hvordan en værdi varierer i forhold på tværs af et geografisk område eller en region.  Fremvis hurtigt disse relative forskelle med skygger, der går fra lys (mindre-hyppige/lavere) til mørk (mere-hyppige/mere).    

![USA-kort](media/power-bi-visualization-filled-maps-choropleths/large-map.png)

## <a name="what-is-sent-to-bing"></a>Hvad sendes til Bing
Power BI integreres med Bing for at angive standardkortkoordinaterne (en proces, der kaldes geokodning). Når du opretter en kortvisualisering i Power BI-tjenesten eller Power BI Desktop, sendes dataene i feltbeholderne **Location**, **Latitude** og **Longitude** ( der bruges til at oprette den pågældende visualisering) til Bing.

Du eller din administrator skal muligvis opdatere firewallen for at tillade adgang til URL-adresser, som Bing bruger til geokodning.  URL-adresserne er:
- https://dev.virtualearth.net/REST/V1/Locations    
- https://platform.bing.com/geo/spatial/v1/public/Geodata    
- https://www.bing.com/api/maps/mapcontrol

Du kan finde flere oplysninger om de data, der sendes til Bing, og få tip til at få større succes med geokodning under [Tip og råd til kortvisualiseringer](power-bi-map-tips-and-tricks.md).

## <a name="when-to-use-a-filled-map"></a>Hvornår er det smart at bruge udfyldte kort?
Udfyldte kort er et godt valg:

* Til at vise kvantitative oplysninger på et kort.
* Til at vise rumlige mønstre og relationer.
* Når dine data er standardiserede.
* Når du arbejder med socioøkonomiske data.
* Når definerede områder er vigtige.
* For at få et overblik over distributionen på tværs af geografiske placeringer.

### <a name="prerequisites"></a>Forudsætninger
- Power BI-tjenesten eller Power BI Desktop
- Eksempel på salg og marketing

Hvis du vil følge med, bruges Power BI-tjenesten i dette selvstudium, ikke Power BI Desktop.

## <a name="create-a-basic-filled-map"></a>Opret et grundlæggende udfyldt kort
I denne video opretter Kim et grundlæggende kort og konverterer det til et udfyldt kort.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>

### <a name="get-data-and-add-a-new-blank-page-to-the-report"></a>Hent data, og tilføj en ny tom side i rapporten
1. Hvis du vil oprette dit eget udfyldte kort, kan du [downloade salgs- og marketingeksemplet](../sample-datasets.md) ved at logge på Power BI og vælge **Hent data \> Eksempler \> Salg og marketing \> Tilslut**. Eller hent appen **Power BI-salg og -marketing** på appsource.com. 

2. Åbn rapporten Salg og marketing.

   ![Rapporten Salg og marketing åbnes](media/power-bi-visualization-filled-maps-choropleths/power-bi-report-canvas.png)
3. Power BI åbner rapporten. Vælg **Rediger rapport** for at åbne rapporten i [redigeringsvisning](../service-interact-with-a-report-in-editing-view.md).

4. Tilføj en ny side ved at vælge det gule plusikon nederst på rapportcanvasset.

    ![Rapportfaner](media/power-bi-visualization-filled-maps-choropleths/power-bi-new-page.png)

### <a name="create-a-filled-map"></a>Opret et kartogram
1. Fra ruden Fields skal du vælge feltet **Geo** \> **State**.    

   ![gult flueben ud for Tilstand](media/power-bi-visualization-filled-maps-choropleths/power-bi-state.png)
2. [Konvertér diagrammet](power-bi-report-change-visualization-type.md) til et udfyldt kort. Bemærk, at **State** nu befinder sig i beholderen **Location**. Bing Maps bruger feltet i beholderen **Location** til at oprette kortet.  Der er mange forskellige muligheder for gyldige placeringer: lande, stater, kommuner, byer, postnumre osv. Bing Maps levere udfyldte kortfigurer for placeringer over hele verden. Uden en gyldig post i beholderen Location kan Power BI ikke oprette det udfyldte kort.  

   ![skabeloner med fremhævet ikon for udfyldte kort](media/power-bi-visualization-filled-maps-choropleths/img003.png)
3. Filtrer kortet, så du kun ser det kontinentale USA.

   a.  Nederst i ruden Visualizations skal du finde området **Filters**.

   b.  Hold markøren over **State**, og klik på pilen Udvid  
   ![Filtre på visualiseringsniveau viser Tilstand (Alle)](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Markér afkrydsningsfeltet ud for **All**, og fjern markeringen ud for **AK**.

   ![Tilstandsrulleliste med Alle og AK ikke valgt](media/power-bi-visualization-filled-maps-choropleths/img005.png)
4. Vælg ikonet med malerrullen for at åbne ruden Formatering, og vælg **Datafarver**.

    ![Ruden Formatering med indstillingen Datafarver](media/power-bi-visualization-filled-maps-choropleths/power-bi-data-color.png)

5. Klik på de tre lodrette prikker, og vælg **Betinget formatering**.

    ![Knappen Betinget formatering af datafarver](media/power-bi-visualization-filled-maps-choropleths/power-bi-conditional-formatting.png)

6. Brug skærmen **Standardfarve - Datafarver** til at bestemme, hvordan dit kartogram skyggelægges. De indstillinger, der er tilgængelige for dig, omfatter, hvilket felt skyggen skal baseres på, og hvordan skyggen skal anvendes. I dette eksempel bruger vi feltet **SalesFact** > **Synspunkt** og angiver den laveste værdi for synspunkt som rød og den højeste værdi som grøn. Værdier, der ligger mellem den maksimale og den minimale, er være nuancer af rød og grøn. På illustration nederst på skærmen vises det farveområde, der bruges. 

    ![Standardfarverude med Synspunkt valgt](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment.png)

7. Kartogrammet har grønne og røde skygger, hvor rød repræsenterer de lavere tillidstal, og grøn repræsenterer den højere, mere positive tillid.  For at få vist yderligere detaljer skal du trække et felt til brønden Værktøjstip.  Her har jeg tilføjet **Synspunktsforskydning** og fremhævet staten Idaho (ID) og kan se, at den pågældende synspunktforskydning er lav, på 6.
   ![kartogram, der viser Idaho-værktøjstip](media/power-bi-visualization-filled-maps-choropleths/power-bi-filled-map-idaho.png)

10. [Gem rapporten](../service-report-save.md).

Power BI giver dig masser af kontrol over dit kartograms udseende. Leg lidt med disse datafarvekontrolelementer, indtil du opnår det ønskede udseende. 

## <a name="highlighting-and-cross-filtering"></a>Fremhævning og krydsfiltrering
Du kan få mere at vide om brug af ruden Filters under [Føj et filter til en rapport](../power-bi-report-add-filter.md).

Hvis du fremhæver en placering på et kartogram, krydsfiltreres de andre visualiseringer på rapportsiden ... og omvendt.

1. For at følge med skal du først gemme denne rapport ved at vælge **Filer > Gem**. 

2. Kopiér kartogrammet ved hjælp af Ctrl + C.

3. Nederst på rapportcanvasset skal du vælge fanen **Synspunkt** for at åbne rapportsiden Synspunkt.

    ![Fanen Synspunkt er valgt](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment-tab.png)

4. Flyt og tilpas størrelsen på visualiseringerne på siden for at få mere plads, indsæt derefter kartogrammet med Ctrl + V fra den tidligere rapport.

   ![Kartogram tilføjet på siden Synspunkt](media/power-bi-visualization-filled-maps-choropleths/power-bi-map.png)

5. Vælg en stat på det udfyldte kort.  Dette fremhæver de andre visualiseringer på siden. Hvis jeg f.eks. vælger **Texas**, viser det mig, at synspunktet er 74, Texas ligger i det centrale distrikt \#23.   
   ![Texas valgt](media/power-bi-visualization-filled-maps-choropleths/power-bi-texas.png)
2. Vælg et datapunkt i kurvediagrammet VanArsdel – tillid efter måned. Derved filtreres kartogrammet for at vise tillidsdata for VanArsdel og ikke deres konkurrenter.  
   ![ny skygge](media/power-bi-visualization-filled-maps-choropleths/power-bi-yes.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
Kortdata kan være tvetydige.  Der er f.eks. en by, der hedder Paris i Frankrig, men der er også en by, der hedder Paris i Texas. Dine geografiske data gemmes sikkert i separate kolonner – en kolonne til bynavne, en kolonne til statsnavne osv. – så Bing kan muligvis ikke regne ud, hvilket Paris du mener. Hvis dit datasæt allerede indeholder data om breddegrad og længdegrad, har Power BI særlige felter, der kan hjælpe med at gøre kortdataene entydige. Træk det felt, der indeholder dine data om breddegrad til området Visualizations \> Latitude.  Og gør det samme med dine længdegradsdata.    

![Ruderne Visualisering og Felter](media/power-bi-visualization-filled-maps-choropleths/pbi-latitude.png)

Hvis du har rettigheder til at redigere datasættet i Power BI Desktop, kan du se denne video for at få hjælp til at korrigere tvetydighed på kortet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Hvis du ikke har adgang til data om breddegrad og længdegrad, men du har redigeringsadgang til datasættet, [skal du følge disse instruktioner for at opdatere datasættet](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Du kan få hjælp til kortvisualiseringer under [Tip og råd til kortvisualiseringer](../power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Næste trin

[Figurkort](desktop-shape-map.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)