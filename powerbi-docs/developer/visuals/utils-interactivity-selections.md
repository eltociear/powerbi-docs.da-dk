---
title: Interaktivitetsutils til Power BI-visuals
description: I artikIen beskrives det, hvordan du føjer valg til Power BI-visuals ved hjælp af interaktivitetsutils
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: e2587140d5436552e26be90c67eb5e6240bf6a1d
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/02/2019
ms.locfileid: "74696134"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>Interaktivitetsutils til Microsoft Power BI-visuals

Interaktivitetsutils er en række funktioner og klasser, der forenkler implementeringen af krydsvalg og krydsfiltrering for brugerdefinerede visuals i Power BI.

## <a name="installation"></a>Installation

> [!NOTE]
> Hvis du fortsætter med at bruge den gamle version af powerbi-visuals-tools (et versionsnummer mindre end 3.x.x), skal du installere den nye version (3.x.x).

> [!IMPORTANT]
> De nye opdateringer af interaktivitetsutils understøtter kun den nyeste version af Tools. [Læs mere om, hvordan du opdaterer din visualkode, så den kan bruges sammen med de nyeste værktøjer](migrate-to-new-tools.md)

Hvis du vil installere pakken, skal du køre følgende kommando i mappen med din aktuelle brugerdefinerede visual:

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

Fra version 3,0 eller nyere skal du også installere ```powerbi-models``` for at løse problemer med afhængigheder.

```bash
npm install powerbi-models --save
```

For at bruge interaktivitetsutils skal du importere den påkrævede komponent i visual'ets kildekode.

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
```

### <a name="including-css-artifacts-to-the-custom-visual"></a>Inkludering af CSS-artefakter i det brugerdefinerede visual

Hvis du vil bruge pakken sammen med dine brugerdefinerede visuals, skal du importere følgende CSS-fil til filen `your.less`:

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

Du får derefter følgende filstruktur:

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

> [!NOTE]
> Du skal importere. css-filen som en .less-fil, da Power BI Visuals Tools samler de eksterne CSS-regler.

## <a name="usage"></a>Forbrug

### <a name="define-interface-for-data-points"></a>Definer grænsefladen for datapunkter

Datapunkter indeholder normalt valg og værdier. Grænsefladen udvider `SelectableDataPoint`-grænsefladen. `SelectableDataPoint` indeholder allerede egenskaber:

```typescript
  /** Flag for identifying that data point was selected */
  selected: boolean;
  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;
  /**
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points should select based
   * only on series even if they exist as category/series intersections.
   */
  specificIdentity?: powerbi.extensibility.ISelectionId;
```

Det første trin i brugen af interaktivitetsutils er oprettelsen af en forekomst af interaktivitetsutils og lagring af objektet som en egenskab for visual'et

```typescript
export class Visual implements IVisual {
  // ...
  private interactivity: interactivityBaseService.IInteractivityService<VisualDataPoint>;
  // ...
  constructor(options: VisualConstructorOptions) {
      // ...
      this.interactivity = interactivitySelectionService.createInteractivitySelectionService(this.host);
      // ...
  }
}
```

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}
```

Det andet trin er at udvide klassen for basisfunktionsmåden:

> [!NOTE]
> BaseBehavior introducerede i [5.6. x-versionen af interaktivitetsutils](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0). Hvis du bruger den gamle version, skal du oprette funktionsmådeklassen fra eksemplet nedenfor (`BaseBehavior`-klassen er den samme):

Definer grænsefladen for indstillinger for funktionsmådeklassen:

```typescript
import { SelectableDataPoint } from "./interactivitySelectionService";

import {
    IBehaviorOptions,
    BaseDataPoint
} from "./interactivityBaseService";

export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {
    /** D3 selection object of main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;
    /** D3 selection object of some element on backgroup to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
}
```

Definer en klasse for `visual behavior`. Den klasse, der er ansvarlig for håndtering af musehændelserne `click`, `contextmenu`.
Når en bruger klikker på dataelementer, kalder visual'et valghandleren for at vælge datapunkter. Hvis brugeren klikker på baggrunds elementet i visual'et, kalder den clear-valghandleren. Og klassen har tilsvarende metoder: `bindClick`, `bindClearCatcher`, `bindContextMenu`.

```typescript
export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {
    /** D3 selection object of main elements on the chart */
    protected options: BaseBehaviorOptions<SelectableDataPointType>;
    protected selectionHandler: ISelectionHandler;

    protected bindClick() {
      // ...
    }

    protected bindClearCatcher() {
      // ...
    }

    protected bindContextMenu() {
      // ...
    }

    public bindEvents(
        options: BaseBehaviorOptions<SelectableDataPointType>,
        selectionHandler: ISelectionHandler): void {
      // ...
    }

    public renderSelection(hasSelection: boolean): void {
      // ...
    }
}
```

Du kan også udvide `BaseBehavior`-klassen:

```typescript
import powerbi from "powerbi-visuals-api";
import { interactivitySelectionService, baseBehavior } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}

export class Behavior extends baseBehavior.BaseBehavior<VisualDataPoint> {
  // ...
}
```

Hvis du vil håndtere klik på elementer, skal du kalde metoden `on` for D3-valgobjektet (også for elementsSelection og clearCatcherSelection):

```typescript
protected bindClick() {
  const {
      elementsSelection
  } = this.options;

  elementsSelection.on("click", (datum) => {
      const mouseEvent: MouseEvent = getEvent() as MouseEvent || window.event as MouseEvent;
      mouseEvent && this.selectionHandler.handleSelection(
          datum,
          mouseEvent.ctrlKey);
  });
}
```

Tilføj en lignende handler, så hændelsen `contextmenu` kalder metoden `showContextMenu` for valgstyringen:

```typescript
protected bindContextMenu() {
    const {
        elementsSelection
    } = this.options;

    elementsSelection.on("contextmenu", (datum) => {
        const event: MouseEvent = (getEvent() as MouseEvent) || window.event as MouseEvent;
        if (event) {
            this.selectionHandler.handleContextMenu(
                datum,
                {
                    x: event.clientX,
                    y: event.clientY
                });
            event.preventDefault();
        }
    });
}
```

Interaktivitetsutils kalder `bindEvents`-metoder for at tildele funktioner til handlere, føje kald af `bindClick`, `bindClearCatcher`og `bindContextMenu` til metoden `bindEvents`:

```typescript
  public bindEvents(
      options: BaseBehaviorOptions<SelectableDataPointType>,
      selectionHandler: ISelectionHandler): void {

      this.options = options;
      this.selectionHandler = selectionHandler;

      this.bindClick();
      this.bindClearCatcher();
      this.bindContextMenu();
  }
```

Metoden `renderSelection` er ansvarlig for at opdatere elementers visualtilstand i diagrammet.

Eksempel på metoden `renderSelection` for implementering:

```typescript
public renderSelection(hasSelection: boolean): void {
    this.options.elementsSelection.style("opacity", (category: any) => {
        if (category.selected) {
            return 0.5;
        } else {
            return 1;
        }
    });
}
```

Det sidste trin er oprettelse af en forekomst af `visual behavior` og kald af metoden `bind` for forekomsten af interaktivitetsutils:

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge` er et D3-valgobjekt, som repræsenterer alle elementer, der kan vælges, i visual'et.

* `select(this.target)` er et D3-valgobjekt, som repræsenterer visual'ets DOM-hovedelementer.

* `this.categories` er datapunkter med elementer, hvor grænsefladen er `VisualDataPoint` (eller `categories: VisualDataPoint[];`)

* `this.behavior` er en ny forekomst af `visual behavior`

  der er oprettet i visualkonstruktøren:

  ```typescript
  export class Visual implements IVisual {
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.behavior = new Behavior();
    }
    // ...
  }
  ```

Nu er dit visual klar til at håndtere valg.

## <a name="next-steps"></a>Næste trin

* [Læs om, hvordan du kan håndtere valg ved skift af bogmærker](bookmarks-support.md#visuals-with-selection)

* [Læs om, hvordan du tilføjer en genvejsmenu for visualdatapunkter](context-menu.md)

* [Læs om, hvordan du bruger valgstyringen til at føje valg til Power BI-visuals](selection-api.md)
