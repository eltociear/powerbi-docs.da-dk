---
title: "Brug bogmærker i Power BI (prøveversion)"
description: "Du kan bruge bogmærker i Power BI Desktop til at gemme visninger og indstillinger i dine rapporter og oprette præsentationer med tekstenheder"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: e60ff6d06e4ac0cddf398ccfc1d30e4d97e0773c
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
---
# <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi-preview"></a>Brug bogmærker til at dele indsigt og oprette tekstenheder i Power BI (prøveversion)
Hvis du bruger **bogmærker** i Power BI, kan du indfange den visning af en rapportside, der er konfigureret i øjeblikket, herunder filtrering af og tilstanden for visuelle elementer, og senere gå tilbage til denne tilstand ved ganske enkelt at vælge det gemte bogmærke. 

Du kan også oprette en samling af bogmærker, arrangere dem i den ønskede rækkefølge og efterfølgende gennemgå hvert bogmærke i en præsentation for at fremhæve en række indsigter eller den tekstenhed, du vil fortælle med dine visuelle elementer og rapporter. 

![Bogmærker i Power BI](media/desktop-bookmarks/bookmarks_01.png)

Bogmærker kan bruges til mange ting. Du kan bruge dem til at holde styr på din egen fremskridt, når du opretter rapporter (det er nemt at tilføje, slette og omdøbe bogmærker), og du kan oprette bogmærker, hvis du vil oprette en PowerPoint-lignende præsentation, der gennemgår bogmærker i en bestemt rækkefølge og dermed fortæller en historie med din rapport. Der kan også være andre anvendelsesmuligheder, afhængigt af hvordan du mener, at bogmærker bedst kan bruges.

### <a name="enable-the-bookmarks-preview"></a>Aktivér eksempelvisning af bogmærker
Du kan prøve den nye **bogmærkefunktion**, der udgives i versionen af **Power BI Desktop** fra **oktober 2017**, og som også kan bruges i rapporter, der er kompatible med bogmærker, i  **Power BI-tjenesten**. Hvis du vil aktivere denne eksempelfunktion, skal du vælge **Filer > Indstillinger > Indstillinger> Funktioner til eksempelvisning** og derefter markere afkrydsningsfeltet ud for **Bogmærker**. Du skal genstarte Power BI Desktop, når du har markeret indstillingen.

![Aktivér bogmærker i vinduet Indstillinger](media/desktop-bookmarks/bookmarks_02.png)

Du skal genstarte **Power BI Desktop**, når du har markeret indstillingen.

## <a name="using-bookmarks"></a>Brug bogmærker
Hvis du vil bruge bogmærker, skal du vælge båndet **Vis** og derefter markere afkrydsningsfeltet ud for **Bogmærkerude**. 

![Vis bogmærkeruden ved at aktivere den på båndet Vis.](media/desktop-bookmarks/bookmarks_03.png)

Når du opretter et bogmærke, gemmes følgende elementer sammen med bogmærket:

* Den aktuelle side
* Filtre
* Udsnitsværktøjer
* Sorteringsrækkefølgen
* Placering af detailudledning
* Synlighed (for et objekt i ruden **Markering**)
* Tilstanden Fokus eller **Spotlight** for et synligt objekt

Bogmærker gemmer ikke den tværgående fremhævningstilstand i øjeblikket. 

Konfigurer en rapportside, som du ønsker, den skal vises i bogmærket. Når din rapportside og dine visuelle elementer er arrangeret, som du ønsker det, skal du vælge **Tilføj** i ruden **Bogmærker** for at tilføje et bogmærke. 

![Tilføj et bogmærke](media/desktop-bookmarks/bookmarks_04.png)

**Power BI Desktop** opretter et bogmærke og giver det et standardnavn. Du kan nemt *omdøbe* et bogmærke, *slette* det eller *opdatere* et bogmærke ved at vælge ellipsen ud for navnet på bogmærket og derefter vælge en handling i den menu, der vises.

![Vælg undermenuen for et bogmærke ved hjælp af ellipsen](media/desktop-bookmarks/bookmarks_05.png)

Når du har et bogmærke, kan du få vist det ved ganske enkelt at klikke på bogmærket i ruden **Bogmærker**. 

## <a name="arranging-bookmarks"></a>Arranger bogmærker
Når du opretter bogmærker, finder du måske ud af, at den rækkefølge, som du opretter dem i, ikke nødvendigvis er den rækkefølge, som de skal vises i. Ikke noget problem. Du kan nemt ændre rækkefølgen af bogmærker.

I ruden **Bogmærker** skal du bare trække og slippe bogmærkerne for at ændre rækkefølgen som vist på følgende billede. Den gule streg mellem bogmærker angiver, hvor det bogmærke, du trækker, placeres.

![Skift rækkefølgen for bogmærker ved at trække og slippe](media/desktop-bookmarks/bookmarks_06.png)

Rækkefølgen for bogmærkerne kan være vigtig, når du anvender funktionen **Vis** på bogmærker, som beskrevet i næste afsnit.

## <a name="bookmarks-as-a-slide-show"></a>Bogmærker som et slideshow
Når du har en samling af bogmærker, du vil vise i en bestemt rækkefølge, kan du vælge **Vis** i ruden **Bogmærker** for at starte et slideshow.

I tilstanden **Vis** er der nogle funktioner, du skal lægge mærke til:

1. Navnet på bogmærket vises på bogmærkets titellinje, der vises nederst på lærredet.
2. Bogmærkets titellinje har pile, som du kan bruge til at flytte til næste eller forrige bogmærke
3. Du kan afslutte tilstanden **Vis** ved at vælge **Afslut** i ruden **Bogmærker** eller ved at vælge krydset (**X**) i bogmærkets titellinje. 

![Funktioner på bogmærkers titellinje](media/desktop-bookmarks/bookmarks_07.png)

Når du er i tilstanden **Vis**, kan du lukke ruden **Bogmærker** (ved at klikke på krydset (X) i ruden) for at give mere plads til præsentationen. Og mens du er i tilstanden **Vis**, er alle visuelle elementer interaktive og tilgængelige for tværgående fremhævning, som når du interagerer med dem. 

## <a name="visibility---using-the-selection-pane"></a>Synlighed – med ruden Markering
Med udgivelsen af bogmærker introduceres den nye rude **Markering** også. Ruden **Markering** indeholder en liste over alle objekter på den aktuelle side, og du kan markere objektet og angive, om et bestemt objekt skal være synligt. 

![Aktivér ruden Markering](media/desktop-bookmarks/bookmarks_08.png)

Du kan vælge et objekt i ruden **Markering**. Du kan også vælge, om objektet i øjeblikket skal være synligt, ved at klikke på ikonet med øjet til højre for det visuelle element. 

![Ruden Markering](media/desktop-bookmarks/bookmarks_09.png)

Når der tilføjes et bogmærke, gemmes synlighedsstatus for de enkelte objekter på baggrund af indstillingen i ruden **Markering**. 

Det er vigtigt at bemærke, at **udsnitsværktøjer** fortsat filtrerer en rapportside, uanset om de er synlige. Du kan derfor oprette mange forskellige bogmærker med forskellige indstillinger for udsnitsværktøj og få en enkelt rapportside vist på forskellige måder (og fremhæve forskellig indsigt) i forskellige bogmærker.

## <a name="bookmarks-for-shapes-and-images"></a>Bogmærker for figurer og billeder
Du kan også knytte figurer og billeder til bogmærker. Når du bruger denne funktion, og du klikker på et objekt, vises det bogmærke, der er knyttet til objektet. 

Hvis du vil knytte et bogmærke til et objekt, skal du vælge **Link** i ruden **Formatér figur**, som vist på følgende billede.

![Tilføj et bogmærkelink til et objekt](media/desktop-bookmarks/bookmarks_10.png)

Når du slår skyderen **Link** **til**, kan du vælge, om objektet skal være et link eller et bogmærke. Hvis du vælger et bogmærke, kan du vælge, hvilket af dine bogmærker objektet skal knyttes til.

Du kan gøre mange forskellige interessante ting med bogmærker, der har tilknyttet et objekt. Du kan oprette en visuel tabel med indhold på din rapportside, eller du kan angive forskellige visninger (f.eks. visuelle typer) med de samme oplysninger ved bare at klikke på et objekt.

Når du er i redigeringstilstand, kan du bruge Ctrl + klik for at følge linket, og når du ikke er i redigeringstilstand, skal du bare klikke på objektet for at følge linket. 

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
Når du publicerer en rapport i **Power BI-tjenesten** med mindst ét bogmærke, kan du få vist og interagere med disse bogmærker i **Power BI-tjenesten**. For de enkelte rapporter, som du publicerer, skal du have mindst ét bogmærke, der er oprettet i rapporten, før du publicerer den, for at bogmærkefunktionen er tilgængelig i **Power BI-tjenesten**.

Når bogmærker er tilgængelige i en rapport, kan du vælge **Vis > ruden Markering** eller **Vis > ruden Bogmærker** for at få vist hver af disse ruder.

![Få vist bogmærker og markeringsruder i Power BI-tjenesten](media/desktop-bookmarks/bookmarks_14.png)

I **Power BI-tjenesten** fungerer **ruden Bogmærker** på samme måde som i **Power BI Desktop**, dvs. du har også mulighed for at vælge **Vis** for at få vist dine bogmærker i rækkefølge, f.eks. som et slideshow.

Bemærk, at du skal bruge titellinjen for det grå bogmærke til at navigere rundt i bogmærkerne og ikke de sorte pile (de sorte pile flytter dig gennem rapportsider, ikke bogmærker).

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
I denne foreløbige version af **bogmærker** er der et par begrænsninger og overvejelser, du skal være opmærksom på.

* Brugerdefinerede visuelle elementer fungerer ikke med bogmærker, hvis de er *kilden* til filteret. Hvis du bruger brugerdefinerede visuelle elementer til at filtrere elementer på en side (f.eks.firkantede udsnit) og vender tilbage til denne side ved hjælp af et bogmærke, er siden måske filtreret, men det brugerdefinerede visuelle element opdateres ikke for at vise, hvordan siden filtreres. 
* Den tværgående fremhævningstilstand for en rapportrude gemmes *ikke*, når du opretter et bogmærke. 
* Hvis du tilføjer et visuelt element på en rapportside, når du har oprettet et bogmærke, vises det visuelle element i standardtilstanden. Det betyder også, at hvis du vil indføre et udsnitsværktøj på en side, hvor du tidligere har oprettet bogmærker, optræder udsnittet i standardtilstanden.
* Hvis du flytter rundt på visuelle elementer, efter at der er oprettet et bogmærke, afspejles det i bogmærket. 
* Du *skal* have mindst ét bogmærke i rapporten, når du publicerer den i **Power BI-tjenesten**, hvis bogmærker skal være tilgængelige i tjenesten. Det er et krav for alle de rapporter, du publicerer.
* Fordi bogmærker i øjeblikket er en funktion i forhåndvisning, er de endnu ikke tilgængelige i [**Power BI Desktop til rapportserveren**](report-server/quickstart-create-powerbi-report.md).

## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om de funktioner, der ligner eller interagerer med bogmærker, i følgende artikler:

* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)
* [Vis et dashboardfelt eller en rapport i fokustilstand](service-focus-mode.md)

