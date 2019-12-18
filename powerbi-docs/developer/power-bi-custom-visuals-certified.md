---
title: Certificerede Power BI-visualiseringer
description: Krav og proces til afsendelse af en brugerdefineret visualisering til certificering. Og en liste over allerede certificerede Power BI-visualiseringer.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: 0a39496ade27cd45fae116eea92ef4b472e04582
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/11/2019
ms.locfileid: "74999738"
---
# <a name="get-a-power-bi-visual-certified"></a>Få en Power BI-visualisering certificeret

Certificerede Power BI-visualiseringer er visualiseringer på *Marketplace*, der opfylder visse *angivne kodekrav*, som *Microsoft Power BI-teamet* har testet og godkendt. Testene er designet til at kontrollere, at visualiseringen ikke tilgår eksterne tjenester eller ressourcer.

Certificerede Power BI-visualiseringer og [Power BI-standardvisualiseringer](power-bi-custom-visuals.md) bruges på samme måde. De kan føjes til [Power BI Desktop](../desktop-what-is-desktop.md) og [Power BI-tjenesten](../power-bi-service-overview.md) og blive vist via [Power BI – Mobil](../consumer/mobile/mobile-apps-for-mobile-devices.md) og [Power BI Embedded](embedding.md).

Certificeringsprocessen er valgfri. Det er op til udviklerne at beslutte, om de vil have deres Power BI-visualiseringer på markedspladsen certificeret. Når en Power BI-visualisering er blevet certificeret, indeholder den flere funktioner. Du kan f.eks. [eksportere til PowerPoint](../consumer/end-user-powerpoint.md) eller få vist visualiseringen i modtagne mails, når en bruger [abonnerer på rapportsider](../consumer/end-user-subscribe.md).

Ikke-certificerede Power BI-visualiseringer er ikke nødvendigvis ensbetydende med usikre visualiseringer. Nogle visualiseringer er ikke certificeret, fordi de ikke er i overensstemmelse med et eller flere af [certificeringskravene](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Det kan f.eks. være i forbindelse med oprettelse af forbindelse til en ekstern tjeneste, som f.eks. kortvisualiseringer eller visualiseringer, der anvender kommercielle biblioteker.

Hvis du er webudvikler, der er interesseret i at oprette dine egne Power BI-visualiseringer og føje dem til  [Microsoft AppSource](https://appsource.microsoft.com), kan du starte med selvstudiet  [Udvikling af en Power BI-visualisering](visuals/custom-visual-develop-tutorial.md).

> [!NOTE]
> **Microsoft** er *ikke* forfatteren af Power BI-visualiseringer fra tredjepart. Vi råder kunderne til at kontakte forfatteren af visualiseringen direkte for at bekræfte funktionaliteten af visualiseringer fra tredjepart.

> [!IMPORTANT]
> Microsoft kan efter eget skøn fjerne en Power BI-visualisering fra [listen over certificerede visualiseringer](#list-of-power-bi-visuals-that-have-been-certified).

## <a name="certification-requirements"></a>Certificeringskrav

Hvis du vil have din Power BI-visualisering [certificeret](#get-a-power-bi-visual-certified), skal du sikre, at Power BI-visualiseringen overholder de krav, der er angivet i dette afsnit. 

> [!TIP]
> Det anbefales, at du bruger EsLint med det sikkerhedsregelsæt, der anvendes som standard, til at validere koden på forhånd inden indsendelse.

* Godkendt via Microsoft Sælgerdashboard eller Partnercenter. Din Power BI-visualisering bør være på vores [markedsplads](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).
* Power BI-visualiseringen er skrevet med *API v2.5* eller nyere.
* Power BI-teamet kan gennemse kodelageret. Det kan f.eks. være et læsevenligt format af kildekoden (JavaScript eller TypeScript), der er tilgængeligt for os via GitHub.

    >[!NOTE]
    > Du behøver ikke at dele din kode offentligt i GitHub.

* Krav til kodelager:
  * Disse filer skal være inkluderet:
    * .gitignore
    * capabilities.json
    * pbiviz.json
    * package.json
    * package-lock.json
    * tsconfig.json
  * Må ikke indeholde mappen *node_modules* (føj *node_modules* til filen .gitingore*).
  * Kommandoen *npm install* må ikke returnere nogen fejl.
  * Kommandoen *npm audit* må ikke returnere nogen advarsler med et højt eller moderat niveau.
  * Kommandoen *pbiviz package* må ikke returnere nogen fejl.
  * [TSlint fra Microsoft](https://www.npmjs.com/package/tslint-microsoft-contrib) skal være inkluderet uden nogen tilsidesatte konfigurationer. Denne kommando må ikke returnere nogen lint-fejl.
   * Den kompilerede pakke for Power BI-visualiseringen skal svare til den indsendte pakke (md5-hashen for begge filer skal være ens).
* Kildekodekrav:
   * Power BI-visualiseringen skal understøtte [API'en til gengivelse af hændelse](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/).
   * Sørg for, at der ikke køres tilfældig/dynamisk kode (bad: eval(), unsafe to use of settimeout(), requestAnimationFrame(), setinterval(some function with user input), running user input/data).
   * Sørg for, at DOM manipuleres sikkert (bad: innerHTML, D3.html(<some user/data input>), brug rensning af brugerinput/-data, før det føjes til DOM'en.
   * Sørg for, at der ikke er nogen javascript-fejl eller -undtagelser i browserkonsollen for nogen inputdata. Brugerne anvender måske din Power BI-visualisering med et andet område af uventede data, så visualiseringen må ikke mislykkes. Du kan bruge denne [eksempelrapport](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) som et testdatasæt.

* Hvis nogen egenskaber i filen *capabilities.json* ændres, skal du sørge for, at de ikke ødelægger eksisterende brugeres rapporter.

* Sørg for, at Power BI-visualiseringen overholder [retningslinjerne for Power BI-visualiseringer](./guidelines-powerbi-visuals.md).
    
* Din kode kan kun bruge OSS-komponenter, der kan gennemses offentligt, f.eks. offentlige Javascript- eller TypeScript-biblioteker. Kildekoden skal være tilgængelig til gennemsyn og ikke have kendte sikkerhedsrisici. Vi kan ikke bekræfte en brugerdefineret visualisering ved hjælp af en kommerciel komponent.

* Power BI-visualiseringen må ikke tilgå eksterne tjenester eller ressourcer. Der må f.eks. ikke sendes nogen HTTP/S- eller WebSocket-anmodninger fra Power BI til nogen tjeneste. 

## <a name="submitting-a-power-bi-visual-for-certification"></a>Indsendelse af en Power BI-visualisering til certificering

Du kan anmode om at få din Power BI-visualisering certificeret af Power BI-teamet via Partnercenter.

>[!TIP]
>Power BI-certificeringsprocessen kan tage lidt tid. Hvis du opretter en ny Power BI-visualisering, anbefales det, at du publicerer Power BI-visualiseringen via Partnercenter, før du anmoder om Power BI-certificering. Dette sikrer, at publiceringen af din visualisering ikke forsinkes.

Sådan anmoder du om Power BI-certificering:

1. Log på Partnercenter.
2. På **siden Oversigt** skal du vælge din Power BI-visualisering og gå til siden **Produktkonfiguration**.
3. Markér afkrydsningsfeltet **Anmod om Power BI-certificering**.
4. På siden **Gennemse og publicer** i tekstfeltet **Noter til certificering** skal du angive et link til kildekoden og de legitimationsoplysninger, der kræves for at få adgang.

>[!NOTE]
> Hvis du er midt i en indsendelsesproces for en Power BI-visualisering og skal bruge [Sælgerdashboard](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) (det tidligere administrationsværktøj), skal du gennemse instruktionerne til [Indsendelsesproces for certificering via Sælgerdashboard](seller-dashboard.md#seller-dashboard-certification-submission-process).

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>Liste over Power BI-visualiseringer, der er blevet certificeret

| Link | video |
| --- | --- |
| [3AG Systems – liggende søjlediagram med relativ varians](https://appsource.microsoft.com/en/product/power-bi-visuals/WA104381912) | |
| [3AG Systems – søjlediagram med relativ varians](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803) | |
| [Visualisering med avanceret kransediagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941) | |
| [Visualisering med avanceret netværk](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942) | |
| [Visualisering med avanceret tidsserie](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943) | |
| [Visualisering med avanceret kombinationsdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381944) | |
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

Du kan finde flere oplysninger om visualiseringer under [Ofte stillede spørgsmål om certificerede visualiseringer](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Næste trin

* [Udvikling af en brugerdefineret visualisering i Power BI](../developer/custom-visual-develop-tutorial.md)
* [Microsofts afspilningsliste for brugerdefinerede visualiseringer på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Visualiseringer i Power BI](../visuals/power-bi-report-visualizations.md)  
* [Brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals.md)  
* [Publicer Power BI-visualiseringer i Microsoft AppSource](../developer/office-store.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
