---
title: Oversigt over bogmærker i Power BI-tjenesten rapporter
description: Oversigtsemne i dokumentationen om forespørgsler i naturligt sprog i Spørgsmål og svar i Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/10/2019
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 55fafb00135908dc4f82151b96ed04d2cf2568da
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608319"
---
# <a name="what-are-bookmarks"></a>Hvad er bogmærker?
Bogmærker indfange den visning, der er konfigureret i øjeblikket af en rapportside, herunder filtre, udsnitsværktøjer og tilstanden for visualiseringer. Når du vælger et bogmærke, vender Power BI du tilbage til visningen. Der er to typer af bogmærker – dem, du opretter, dig selv, og dem, der er oprettet af rapporten *designere*.

## <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi"></a>Brug bogmærker til at dele indsigt og oprette historier i Power BI 
Der er mange situationer, hvor bogmærker. Sige, at du finder en interessant indsigt, og du vil bevare den – Opret et bogmærke, så du kan vende tilbage senere. Skal du lade og vil bevare din aktuelle arbejde, skal du oprette et bogmærke. Du kan endda gøre et bogmærke, din standardvisning af rapporten, så hver gang du vender tilbage, visning af rapportsiden åbnes først. 

Du kan også oprette en samling af bogmærker, arrangere dem i den rækkefølge, du vil, og efterfølgende Gennemgå hvert bogmærke i en præsentation for at fremhæve en række Indsigter, der fortæller en historie.  

![Vis Bogmærkeruden ved at vælge det på båndet.](media/end-user-bookmarks/power-bi-bookmarks-pane.png)

## <a name="using-bookmarks"></a>Brug bogmærker
For at åbne ruden bogmærker, skal du vælge **bogmærker** på menulinjen. For at vende tilbage til den oprindelige publicerede visning af rapporten, skal du vælge **Nulstil til standard**.

### <a name="report-bookmarks"></a>Rapporten bogmærker
Hvis rapporten *designer* inkluderet rapport bogmærker, du kan finde dem under den **rapportere bogmærker** overskrift. 

![Få vist rapporten bogmærker.](media/end-user-bookmarks/power-bi-report-bookmark.png)

Vælg et bogmærke til at skifte til den pågældende rapportvisningen. 

![Videoen viser rapporten bogmærker er valgt.](media/end-user-bookmarks/power-bi-bookmarks.gif)

### <a name="personal-bookmarks"></a>Personlige bogmærker

Når du opretter et bogmærke, gemmes følgende elementer sammen med bogmærket:

* Den aktuelle side
* Filtre
* Udsnit, herunder udsnitstypen (f.eks. rulleliste eller rullemenu) og udsnitstilstand
* Tilstand for visuel markering (f.eks. tværgående fremhævningsfiltre)
* Sorteringsrækkefølgen
* Placering af detailudledning
* Synlighed (for et objekt i ruden **Markering**)
* Tilstanden Fokus eller **Spotlight** for et synligt objekt

Konfigurer en rapportside, som du ønsker, den skal vises i bogmærket. Når din rapportside og dine visuelle elementer er arrangeret, som du ønsker det, skal du vælge **Tilføj** i ruden **Bogmærker** for at tilføje et bogmærke. I dette eksempel har vi tilføjet nogle filtre for område og dato. 

![Tilføj personlige bogmærker.](media/end-user-bookmarks/power-bi-add-personal.png)

**Power BI** opretter et bogmærke og giver det et standardnavn eller et navn, du angiver. Du kan *Omdøb*, *slette*, eller *opdatere* et bogmærke ved at vælge ellipsen ud for bogmærkets navn og derefter vælge en handling i den viste menu.

Når du har et bogmærke, du kan få vist det ved ganske enkelt at vælge bogmærket i den **bogmærker** rude. 

![Tilføj personlige bogmærker.](media/end-user-bookmarks/power-bi-personal-bookmark.png)


<!--
## Arranging bookmarks
As you create bookmarks, you might find that the order in which you create them isn't necessarily the same order you'd like to present them to your audience. No problem, you can easily rearrange the order of bookmarks.

In the **Bookmarks** pane, simply drag-and-drop bookmarks to change their order, as shown in the following image. The yellow bar between bookmarks designates where the dragged bookmark will be placed.

![Change bookmark order by drag-and-drop](media/desktop-bookmarks/bookmarks_06.png)

The order of your bookmarks can become important when you use the **View** feature of bookmarks, as described in the next section. 

-->

## <a name="bookmarks-as-a-slide-show"></a>Bogmærker som et slideshow
Hvis du vil præsentere eller få vist bogmærker i rækkefølge, skal du vælge **visning** fra den **bogmærker** rude for at starte et slideshow.

I tilstanden **Vis** er der nogle funktioner, du skal lægge mærke til:

1. Navnet på bogmærket vises på bogmærkets titellinje, der vises nederst på lærredet.
2. Bogmærkets titellinje har pile, som du kan bruge til at flytte til næste eller forrige bogmærke.
3. Du kan afslutte tilstanden **Vis** ved at vælge **Afslut** i ruden **Bogmærker** eller ved at vælge krydset (**X**) i bogmærkets titellinje. 

![Diasshow bogmærke](media/end-user-bookmarks/power-bi-bookmark-slideshow.png)

Når du er i tilstanden **Vis**, kan du lukke ruden **Bogmærker** (ved at klikke på krydset (X) i ruden) for at give mere plads til præsentationen. Mens du er i tilstanden **Vis**, er alle visualiseringer interaktive og tilgængelige for tværgående fremhævning, ligesom når du interagerer med dem. 

<!--
## Visibility - using the Selection pane
With the release of bookmarks, the new **Selection** pane is also introduced. The **Selection** pane provides a list of all objects on the current page and allows you to select the object and specify whether a given object is visible. 

![Enable the Selection pane](media/desktop-bookmarks/bookmarks_08.png)

You can select an object using the **Selection** pane. Also, you can toggle whether the object is currently visible by clicking the eye icon to the right of the visual. 

![Selection pane](media/desktop-bookmarks/bookmarks_09.png)

When a bookmark is added, the visible status of each object is also saved based on its setting in the **Selection** pane. 

It's important to note that **slicers** continue to filter a report page, regardless of whether they are visible. As such, you can create many different bookmarks, with different slicer settings, and make a single report page appear very different (and highlight different insights) in various bookmarks.


## Bookmarks for shapes and images
You can also link shapes and images to bookmarks. With this feature, when you click on an object, it will show the bookmark associated with that object. This can be especially useful when working with buttons; you can learn more by reading the article about [using buttons in Power BI](desktop-buttons.md). 

To assign a bookmark to an object, select the object, then expand the **Action** section from the **Format Shape** pane, as shown in the following image.

![Add bookmark link to an object](media/desktop-bookmarks/bookmarks_10.png)

Once you turn the **Action** slider to **On** you can select whether the object is a back button, a bookmark, or a Q&A command. If you select bookmark, you can then select which of your bookmarks the object is linked to.

There are all sorts of interesting things you can do with object-linked bookmarking. You can create a visual table of contents on your report page, or you can provide different views (such as visual types) of the same information, just by clicking on an object.

When you are in editing mode you can use ctrl+click to follow the link, and when not in edit mode, simply click the object to follow the link. 


## Bookmark groups

Beginning with the August 2018 release of **Power BI Desktop**, you can create and use bookmark groups. A bookmark group is a collection of bookmarks that you specify, which can be shown and organized as a group. 

To create a bookmark group, hold down the CTRL key and select the bookmarks you want to include in the group, then click the ellipses beside any of the selected bookmarks, and select **Group** from the menu that appears.

![Create a bookmark group](media/desktop-bookmarks/bookmarks_15.png)

**Power BI Desktop** automatically names the group *Group 1*. Fortunately, you can just double-click on the name and rename it to whatever you want.

![Rename a bookmark group](media/desktop-bookmarks/bookmarks_16.png)

With any bookmark group, clicking on the bookmark group's name only expands or collapses the group of bookmarks, and does not represent a bookmark by itself. 

When using the **View** feature of bookmarks, the following applies:

* If the selected bookmark is in a group when you select **View** from bookmarks, only the bookmarks *in that group* are shown in the viewing session. 

* If the selected bookmark is not in a group, or is on the top level (such as the name of a bookmark group), then all bookmarks for the entire report are played, including bookmarks in any group. 

To ungroup bookmarks, just select any bookmark in a group, click the ellipses, and then select **Ungroup** from the menu that appears. 

![Ungroup a bookmark group](media/desktop-bookmarks/bookmarks_17.png)

Note that selecting **Ungroup** for any bookmark from a group takes all bookmarks out of the group (it deletes the group, but not the bookmarks themselves). So to remove a single bookmark from a group, you need to **Ungroup** any member from that group, which deletes the grouping, then select the members you want in the new group (using CTRL and clicking each bookmark), and select **Group** again. 
-->





## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
I denne version af **bogmærker** er der nogle få begrænsninger og overvejelser at tage betragtning.

* De fleste brugerdefinerede visuals fungerer fint sammen med bogmærker. Hvis du oplever problemer med et bogmærke og en brugerdefineret visual, kan du kontakte forfatteren af denne visual og bede om at få føjet understøttelse af bogmærker til deres visuals. 
* Hvis du tilføjer et visuelt element på en rapportside, når du har oprettet et bogmærke, vises det visuelle element i standardtilstanden. Det betyder også, at hvis du vil indføre et udsnitsværktøj på en side, hvor du tidligere har oprettet bogmærker, optræder udsnittet i standardtilstanden.
* Hvis du flytter rundt på visuelle elementer, efter at der er oprettet et bogmærke, afspejles det i bogmærket. 
* Som hovedregel dine bogmærker vil ikke blive berørt, hvis rapporten *designer* opdaterer eller genudgiver rapporten. Men hvis designeren gør større ændringer i rapporten, f.eks fjerne felter, der bruges af et bogmærke, derefter får du en fejlmeddelelse næste gang du forsøger at åbne denne bogmærke. 

<!--
## Next steps
spotlight?
-->
