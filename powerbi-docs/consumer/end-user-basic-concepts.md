---
title: Power BI-tjenesten – grundlæggende begreber for forbrugere
description: apps til Power BI-tjenesten, arbejdsområde, dashboards, rapporter, datasæt og projektmapper.
author: mihart
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.custom: seodec18
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/16/2019
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 7513479d14b57e47b30d2cd7ac9cc4acfe69d075
ms.sourcegitcommit: 17aad73762579d6822383b27b96b1b63f87f2d6f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/14/2020
ms.locfileid: "77260111"
---
# <a name="basic-concepts-for-the-power-bi-service-consumers"></a>Grundlæggende begreber for forbrugere af Power BI-tjenesten

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Denne artikel forudsætter, at du allerede har læst [Oversigt over Power BI](../fundamentals/power-bi-overview.md) og har identificeret dig selv som [Power BI- **_forbruger_** ](end-user-consumer.md). Forbrugere modtager Power BI-indhold, f.eks. dashboards og rapporter, fra kolleger. Forbrugere bruger Power BI-tjenesten, som er den webstedsbaserede version af Power BI.

Du vil uden tvivl høre begrebet "Power BI Desktop" eller bare "Desktop". Det er det enkeltstående værktøj, der bruges af *designere*, som bygger og deler dashboards og rapporter med dig. Det er vigtigt at vide, at der findes andre Power BI-værktøjer. Så længe du er forbruger, skal du kun arbejde med Power BI-tjenesten. Denne artikel drejer sig kun om Power BI-tjenesten.

## <a name="terminology-and-concepts"></a>Terminologi og begreber

Denne artikel er ikke en visuel gennemgang af Power BI, og den er heller ikke et praktisk selvstudium. Artiklen byder i stedet på en oversigt, som hjælper dig med at blive fortrolig med Power BI-terminologien og -begreberne. Du lærer sproget og karakteristikaene at kende. Du kan få en præsentation af Power BI-tjenesten, og hvordan du navigerer i den, i [Hurtig start – Navigation i Power BI-tjenesten](end-user-experience.md).

## <a name="open-the-power-bi-service-for-the-first-time"></a>Åbn Power BI-tjenesten første gang

De fleste Power BI-forbrugere får Power BI-tjenesten, fordi 1) deres virksomhed køber licenser, og 2) en administrator tildeler disse licenser til medarbejdere som dig.

Du kommer i gang ved at åbne en browser og skrive **app.powerbi.com**. Første gang, du åbner Power BI-tjenesten, vil du se noget i stil med følgende:

![Et skærmbillede af velkomstskærmen for Power BI-tjenesten.](media/end-user-basic-concepts/power-bi-home.png)

I takt med at du bruger Power BI, kan du tilpasse det, du ser, når du åbner webstedet. Nogle personer foretrækker for eksempel, at Power BI åbner med **startsiden**, mens andre har et favoritdashboard, de vil have vist først. Bare rolig, i denne artikel viser vi dig, hvordan du tilpasser din oplevelse.

- [Introduktion til Power BI Start og global søgning](https://powerbi.microsoft.com/blog/introducing-power-bi-home-and-global-search)

- [Udvalgte dashboards i Power BI-tjenesten](end-user-featured.md)

![Et skærmbillede, der viser startsiden og dashboardvisningen.](media/end-user-basic-concepts/power-bi-first.png)

Før vi fortsætter, skal vi lige vende tilbage og tale om de byggesten, der udgør Power BI-tjenesten.

_______________________________________________________

## <a name="power-bi-content"></a>Power BI-indhold

### <a name="introduction-to-building-blocks"></a>Introduktion til byggestenene

For Power BI-forbrugere er de fem byggesten: **_visualiseringer_** , **_dashboards_** , **_rapporter_** , **_apps_** og **_datasæt_** . Disse omtales nogle gange som *Power BI*- **_indhold_** *Indhold* findes i **_arbejdsområder_** . En typisk arbejdsproces omfatter alle byggestenene: En Power BI-*designer* (gul i nedenstående diagram) indsamler data fra *datasæt*, overfører dem til Power BI med henblik på analyse, opretter *rapporter* med mange *visualiseringer*, der fremhæver interessante fakta og indsigt, fastgør visualiseringerne fra rapporter til et dashboard og deler rapporter og dashboards med *forbrugere* som dig (sort i nedenstående diagram). *Designeren* deler dem i form af *apps* eller andre former for delt indhold.

![Et diagram over en grundlæggende Power BI-arbejdsproces.](media/end-user-basic-concepts/power-bi-workflow.png)

Kort fortalt:

- ![Et skærmbillede af visualiseringsikonet.](media/end-user-basic-concepts/visual.png) en **_visualisering_** (eller *visual*) er en form for diagram, der er bygget af Power BI-*designere*. I visualiseringerne vises dataene fra *rapporter* og *datasæt*. *Designere* udarbejder typisk visualiseringerne i Power BI Desktop.

    Du kan finde flere oplysninger i [Interager med visualiseringer i rapporter, på dashboards og i programmer](end-user-visualizations.md).

- ![Et skærmbillede af databaseikonet.](media/end-user-basic-concepts/power-bi-dataset-icon.png) Et *datasæt* er en objektbeholder for data. Det kan f.eks. være en Excel-fil fra Verdenssundhedsorganisationen. Det kan også være en virksomhedsejet database over kunder, eller det kan være en Salesforce-fil.  

- ![Et skærmbillede af dashboardikonet.](media/end-user-basic-concepts/dashboard.png) Et *dashboard* er en enkelt skærm med interaktive visualiseringer, tekst og grafik. På et dashboard samles dine vigtigste metrikværdier på én skærm for at fortælle en historie eller svare på spørgsmål. Dashboardindholdet stammer fra en eller flere rapporter og et eller flere datasæt.

    Du kan finde flere oplysninger i [Dashboards til forbrugere af Power BI-tjenesten](end-user-dashboards.md).

- ![Et skærmbillede af rapportikonet.](media/end-user-basic-concepts/report.png) En *rapport* er en eller flere sider med interaktive visualiseringer, tekst og grafik, der tilsammen udgør en enkelt rapport. Power BI baserer en rapport på et enkelt datasæt. Tjenesten organiserer ofte rapporter, så de behandler et enkelt interesseområde eller besvarer et enkelt spørgsmål.

    Du kan finde flere oplysninger i [Rapporter i Power BI](end-user-reports.md).

- ![Et skærmbillede af appikonet.](media/end-user-basic-concepts/app.png) *Designere* kan bruge en *app* til at samle og dele relaterede dashboards og rapporter samlet. *Forbrugere* modtager nogle apps automatisk, men kan søge efter andre apps, der er oprettet af kollegaer eller af community'et. Nogle eksterne tjenester, som du allerede bruger, såsom Google Analytics og Microsoft Dynamics CRM, tilbyder f.eks. Power BI-apps.

For at gøre det helt klart: Hvis du er ny bruger, og det er første gang, du logger på Power BI, kan du ikke se dashboards, apps eller rapporter.

_______________________________________________________

## <a name="datasets"></a>Datasæt

Et *datasæt* er en samling af data, som *designere* importerer eller opretter forbindelse til og derefter bruger til at oprette rapporter og dashboards. Som forbruger interagerer du ikke direkte med datasæt, men det er stadig rart at forstå, hvordan de passer ind i den større sammenhæng.  

Hvert datasæt repræsenterer en enkelt datakilde. Kilden kunne f.eks. være en Excel-projektmappe på OneDrive, et lokal SQL Server Analysis Services-datasæt i tabelformat eller et Salesforce-datasæt. Power BI understøtter mange forskellige datakilder.

Når en designer deler en app med dig, kan du se, hvilke datasæt designeren har inkluderet i appen.

![Skærmbillede af Power BI-brugergrænsefladen og en pil, der peger på sektionen Datasæt på lærredet.](media/end-user-basic-concepts/power-bi-dataset-lists.png)

Ét datasæt ...

- Kan bruges igen og igen af en rapportdesigner til at oprette dashboards og rapporter

- Kan bruges til at oprette forskellige rapporter

- Visualiseringer fra dette ene datasæt kan vises på mange forskellige dashboards

  ![En grafik, der viser et datasæt med mange til en-relationer](media/end-user-basic-concepts/drawing2.png)

Videre til næste byggesten: visualiseringer.

_______________________________________________________

## <a name="visualizations"></a>Visualiseringer

Visualiseringer (også kaldet visuals) viser indsigter, som Power BI har registreret i dataene. Visualiseringer gør det nemmere at fortolke indsigt, da du opfatter et billede hurtigere end et regneark fuld af tal.

Her er blot nogle af de visualiseringer, du kan støde på i Power BI: vandfald, bånd, træstruktur, cirkel, tragtformet, kort, punkt og måler:

   ![Et skærmbillede af otte eksempler på visualiseringer.](media/end-user-basic-concepts/power-bi-visuals.png)

Se den [fulde liste over visualiseringer, der er inkluderet i Power BI](../power-bi-visualization-types-for-reports-and-q-and-a.md).

Visualiseringer, der kaldes *brugerdefinerede visualiseringer*, er også tilgængelige fra community'et. Hvis du modtager en rapport med en visualisering, du ikke genkender, er det sandsynligvis en brugerdefineret visualisering. Hvis du har brug for hjælp til at forstå den brugerdefinerede visualisering, kan du slå navnet på *designeren* af rapporten eller dashboardet op og kontakte vedkommende.

Én visualisering i en rapport...

- Kan vises flere gange i den samme rapport

- Kan vises i mange forskellige dashboards

_______________________________________________________

## <a name="reports"></a>Rapporter

En Power BI-rapport er en eller flere sider med visualiseringer, grafik og tekst. Alle visualiseringerne i en rapport stammer fra et enkelt datasæt. *Designere* deler rapporter med *forbrugere*, som [interagerer med rapporterne i *Læsevisning*](end-user-reading-view.md).

![Skærmbillede af en rapport med faner.](media/end-user-basic-concepts/power-bi-report.png)

Én rapport...

- Kan være knyttet til flere dashboards (felter, der er fastgjort fra den ene rapport kan vises på flere dashboards).

- Kan oprettes ved hjælp af data fra kun ét datasæt.  

- Kan være en del af flere apps.

  ![Grafik, der viser relationer for en rapport.](media/end-user-basic-concepts/drawing5.png)

_______________________________________________________

## <a name="dashboards"></a>Dashboards

Et dashboard repræsenterer en brugerdefineret visning af nogle undersæt af de underliggende datasæt. *Designere* udarbejder dashboards og deler dem med *forbrugere* – enten enkeltvist eller som en del af en app. Et dashboard er et enkelt lærred, der indeholder *felter*, grafik og tekst.

  ![Skærmbillede af et eksempel på et dashboard](media/end-user-basic-concepts/power-bi-dashboard.png)

Et felt er en gengivelse af en visualisering, som en *designer* *fastgør* f.eks. fra en rapport til et dashboard. Hvert fastgjorte felt viser en [visualisering](end-user-visualizations.md), som en designer har oprettet ud fra et datasæt og fastgjort til det pågældende dashboard. Et felt kan også indeholde en hel rapportside og data til livestreaming eller en video. *Designere* kan føje felter til dashboards på mange måder. Der er for mange måder, til at vi kan dække dem i denne oversigtsartikel. Du kan få mere at vide i [Dashboard-felter i Power BI](end-user-tiles.md).

Forbrugere kan ikke redigere dashboards. En forbruger kan derimod tilføje kommentarer, få vist relaterede data, angive det som favorit, abonnere og meget mere.

Hvad er nogle formål med dashboards?  Her er nogle få:

- at få et hurtigt overblik over alle de oplysninger, der er nødvendige for at træffe beslutninger

- at overvåge de vigtigste oplysninger om virksomheden

- at sikre, at alle kolleger er opdateret og får vist og bruger de samme oplysninger

- at overvåge tilstanden for et produkt eller en virksomhed, en afdeling eller marketingkampagne osv.

- for at oprette en tilpasset visning af et større dashboard – alle de målepunkter, der betyder noget for dig

**ÉT** dashboard...

- kan vise visualiseringer fra mange forskellige datasæt

- kan vise visualiseringer fra mange forskellige rapporter

- kan vise visualiseringer, der er fastgjort fra andre funktioner (f.eks. Excel)

  ![Et billede af relationer for et dashboard.](media/end-user-basic-concepts/drawing1.png)

_______________________________________________________

## <a name="apps"></a>Apps

Disse samlinger af dashboards og rapporter organiserer relateret indhold sammen i en enkelt pakke. Power BI-*designere* udarbejder dem og deler dem med enkeltpersoner, grupper, en hel organisation eller offentligheden. Som forbruger kan du være sikker på, at du og dine kolleger arbejder med de samme data – én version, der fungerer som fælles udgangspunkt.

![Skærmbillede af apps, der er valgt i ruden til venstre i Power BI.](media/end-user-basic-concepts/power-bi-apps.png)

Det er nemt at finde og installere apps i [Power BI-tjenesten](https://powerbi.com) og på din mobilenhed. Når du har installeret en app, behøver du ikke at huske navnene på mange forskellige dashboards. De er alle samlet i én app, i din browser eller på din mobilenhed.

Denne app har tre relaterede dashboards og tre relaterede rapporter, der udgør en enkelt app.

![Skærmbillede af relateret indhold for den valgte app.](media/end-user-basic-concepts/power-bi-app-list.png)

Med apps ser du automatisk ændringerne, hver gang appens forfatteren udgiver opdateringer. Forfatteren styrer også tidsplanen for, hvor ofte dataene opdateres i Power BI. Du behøver ikke tænke på at holde dem opdateret.

Du kan hente apps på forskellige måder:

- Appdesigneren kan installere appen automatisk på din Power BI-konto.

- Appdesigneren kan sende dig et direkte link til en app.

- Du kan søge efter den i [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi), hvor du kan se alle de apps, du kan bruge.

I Power BI på din mobilenhed kan du kun installere apps fra et direkte link og ikke fra AppSource. Hvis appdesigneren installerer appen automatisk, kan du se den på din liste over apps.

Når du har installeret appen, skal du blot vælge den på listen over apps og vælge, hvilket dashboard eller hvilken rapport du vil åbne og udforske først.

Jeg håber, at denne artikel har givet dig en forståelse for de byggesten, der udgør Power BI-tjenesten for forbrugere.

## <a name="next-steps"></a>De næste trin

- Gennemse og angiv bogmærke for [ordlisten](end-user-glossary.md)

- Få en [præsentation af Power BI-tjenesten](end-user-experience.md)

- Læs [oversigten over Power BI, der er skrevet specielt til forbrugere](end-user-consumer.md)

- Se en video, hvor Will gennemgår de grundlæggende begreber og præsenterer Power BI-tjenesten.

    <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
