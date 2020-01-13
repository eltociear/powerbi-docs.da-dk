---
title: Struktur for visual-projekter i Power BI
description: I artiklen beskrives en struktur for visual-projekter
author: zBritva
ms.author: v-ilgali
ms.reviewer: ''
ms.service: powerbi
ms.topic: tutorial
ms.subservice: powerbi-custom-visuals
ms.date: 03/15/2019
ms.openlocfilehash: 728aba749f80710fdc0bb1e180b3318e63caa88c
ms.sourcegitcommit: 331ebf6bcb4a5cdbdc82e81a538144a00ec935d4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/28/2019
ms.locfileid: "75542087"
---
# <a name="power-bi-visual-project-structure"></a>Struktur for visual-projekter i Power BI

Når du har kørt pbiviz new `<visual project name>`, opretter værktøjet den grundlæggende struktur for filer og mapper i mappen `<visual project name>`.

## <a name="visual-project-structure"></a>Struktur for visual-projekter

![Struktur for visual-projekter](./media/visual-project-structure.png)

* `.vscode` – indeholder projektindstillinger for VS-kode. Hvis du vil konfigurere dit arbejdsområde, skal du redigere filen `.vscode/settings.json`. Læs mere [om indstillingerne for VS-kode i dokumentationen](https://code.visualstudio.com/docs/getstarted/settings)

* Mappen `assets` indeholder kun filen `icon.png`. Værktøjet bruger denne fil som et ikon for visual'et i ruden Visualisering i Power BI.

    ![Ruden Visualisering](./media/visualization-pane-analytics-tab.png)

* Mappen `node_modules` indeholder alle pakker [, der er installeret af nodepakkestyringen](https://docs.npmjs.com/files/folders.html).

* Mappen `src` indeholder kildekoden til visual'et. Der oprettes som standard to filer i værktøjet:

  * `visual.ts` – visual'ets hovedkildekode.

  * `settings.ts` – visual'ets indstillingskode. Klasserne i filen forenkler [arbejdet med visual-egenskaberne](./objects-properties.md#properties).

* Mappen `style` indeholder `visual.less` filen med typografier til visual'et.

* Filen `capabilities.json` visual'ets primære egenskaber og indstillinger. Den gør det muligt for visual'et at deklarere understøttede funktioner, objekter, egenskaber og tilknytning af datavisning.

    Læs mere [om egenskaber i dokumentation](./capabilities.md).

* `package-lock.json` genereres automatisk for alle handlinger, hvor NPM ændrer enten `node_modules` træet eller `package.json`.

    Læs mere [om `package-lock.json` i den officielle dokumentation til NPM](https://docs.npmjs.com/files/package-lock.json).

* `package.json` beskriver projektpakken. Den indeholder normalt oplysninger om projektet og forfatterne, beskrivelsen af og afhængighederne i projektet.

    Læs mere [om `package.json` i den officielle dokumentation til NPM](https://docs.npmjs.com/files/package.json.html).

* `pbiviz.json` indeholder visual-metadataene. Angiv metadataene for visual'et i denne fil.

    Typisk indhold i fil:

  ```json
    {
        "visual": {
            "name": "<visual project name>",
            "displayName": "<visual project name>",
            "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",
            "visualClassName": "Visual",
            "version": "1.0.0",
            "description": "",
            "supportUrl": "",
            "gitHubUrl": ""
        },
        "apiVersion": "2.6.0",
        "author": { "name": "", "email": "" },
        "assets": { "icon": "assets/icon.png" },
        "externalJS": null,
        "style": "style/visual.less",
        "capabilities": "capabilities.json",
        "dependencies": null,
        "stringResources": []
    }
  ```

    hvor

  * `name` – internt navn på det visual'et.

  * `displayName` – navnet på visual'et i brugergrænsefladen til Power BI.

  * `guid` – entydigt id for visual'et.

  * `visualClassName` –navnet på den primære klasse for visual'et. Power BI opretter forekomsten af denne klasse for at begynde at bruge visual'et i Power BI-rapporten.

  * `version` – visual'ets versionsnummer.

  * `author` – indeholder navnet på forfatteren og kontaktmail.

  * `icon` i `assets` – stien til visual'ets ikonfil.

  * `externalJS` indeholder stier til JS-biblioteker, der bruges i visual'et.

    > [!IMPORTANT]
    > Den nyeste version af værktøjet 3. x. x eller nyere bruger ikke `externalJS` længere.

  * `style` er stien til typografifiler.

  * `capabilities` er stien til filen `capabilities.json`.

  * `dependencies` er stien til filen `dependencies.json`. `dependencies.json` indeholder oplysninger om R-pakker, der bruges i R-baserede visuals.

  * `stringResources` er en matrix af stier til filer med lokaliseringer.

  Læs mere [om lokalisering i visuals i dokumentationen](./localization.md)

* `tsconfig.json` er en konfigurationsfil til TypeScript.

    Læs mere [om konfiguration af TypeScript i den officielle dokumentation](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

    `tsconfig.json` i afsnittet `files` skal indeholde stien til *. ts-filen, hvor visual'ets primære klasse er placeret som angivet i egenskaben `visualClassName` for filen `pbiviz.json`.

* Filen `tslint.json` indeholder TSLint-konfigurationen.

    Læs mere [om konfiguration af TSLint i den officielle dokumentation](https://palantir.github.io/tslint/usage/configuration/)

## <a name="next-steps"></a>Næste trin

* Læs mere [om visual-konceptet](./power-bi-visuals-concept.md) for at få en bedre forståelse af, hvordan visual'et, brugeren og Power BI interagerer med hinanden.

* Begynd at udvikle dine egne Power BI-visuals fra bunden [med en trinvis vejledning](./custom-visual-develop-tutorial.md).
