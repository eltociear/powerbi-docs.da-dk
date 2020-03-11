---
title: Certificerede Power BI-visualiseringer
description: Krav og proces til afsendelse af en brugerdefineret visualisering til certificering og en liste over certificerede Power BI-visualiseringer.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 03/01/2020
ms.openlocfilehash: 8aea9041665de69b2c5be954dc8f13a6402a06e0
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260755"
---
# <a name="get-a-power-bi-visual-certified"></a>Få en Power BI-visualisering certificeret

Certificerede Power BI-visualiseringer er Power BI-visualiseringer i [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals), der opfylder [kodekrav](#certification-requirements) for Microsoft Power BI-teamet. Disse visualiseringer testes for at bekræfte, at de ikke har adgang til eksterne tjenester, og at de følger sikre kodemønstre og retningslinjer.

Når en Power BI-visualisering er blevet certificeret, indeholder den flere funktioner. Du kan f.eks. [eksportere til PowerPoint](../consumer/end-user-powerpoint.md) eller få vist visualiseringen i modtagne mails, når en bruger [abonnerer på rapportsider](../consumer/end-user-subscribe.md).

Certificeringsprocessen er valgfri. Visualiseringer i Power BI, der ikke er certificeret, er ikke nødvendigvis usikre Power BI-visualiseringer. Nogle Power BI-visualiseringer er ikke certificeret, fordi de ikke er i overensstemmelse med et eller flere af [certificeringskravene](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Det kunne f.eks. være en kortvisualisering i Power BI, der opretter forbindelse til en ekstern tjeneste, eller en Power BI-visualisering, der benytter kommercielle biblioteker.

> [!NOTE]
> Microsoft er ikke forfatteren af Power BI-visualiseringer fra tredjepart. Kontakt forfatteren af visualiseringen direkte for at få bekræftet funktionaliteten af visualiseringer fra tredjepart.

## <a name="certification-requirements"></a>Certificeringskrav

Hvis du vil have din Power BI-visualisering [certificeret](#get-a-power-bi-visual-certified), skal Power BI-visualiseringen overholde de krav, der er angivet i dette afsnit. 

### <a name="general-requirements"></a>Generelle krav

Din Power BI-visualisering skal godkendes af Seller Dashboard eller Partnercenter. Vi anbefaler, at din Power BI-visualisering allerede er i [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals). Du kan få mere at vide om, hvordan du publicerer en Power BI-visualisering i AppSource i [Publicer Power BI-visualiseringer i Partnercenter](office-store.md).

Før du indsender din Power BI-visualisering til certificering, skal du kontrollere, at den overholder [retningslinjerne for Power BI-visualiseringer](./guidelines-powerbi-visuals.md).

Når du indsender Power BI-visualiseringen, skal du sørge for, at den kompilerede pakke nøjagtigt svarer til den sendte pakke.

### <a name="code-repository-requirements"></a>Krav til kodelager

Selvom du ikke behøver at dele din kode i GitHub, skal kodelageret være tilgængeligt, så Power BI-teamet kan gennemgå det. Den bedste måde at gøre det på er ved at levere kildekoden (JavaScript eller type) til GitHub.

Lageret skal indeholde følgende:
* Kode for kun én Power BI-visualisering. Det må ikke indeholde kode for flere Power BI-visualiseringer eller ikke-relateret kode.
* En forgrening ved navn **certificering** (skal skrives med små bogstaver). Kildekoden i denne forgrening skal matche den sendte pakke. Denne kode kan kun opdateres under den næste afsendelsesproces, hvis du sender din Power BI-visualisering igen.

Hvis din Power BI-visualisering bruger private NPM-pakker eller git-undermoduler, skal du give adgang til de ekstra lagre, der indeholder denne kode.

Hvis du vil vide, hvordan et lager med Power BI-visualiseringer ser ud, skal du gennemse GitHub-lageret for at finde [søjlediagrammet med eksempler på Power BI-visualiseringer](https://github.com/microsoft/PowerBI-visuals-sampleBarChartgi).

### <a name="file-requirements"></a>Filkrav

Brug den nyeste version af API'en til at skrive Power BI-visualiseringen.

Lageret skal indeholde følgende filer:
* **.gitignore** – Føj `node_modules`, `.tmp`, `dist` til denne fil. Koden må ikke indeholde mapperne *node_modules*, *.tmp* eller *dist*.
* **capabilities.json** – hvis du sender en nyere version af din Power BI-visualisering med ændringer af egenskaberne i denne fil, skal du bekræfte, at de ikke ødelægger rapporter for eksisterende brugere.
* **pbiviz.json** 
* **package.json**. Følgende pakke skal være installeret for visualiseringen:
   * ["tslint"](https://www.npmjs.com/package/tslint): "5.18.0" eller nyere
   * ["typescript"](https://www.npmjs.com/package/typescript): "3.0.0" eller nyere
   * ["tslint-microsoftcontrib"](https://www.npmjs.com/package/tslint-microsoft-contrib): "6.2.0" eller nyere
   * Filen skal indeholde en kommando for at køre Linter: "lint": "tslint -c tslint.json -p tsconfig.json"
* **package-lock.json**
* **tsconfig.json**

### <a name="command-requirements"></a>Kommandokrav

Sørg for, at følgende kommandoer ikke returnerer nogen fejl.

* `npm install`
* `pbiviz package`
* `npm audit` – må ikke returnere nogen advarsler med et højt eller moderat niveau.
* [TSlint fra Microsoft](https://www.npmjs.com/package/tslint-microsoft-contrib) med [den påkrævede konfiguration](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/tslint.json). Denne kommando må ikke returnere nogen lint-fejl.

### <a name="compiling-requirements"></a>Krav til kompilering

Brug den nyeste version af [powerbi-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools) til at skrive Power BI-visualiseringen.

Du skal kompilere din Power BI-visualisering med `pbiviz package`. Hvis du bruger dine egne buildscripts, skal du angive en `npm run package` brugerdefineret buildkommando.



### <a name="source-code-requirements"></a>Kildekodekrav

Kontrollér, at du følger politiklisten med [ekstra certificering for Power BI-visualiseringer](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification). Hvis din udgivelse ikke følger disse retningslinjer, vil mailen med afvisningen fra Partnercenter indeholde numrene på de politikker, der er angivet i dette link.

Følg nedenstående kodekrav for at sikre dig, at din kode er i overensstemmelse med Power BI-certificeringspolitikkerne.  

**Påkrævet**
* Du kan kun bruge OSS-komponenter, der kan gennemses offentligt, f.eks. offentlige Javascript- eller TypeScript-biblioteker.
* Koden skal understøtte [API'en til gengivelse af hændelser](./visuals/event-service.md).
* Sørg for, at DOM er sikkert manipuleret. Brug sanering til brugerinput eller brugerdata, før du føjer det til DOM.
* Brug denne [eksempelrapport](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) som et testdatasæt.

**Ikke tilladt**
* Adgang til eksterne tjenester eller ressourcer. Der må f.eks. ikke sendes nogen HTTP/S- eller WebSocket-anmodninger fra Power BI til nogen tjeneste.
* Brug af `innerHTML` eller `D3.html(user data or user input)`.
* Javascript-fejl eller -undtagelser i browserkonsollen for inputdata.
* Arbitrær eller dynamisk kode, f.eks. `eval()`, usikker brug af `settimeout()`, `requestAnimationFrame()`, `setinterval(user input function)` og brugerinput eller brugerdata.
* Formindskede JavaScript-filer eller -projekter.

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

### <a name="private-repository-submission-process"></a>Processen til indsendelse af privat lager

Hvis du bruger et privat lager, f.eks. GitHub, til at sende din Power BI-visualisering til certificering, skal du følge vejledningen i dette afsnit.
1. Opret en ny konto til valideringsteamet.
2. Konfigurer [tofaktorgodkendelse](https://help.github.com/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa) til din konto.
3. [Generer et nyt sæt genoprettelseskoder](https://help.github.com/github/authenticating-to-github/configuring-two-factor-authentication-recovery-methods#generating-a-new-set-of-recovery-codes).
4. Når du indsender din Power BI-visualisering, skal du angive følgende:
    * Et link til lageret
    * Legitimationsoplysninger til logon (inklusive en adgangskode)
    * Genoprettelseskoder
    * Skrivebeskyttede tilladelser til vores konto ([pbicvsupport](https://github.com/pbicvsupport))

## <a name="certified-power-bi-visuals"></a>Certificerede Power BI-visualiseringer

De certificerede Power BI-visuals er angivet nedenfor. Klik på linket for at åbne Power BI-visual'et i AppSource. Hvis en video er tilgængelig, kan du klikke på videolinket for at se den.

* [3AG Systems – liggende søjlediagram med absolut varians](https://appsource.microsoft.com/product/power-bi-visuals/WA104381802)
*  [3AG Systems – liggende søjlediagram med relativ varians](https://appsource.microsoft.com/product/power-bi-visuals/WA104381912)
*  [3AG Systems – søjlediagram med relativ varians](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803)
*  [3AG Systems – søjlediagram med varians](https://appsource.microsoft.com/product/power-bi-visuals/WA104381724)
* [Visual med avanceret kransediagram (fuld udgave)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941)
*  [Visual med avanceret kransediagram (reduceret udgave)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)
*  [Visual med avanceret graf](https://appsource.microsoft.com/product/power-bi-visuals/WA104382086)
*  [Visuelt element med avanceret netværk](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942)
*  [Visual med avanceret TimeSeries (fuld udgave)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943)
*  [Aster-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759)
*  [Beyondsoft-kalender](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096)
*  [Butterflydiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838)
*  [Kasse med hale-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831)
* [Kasse med hale-diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351)
*  [Murstensdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836)
*  [Boblediagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340)
*  [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755), **[videolink](https://youtu.be/AOlsFYkfkcw)**
* [Punkttegnsdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)
*  [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953), **[videolink](https://youtu.be/mtvUNl9bMjA)**
* [Kalender fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381844)
*  [Kalender fra Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146)
*  [Candlestick by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952), **[videolink](https://youtu.be/nT_18gyRxPo)**
*  [Kort med tilstand fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967)
*  [Firkantudsnitsværktøj](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756)
*  [Chord](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761), **[videolink](https://youtu.be/AQvd2FhRyCI)**
*  [Cirkulær måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837)
*  [Klyngekort](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806)
* [Brugerdefineret kalender fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381179)
* [Cylindrisk måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874)
*  [Skivemåler](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184)
-[punktdiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760)
*  [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949), **[videolink](https://youtu.be/By16pX9KT40)**
*  [Detaljeret kartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045)
*  [Detaljeret fladekort](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044)
*  [Drill-down column chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857), **[videolink](https://youtu.be/lBy2gQQ5YsQ)**
*  [Drill-down column chart for time based data](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881), **[videolink](https://youtu.be/T_mRou18vx0)**
*  [Drill-down donut chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858), **[videolink](https://youtu.be/AUVFrSHmPeo)**
*  [Dobbelt-KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774)
*  [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983)
*  [Enhanced Scatter](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762), **[videolink](https://youtu.be/xCfM0cjM4do)**
*  [Enlighten-akvarie](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112)
*  [Enlighten-udsnitsværktøj](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960)
*  [Enlighten-stakblanding](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849)
*  [Enlighten-vaffeldiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850)
*  [Filter by List by Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413), **[videolink](https://youtu.be/RetEWGwBu0I)**
*  [Force-Directed Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764), **[videolink](https://youtu.be/YsTa7uyJ4sg)**
*  [Tragtformet diagram med kilde fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334)
*  [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765), **[videolink](https://youtu.be/qJ7s_KrGiUU)**
* [Ganttdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364)
*  [Globus med datalinjer](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344)
*  [Grid fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825)
*  [Hierarchy Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333), **[videolink](https://youtu.be/0ZGzJaq_KT4)**
*  [Histogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776)
*  [Histogram med punkter fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032)
* [Vandret søjlediagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381230)
*  [Horisontalt tragtformet diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846)
*  [Billede fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297)
*  [Billedgitter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355)
*  [Infographic Designer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898)
*  [KPI-diagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432)
*  [KPI-kolonne fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996)
*  [KP Grid fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947)
*  [KPI-indikator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832)
*  [KPI-ticker fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946)
* [Lineær måler fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821)
*  [LineDot-diagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766)
*  [Mekko Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785), **[videolink](https://youtu.be/90FLCKpgicA)**
*  [Multi-KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763)
*  [Oversigt fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477)
*  [Afspilningsakse (dynamisk udsnitsværktøj)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981)
*  [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083), [videolink](https://youtu.be/IvfIP3E6-1Q)
*  [Power KPI Matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299), **[videolink](https://youtu.be/1enze8pcGzY)**
*  [Pulse Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006), **[videolink](https://youtu.be/DQWdcQtjDVw)**
*  [Kvadrantdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011)
*  [Radardiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771)
*  [Cirkeldiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824)
*  [Roterende diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007)
*  [Sankey Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777), **[videolink](https://youtu.be/WWP9wVUHGaA)**
*  [Punktdiagram fra Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703)
*  [Rulning](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018)
*  [Smart Filter by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859), **[videolink](https://youtu.be/gcJsDDRQq28)**
*  [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910), **[videolink](https://youtu.be/0m3Vnvso9tY)**
*  [Stream-graf](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772)
*  [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767)
*  [Synoptic Panel fra OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873)
*  [Heatmaptabel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818)
*  [Tachometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937), **[videolink](https://youtu.be/C3OXdETbS9o)**
*  [Tekstfilter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309)
*  [Tekstombrydning fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826)
*  [Thermometer fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847)
*  [Time Brush Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798)
*  [Timeline Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786), **[videolink](https://youtu.be/ozMtZ4_NZ10)**
*  [Timeline by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427), [videolink](https://youtu.be/szNi9YgXFJc)
*  [Tornado chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768), **[videolink](https://www.youtube.com/watch?v=AQvd2FhRyCI)**
*  [Handelsdiagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823)
* [Ultimativt KPI-kort](https://appsource.microsoft.com/product/power-bi-visuals/WA104381977)
*  [Ultimate Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140), **[videolink](https://youtu.be/pDYF8iZxERs)**
*  [Ultimate Waterfall](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956), **[videolink](https://youtu.be/0BZsVCQdEkc)**
*  [Liste over brugere fra CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426)
*  [Venn-diagram fra MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381231)
*  [Violindiagram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381947)
*  [Visio-visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381132)
*  [Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049), **[videolink](https://youtu.be/1vRqYUsm3Vk)**
*  [Word Cloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752), **[videolink](https://youtu.be/AblTenl9fqo)**

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger om visualiseringer under [Ofte stillede spørgsmål om certificerede visualiseringer](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Næste trin

* [Udvikling af en brugerdefineret visualisering i Power BI](../developer/custom-visual-develop-tutorial.md)
* [Microsofts afspilningsliste for brugerdefinerede visualiseringer på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Visualiseringer i Power BI](../visuals/power-bi-report-visualizations.md)  
* [Brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals.md)  
* [Publicer Power BI-visualiseringer i Microsoft AppSource](../developer/office-store.md) 
* Hvis du er webudvikler, der er interesseret i at oprette dine egne Power BI-visualiseringer og føje dem til  [Microsoft AppSource](https://appsource.microsoft.com), kan du starte med selvstudiet  [Udvikling af en Power BI-visualisering](visuals/custom-visual-develop-tutorial.md). 

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
