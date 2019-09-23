---
title: Brug af bogmærker i Power BI
description: Du kan bruge bogmærker i Power BI Desktop til at gemme visninger og indstillinger i dine rapporter og oprette præsentationer med tekstenheder
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/22/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 59d5ccd6a7179ca4c44210854fb66abb5371ac6c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61325826"
---
# <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi"></a>Brug bogmærker til at dele indsigt og oprette historier i Power BI 
Ved hjælp af **bogmærker** i Power BI kan du indfange den visning af en rapportside, der er konfigureret i øjeblikket, herunder filtrering af og tilstanden for visualiseringer, og senere gå tilbage til denne tilstand ved ganske enkelt at vælge det gemte bogmærke. 

Du kan også oprette en samling af bogmærker, arrangere dem i den ønskede rækkefølge og efterfølgende gennemgå hvert bogmærke i en præsentation for at fremhæve en række indsigter eller den tekstenhed, du vil fortælle med dine visuelle elementer og rapporter. 

![Bogmærker i Power BI](media/desktop-bookmarks/bookmarks_01.png)

Bogmærker kan bruges til mange ting. Du kan bruge dem til at holde styr på dit eget fremskridt, når du opretter rapporter (det er nemt at tilføje, slette og omdøbe bogmærker), og du kan oprette bogmærker, hvis du vil lave en PowerPoint-lignende præsentation, der gennemgår bogmærker i en bestemt rækkefølge og dermed fortæller en historie med din rapport. Der kan også være andre anvendelsesmuligheder, afhængigt af hvordan du mener, at bogmærker bedst kan bruges.

> [!TIP]
> Du kan finde oplysninger om brug af Personlige bogmærker i Power BI-tjenesten ved at se [blogindlægget](https://powerbi.microsoft.com/blog/announcing-personal-bookmarks-in-the-power-bi-service/) om funktionen Personlige bogmærker. 

### <a name="enable-the-bookmarks-preview-versions-prior-to-march-2018"></a>Aktivér eksempelvisning af bogmærker (versioner fra før marts 2018)
Bogmærker er generelt tilgængelige fra og med versionen fra marts 2018 af Power BI Desktop. 

Det anbefales altid at opgradere til den nyeste version. Hvis din version af Power BI Desktop derimod er fra før marts 2018, kan du prøve funktionen til **bogmærker** fra og med versionen af **Power BI Desktop** fra **oktober 2017** samt i **Power BI-tjenesten** i forbindelse med rapporter, hvor bogmærker er aktiveret. Du aktiverer eksempelvisningen ved at vælge **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning** og derefter markere afkrydsningsfeltet ud for **Bogmærker**. 

![Aktivér bogmærker i vinduet Indstillinger](media/desktop-bookmarks/bookmarks_02.png)

Du skal genstarte **Power BI Desktop**, når du har aktiveret funktionen til eksempelvisning af bogmærker.

## <a name="using-bookmarks"></a>Brug bogmærker
Hvis du vil bruge bogmærker, skal du vælge båndet **Vis** og derefter markere afkrydsningsfeltet ud for **Bogmærkerude**. 

![Vis bogmærkeruden ved at aktivere den på båndet Vis.](media/desktop-bookmarks/bookmarks_03.png)

Når du opretter et bogmærke, gemmes følgende elementer sammen med bogmærket:

* Den aktuelle side
* Filtre
* Udsnit, herunder udsnitstypen (f.eks. rulleliste eller rullemenu) og udsnitstilstand
* Tilstand for visuel markering (f.eks. tværgående fremhævningsfiltre)
* Sorteringsrækkefølgen
* Placering af detailudledning
* Synlighed (for et objekt i ruden **Markering**)
* Tilstanden Fokus eller **Spotlight** for et synligt objekt

Konfigurer en rapportside, som du ønsker, den skal vises i bogmærket. Når din rapportside og dine visuelle elementer er arrangeret, som du ønsker det, skal du vælge **Tilføj** i ruden **Bogmærker** for at tilføje et bogmærke. 

![Tilføj et bogmærke](media/desktop-bookmarks/bookmarks_04.png)

**Power BI Desktop** opretter et bogmærke og giver det et standardnavn. Du kan nemt *omdøbe*, *slette* eller *opdatere* et bogmærke ved at vælge ellipsen ud for bogmærkets navn og derefter vælge en handling i den viste menu.

![Vælg undermenuen for et bogmærke ved hjælp af ellipserne](media/desktop-bookmarks/bookmarks_05.png)

Når du har et bogmærke, kan du få vist det ved ganske enkelt at klikke på bogmærket i ruden **Bogmærker**. 

Du kan også vælge, om de enkelte bogmærker skal anvende *data*egenskaber, f.eks. filtre og udsnit, *visnings*egenskaber, f.eks. spotlight og synlighed, og sideændringer, der viser den side, som kunne ses, da bogmærket blev tilføjet. Disse funktioner er nyttige, når du bruger bogmærker til at skifte mellem rapportvisninger eller valg af visualiseringer – i så fald vil du sandsynligvis deaktivere dataegenskaber, så filtre ikke nulstilles, når brugerne skifter visning ved at vælge et bogmærke. 

Du kan foretage sådanne ændringer ved at vælge ellipserne ud for bogmærkets navn, som vist på forrige billede, og derefter markere eller fjerne markeringen i afkrydsningsfeltet ud for *Data*, *Visning* og andre objekter. 

## <a name="arranging-bookmarks"></a>Arranger bogmærker
Når du opretter bogmærker, finder du måske ud af, at den rækkefølge, som du opretter dem i, ikke nødvendigvis er den rækkefølge, som de skal vises i. Ikke noget problem. Du kan nemt ændre rækkefølgen af bogmærker.

I ruden **Bogmærker** skal du blot trække og slippe bogmærkerne for at ændre rækkefølgen som vist på følgende billede. Den gule streg mellem bogmærker angiver, hvor det bogmærke, du trækker, placeres.

![Skift rækkefølgen for bogmærker ved at trække og slippe](media/desktop-bookmarks/bookmarks_06.png)

Rækkefølgen for bogmærkerne kan være vigtig, når du anvender funktionen **Vis** på bogmærker, som beskrevet i næste afsnit.

## <a name="bookmarks-as-a-slide-show"></a>Bogmærker som et slideshow
Når du har en samling af bogmærker, du vil vise i en bestemt rækkefølge, kan du vælge **Vis** i ruden **Bogmærker** for at starte et slideshow.

I tilstanden **Vis** er der nogle funktioner, du skal lægge mærke til:

1. Navnet på bogmærket vises på bogmærkets titellinje, der vises nederst på lærredet.
2. Bogmærkets titellinje har pile, som du kan bruge til at flytte til næste eller forrige bogmærke.
3. Du kan afslutte tilstanden **Vis** ved at vælge **Afslut** i ruden **Bogmærker** eller ved at vælge krydset (**X**) i bogmærkets titellinje. 

![Funktioner på bogmærkers titellinje](media/desktop-bookmarks/bookmarks_07.png)

Når du er i tilstanden **Vis**, kan du lukke ruden **Bogmærker** (ved at klikke på krydset (X) i ruden) for at give mere plads til præsentationen. Mens du er i tilstanden **Vis**, er alle visualiseringer interaktive og tilgængelige for tværgående fremhævning, ligesom når du interagerer med dem. 

## <a name="visibility---using-the-selection-pane"></a>Synlighed – med ruden Markering
Med udgivelsen af bogmærker introduceres den nye rude **Markering** også. Ruden **Markering** indeholder en liste over alle objekter på den aktuelle side, og du kan markere objektet og angive, om et bestemt objekt skal være synligt. 

![Aktivér ruden Markering](media/desktop-bookmarks/bookmarks_08.png)

Du kan vælge et objekt i ruden **Markering**. Du kan også vælge, om objektet i øjeblikket skal være synligt, ved at klikke på ikonet med øjet til højre for det visuelle element. 

![Ruden Markering](media/desktop-bookmarks/bookmarks_09.png)

Når der tilføjes et bogmærke, gemmes synlighedsstatus for de enkelte objekter på baggrund af indstillingen i ruden **Markering**. 

Det er vigtigt at bemærke, at **udsnitsværktøjer** fortsat filtrerer en rapportside, uanset om de er synlige. Du kan derfor oprette mange forskellige bogmærker med forskellige indstillinger for udsnitsværktøj og få en enkelt rapportside vist på forskellige måder (og fremhæve forskellig indsigt) i forskellige bogmærker.

## <a name="bookmarks-for-shapes-and-images"></a>Bogmærker for figurer og billeder
Du kan også knytte figurer og billeder til bogmærker. Når du bruger denne funktion, og du klikker på et objekt, vises det bogmærke, der er knyttet til objektet. Det kan især være nyttigt, når du arbejder med knapper. Du kan få mere at vide ved at læse artiklen om [brug af knapper i Power BI](desktop-buttons.md). 

Hvis du vil knytte et bogmærke til et objekt, skal du vælge objektet og derefter udvide sektionen **Handling** i ruden **Formatér figur**, som vist på følgende billede.

![Tilføj et bogmærkelink til et objekt](media/desktop-bookmarks/bookmarks_10.png)

Når du slår skyderen **Handling** **til**, kan du vælge, om objektet skal være en tilbage-knap, et bogmærke eller en spørgsmål og svar-kommando. Hvis du vælger et bogmærke, kan du vælge, hvilket af dine bogmærker objektet skal knyttes til.

Du kan gøre mange forskellige interessante ting med bogmærker, der har tilknyttet et objekt. Du kan oprette en visuel tabel med indhold på din rapportside, eller du kan angive forskellige visninger (f.eks. visuelle typer) med de samme oplysninger ved bare at klikke på et objekt.

Når du er i redigeringstilstand, kan du bruge Ctrl + klik for at følge linket, og når du ikke er i redigeringstilstand, skal du bare klikke på objektet for at følge linket. 

## <a name="bookmark-groups"></a>Bogmærkegrupper

Fra og med versionen af **Power BI Desktop** fra august 2018 kan du oprette og bruge bogmærkegrupper. En bogmærkegruppe er en samling af bogmærker, som du angiver, og som kan vises og organiseres som en gruppe. 

Hvis du vil oprette en bogmærkegruppe, skal du holde Ctrl nede og vælge de bogmærker, du vil medtage i gruppen. Klik derefter på de tre prikker ud for et af de valgte bogmærker, og vælg **Gruppér** i den viste menu.

![Opret en bogmærkegruppe](media/desktop-bookmarks/bookmarks_15.png)

**Power BI Desktop** kalder automatisk gruppen for *Gruppe 1*. Hvis du vil omdøbe gruppen, skal du blot dobbeltklikke på navnet og give den et nyt navn.

![Omdøb en bogmærkegruppe](media/desktop-bookmarks/bookmarks_16.png)

Hvis du klikker på navnet på en bogmærkegruppe, bliver gruppen af bogmærker vist eller skjult. Selve gruppenavnet repræsenterer ikke et bogmærke. 

Når du bruger funktionen **Vis** med bogmærker, gælder følgende:

* Hvis det valgte bogmærke er i en gruppe, når du vælger **Vis** fra bogmærkerne, er det kun bogmærkerne *i den pågældende gruppe*, der vises. 

* Hvis det valgte bogmærke ikke er i en gruppe, eller det er på øverste niveau (f.eks navnet på en bogmærkegruppe), vises alle bogmærkerne for hele rapporten, herunder bogmærkerne i en gruppe. 

Hvis du vil ophæve en gruppe af bogmærker, skal du vælge et bogmærke i en gruppe, klikke på de tre prikker og derefter vælge **Opdel gruppe** i den viste menu. 

![Opdel en bogmærkegruppe](media/desktop-bookmarks/bookmarks_17.png)

Hvis du vælger **Opdel gruppe** for et bogmærke i en gruppe, fjernes alle bogmærkerne fra gruppen (det er kun gruppen, der slettes, ikke selve bogmærkerne). Hvis du vil fjerne et enkelt bogmærke fra en gruppe, skal du vælge **Opdel gruppe** for et bogmærke i gruppen, hvilket fjerner gruppen, og derefter skal du vælge de medlemmer, du vil have i en ny gruppe (hold Ctrl nede, og klik på hvert bogmærke), og vælg **Gruppér** igen. 


## <a name="using-spotlight"></a>Brug Spotlight
En anden funktion, der er udgivet sammen med bogmærker, er **Spotlight**. Du kan bruge **Spotlight** til at fremhæve et bestemt diagram, f.eks. når du viser dine bogmærker i tilstanden **Vis**.

Lad os sammenligne **Spotlight** med tilstanden **Fokus** for at se, hvordan de adskiller sig fra hinanden.

1. I tilstanden **Fokus** kan du få ét visuelt element til at fylde hele lærredet ved at vælge ikonet for **fokustilstanden**.
2. Du kan bruge **Spotlight** til at fremhæve ét visuelt element i den oprindelige størrelse ved at få alle andre visuelle elementer på siden til at tone ud, så de næsten er gennemsigtige. 

![Sammenlign fokustilstand med spotlight](media/desktop-bookmarks/bookmarks_11.png)

Når der klikkes på ikonet **Fokus** for det visuelle element på forrige side, ser siden sådan ud:

![fokustilstand](media/desktop-bookmarks/bookmarks_12.png)

Når **Spotlight** derimod er valgt i ellipsemenuen for det visuelle element, ser siden ud, som det, du kan se her:

![spotligthtilstand](media/desktop-bookmarks/bookmarks_13.png)

Hvis en af tilstandene er markeret, når der tilføjes et bogmærke, bevares denne tilstand (fokus eller spotlight) i bogmærket.

## <a name="bookmarks-in-the-power-bi-service"></a>Bogmærker i Power BI-tjenesten
Når du publicerer en rapport i **Power BI-tjenesten** med mindst ét bogmærke, kan du få vist og interagere med disse bogmærker i **Power BI-tjenesten**. Når bogmærker er tilgængelige i en rapport, kan du vælge **Vis > ruden Markering** eller **Vis > ruden Bogmærker** for at få vist hver af disse ruder.

![Få vist bogmærker og markeringsruder i Power BI-tjenesten](media/desktop-bookmarks/bookmarks_14.png)

I **Power BI-tjenesten** fungerer **ruden Bogmærker** på samme måde som i **Power BI Desktop**, dvs. du har også mulighed for at vælge **Vis** for at få vist dine bogmærker i rækkefølge, f.eks. som et slideshow.

Bemærk, at du skal bruge titellinjen for det grå bogmærke til at navigere rundt i bogmærkerne og ikke de sorte pile (de sorte pile flytter dig gennem rapportsider, ikke bogmærker).

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
I denne version af **bogmærker** er der nogle få begrænsninger og overvejelser at tage betragtning.

* De fleste brugerdefinerede visuals fungerer fint sammen med bogmærker. Hvis du oplever problemer med et bogmærke og en brugerdefineret visual, kan du kontakte forfatteren af denne visual og bede om at få føjet understøttelse af bogmærker til deres visuals. 
* Hvis du tilføjer et visuelt element på en rapportside, når du har oprettet et bogmærke, vises det visuelle element i standardtilstanden. Det betyder også, at hvis du vil indføre et udsnitsværktøj på en side, hvor du tidligere har oprettet bogmærker, optræder udsnittet i standardtilstanden.
* Hvis du flytter rundt på visuelle elementer, efter at der er oprettet et bogmærke, afspejles det i bogmærket. 


## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om de funktioner, der ligner eller interagerer med bogmærker, i følgende artikler:

* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)
* [Vis et dashboardfelt eller en rapport i fokustilstand](consumer/end-user-focus.md)

