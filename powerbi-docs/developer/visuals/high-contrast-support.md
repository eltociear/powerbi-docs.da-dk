---
title: Understøttelse af tilstand med stor kontrast
description: Sådan føjer du tilstanden med understøttelse af stor kontrast til visuelle elementer i Power BI
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: cb77ea012fdfdbd5be62c58c6f9b94a0355db1a9
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424924"
---
# <a name="high-contrast-mode-support"></a>Understøttelse af tilstand med stor kontrast

Indstillingen *Stor kontrast* i Windows gør det nemmere at se tekst og apps ved at bruge tydeligere farver.
Læs mere om [understøttelse af stor kontrast i Power BI](https://powerbi.microsoft.com/blog/power-bi-desktop-june-2018-feature-summary/#highContrast).

Hvis du tilføjer understøttelse af stor kontrast til din visualisering, skal du benytte følgende fremgangsmåde:

1. Ved init: Kontrollér, om Power BI er i en tilstand med stor kontrast, og hvis det er tilfældet, kan du hente aktuelle farver med stor kontrast.
2. Alle opdateringer: Rediger den måde, det visuelle element gengives på, for at gøre det nemmere at se det.

Visualiseringen PowerBI-visuals-sampleBarChart understøtter implementering af stor kontrast.

Du kan finde flere oplysninger i [lageret med PowerBI-visuals-sampleBarChart-visualiseringen](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/61011c82b66ca0d3321868f1d089c65101ca42e6).

## <a name="on-init"></a>Ved init

ColorPalette-medlemmet af `options.host` har flere egenskaber for tilstand med stor kontrast. Brug disse egenskaber til at afgøre, om tilstanden med stor kontrast er aktiv, og hvilke farver der skal bruges.

### <a name="detect-that-power-bi-is-in-high-contrast-mode"></a>Kontrollér, om Power BI er i tilstanden med stor kontrast

Hvis `host.colorPalette.isHighContrast` er `true`, er tilstanden med stor kontrast aktiv, og det visuelle element oprettes i overensstemmelse hermed.

### <a name="get-high-contrast-colors"></a>Hent farver med stor kontrast

I tilstanden med stor kontrast bør dit visuelle element begrænse sig selv til følgende farver:

* **Forgrundsfarven** bruges til at tegne streger, ikoner, tekst og konturer eller udfyldning af figurer.
* **Baggrundsfarven** bruges til baggrunden og som fyldfarve for skitserede figurer.
* **Den valgte forgrundsfarve** bruges til at angive et markeret eller aktivt element.
* **Linkfarven** bruges kun til hyperlinktekst.

> [!NOTE]
> Hvis der er behov for en sekundær farve, kan forgrundsfarven bruges sammen med en vis uigennemsigtighed (indbyggede visuelle elementer i Power BI anvender 40 % uigennemsigtighed). Brug dette med måde for at gøre det nemt at se de visuelle detaljer.

Du kan gemme disse værdier under initialisering:

```typescript
private isHighContrast: boolean;

private foregroundColor: string;
private backgroundColor: string;
private foregroundSelectedColor: string;
private hyperlinkColor: string;
//...

constructor(options: VisualConstructorOptions) {
    this.host = options.host;
    let colorPalette: ISandboxExtendedColorPalette = host.colorPalette;
    //...
    this.isHighContrast = colorPalette.isHighContrast;
    if (this.isHighContrast) {
        this.foregroundColor = colorPalette.foreground.value;
        this.backgroundColor = colorPalette.background.value;
        this.foregroundSelectedColor = colorPalette.foregroundSelected.value;
        this.hyperlinkColor = colorPalette.hyperlink.value;
    }
```

Eller du kan gemme objektet `host` under initialisering og få adgang til de relevante `colorPalette`-egenskaber under opdateringen.

## <a name="on-update"></a>Ved opdatering

De specifikke implementeringer af understøttelse med stor kontrast varierer fra visualisering til visualisering og afhænger af detaljerne i det grafiske design. Tilstanden med stor kontrast kræver typisk et lidt andet design end standarddesignet, så det er nemt at skelne detaljerne fra hinanden med de begrænsede farver.

Her er nogle retningslinjer efterfulgt af indbyggede visualiseringer i Power BI:

* Alle datapunkter bruger samme farve (forgrund).
* Al tekst samt alle akser, pile, linjer osv. bruger forgrundsfarve.
* Tykke figurer tegnes som konturer med tykke strøg (mindst to pixel) og baggrundsfarvefyld.
* Når det er relevant, skelnes der mellem datapunkter med forskellige markørfigurer, og til datalinjer bruges forskellige tankestreger.
* Når et dataelement fremhæves, ændres uigennemsigtigheden for alle andre elementer til 40 %.
* I forbindelse med udsnitsværktøjer bruger aktive filterelementer den farve, der er valgt til forgrunden.

I eksemplet med søjlediagrammet tegnes alle linjer med en to pixel tyk forgrundskontur og baggrundsfyld. Sammenlign den måde, det ser ud på, med standardfarver og med et par temaer med stor kontrast:

![Eksempel på søjlediagram med standardfarver](./media/hc-samplebarchart-standard.png)
![Eksempel på søjlediagram med farvetemaet *Dark #2*](./media/hc-samplebarchart-dark2.png)
![Eksempel på søjlediagram med farvetemaet *White*](./media/hc-samplebarchart-white.png)

Her er ét sted i funktionen `visualTransform`, der blev ændret for at understøtte stor kontrast, den kaldes som en del af gengivelsen under `update`:

### <a name="before"></a>Før

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    let defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(category.values[i] + '').value
        }
    };

    barChartDataPoints.push({
        category: category.values[i] + '',
        value: dataValue.values[i],
        color: getCategoricalObjectValue<Fill>(category, i, 'colorSelector', 'fill', defaultColor).solid.color,
        selectionId: host.createSelectionIdBuilder()
            .withCategory(category, i)
            .createSelectionId()
    });
}
```

### <a name="after"></a>Efter

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    const color: string = getColumnColorByIndex(category, i, colorPalette);

    const selectionId: ISelectionId = host.createSelectionIdBuilder()
        .withCategory(category, i)
        .createSelectionId();

    barChartDataPoints.push({
        color,
        strokeColor,
        strokeWidth,
        selectionId,
        value: dataValue.values[i],
        category: `${category.values[i]}`,
    });
}

//...

function getColumnColorByIndex(
    category: DataViewCategoryColumn,
    index: number,
    colorPalette: ISandboxExtendedColorPalette,
): string {
    if (colorPalette.isHighContrast) {
        return colorPalette.background.value;
    }

    const defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(`${category.values[index]}`).value,
        }
    };

    return getCategoricalObjectValue<Fill>(category, index, 'colorSelector', 'fill', defaultColor).solid.color;
}
```
