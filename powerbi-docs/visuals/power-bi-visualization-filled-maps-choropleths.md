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
ms.date: 09/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 67055f855ad2872a7cf175aba85aefae7945f670
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54276301"
---
# <a name="filled-maps-choropleths-in-power-bi"></a>Udfyldte kort (Choropleths) i Power BI
Et udfyldt kort bruger skygger eller toner eller mønstre til at vise, hvordan en værdi varierer i forhold på tværs af et geografisk område eller en region.  Fremvis hurtigt disse relative forskelle med skygger, der går fra lys (mindre-hyppige/lavere) til mørk (mere-hyppige/mere).    

![USA-kort](media/power-bi-visualization-filled-maps-choropleths/large_map.png)

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
1. Hvis du vil oprette dit eget udfyldte kort, kan du [downloade salgs- og marketingeksemplet](../sample-datasets.md) ved at logge på Power BI og vælge **Hent data \> Eksempler \> Salg og marketing \> Tilslut**.
2. Når du får vist meddelelsen om, at processen lykkedes, skal du lukke den og vælge fanen **Rapporter**. Vælg derefter **Eksempel på salg og marketing** for at åbne rapporten.

   ![Liste over rapportindhold](media/power-bi-visualization-filled-maps-choropleths/power-bi-content-reports2.png)
3. Power BI åbner rapporten. Vælg **Rediger rapport** for at åbne rapporten i [redigeringsvisning](../service-interact-with-a-report-in-editing-view.md).

4. Tilføj en ny side ved at vælge det gule plusikon nederst på rapportcanvasset.

    ![Rapportfaner](media/power-bi-visualization-filled-maps-choropleths/power-bi-new-page.png)

### <a name="create-a-filled-map"></a>Opret et kartogram
1. Fra ruden Fields skal du vælge feltet **Geo** \> **State**.    

   ![gult flueben ud for Tilstand](media/power-bi-visualization-filled-maps-choropleths/power-bi-state.png)
5. [Konvertér diagrammet](power-bi-report-change-visualization-type.md) til et udfyldt kort. Bemærk, at **State** nu befinder sig i beholderen **Location**. Bing Maps bruger feltet i beholderen **Location** til at oprette kortet.  Der er mange forskellige muligheder for gyldige placeringer: lande, stater, kommuner, byer, postnumre osv. Bing Maps levere udfyldte kortfigurer for placeringer over hele verden. Uden en gyldig post i beholderen Location kan Power BI ikke oprette det udfyldte kort.  

   ![skabeloner med fremhævet ikon for udfyldte kort](media/power-bi-visualization-filled-maps-choropleths/img003.png)
6. Filtrer kortet, så du kun ser det kontinentale USA.

   a.  Nederst i ruden Visualizations skal du finde området **Filters**.

   b.  Hold markøren over **State**, og klik på pilen Udvid  
   ![Filtre på visualiseringsniveau viser Tilstand (Alle)](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Markér afkrydsningsfeltet ud for **All**, og fjern markeringen ud for **AK**.

   ![Tilstandsrulleliste med Alle og AK ikke valgt](media/power-bi-visualization-filled-maps-choropleths/img005.png)
7. Vælg **SalesFact** \> **Sentiment** for at føje det til beholderen **Color saturation**. Feltet i beholderen **Color saturation** styrer skyggerne på kortet.  
   ![Synspunkt i feltet Farvemætning godt](media/power-bi-visualization-filled-maps-choropleths/power-bi-filled-map.png)
8. Kartogrammet har grønne og røde skygger, hvor rød repræsenterer de lavere tillidstal, og grøn repræsenterer den højere, mere positive tillid.  Jeg har her fremhævet staten Wyoming (WY), og vi kan se, at tilliden (sentiment) er rigtig god, 74.  
   ![sort dialogboksen viser tilstand og synspunkt](media/power-bi-visualization-filled-maps-choropleths/power-bi-wy.png)
9. [Gem rapporten](../service-report-save.md).
##    <a name="adjust-the-color-formatting"></a>Juster farveformateringen
I Power BI kan du i høj grad selv styre udseendet af dit kartogram.
1. Vælg ikonet med malerrullen for at åbne fanen Formatering.

    ![Ruden Formatering](media/power-bi-visualization-filled-maps-choropleths/power-bi-data-colors.png)

2. Vælg **Datafarver** for at få vist indstillinger for farver.
3. Angiv minimum- og maksimumfarverne til gul og blå. Og tilføj minimum- og maksimumværdier baseret på dine data. Leg lidt med disse funktioner, indtil du får det ønskede udseende. 

    ![ikke-divergerende farver](media/power-bi-visualization-filled-maps-choropleths/power-bi-color.png)

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

![Ruderne Visualisering og Felter](media/power-bi-visualization-filled-maps-choropleths/pbi_latitude.png)

Hvis du har rettigheder til at redigere datasættet i Power BI Desktop, kan du se denne video for at få hjælp til at korrigere tvetydighed på kortet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Hvis du ikke har adgang til data om breddegrad og længdegrad, [kan du følge disse instrukser for at opdatere datasættet](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Du kan få hjælp til kortvisualiseringer under [Tip og råd til kortvisualiseringer](../power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Næste trin

[Figurkort](desktop-shape-map.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)