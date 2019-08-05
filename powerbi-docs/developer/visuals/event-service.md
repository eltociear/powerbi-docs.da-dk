---
title: Gengivelse af hændelser
description: Power BI-visualiseringer kan give Power BI besked om, at de er klar til at blive eksporteret til Power Point/PDF
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 46166b3503a770e033b98474fcf9240235296cc2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425085"
---
# <a name="event-service"></a>Hændelsestjeneste

Den nye API består af tre metoder (startet, afsluttet eller mislykket), som skal kaldes under gengivelse.

Når gengivelsen starter, kalder den brugerdefinerede visualiseringskode metoden renderingStarted for at angive, at gengivelses processen er startet.

Hvis gengivelsen er fuldført, kalder den brugerdefinerede visualiseringskode øjeblikkeligt metoden `renderingFinished`, hvilket giver lyttefunktionen (**primært "eksportér til PDF" og "eksportér til PowerPoint"** ) besked om, at visualiseringens afbildning er klar.

Hvis der opstod problemer under gengivelsesprocessen, kan det forhindre, at den brugerdefinerede visualisering fuldføres korrekt. Den brugerdefinerede visualiseringskode bør kalde metoden `renderingFailed`, hvilket giver lyttefunktionen besked om, at gengivelsesprocessen ikke er fuldført. Denne metode indeholder også en valgfri streng med årsagen til fejlen.

## <a name="usage"></a>Forbrug

```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    eventService: IVisualEventService ;
}

/**
 * An interface for reporting rendering events
 */
export interface IVisualEventService {
    /**
     * Should be called just before the actual rendering was started. 
     * Usually at the very start of the update method.
     *
     * @param options - the visual update options received as update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Shoudl be called immediately after finishing successfull rendering.
     * 
     * @param options - the visual update options received as update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering failed with optional reason string
     * 
     * @param options - the visual update options received as update parameter
     * @param reason - the option failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="simple-sample-the-visual-hasnt-any-animations-on-rendering"></a>Enkelt eksempel. Visualiseringen indeholder ingen animationer, der kan gengives

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

### <a name="sample-the-visual-with-animation"></a>Eksempel. Visualisering med animation

Hvis visualiseringen indeholder animationer eller asynkrone funktioner til gengivelse, skal metoden `renderingFinished` kaldes efter animationen eller inde i den asynkrone funktion.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // read more https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>Gengivelse af hændelser til visuel certificering

Understøttelsen af gengivelseshændelser fra visualiseringen er en af kravene til certificering af visualiseringer. Læs mere om [certificeringskrav](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements)
