---
title: Overførsel til powerbi-visuals-tools version 3.x
description: Kom i gang med den nye version af powerbi-visuals-tools
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: d9af0ab870732990201ab3478d71fdafa9e13439
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818818"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-version-3x"></a>Overfør til den nye powerbi-visuals-tools version 3.*x*

Fra og med version 3 bruger Power BI Visuals Tools (powerbi-visuals-tools eller `pbiviz`) webpack til bygning af brugerdefinerede visualiseringer.
Den nye version giver udviklere mange forbedringer til oprettelse af visualiseringer:

- TypeScript version 3.*x* bruges som standard. Nomenklaturen er ændret fra og med TypeScript 1.5. [Få mere at vide om TypeScript](https://www.typescriptlang.org/docs/handbook/modules.html).

- ES6-moduler (ECMAScript 6) understøttes. Brug ES6-import nu i stedet for [externalJS](migrate-to-new-tools.md#configure-loading-of-external-libraries).

- Nye versioner af [D3v5](https://d3js.org/) (Data-Driven Documents) og andre ES6-modulbaserede biblioteker understøttes.

- Reduceret pakkestørrelse. [Tree shaking](https://webpack.js.org/guides/tree-shaking/) bruges af webpack til at fjerne ubrugt kode. Den reducerer JavaScript-koden og giver dig en bedre ydeevne ved indlæsning af visualiseringer.

- Forbedret API-ydeevne.

- Biblioteket Globalize.js [er integreret](migrate-to-new-tools.md#remove-the- globalizejs-library) i FormattingUtils.

- Power BI Visuals Tools bruger [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) til at vise visualiseringens kodebase.

Denne artikel beskriver alle overførselstrin for den nye version af Power BI Visuals Tools.

## <a name="backward-compatibility"></a>Bagudkompatibilitet

Den nye version af Tools gemmer oplysninger om bagudkompatibilitet for den gamle visualiserings kodebase, men kan kræve yderligere ændringer for at indlæse eksterne biblioteker.

De biblioteker, der understøtter modulsystemer, importeres som webpack-moduler. Alle andre biblioteker og kildekode for visualiseringen ombrydes til ét modul.

Globale variabler, f.eks. JQuery og Lodash, der blev brugt i de forrige Power BI Visuals Tools, er nu forældede. Hvis den gamle kode til din visualisering er afhængig af globale variabler, fungerer visualiseringen sandsynligvis ikke sammen med de nye værktøjer.

I den tidligere version af Power BI Visuals Tools skulle du definere en visuel klasse under modulet `powerbi.extensibility.visual`. Med den nye version af værktøjerne skal du i stedet definere en visuel klasse i den overordnede TypeScript-fil (.ts). Normalt er denne fil `src/visual.ts`.

## <a name="install-powerbi-visuals-tools"></a>Installer powerbi-visuals-tools

Kør denne kommando for at installere de nye værktøjer:

```cmd
npm install -g powerbi-visuals-tools
```

Den følgende kode er fra `package.json`-filen i det [visuelle lager for sampleBarChart](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L15), når det visuelle projekt er blevet opdateret til at fungere med de nye værktøjer:

```json
{
    "name": "visual",
    "version": "3.0.0",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "package": "pbiviz package",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
        "@types/d3": "5.7.2",
        "d3": "5.12.0",
        "powerbi-visuals-api": "^2.6.1",
        "powerbi-visuals-tools": "^3.1.7",
        "powerbi-visuals-utils-dataviewutils": "^2.2.1",
        "powerbi-visuals-utils-formattingutils": "^4.4.2",
        "powerbi-visuals-utils-interactivityutils": "^5.6.0",
        "powerbi-visuals-utils-tooltiputils": "^2.3.1",
        "tslint": "^5.20.0",
        "tslint-microsoft-contrib": "^6.2.0"
    }
}
```

## <a name="install-the-power-bi-custom-visuals-api"></a>Installer Power BI Custom Visuals API

Den nye version af powerbi-visual-tools indeholder ikke alle API-versioner. I stedet skal du installere en bestemt version af [powerbi-visuals-api](https://www.npmjs.com/package/powerbi-visuals-api)-pakken. Vælg den version af pakken, der stemmer overens med API-versionen af dine brugerdefinerede visualiseringer i Power BI. Pakken indeholder alle typedefinitioner til Power BI Custom Visuals API.

Føj `powerbi-visuals-api` til dine projektafhængigheder af et projekt ved at køre denne kommando:

```cmd
npm install --save-dev powerbi-visuals-api
```

Fjern også links til gamle API-typedefinitioner, da webpack automatisk indeholder typer fra `powerbi-visuals-api`. De tilsvarende ændringer findes i [package.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L14) og [tsconfig. json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L14).

## <a name="update-tsconfigjson"></a>Opdater tsconfig.json

Hvis du vil bruge eksterne moduler, skal du ændre indstillingen `out` til `outDir`. Brug f.eks. `"outDir": "./.tmp/build/",` i stedet for `"out": "./.tmp/build/visual.js",`.

Denne ændring er påkrævet, da TypeScript-filer kompileres til JavaScript-filer uafhængigt af hinanden. Det er derfor, at du ikke længere behøver at angive visual.js-filen som output.

Du kan også ændre indstillingen `target` til `ES6`, hvis du vil bruge moderne JavaScript som output. Denne ændring er [valgfri](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L7).

## <a name="update-custom-visuals-utilities"></a>Opdater hjælpeprogrammer til brugerdefinerede visualiseringer

Hvis du bruger en af [powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils)-pakkerne, skal du også opdatere dem til den seneste version. Det gør du ved at køre denne kommando:

```cmd
npm install powerbi-visuals-utils-<UTILNAME> --save
```

For at få den nye version med eksterne TypeScript-moduler skal du f.eks. køre: 

```cmd
npm install powerbi-visuals-utils-dataviewutils --save
```

Hvis du vil se et eksempel på en visualisering, der bruger alle `powerbi-visuals-utils`-pakker, skal du se [MekkoChart-lager](https://github.com/Microsoft/powerbi-visuals-mekkochart).

## <a name="remove-the-globalizejs-library"></a>Fjern biblioteket Globalize.js

Den nye version af [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) omfatter Globalize.js. Så du behøver ikke at inkludere dette bibliotek manuelt i projektet. Alle påkrævede lokaliseringer føjes automatisk til den endelige pakke.

## <a name="configure-loading-of-external-libraries"></a>Konfigurer indlæsning af eksterne biblioteker

Medtag nye JavaScript-filer efter biblioteker i `externalJS`-matrixet for `pbiviz.json`. Eksempel:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Importér bibliotekerne i din kildekode. Du kan f.eks. bruge denne sætning til `lodash-es`:

```JS
import * as _ from "lodash-es";
```

I det foregående eksempel er `_` den globale variabel for biblioteket `lodash`.

## <a name="make-changes-in-the-sources-of-your-visuals"></a>Foretag ændringer i kilderne til dine visualiseringer

Den primære ændring, du skal foretage, er at konvertere interne moduler til eksterne moduler. Du kan ikke bruge eksterne moduler i interne moduler.

Her er en detaljeret beskrivelse af de ændringer, du skal foretage. Ændringerne er beskrevet i konteksten af den brugerdefinerede visualiserings kodeeksempel på søjlediagrammet:

1. Fjern alle moduldefinitioner fra hver fil med [kildekode](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbL1-L3):

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Importér API-definitioner til brugerdefinerede visualiseringer i Power BI](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR4):

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [Importér de nødvendige grænseflader eller klasser](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR12-R35) fra det `powerbi`interne modul.

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

4. [Importér D3.js-biblioteket](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR2):

    ```typescript
    import * as d3 from "d3";
    ```

    Eller importér kun de påkrævede D3-biblioteksmoduler:

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Importér de hjælpeprogrammer, klasser og grænseflader, der er defineret i det visuelle projekt](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR38-R41), til hovedkildefilen:

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

Den nye version af værktøjet gør det muligt for udviklere at importere `CSS`- og `Less`-typografier direkte til TypeScript-koden. Afsnittet [Styles](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/pbiviz.json#L21), der blev brugt tidligere, ignoreres nu af compileren.

Hvis du vil bruge dit typografiark, skal du åbne TypeScript-filen (.ts) og tilføje denne linje:  

```typescript
import "./../style/visual.less";
```  

Dine `CSS`- og `Less`-typografier kompileres automatisk.

### <a name="externaljs-section-in-pbivizjson"></a>Afsnittet externalJS i pbiviz.json

Værktøjerne [kræver ikke en liste over `externalJS`-biblioteker](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-a1a7bbee7e7d2f9d449f4b534532bcf2R20) for at indlæses i det visuelle bundt, da webpack indeholder alle importerede biblioteker.

> [!NOTE]
> I `pbiviz.json` skal du lade afsnittet `externalJS` være tomt.

Brug den typiske kommando `npm run package` for at oprette den visuelle pakke eller `npm run start` for at starte udviklingsserveren.

## <a name="update-the-d3js-library-to-version-5"></a>Opdater D3.js-biblioteket til version 5

Med det nye visualiseringsværktøj kan du begynde at bruge den nye version af D3.js-biblioteket. Kør disse kommandoer for at opdatere D3 i dit visualiseringsprojekt:

- `npm install --save d3@5` for at installere det nye D3.js.

- `npm install --save-dev @types/d3@5` for at installere de nye typedefinitioner til D3.js.

> [!IMPORTANT]
> D3 version 5 introducerer adskillige vigtige ændringer.

Rediger din kode for at arbejde med den nye D3.js:

- Grænsefladen `d3.Selection<T>` [blev ændret](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) til `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`.

- Du kan ikke anvende flere attributter ved at bruge et enkelt kald af metoden `attr`. I stedet skal du [sende hver attribut i et separat kald](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) til `attr`. Foretag også [særskilte kald til metoden `style`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247).

- D3.js version 4 introducerede den nye `merge`-metode. Denne metode bruges ofte til at flette `enter`- og `update`-valg efter en datasammenføjning. Hvis du vil bruge D3 korrekt, skal du [kalde metoden `merge`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272).

[Læs mere](https://github.com/d3/d3/blob/master/CHANGES.md) om ændringer i D3.js-biblioteket.

## <a name="install-babel-and-core-js"></a>Installer Babel og core-js

Fra og med version 3.1 kan visualiseringsværktøjet bruge Babel til at kompilere moderne JavaScript-kode til gammel ES5 (ECMAScript 5), der understøtter en lang række browsere.

Babel-indstillingen er som standard aktiveret, men du skal importere pakken [`core-js`](https://www.npmjs.com/package/core-js) manuelt. Kør denne kommando for at installere pakken:

```cmd
npm install --save core-js
```

Importér derefter pakken til startpunktet for visualiseringskoden. Det er typisk filen 'src/visual.ts'.

```JS
import "core-js/stable";
```

Læs mere om Babel [i dokumentationen](https://babeljs.io/docs/en/).
