---
title: Overførsel til powerbi-visuals-tools 3.x
description: Kom i gang med den nye version af powerbi-visuals-tools
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 245475feeb43ee544117aaa54969f2de1e207cd5
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/02/2019
ms.locfileid: "74696276"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-3xx"></a>Overfør til den nye powerbi-visuals-tools 3.x.x

Fra og med version 3 bruger Power BI Visuals Tools Webpack til bygning af brugerdefinerede visuals.
Den nye version giver udviklere mange nye muligheder for at oprette visuals:

* TypeScript v3.x.x som standard. Nomenklaturen er ændret fra TypeScript 1.5. [Få mere at vide om TypeScript](https://www.typescriptlang.org/docs/handbook/modules.html).

* ES6-moduler understøttes. Du behøver ikke at bruge [externalJS](migrate-to-new-tools.md#fix-loading-external-libraries) mere, brug ES6-importer i stedet.

* Nye versioner af [D3v5](https://d3js.org/) og andre ES6-modulbaserede biblioteker understøttes.

* Reduceret pakkestørrelse. Webpack bruger [Tree Shaking](https://webpack.js.org/guides/tree-shaking/) til at fjerne ubrugt kode. Det reducerer JS-koden, og ydeevnen for indlæsning af visuals bliver derfor bedre.

* Forbedret API-ydeevne.

* Biblioteket Globalize.js [er integreret](migrate-to-new-tools.md#remove-globalizejs-library) i formatting-utils.

* Tools bruger [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) til at vise visualkodebasen.

Alle overførselstrin for den nye version af Power BI Visuals Tools beskrives nedenfor.

## <a name="backward-compatibility"></a>Bagudkompatibilitet

Den nye version af Tools gemmer bagudkompatibilitet for gammel visualkodebase, men kan kræve yderligere ændringer for at indlæse eksterne biblioteker.

De biblioteker, der understøtter modulsystemer, importeres som Webpack-moduler. Alle andre biblioteker og visualkildekode samles i ét modul.

Globale variabler, f. eks. JQuery og Lodash, der blev brugt i de forrige pbiviz-værktøjer, er nu forældede. Det betyder, at hvis den gamle visualkode er afhængig af globale variabler, kan visual'et i dette tilfælde deles.

Den tidligere version af Power BI Visuals Tools kræves for at definere en visualklasse under modulet `powerbi.extensibility.visual`.

## <a name="how-to-install-powerbi-visuals-tools"></a>Sådan installerer du powerbi-visuals-tools

Du kan installere det nye værktøj ved at udføre kommandoen

```cmd
npm install -g powerbi-visuals-tools
```

Eksemplet på sampleBarChart-visual og tilsvarende [ændringer](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L16) i `package.json`:

```json
{
    "name": "visual",
    "version": "1.2.3",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
      "@types/d3": "5.0.0",
      "d3": "5.5.0",
      "powerbi-visuals-tools": "^3.1.0",
      "tslint": "^4.4.2",
      "tslint-microsoft-contrib": "^4.0.0"
    }
}
```

## <a name="how-to-install-power-bi-custom-visuals-api"></a>Sådan installerer du API'en til brugerdefinerede visuals i Power BI

Den nye version af powerbi-visual-tools indeholder ikke alle API-versioner. I stedet for skal udvikleren installere en bestemt version af [`powerbi-visuals-api`](https://www.npmjs.com/package/powerbi-visuals-api)-pakken. Pakkeversionen stemmer overens med API-versionen for brugerdefinerede visuals i Power BI og omfatter alle API-typedefinitionerne til brugerdefinerede visuals i Power BI.

Føj `powerbi-visuals-api` til projektafhængigheder ved at udføre kommandoen `npm install --save-dev powerbi-visuals-api`.
Og du skal fjerne linket til gamle API-typedefinitioner. Fordi typer fra `powerbi-visuals-api` inkluderes automatisk af Webpack. Tilsvarende ændringer findes i [denne](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L14) linje af `package.json`.

## <a name="update-tsconfigjson"></a>Opdater `tsconfig.json`

Hvis du vil bruge eksterne moduler, skal du ændre indstillingen `out` til `outDir`.
`"outDir": "./.tmp/build/",` i stedet `"out": "./.tmp/build/visual.js",`.

Det er påkrævet, da TypeScript-filer kompileres til JavaScript-filer uafhængigt af hinanden. Det er derfor, at du ikke længere behøver at angive visual.js-filen som output.

Og du kan også ændre indstillingen `target` til `ES6` hvis du vil bruge moderne JavaScript som output. [Det er valgfrit](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/tsconfig.json#L6).

## <a name="update-custom-visuals-utils"></a>Opdater utils for brugerdefinerede visuals

Hvis du bruger en powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils), skal du også opdatere dem til den seneste version.

Udfør kommandoen `npm install powerbi-visuals-utils-<UTILNAME> --save`. (F.eks. `npm install powerbi-visuals-utils-dataviewutils --save` ) for at få den nye version med eksterne TypeScript-moduler.

Du kan finde et eksempel i MekkoChart-[lageret](https://github.com/Microsoft/powerbi-visuals-mekkochart).
Denne visual bruger alle utils.

## <a name="remove-globalizejs-library"></a>Fjern biblioteket Globalize.js

Den nye version af [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) omfatter som standard globalize.js.
Du behøver ikke at inkludere dette bibliotek manuelt i projektet.
Alle påkrævede lokaliseringer føjes automatisk til den endelige pakke.

## <a name="fix-loading-external-libraries"></a>Ret indlæsning af eksterne biblioteker

Medtag i stedet for ny JS-fil efter biblioteker i `externalJS`-matrixen `pbiviz.json`. Eksempel:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Importér bibliotekerne i kilden. Eksempel for `lodash-es`:

```JS
import * as _ from "lodash-es";
```

hvor `_` er den globale variabel for biblioteket `lodash`.

## <a name="changes-in-the-visuals-sources"></a>Ændringer i visualkilderne

Den primære ændring konverterer interne moduler til eksterne moduler, da du ikke kan bruge eksterne moduler i interne moduler.

Disse ændringer beskriver ændringer, der er blevet anvendt på eksemplet med et liggende søjlediagram

Du kan finde en detaljeret beskrivelse af ændringerne nedenfor:

1. Fjern alle moduldefinitioner fra alle filer med [kildekode](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L153)

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Importér API-definitioner til brugerdefinerede visuals i Power BI](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L2).

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [Importér](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L12-L23) nødvendige grænseflader eller klasser fra internt `powerbi`-modul.

    ```typescript
    import PrimitiveValue = powerbi.PrimitiveValue; 
    import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions; 
    import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions; 
    import IVisualHost = powerbi.extensibility.visual.IVisualHost; 
    import IColorPalette = powerbi.extensibility.IColorPalette; 
    import IVisual = powerbi.extensibility.visual.IVisual; 
    import VisualObjectInstance = powerbi.VisualObjectInstance; 
    import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration; 
    import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions; 
    import Fill = powerbi.Fill; 
    import VisualTooltipDataItem = powerbi.extensibility.VisualTooltipDataItem; 
    import ISelectionManager = powerbi.extensibility.ISelectionManager; 
    ```

4. [Importér](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L1) D3.js-biblioteket

    ```typescript
    import * as d3 from "d3";
    ```

    Eller importér kun de påkrævede d3-biblioteksmoduler

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Importér](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L4-L10) de utils, klasser og grænseflader, der er defineret i visualprojektet, til hovedkildefilen

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>Importér CSS-typografier

Den nye version af Tools gør det muligt for udviklere at importere CSS, LESS-typografi direkte til TypeScript-koden.

Derfor ignorerer en compiler det tidligere brugte [typografiafsnit](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L22).

Hvis du vil bruge dit typografiark, skal du åbne ts-hovedfilen og tilføje følgende linje:  

```typescript
import "./../style/visual.less";
```  

Dine CSS, LESS-formater kompileres automatisk.  

### <a name="externaljs-section-in-pbivizjson"></a>Afsnittet externalJS i pbiviz.json

Værktøjerne [kræver ikke](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L20) en liste over `externalJS`, der kan indlæses i visualbundtet. Det skyldes, at Webpack indeholder alle importerede biblioteker.

**Afsnittet etxternalJS i pbivi.json skal være tom.**

Kald de typiske kommandoer `npm run package` for at oprette visualpakken eller `npm run start` starte udviklingsserveren.

## <a name="updating-d3js-library-to-version-5"></a>Opdatering af D3.js-biblioteket til version 5

Med den nye version af Tools kan du begynde at bruge den nye version af D3.js-biblioteket.

Kald kommandoerne for at opdatere D3 i dit visualprojekt

`npm install --save d3@5` for at installere det nye D3.js.

`npm install --save-dev @types/d3@5` for at installere de nye typedefinitioner til D3.js.

Der er flere væsentlige ændringer, og du skal ændre din kode, så den bruger det nye D3.js.

1. Grænsefladen `d3.Selection<T>` [blev ændret](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) til `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`

2. Du kan ikke anvende flere attributter med et enkelt kald af metoden `attr`. Du [skal overføre](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) hver attribut i et separat kald af metoden `attr`. Der gælder det [samme](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247) for metoden `style`.

3. I D3.js v4 introduceres den nye flettemetode. Denne metode bruges ofte til at flette, angive og opdatere valg efter en datasammenføjning. [Kald flettemetoden](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272) for at bruge D3 korrekt.

[Læs mere](https://github.com/d3/d3/blob/master/CHANGES.md) om ændringer i D3.js-biblioteket.

## <a name="babel"></a>Babel

Fra og med version 3.1 kan Tools bruge Babel til at kompilere ny moderne JS-kode til gammel ES5, der understøtter en lang række browsere.

Denne indstilling er som standard aktiveret, men du skal importere pakken [`@babel/polyfill`](https://babeljs.io/docs/en/babel-polyfill)manuelt.

Udfør kommandoen for at installere pakken,

`npm install --save @babel/polyfill`

og importér pakken på startpunktet for visualkoden (normalt er det filen 'src/visual.ts'):

`import "@babel/polyfill";`

Læs mere om Babel [i dokumentationen](https://babeljs.io/docs/en/).

Kør til sidst [webpack-visualizer](https://github.com/chrisbateman/webpack-visualizer) for at få vist visualkodebasen.  

![Statistik for visualkode](./media/webpack-stats.png)
