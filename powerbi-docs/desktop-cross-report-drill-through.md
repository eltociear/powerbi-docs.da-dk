---
title: Brug tværgående detaljeadgang i rapport i Power BI Desktop
description: Få mere at vide om, hvordan du kan få detaljeadgang fra én rapport til en anden i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/18/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 6424180dde3dac0d6d2b66c8a9303810b6aa0dc6
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/18/2019
ms.locfileid: "71100111"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Brug tværgående detaljeadgang i rapport i Power BI Desktop

Med funktionen til detaljeadgang på tværs af rapporter i Power BI Desktop kan du gå fra én rapport til en anden rapport, afhængigt af konteksten. Dette er muligt, når rapporterne er inden for det samme arbejdsområde eller den samme app i Power BI-tjenesten. Brug detaljeadgang på tværs af rapporter til at forbinde to eller flere rapporter, der har relateret indhold, og til at overføre filterkonteksten sammen med forbindelsen på tværs af rapporter. I denne artikel får du mere at vide om, hvordan du konfigurerer en detaljeadgang på tværs af rapporter til Power BI-rapporter, og hvad brugerne oplever, når de benytter detaljeadgang på tværs af rapporter.

![Skærmbillede af indstillingen til detaljeadgang i Power BI Desktop](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Følgende definitioner er vigtige at forstå, før vi begynder at konfigurere og bruge detaljeadgang på tværs af rapporter:

* **Kildens visuelle element:** Det visuelle element, der aktiverer detaljeadgangshandlingen ved hjælp af den visuelle genvejsmenu.
* **Kildens rapport:** Den rapport, der indeholder kildens visuelle element til detaljeadgang på tværs af rapporter.
* **Destinationsside:** Den side, som en bruger lander på, efter at du har igangsat en detaljeadgangshandling.
* **Destinationsrapport:** Den rapport, der indeholder destinationssiden for detaljeadgang på tværs af rapporter.


> [!NOTE]
> Med funktionen til detaljeadgang på tværs af rapporter i Power BI Desktop kan du gå fra én rapport til en anden rapport, afhængigt af konteksten. Dette er muligt, når rapporterne er inden for det samme arbejdsområde eller den samme app i Power BI-tjenesten. Dette gælder ikke, når rapporter, der deles enkeltvist i *Mit arbejdsområde*, tilgås ([rapporter, der er delt med mig](service-share-dashboards.md#share-a-dashboard-or-report)). Du skal i stedet tilgå rapporten i det arbejdsområde, hvorfra den oprindeligt blev delt.


## <a name="enable-cross-report-drillthrough"></a>Aktivér tværgående detaljeadgang i rapport

Hvis du vil gøre en rapport til destinationen for en tværgående detaljeadgang, skal du aktivere funktionen for den pågældende rapport i vinduet **Indstillinger**. Gå til **Fil** > **Indstillinger** > **Indstillinger**, og gå derefter til **Rapportindstillinger** nederst på siden til venstre.

Markér afkrydsningsfeltet **Tillad, at visuelle elementer i denne rapport bruger detaljeadgangsmål fra andre rapporter** som vist på følgende billede.

![Skærmbillede af vinduet Indstillinger, hvor Rapportindstillinger er fremhævet](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Detaljeadgang på tværs af rapporter er nu aktiveret.

## <a name="set-up-cross-report-drillthrough"></a>Konfigurer detaljeadgang på tværs af rapporter

Konfiguration af detaljeadgang på tværs af rapporter minder om konfiguration af detaljeadgang i en rapport. Detaljeadgang er aktiveret på destinationssiden, så andre visualiseringer er rettet mod den aktiverede side til detaljeadgang. Hvis du vil have vist trinnene til at oprette detaljeadgang i en enkelt rapport, kan du se [Brug af detaljeadgang i Power BI Desktop](desktop-drillthrough.md).

Hvis du vil starte konfigurationsprocessen, skal du foretage et par indledende trin:

* Konfigurer en destinationsside til detaljeadgang, som du kan få adgang til fra andre rapporter i arbejdsområdet eller i appen.
* Tillad, at en rapport kan se detaljeadgangssider uden for dens egen rapport.

Find indstillinger for detaljeadgang i afsnittet **Felter** i ruden **Visualiseringer** som vist på følgende billede.

![Skærmbillede af ruden Visualiseringer, hvor indstillinger for detaljeadgang er fremhævet](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Det første trin i aktivering af detaljeadgang for en side er at validere datamodellerne for kilde- og destinationsrapporterne. Kontrollér, at: 

* De felter, du vil overføre, findes i begge datamodeller.
* Navnene på felterne og navnene på de tabeller, som felterne tilhører, er identiske (strengene skal også matche, og der skelnes mellem store og små bogstaver).

Hvis du f.eks. vil overføre et filter for feltet *Country* i tabellen *Geography*, skal begge modeller have tabellen *Geography* og feltet *Country* i den pågældende tabel. Hvis det ikke er tilfældet, skal du opdatere feltnavnet eller tabelnavnet i den underliggende model. Hvis du blot opdaterer det viste navn for felterne, fungerer det ikke korrekt for detaljeadgang på tværs af rapporter. (Bemærk, at skemaerne i de enkelte rapporter ikke behøver at være helt ens).

Hvis du vil i gang med konfigurationen, skal destinationssiden være klar. Gå til siden i Power BI Desktop, og sørg for, at **Tværgående detaljeadgang i rapport** er slået **til**. 

![Skærmbillede af Tværgående detaljeadgang i rapport, der er slået til](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Herefter skal du trække de relevante felter, som du vil bruge som destination for detaljeadgangen, til lærredet. Vælg, om feltet skal bruges som en kategori eller opsummeres som en måling. På dette tidspunkt kan du vælge, om du vil deaktivere **Behold alle filtre** for det visuelle element. Hvis du ikke vil overføre andre anvendte filtre fra kildens visuelle element til destinationsvisualiseringen for detaljeadgangen, skal du vælge **Fra**.

> [!NOTE]
> Hvis du kun bruger siden til detaljeadgang på tværs af rapporter, skal du slette knappen **Tilbage**, der tilføjes automatisk. Knappen **Tilbage** fungerer kun til navigation i en enkelt rapport. 

Når du har konfigureret det visuelle element, skal du sørge for at gemme rapporten, hvis du er i Power BI-tjenesten, eller gemme og publicere rapporten, hvis du bruger Power BI Desktop.

I det forrige afsnit blev det beskrevet, hvordan du aktiverer detaljeadgang på tværs af rapporter for Power BI Desktop (i vinduet **Indstillinger**). Hvis du bruger Power BI-tjenesten til at oprette en destination for detaljeadgang på tværs af rapporter, skal du for at aktivere detaljeadgang på tværs af rapporter 

1. vælge det arbejdsområde, som din destinationsrapport og kildens rapport er placeret i.
2. Vælg **Rapporter**.
3. Vælg ikonet **Indstillinger** for kilderapporten.
4. Sørg for, at tværgående detaljeadgang i rapport er slået **til**.
5. Gem din rapport.

Det var det. Din rapport er klar til detaljeadgang på tværs af rapporter. 

I det næste afsnit kigger vi på oplevelsen fra brugerens perspektiv.

## <a name="cross-report-drillthrough-experience"></a>Tværgående detaljeadgang i rapport

Når du konfigurerer brugen af detaljeadgang på tværs af rapporter for en rapport, kan du aktivere funktionen.

Vælg kilderapporten i Power BI-tjenesten, og vælg derefter et visuelt element, der bruger feltet eller felterne på den måde, du angav, da du konfigurerede destinationssiden. Højreklik derefter på et datapunkt for at åbne genvejsmenuen for det visuelle element, og vælg **Detaljeadgang**.

![Skærmbillede af kilderapport i Power BI-tjenesten, hvor detaljeadgang er fremhævet](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Derefter kan du se resultaterne på destinationssiden for detaljeadgang på tværs af rapporter, på samme måde som du konfigurerede dem, da du oprettede destinationen. Resultaterne filtreres i overensstemmelse med indstillingerne for detaljeadgang.

> [!IMPORTANT]
> Power BI cachelagrer destinationer for detaljeadgang på tværs af rapporter. Hvis du foretager ændringer, skal du sørge for at opdatere din browser, hvis destinationerne for detaljeadgangen ikke ser ud som forventet. 

Destinationer på tværs af rapporter formateres på følgende måde: 

`Target Page Name [Target Report Name]`

Når du har valgt den destinationsside, du vil foretage detaljeadgang til, går Power BI til den pågældende side. Filterkonteksten overføres på baggrund af indstillingerne for destinationssiden. 

Filterkontekst fra kildens visuelle element kan f.eks. indeholde følgende: 

* Rapport, side og filtre på det visuelle elements niveau, der påvirker kildens visuelle element. 
* Tværgående filtrering og tværgående fremhævning, der påvirker kildens visuelle element. 
* Udsnit på siden og synkroniseringsudsnit.
* URL-parametre.

Når du lander på destinationsrapporten for detaljeadgang, anvender Power BI kun filtre for de felter, som programmet finder præcise strengmatches for i forbindelse med feltnavn og tabelnavn. Power BI anvender ikke selvklæbende filtre fra destinationsrapporten. Dit personlige standardbogmærke anvendes dog, hvis der er et. Hvis dit personlige standardbogmærke f.eks. omfatter et filter på rapportniveau for *Country = USA*, anvender Power BI dette filter først, før filterkonteksten fra kildens visuelle element anvendes. 

I forbindelse med detaljeadgang på tværs af rapporter overfører Power BI filterkonteksten til alle standardsider i destinationsrapporten. Power BI overfører ikke filterkontekst for sider med værktøjstip, fordi sider med værktøjstip er filtreret på baggrund af det visuelle element for den kilde, der udløser værktøjstippet.

Hvis du vil vende tilbage til kilderapporten efter detaljeadgangen på tværs af rapporter, skal du bruge knappen **Tilbage** i browseren. 

## <a name="next-steps"></a>Næste trin

Du vil måske også være interesseret i følgende artikler:

* [Brug af udsnitsværktøjer i Power BI Desktop](visuals/power-bi-visualization-slicers.md)
* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)

