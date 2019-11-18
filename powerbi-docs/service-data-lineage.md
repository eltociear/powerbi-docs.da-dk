---
title: Dataafstamning (prøveversion)
description: I moderne BI-projekter (Business Intelligence) er det en vigtig udfordring for mange kunder at forstå flowet af data fra datakilden til destinationen.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: painbar
LocalizationGroup: ''
ms.openlocfilehash: 774b8b19f8b199e1d98b2bd5e079b35f1a9a6935
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877358"
---
# <a name="data-lineage-preview"></a>Dataafstamning (prøveversion)
I moderne BI-projekter (Business Intelligence) kan det være en udfordring for mange kunder at forstå flowet af data fra datakilden til destinationen. Udfordringen er endnu større, hvis du har oprettet avancerede analyseprojekter, der strækker sig over flere datakilder, artefakter og afhængigheder.  Spørgsmål som "Hvad sker der, hvis jeg ændrer disse data?" eller "Hvorfor er denne rapport ikke ajourført?" kan være vanskelige at besvare. Det kan være nødvendigt med et team af eksperter eller en grundig undersøgelse for at forstå dem. Vi har designet dataafstamningsvisningen for at hjælpe dig med at besvare disse spørgsmål.

[ ![Afstamningsvisning i Power BI](media/service-data-lineage/power-bi-lineage-view-cropped.png) ](media/service-data-lineage/power-bi-lineage-view-full-size.png#lightbox)
 
Power BI har flere artefakttyper, f.eks. dashboards, rapporter, datasæt og dataflows. Mange datasæt og dataflows har forbindelse til eksterne datakilder, f.eks. SQL Server, og til eksterne datasæt i andre arbejdsområder. Når et datasæt er eksternt for et arbejdsområde, som du ejer, kan det være i et arbejdsområde, der ejes af en person i it-afdelingen eller en anden analytiker. Eksterne datakilder og datasæt gør det i sidste ende svært at vide, hvor dataene kommer fra. I forbindelse med mere eller mindre komplekse projekter introducerer vi afstamningsvisningen. 

I afstamningsvisningen kan du få vist afstamningsrelationer mellem alle artefakterne i et arbejdsområde og alle dens eksterne afhængigheder. Dataflows har allerede en diagramvisning, og afstamningsvisningen udvider denne visning. Den viser forbindelser mellem alle arbejdsområdeartefakter, herunder forbindelser til dataflows, både upstream og downstream. Den særskilte diagramvisning i dataflows forsvinder i starten af november.

## <a name="explore-lineage-view"></a>Udforsk afstamningsvisningen

Hvert arbejdsområde, uanset om det er nyt eller klassisk, har automatisk en afstamningsvisning, undtagen Mit arbejdsområde. Du skal mindst have rollen som bidragyder i arbejdsområdet for at kunne få vist visningen. Se [Tilladelser](#permissions) i denne artikel for at få flere oplysninger. 

- Du åbner afstamningsvisning ved at gå til listevisningen i arbejdsområdet. Tryk på pilen ud for **Listevisning**, og vælg **Afstamningsvisning**.

    [ ![Skift til afstamningsvisning](media/service-data-lineage/power-bi-lineage-list-view-cropped.png) ](media/service-data-lineage/power-bi-lineage-list-view.png#lightbox)

    I denne visning kan du se alle arbejdsområdeartefakter, og hvordan dataene flyder fra artefakt til artefakt.

**Datakilder**

Du får vist de datakilder, som datasæt og dataflows henter deres data fra. På datakildekortene får du vist flere oplysninger, der kan hjælpe med at identificere kilden. For Azure SQL Server får du f.eks. også vist navnet på databasen.

![Afstamningsvisning i en datakilde uden en gateway](media/service-data-lineage/power-bi-lineage-data-source-no-gateway.png)
 
**Gateways**

Hvis en datakilde har forbindelse via en gateway i det lokale miljø, føjes gatewayoplysningerne til datakildekortet. Hvis du har tilladelser som enten gatewayadministrator eller som datakildebruger, får du vist flere oplysninger, f.eks. gatewaynavnet.

![Afstamningsvisning i en datakilde med en gateway](media/service-data-lineage/power-bi-lineage-data-source-with-gateway.png)

**Datasæt og dataflows**
 
I datasæt får du vist tidspunktet for den seneste opdatering, og om et datasæt er certificeret eller fremhævet.

![Certificeret datasæt i afstamningsvisning](media/service-data-lineage/power-bi-lineage-external-certified-dataset.png)
 
Hvis en rapport i arbejdsområdet er baseret på et datasæt i et andet arbejdsområde, får du vist navnet på kildearbejdsområdet på datasætkortet. Vælg navnet på kildearbejdsområdet for at gå til det pågældende arbejdsområde.
 
- For en hvilken som helst artefakt skal du vælge **Flere indstillinger** (...) for at få vist menuen med indstillinger. Den indeholder alle de samme handlinger, der er tilgængelige i listevisningen.
  
Hvis du vil have vist flere metadata om datasæt, skal du vælge selve datsætkortet. Der vises flere oplysninger om datasættet i en siderude.

![Siderude med flere oplysninger](media/service-data-lineage/power-bi-lineage-side-pane.png)
 
## <a name="show-lineage-for-any-artifact"></a>Vis afstamning for alle artefakter 

Lad os sige, at du vil have vist afstamningen for en bestemt artefakt.

- Vælg dobbeltpilene under en artefakt.

    [ ![Fremhæv afstamning for en bestemt artefakt](media/service-data-lineage/power-bi-lineage-highlight-cropped.png) ](media/service-data-lineage/power-bi-lineage-highlight-full-size.png#lightbox)

    Power BI fremhæver alle de artefakter, der er relateret til denne artefakt, og nedtoner resten. 

## <a name="navigation-and-full-screen"></a>Navigation og fuld skærm 

Afstamningsvisning er et interaktivt lærred. Du kan bruge musen og touchpad'en til at navigere på lærredet og zoome ind eller ud.  

- Hvis du vil zoome ind og ud, skal du enten bruge menuen i det nederste højre hjørne eller din mus eller touchpad. 

- Hvis du vil have mere plads til selve grafen, skal du bruge indstillingen til fuld skærm i nederste højre hjørne. 

    ![Zoom ind eller ud eller fuld skærm](media/service-data-lineage/power-bi-lineage-zoom-full-screen.png)

## <a name="permissions"></a>Tilladelser

- Du skal have en Power BI Pro-licens for at få vist afstamningsvisningen.
- Afstamningsvisningen er kun tilgængelig for brugere med adgang til arbejdsområdet.
- Brugerne skal have rollen som administrator, medlem eller bidragyder i arbejdsområdet. Brugere med læseadgang kan ikke skifte til afstamningsvisning.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

- Afstamningsvisning er ikke tilgængelig i Internet Explorer. Se [Understøttede browsere til Power BI](power-bi-browsers.md) for at få mere at vide.
- Afstamningsvisning er ikke tilgængelig i Mit arbejdsområde.

## <a name="next-steps"></a>Næste trin

- [Introduktion til datasæt på tværs af arbejdsområder (prøveversion)](service-datasets-across-workspaces.md)
