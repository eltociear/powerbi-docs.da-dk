---
title: "Power BI – grundlæggende begreber"
description: "Power BI – grundlæggende begreber"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/31/2017
ms.author: mihart
ms.openlocfilehash: f20ea18fb46928bf7533caacf55a0cdb3d761571
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi---basic-concepts-for-power-bi-service"></a>Power BI – grundlæggende begreber for Power BI-tjenesten
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

Denne artikel forudsætter, at du har allerede har [tilmeldt dig Power BI](service-self-service-signup-for-power-bi.md) og [tilføjet nogle data](service-get-data.md).

Når du åbner Power BI-tjenesten, får du vist et ***dashboard***. Dashboards er noget, der adskiller Power BI-tjenesten fra Power BI Desktop.

![](media/service-basic-concepts/completenewer.png)

De vigtigste funktioner i Power BI-tjenestens brugergrænsefladen er følgende:

1. navigationslinje
2. dashboard med felter
3. Boks med spørgsmål og svar
4. knapperne hjælp og feedback
5. dashboardets titel
6. Office 365-appstarter
7. Power BI-startknapper
8. Flere handlinger på dashboardet

Vi vil gå i dybden med dette senere, men lad os først se på nogle Power BI-begreber.

Du kan også vælge at se denne video, før du læser resten af denne artikel.  I videoen gennemgår Will de grundlæggende begreber og giver en præsentation af Power BI-tjenesten.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>


## <a name="power-bi-concepts"></a>Power BI-begreber
De tre overordnede elementer i Power BI er: ***dashboards***, ***rapporter*** og ***datasæt***. Du kan ikke have dashboards og rapporter uden data (det vil sige, du kan have tomme dashboards og tomme rapporter, men de er ikke til meget nytte, før de har data), så lad os starte med **datasæt**.

## <a name="datasets"></a>Datasæt
Et *datasæt* er en samling af data, som du *importerer* eller *opretter forbindelse* til. Med Power BI kan du oprette forbindelse til og importere alle mulige forskellige datasæt og samle dem alle sammen på ét sted.  

I navigationslinjen er de datasæt, du har oprettet forbindelse til eller importeret, angivet under overskriften **Datasæt**. Hvert angivet datasæt repræsenterer en enkelt datakilde, f.eks. en Excel-projektmappe på OneDrive, et lokalt SSAS-tabeldatasæt eller et Salesforce-datasæt. Der er mange forskellige understøttede datakilder, og vi tilføjer hele tiden nye. [Se listen over typer af datasæt, der kan bruges med Power BI](service-get-data.md).

**ÉT** datasæt...

* kan bruges igen og igen.
* kan bruges i mange forskellige rapporter.
* Visualiseringer fra dette ene datasæt kan vises på mange forskellige dashboards.
  
  ![](media/service-basic-concepts/drawing2.png)

Hvis du vil [oprette forbindelse til eller importere et datasæt](service-get-data.md), skal du vælge **Hent Data** (nederst i navigationslinjen) eller vælge plusikonet ud for overskriften **Datasæt**. Følg vejledningen for at oprette forbindelse til eller importere den specifikke kilde og føje datasættet til arbejdsområdet. Nye datasæt er angivet i venstre navigationslinje og markeret med en gul stjerne. Det arbejde, du udfører i Power Bi, ændrer ikke det underliggende datasæt.

Hvis du er [en del af et ***apparbejdsområde***](service-collaborate-power-bi-workspace.md), er datasæt, der er tilføjet af et medlem af arbejdsområdet, tilgængelige for de andre medlemmer af arbejdsområdet.

Datasæt kan opdateres, omdøbes, udforskes, bruges til at oprette rapporter og fjernes. Vælg et datasæt for at udforske det. Det, du rent faktisk gør, er at åbne datasættet i rapporteditoren, hvor du virkelig kan starte med at udforske dataene og oprette visualiseringer. Så lad os gå videre til næste emne: rapporter.

### <a name="dig-deeper"></a>Grav dybere:
* [Power BI Premium – hvad er det?](service-premium.md)
* [Hent data til Power BI](service-get-data.md)
* [Se eksempler på datasæt og indholdspakker til Power BI](sample-datasets.md)

## <a name="reports"></a>Rapporter
En Power BI-rapport er en eller flere sider med visualiseringer (diagrammer og grafer, f.eks. kurvediagrammer, cirkeldiagrammer, træstrukturdiagrammer og mange, mange flere). Visualiseringer kaldes også ***visuelle elementer***. Alle visualiseringerne i en rapport stammer fra et enkelt datasæt. Rapporter kan oprettes fra bunden i Power BI, kan importeres med dashboards, som kollegaer deler med dig, eller kan oprettes, når du opretter forbindelse til datasæt fra Excel, Power BI Desktop, databaser, SaaS-programmer og [indholdspakker](service-organizational-content-pack-introduction.md).  Når du f.eks. opretter forbindelse til en Excel-projektmappe, der indeholder Power View-ark, opretter Power BI en rapport, der er baseret på de ark. Og når du opretter forbindelse til et SaaS-program, importerer Power BI en færdigbygget rapport.

Der er to forskellige tilstande, som du kan se og interagere med rapporter i: [Læsevisning](service-report-open-in-reading-view.md) og [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md).  Kun forfatteren af rapporten, medejerne og dem, der har tilladelse, har adgang til alle den udforskning, udformning, oprettelse og delingsfunktionen i ***Redigeringsvisning*** for denne rapport. Og de personer, de deler rapporten med, kan udforske og interagere med rapport ved hjælp af ***Læsevisning***.   

I navigationsruden er dine rapporter angivet under overskriften **Rapporter**. Hver nævnte rapport repræsenterer én eller flere siders visualiseringer baseret på én af de underliggende datasæt. Hvis du vil åbne en rapport, skal du blot markere den. Som standard åbnes rapporten først i Læsevisning.  Du skal blot vælge **Rediger rapporten** for at åbne den i Redigeringsvisning (hvis du har de nødvendige tilladelser).  Hvis et delt dashboard indeholder rapporter, kan du IKKE se rapporten angivet i navigationslinjen. I stedet skal du åbne delte rapporter direkte fra det delte dashboard ved at vælge et dashboardfelt (mere om dette senere).

**ÉN** rapport...

* kan være knyttet til flere dashboards (felter, der er fastgjort fra den ene rapport kan vises på flere dashboards).
* kan oprettes ved brug af data fra et datasæt. (en lille undtagelse til dette er, at Power BI Desktop kan kombinere mere end et datasæt til en enkelt rapport, og at rapporten kan importeres til Power BI)
  
  ![](media/service-basic-concepts/drawing3new.png)

## <a name="dashboards"></a>Dashboards
Et *dashboard* er noget, du opretter, eller noget, en kollega opretter og deler med dig. Det er et enkelt lærred, der indeholder ingen eller flere felter og widgets. Hvert felt viser en enkelt [visualisering](power-bi-report-visualizations.md), der blev oprettet fra et datasæt og fastgjort til dashboardet. Der er mange forskellige måder at føje felter til dit dashboard; for mange til at dække i dette oversigtsemne. Du kan få mere at vide i [Dashboard-felter i Power BI](service-dashboard-tiles.md). 

I navigationslinjen er "dine" dashboards angivet under overskriften **Dashboards**. "Dine" betyder, at du har adgang til dem, men ikke nødvendigvis at du har oprettet dem. Hvert enkelt dashboard repræsenterer en brugerdefineret visning af nogle undersæt af de underliggende datasæt.  Hvis du ejer dashboardet, har du også adgang til den/de underliggende datasæt, og de vises i navigationslinjen under **Datasæt**.  Hvis dashboardet er delt med dig, har det et delingsikon ![](media/service-basic-concepts/sharing-icon.png) ud for det, og afhængigt af hvordan det blev delt, kan du muligvis se de underliggende datasæt, der er angivet i din navigationslinje.

> [!NOTE]
> Fastgørelse og felter dækkes mere detaljeret nedenfor under overskriften "Dashboard med felter".
> 
> 

**ÉT** dashboard...

* kan vise visualiseringer fra mange forskellige datasæt
* kan vise visualiseringer fra mange forskellige rapporter
* kan vise visualiseringer, der er fastgjort fra andre funktioner (f.eks. Excel)
  
  ![](media/service-basic-concepts/drawing1.png)

### <a name="dig-deeper"></a>Grav dybere:
**Et dashboard kan være [oprettet fra bunden](service-dashboard-create.md)** – opret et nyt, tomt dashboard, og hent derefter nogle data. 

**Du eller en kollega kan oprette et dashboard og [dele det](service-share-dashboards.md)**. Når du accepterer invitationen, føjes det delte dashboard (og eventuelle tilknyttede rapport og datasæt) til din navigationslinje. Power BI Pro er påkrævet både for at dele et dashboard og få vist et delt dashboard.

**Nogle gange importeres dashboards med datasættet eller oprettes, når du opretter forbindelse til datasættet**. Guiden **Hent Data** til Salesforce spørger f.eks., om du ønsker, at et dashboard og/eller en rapport skal oprettes fra datasættet. 

**Hvorfor opretter personer dashboards?**  Her er blot nogle af årsagerne:

* for hurtigt at se alle de oplysninger, der er nødvendige for at træffe beslutninger
* for at overvåge de vigtigste oplysninger om virksomheden
* for at sikre, at alle kollegaer er på samme side og får vist og bruger de samme oplysninger
* for at overvåge tilstanden for et produkt eller en virksomhed, en afdeling eller marketingkampagne osv.
* for at oprette en tilpasset visning af et større dashboard – alle de målepunkter, der betyder noget for mig

## <a name="my-workspace"></a>Mit arbejdsområde
Vi er nu tilbage til dit Power BI-dashboard og arbejdsområde. Lad os se nærmere på de enheder, der udgør landingssiden til Power BI-tjenesten.

![](media/service-basic-concepts/completenewer.png)

### <a name="1-navigation-bar-navbar"></a>1. **Navigationslinje**
Brug navigationslinjen til at flytte mellem Power BI-komponenterne: dashboards, rapporter og datasæt.  

  ![](media/service-basic-concepts/navpane-new.png)

* Vælg **Hent Data** for at [føje datasæt, rapporter og dashboards til Power BI](service-get-data.md).
* Udvid og skjul navigationslinjen med dette ikon ![](media/service-basic-concepts/expand-icon.png).
* Brug **Søg** til at finde bestemte elementer i navigationslinjen.
* Vælg et plus-ikon ![](media/service-basic-concepts/pbi_nancy_plus.png) for at oprette et nyt dashboard eller hente et nyt datasæt.
* De angivne **Dashboards, Rapporter** og **Datasæt** er tilgængelige for dig at bruge.  Delte dashboards er skrivebeskyttede og viser det delte ikon ![](media/service-basic-concepts/sharing-icon.png) .
* Navnene på dashboards, rapporter og datasæt matcher normalt navnet på den underliggende datasætfil, men du kan [omdøbe dem](service-rename.md).
* Højreklik på et dashboard, en rapport eller et datasæt for at få vist den kontekstafhængige menu. 
  
  ![](media/service-basic-concepts/menu.png)

Klik én gang

* på en overskrift for at skjule eller udvide den
* på et dashboard for at få det vist
* på en rapport for at åbne den i Læsevisning
* på et datasæt for at udforske det

### <a name="2-dashboard-with-tiles"></a>2. **Dashboard med felter**
Dashboards består af [felter](service-dashboard-tiles.md).  Felter oprettes i rapportens Redigeringsvisning, Spørgsmål og svar, andre dashboards og kan fastgøres fra Excel, SSRS og meget mere. En særlig type felt kaldet en [widget](service-dashboard-add-widget.md) føjes direkte til dashboardet. De felter, der vises på et dashboard, blev specifikt sat der af en rapportforfatter/-ejer.  Dét at føje et felt til et dashboard kaldes *fastgørelse*.

![](media/service-basic-concepts/canvas.png)

Du kan få mere at vide om dette i **Dashboards** (ovenfor).

### <a name="3-qa-question-box"></a>3. **Boks med spørgsmål og svar**
Én måde at udforske dine data er at stille et spørgsmål og lade Power BIs Spørgsmål og svar give dig et svar i form af en visualisering. Spørgsmål og svar kan ikke bruges til at føje indhold til en rapport, kun til at føje indhold, i form af felter, til dashboards.

Spørgsmål og svar søger efter et svar i den/de datasæt, der har forbindelse til dashboardet.  Et forbundet datasæt er et datasæt, der har mindst ét felt, der er fastgjort til dette dashboard.

![](media/service-basic-concepts/qna.png)

Så snart du begynder at skrive dit spørgsmål, fører Spørgsmål og svar dig til siden Spørgsmål og svar. Mens du skriver, hjælper Spørgsmål og svar dig med at stille det rette spørgsmål og finde det bedste svar med omformuleringer, autofyld, forslag og meget mere. Når du har en visualisering (svar), som du synes om, kan du fastgøre den til dashboardet. Du kan få mere at vide i [Spørgsmål og svar i Power BI](service-q-and-a.md).

### <a name="4-full-screen-notifications-settings-downloads-help-and-feedback"></a>4. **Fuld skærm, Beskeder, Indstillinger, Downloads, Hjælp og feedback**
Ikonerne øverst til højre er dine ressourcer til indstillinger, beskeder, downloads, at få hjælp og give feedback til Power BI-teamet. Vælg den dobbelte pil for at åbne dashboardet i **fuldskærmsvisning**.  

![](media/service-basic-concepts/help-new.png)

### <a name="5-dashboard-title-aka-what-dashboard-is-active"></a>5. **Dashboardets titel** (dvs. Hvilket dashboard er aktivt?)
Det er ikke altid nemt at finde ud af, hvilket dashboard er aktivt.  Dashboardets titel vises på dashboardets visningsside, på siden Spørgsmål og svar, i rapportens Redigeringsvisning og rapportens Læsevisning, og når du åbner et datasæt.   

![](media/service-basic-concepts/dash-title-new.png)

### <a name="6-office-365-app-launcher"></a>6. **Office 365-appstarter**
Appstarteren er udviklet til at hjælpe dig med at få adgang til dine Office 365-apps.

![](media/service-basic-concepts/basicconcepts2-newer.png)

### <a name="7-power-bi-home"></a>7. **Power BI-startside**
Hvis du vælger dette, vender du tilbage til det dashboard, du senest har fået vist.

   ![](media/service-basic-concepts/version-new.png)

### <a name="8-options"></a>8. **Indstillinger**
Dette område af arbejdsområdet indeholder ikoner for interaktion med dashboardet.  Ud over **Tilføj felt**, **Gør til favorit** og **Del** vises der indstillinger til at kopiere, udskrive og opdatere dashboardet og meget mere, når du vælger ellipsen.

   ![](media/service-basic-concepts/options.png)

## <a name="next-steps"></a>Næste trin
[kom i gang med Power BI](service-get-started.md)  
[Power BI-videoer](videos.md)  
[Power BI Premium – hvad er det?](service-premium.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

