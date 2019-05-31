---
title: Brug detaljeadgang på tværs af-rapport i Power BI Desktop
description: Lær, hvordan du få detaljeadgang fra én rapport til en anden i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 45a7cdd3c7b5324f3d618eaba4bdb3968a9549a5
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375205"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Brug detaljeadgang på tværs af-rapport i Power BI Desktop

Med funktionen detaljeadgang på tværs af-rapport i Power BI Desktop, kan du konteksten gå fra en rapport til en anden rapport. Dette er tilfældet, så længe rapporterne, der er i det samme arbejdsområde eller app i Microsoft Power BI-tjenesten. Brug detaljeadgang på tværs af-rapport til at oprette forbindelse til to eller flere rapporter, der har relateret indhold og overføre filterkonteksten sammen med rapporten – på tværs af forbindelsen. I denne artikel kan lære du, hvordan du konfigurerer en rapport på tværs af detaljeadgang til Power BI-rapporter, og hvad brugerne oplever, når de bruger på tværs af-rapport detaljeadgang til sig selv.

![Skærmbillede af Power BI Desktop detaljeadgang indstilling](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Følgende definitioner, der er vigtigt at forstå, før vi begynder at konfigurere og bruge på tværs af rapport detaljeadgang:

* **Visuel kilde:** Det visuelle element, som aktiverer drillthrough-handling ved hjælp af menuen visuel kontekst.
* **Kilderapporten:** Den rapport, der indeholder kildeillustrationen for detaljeadgang på tværs af-rapport.
* **Target side:** Den side, som en bruger lander på, når du har startet en drillthrough-handling.
* **Target rapport:** Den rapport, der indeholder destinationssiden for detaljeadgang på tværs af-rapport.

## <a name="enable-cross-report-drillthrough"></a>Aktivér detaljeadgang på tværs af-rapport

Hvis du vil aktivere en rapport til at være destination for en rapport på tværs af detaljeadgang, skal du aktivere funktionen for den pågældende rapport i den **indstillinger** vindue. Gå til **fil** > **indstillinger** > **indstillinger**, og derefter gå til **rapportere indstillinger** i nærheden af den nederst på siden til venstre.

Vælg den **Tillad visuelle elementer i denne rapport til at bruge detaljeadgang mål fra andre rapporter** afkrydsningsfelt, som vist på følgende billede.

![Skærmbillede af indstillinger vindue med rapportindstillinger fremhævet](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Detaljeadgang på tværs af-rapport er nu aktiveret.

## <a name="set-up-cross-report-drillthrough"></a>Konfigurere detaljeadgang på tværs af-rapport

Konfigurere detaljeadgang på tværs af-rapport er svarer til at konfigurere detaljeadgang inden for en rapport. Detaljeadgang er aktiveret på siden target, så andre visuelle elementer til at målrette siden er aktiveret for detaljeadgang. Trinnene til at oprette detaljeadgang inden for en enkelt rapport, kan du se [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md).

For at starte installationen, skal du tage et par indledende trin:

* Konfigurer en detaljeadgang target side, som kan åbnes fra andre rapporter i arbejdsområdet eller app.
* Tillad, at en rapport for at se detaljeadgang sider fra uden for sin rapport.

Find detaljeadgang indstillinger i den **felter** afsnit i den **visualiseringer** rude, som vist på følgende billede.

![Skærmbillede af visualiseringer ruden med indstillinger for detaljeadgang fremhævet](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Der er det første trin i at aktivere detaljeadgang til en side til at validere datamodeller for kilde- og rapporter. Kontrollér, at: 

* Felter, du vil overføre findes i både datamodeller.
* Navnene på felterne, og navnene på tabellerne, de tilhører, er identiske (strengene skal også stemme overens, og der skelnes mellem store).

Hvis du vil overføre et filter på feltet for eksempel *land* i tabellen *Geografi*, begge modeller skal have en *Geografi* tabel, og en *land* feltet i den pågældende tabel. Hvis ikke, skal du opdatere feltets navn eller tabelnavnet i den underliggende model. Ganske enkelt opdatere det viste navn på felterne, der fungerer ikke korrekt for detaljeadgang på tværs af-rapport. (Bemærk, at skemaerne i hver enkelt rapport ikke behøver at være nøjagtigt de samme).

Kom i gang med konfiguration, skal du få destinationssiden klar. I Power BI Desktop, gå til siden, og Sørg for, at den **på tværs af-rapport** detaljeadgang slå er indstillet til **på**. 

![Skærmbillede af slå Cross-rapport, der er indstillet til til](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Derefter skal du trække de felter, du vil bruge som destination for detaljeadgang til canvasset. Vælg, om det felt, der skal bruges som en kategori eller opsummerede som en måling. På dette tidspunkt, du kan vælge, om du vil deaktivere den **hold alle filtre** slå for Visualiseringen. Hvis du ikke vil overføre andre anvendte filtre fra kilden visual til dine mål detaljeadgang visual, skal du vælge **fra**.

> [!NOTE]
> Hvis du bruger siden for kun drillthrough til cross-rapport, skal du slette den **tilbage** knap, der er tilføjet automatisk. Den **tilbage** knappen fungerer kun for nagivation inden for en enkelt rapport. 

Når du har konfigureret det visuelle element, Sørg for, at du gemmer rapporten, hvis du er i Power BI-tjenesten, eller gemme og udgive rapporten, hvis du bruger Power BI Desktop.

Det forrige afsnit beskrives, hvordan du aktiverer detaljeadgang på tværs af-rapport til Power BI Desktop (i den **indstillinger** vindue). Hvis du bruger Power BI-tjenesten til at oprette en rapport på tværs af detaljeadgang destination, for at aktivere detaljeadgang på tværs af-rapport skal du: 

1. Vælg det arbejdsområde, hvor dine destinationsrapporten og kilderapporten, der er placeret.
2. Vælg **rapporter**.
3. Vælg den **indstillinger** ikonet for kilderapporten.
4. Sørg for, at Skift cross-rapport detaljeadgang er **på**.
5. Gem din rapport.

Det var det. Rapporten er klar til at få detaljeadgang på tværs af rapport oplevelsen. 

I næste afsnit, kan vi se nærmere på oplevelsen fra brugerens perspektiv.

## <a name="cross-report-drillthrough-experience"></a>Oplevelse på tværs af-rapport detaljeadgang

Når du konfigurerer på tværs af-rapport detaljeadgang oplevelse for en rapport, kan du sætte funktionen til at bruge.

Vælg kilderapporten i Power BI-tjenesten, og vælg derefter et visuelt element, der bruger det eller de felter på den måde, du angav, da du konfigurere siden mål. Derefter skal du højreklikke på et datapunkt for at åbne menuen visuel kontekst, og vælg **detaljeadgang**.

![Skærmbillede af kilderapporten i Power BI-tjenesten, med detaljeadgang, der er fremhævet](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Du får derefter vist resultaterne target detaljeadgang på tværs af rapport siden samme måde som du konfigurerer dem da du oprettede målet. Resultaterne er filtreret i henhold til indstillingerne for detaljeadgang.

> [!IMPORTANT]
> På tværs af-rapport detaljeadgang mål cachelagrer Powerbi. Hvis du foretager ændringer, skal du opdatere din browser, hvis du ikke kan se detaljeadgang mål som forventet. 

På tværs af rapport mål er formateret på følgende måde: 

`Target Page Name [Target Report Name]`

Når du vælger den target-side, du vil få detaljeadgang, Power BI er med til denne side. Den går langs filterkontekst, der er baseret på indstillingerne for target siden. 

Filterkontekst fra kildens visuelle element kan omfatter følgende: 

* Rapport, side og filtre på visualiseringsniveau påvirker kildeillustrationen. 
* Tværgående filtrering og tværgående fremhævning, som påvirker kildeillustrationen. 
* Udsnit på siden, og Synkroniser udsnitsværktøjer.
* URL-parametre.

Når du besøger destinationsrapporten for detaljeadgang, gælder kun filtre for felter, som det finder nøjagtig streng svarer til feltnavn og tabelnavnet i Power BI. Powerbi kan ikke anvendes sticky filtre fra destinationsrapporten. Det, men gælder dit personlige bogmærke standard, hvis en sådan findes. Hvis din personlige bogmærke standard omfatter et filter på rapportniveau for f.eks. *Country = USA*, Power BI anvender filteret først, før du anvender filterkonteksten fra kildens visuelle element. 

Power BI overfører for detaljeadgang på tværs af-rapport, filterkontekstens på alle sider, der er standard i målrapporten. Powerbi overføre ikke filterkontekst for værktøjstipsider, fordi værktøjstipsider filtreres baseret på kildens visuelle element, som aktiverer værktøjstippet.

Hvis du vil vende tilbage til kilderapporten efter handlingen på tværs af-rapport, detaljeadgang, kan du bruge browserens **tilbage** knap. 

## <a name="next-steps"></a>Næste trin

Du vil måske også være interesseret i følgende artikler:

* [Brug af udsnitsværktøjer i Power BI Desktop](visuals/power-bi-visualization-slicers.md)
* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)

