---
title: Certificerede Power BI-visualiseringer
description: Krav og proces til afsendelse af en brugerdefineret visualisering til certificering. Og en liste over allerede certificerede Power BI-visualiseringer.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 05/9/2019
ms.openlocfilehash: 2203e3a9abddb52902c09fdc98665ba013f604ee
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/04/2019
ms.locfileid: "71946227"
---
# <a name="get-a-power-bi-visual-certified"></a>Få en Power BI-visualisering certificeret

## <a name="what-are-_certified_-power-bi-visuals"></a>Hvad er **_certificerede_** Power BI-visualiseringer?

Certificerede Power BI-visualiseringer er visualiseringer på **Marketplace**, der opfylder visse **angivne kodekrav**, som **Microsoft Power BI-teamet** har testet og godkendt. Når en brugerdefineret visualisering er certificeret, indeholder den flere funktioner. Det kan f.eks. være, at du kan [eksportere til PowerPoint](consumer/end-user-powerpoint.md), og du kan få vist visualiseringen i modtagne mails, når en bruger [abonnerer på rapportsider](consumer/end-user-subscribe.md).

**Certificerede Power BI-visualiseringer** bruges på samme måde som [Power BI-standardvisualiseringer](power-bi-custom-visuals.md). Certificerede Power BI-visualiseringer kan føjes til **Power BI-tjenesten**, en **Power BI Desktop-rapport** og blive vist vha. **Power BI – Mobil** og **Power BI Embedded**.

De udførte tests er udviklet for at kontrollere, at visualiseringen ikke har adgang til eksterne tjenester eller ressourcer. **Microsoft** er *ikke* forfatter af Power BI-visualiseringer fra tredjepart, og kunderne rådes til at kontakte forfatteren direkte for at kontrollere funktionaliteten af sådanne visualiseringer.

Certificeringsprocessen er en valgfri proces, og det er op til udviklerne at beslutte, om de ønsker, at deres visualiseringer på Marketplace skal certificeres.  

**Ikke-certificerede Power BI-visualiseringer** er ikke nødvendigvis ensbetydende med usikre visualiseringer. Nogle visualiseringer er ikke certificeret, fordi de ikke er i overensstemmelse med et eller flere af [certificeringskravene](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Det kan f.eks. være i forbindelse med oprettelse af forbindelse til en ekstern tjeneste, som f.eks. kortvisualiseringer eller visualiseringer, der anvender kommercielle biblioteker.

Er du webudvikler og interesseret i at oprette dine egne visualiseringer og føje dem til  **[Microsoft AppSource](https://appsource.microsoft.com)** ? Du kan se under  **[Udvikling af en brugerdefineret Power BI-visualisering for at få mere at vide](developer/custom-visual-develop-tutorial.md)** .

## <a name="removal-of-power-bi-certified-power-bi-visuals"></a>Fjernelse af certificerede Power BI-visualiseringer

Microsoft kan, efter eget skøn, fjerne en visualisering fra [listen over certificerede visualiseringer](#list-of-power-bi-visuals-that-have-been-certified).

## <a name="getting-a-custom-visualcertified"></a>Hentning af en certificeret brugerdefineret visualisering

### <a name="certification-requirements"></a>Certificeringskrav

Hvis du vil have din brugerdefinerede visualisering [certificeret](#get-a-power-bi-visual-certified), skal du sørge for, at den er i overensstemmelse med følgende:  

* Godkendt af Microsoft AppSource. Din brugerdefinerede visualisering skal findes på vores [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).
* Brugerdefineret visuelt element er skrevet med version **API v2.5** eller nyere.
* Et kodelager er tilgængeligt til gennemsyn af Power BI-teamet (f.eks. kildekoden (JavaScript eller TypeScript) i formater, der kan læses af mennesker, og som er tilgængeligt via GitHub).

    >[!Note]
    > Du behøver ikke at dele din kode offentligt i GitHub.
* Krav til kodelager:
   * Skal indeholde det påkrævede minimumantal filer:
      * .gitignore
      * capabilities.json
      * pbiviz.json
      * package.json
      * package-lock.json
      * tsconfig.json
   * Må ikke indeholde mappen include node_modules (add node_modules til .gitingore-fil)
   * **npm install**-kommandoen må ikke returnere nogen fejl.
   * **npm audit**-kommandoen må ikke returnere nogen advarsler med et højt eller moderat niveau.
   * **pbiviz package**-kommandoen må ikke returnere nogen fejl.
   * Skal indeholde [TSlint fra Microsoft](https://www.npmjs.com/package/tslint-microsoft-contrib) uden nogen tilsidesat konfiguration, og denne kommando må ikke returnere nogen lint-fejl.
   * Den kompilerede pakke for det brugerdefinerede visuelle element skal svare til den sendte pakke (md5-hashen for begge filer skal være ens).
* Kildekodekrav:
   * Det visuelle element skal understøtte [Rendering Events-API'en](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/).
   * Sørg for, at der ikke køres tilfældig/dynamisk kode (bad: eval(), unsafe to use of settimeout(), requestAnimationFrame(), setinterval(some function with user input), running user input/data).
   * Sørg for, at DOM manipuleres sikkert (bad: innerHTML, D3.html(<some user/data input>), brug rensning af brugerinput/-data, før det føjes til DOM'en.
   * Sørg for, at der ikke er nogen javascript-fejl/-undtagelser i browserkonsollen for nogen inputdata. Brugerne kan bruge et visuelt element med et andet interval af uventede data. Det visuelle element må derfor ikke mislykkes. Du kan bruge [denne eksempelrapport](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) som et testdatasæt.

* Hvis nogle egenskaber i capabilities. JSON ændres, skal du sørge for, at de ikke ødelægger den eksisterende brugers rapporter.

* Sørg for, at det visuelle element opfylder [retningslinjerne for visuelle elementer i Power BI](https://docs.microsoft.com/en-us/power-bi/developer/guidelines-powerbi-visuals#guidelines-for-power-bi-visuals-with-additional-purchases). **Vandmærker er ikke tilladt**.

* Anvender kun OSS-komponenter, der kan gennemses offentligt (Offentlige JS-biblioteker eller TypeScript. Kildekoden er tilgængelig til gennemsyn og har ikke kendte sikkerhedsrisici). Vi kan ikke bekræfte en brugerdefineret visualisering ved hjælp af en kommerciel komponent.

* Har ikke adgang til eksterne tjenester eller ressourcer, herunder men ikke begrænset til, ingen HTTP/S- eller WebSocket-anmodninger fra Power BI til andre tjenester. 

> [!TIP]
> Vi anbefaler, at du bruger EsLint med det sikkerhedsregelsæt, der anvendes som standard, til at validere koden på forhånd inden indsendelse.

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Proces for indsendelse af en brugerdefineret visualisering til certificering

Sådan indsender du en brugerdefineret visualisering til certificering:

1. Send en mail til supportteamet for Power BI-visualiseringer (pbicvsupport@microsoft.com). Du skal inkludere følgende oplysninger i mailen:
    * Titel: Anmodning om certificering af visualisering
    * Link til GitHub-lageret, der hoster kildekoden, som kan læse af mennesker
    * [Overhold kravene](#certification-requirements)
    * Bestå kodegennemgangen

2. Teamet for Microsoft Power BI-visualiseringer giver dig besked, når din brugerdefinerede visualisering er certificeret og føjet til [listen over certificerede visualiseringer](#list-of-power-bi-visuals-that-have-been-certified) eller afvises med en rapport over de problemer, der skal løses. Det er udviklerens ansvar at have en åben kommunikation med Microsoft og opdatere deres certificerede visualiseringer efter behov.

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>Liste over Power BI-visualiseringer, der er blevet certificeret

| Link til AppSource | Link til video |
| --- | --- |
| [3AG Systems – liggende søjlediagram med relativ varians](https://appsource.microsoft.com/en/product/power-bi-visuals/WA104381912) | |
| [3AG Systems – søjlediagram med relativ varians](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803) | |
| [Visuelt element med avanceret kransediagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941) | |
| [Visuelt element med avanceret netværk](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942) | |
| [Visuelt element med avanceret tidsserie](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943) | |
| [Visuelt element med avanceret kombinationsdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381944) | |
| [Aster-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft-kalender](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096) | |
| [Butterflydiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Kasse med hale-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831) | |
| [Kasse med hale-diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [Murstensdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Boblediagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340) | |
| [Punkttegnsdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [Punkttegnsdiagram fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Kalender fra Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146) | |
| [Lysestange fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [Kort med tilstand fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967) | |
| [Firkantudsnitsværktøj](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756) | |
| [Korde](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [Cirkulær måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Klyngekort](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806) | |
| [Cylindrisk måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Skivemåler](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) | |
| [Prikdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760) | |
| [Punktvisning af OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Detaljeret kartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045) | |
| [Detaljeret fladekort](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044) | |
| [Søjlediagram med detailudledning](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Søjlediagram med detailudledning for tidsbaserede data](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Kransediagram med detailudledning](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dobbelt-KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774) | |
| [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983) | [Video](https://youtu.be/Z-tl97BpEr0) |
| [Forbedret punktdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlighten-akvarie](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112) | |
| [Enlighten-udsnitsværktøj](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960) | |
| [Enlighten-stakblanding](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849) | |
| [Enlighten-vaffeldiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850) | |
| [Filter by List af Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413) | [Video](https://youtu.be/RetEWGwBu0I) |
| [Force-styret graf](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [Tragtformet diagram med kilde fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [Ganttdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Globus med datalinjer](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344) | |
| [Grid fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825) | [Video](https://youtu.be/VOPoDJgZfOY) |
| [Hierarkidiagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Histogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776) | |
| [Histogram med punkter fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [Horisontalt tragtformet diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [Billede fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297) | |
| [Billedgitter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355) | |
| [Infographic Designer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898) | |
| [KPI-diagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432) | |
| [KPI-kolonne fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996) | [Video](https://youtu.be/rU0xoOlIq1U) |
| [KP Grid fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947) | [Video](https://youtu.be/dM4PvZh71V0) |
| [KPI-indikator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832) | |
| [KPI-ticker fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [Lineær måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [LineDot-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766) | |
| [Mekko-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [Multi-KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763) | |
| [Oversigt fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477) | |
| [Afspilningsakse (dynamisk udsnitsværktøj)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981) | |
| [Power-KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power-KPI-matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Impulsdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006) | [Video](https://youtu.be/DQWdcQtjDVw) |
| [Kvadrantdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Radardiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771) | |
| [Cirkeldiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [Roterende diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Punktdiagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703) | |
| [Rulning](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018) | |
| [Smartfilter fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline af OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Stream-graf](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767) | |
| [Synoptic Panel fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873) | |
| [Heatmaptabel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818) | |
| [Omdrejningstæller](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Tekstfilter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309) | |
| [Tekstombrydning fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Thermometer fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847) | [Video](https://youtu.be/SPX9mgrAdBc) |
| [Time Brush Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798) | |
| [Tidslinjeudsnitsværktøj](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tidslinje fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427) | [Video](https://youtu.be/szNi9YgXFJc) |
| [Tornadodiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Handelsdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimativt afvigelsesdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ultimativt vandfaldsdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [Liste over brugere fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426) | |
| [Vaffeldiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Ordcloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger om visualiseringer under [Ofte stillede spørgsmål om certificerede visualiseringer](#get-a-power-bi-visual-certified).

## <a name="next-steps"></a>Næste trin

* [Udvikling af en brugerdefineret visualisering i Power BI](developer/custom-visual-develop-tutorial.md)
* [Microsofts afspilningsliste for brugerdefinerede visualiseringer på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Visualiseringer i Power BI](visuals/power-bi-report-visualizations.md)  
* [Brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals.md)  
* [Publicer Power BI-visualiseringer i Microsoft AppSource](developer/office-store.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
