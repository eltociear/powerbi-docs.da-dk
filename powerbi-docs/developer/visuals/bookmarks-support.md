---
title: Bogmærker
description: Power BI Visuals kan håndtere skift mellem bogmærker
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 90e3fc73cd49a5c84a5c2acc68a8cf5e0e4aa42b
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425499"
---
# <a name="add-bookmarks-support-for-power-bi-visuals"></a>Tilføj understøttelse af bogmærker i Power BI Visuals

Bogmærker i Power BI-rapporter giver mulighed for at registrere en konfigureret visning af en rapportside med visualiseringens markeringstilstand og filtreringstilstand. Dette kræver dog yderligere handlinger i forbindelse med brugerdefinerede visualiseringer for at understøtte bogmærket og reagere korrekt på ændringer.

Få mere at vide om bogmærker i [dokumentationen](https://docs.microsoft.com/power-bi/desktop-bookmarks)

## <a name="report-bookmarks-support-in-your-visual"></a>Understøttelse af bogmærker i rapporter for din visualisering

Hvis din visualisering interagerer med andre visualiseringer, vælger datapunkter eller filtrerer andre visualiseringer, skal du gendanne tilstanden fra egenskaberne.

## <a name="how-to-add-report-bookmarks-support"></a>Sådan tilføjer du understøttelse af bogmærker i rapporter

1. Installér (eller opdater) det krævede værktøj: `powerbi-visuals-utils-interactivityutils` (https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) ) version 3.0.0 eller nyere. Det indeholder flere klasser til redigering af valg af tilstand eller filter. Det er påkrævet til visualiseringer med filtrering og alle visualiseringer, der bruger `InteractivityService`.

2. Opdater Visual API til 1.11.0 for at kunne bruge `registerOnSelectCallback` i forekomster af `SelectionManager`. Det er påkrævet for visualiseringer uden filtrering, der bruger den almindelige `SelectionManager` i stedet for `InteractivityService`.

### <a name="how-custom-visuals-interact-with-power-bi-in-the-report-bookmarks-scenario"></a>Sådan interagerer brugerdefinerede visualiseringer med Power BI i scenarier med bogmærker i rapporter

Lad os se på følgende eksempel: En bruger opretter flere bogmærker på rapportsiden med forskellig markeringstilstand i hvert bogmærke.

Først vælger brugeren et datapunkt i din visualisering. Visualiseringen interagerer med Power BI og andre visualiseringer ved at sende valgene til værten. Derefter vælger brugeren "Tilføj" i `Bookmark panel`, og Power BI gemmer de aktuelle valg til det nye bogmærke.

Det sker gentagne gange, når brugeren ændrer valget og tilføjer nye bogmærker.
Når bogmærkerne er oprettet, kan brugeren skifte mellem dem.

Når brugerne vælger et bogmærke, gendanner Power BI det gemte filter eller den gemte markeringstilstand, som sendes til visualiseringerne. Andre visualiseringer markeres eller filtreres i overensstemmelse med den tilstand, der er gemt i bogmærket. Power BI-værten er ansvarlig for handlingerne. Din visualisering er ansvarlig for at afspejle den nye markeringstilstand korrekt (f.eks. ændre farve på de gengivne datapunkter).

Den nye markeringstilstand kommunikeres til visualiseringen gennem metoden `update`. Argumentet `options` indeholder en særlig egenskab: `options.jsonFilters`. Det er et JSONFilter, og egenskaben kan indeholde værdierne `Advanced Filter` og `Tuple Filter`.

Visualiseringen skal gendanne filterværdierne for at vise den tilsvarende tilstand for visualiseringen for det valgte bogmærke.

Alternativt kan du bruge den specielle metode `registerOnSelectCallback` i ISelectionManager, der er registreret til callback-funktionskald, hvis visualiseringen kun bruger markeringer.

### <a name="visuals-with-selections"></a>Visualiseringer med markeringer

Hvis dine visualiseringer interagerer med andre visualiseringer ved hjælp af [markeringer](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md). Du kan tilføje bogmærker på to måder.

* Du kan bruge metoden `FilterManager.restoreSelectionIds`, hvis du **ikke har brugt [`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** tidligere i din visualisering.

* Hvis din visualisering allerede bruger **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** til at administrere markeringer, skal du bruge metoden `applySelectionFromFilter` i forekomster af `InteractivityService`.

#### <a name="using-iselectionmanagerregisteronselectcallback"></a>Brug af `ISelectionManager.registerOnSelectCallback`

Når en bruger klikker på bogmærker, kalder Power BI metoden `callback` for visualiseringen med de tilsvarende markeringer. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

Lad os antage, at du har et datapunkt i din visualisering, der er oprettet i metoden [`'visualTransform'`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74).

Desuden ser `datapoints` således ud:

```typescript
visualDataPoints.push({
    category: categorical.categories[0].values[i],
    color: getCategoricalObjectValue<Fill>(categorical.categories[0], i, 'colorSelector', 'fill', defaultColor).solid.color,
    selectionId: host.createSelectionIdBuilder()
        .withCategory(categorical.categories[0], i)
        .createSelectionId(),
    selected: false
});
```

Du har dermed `visualDataPoints` som dine datapunkter, og et `ids`-matrix overføres til funktionen `callback`.

På dette tidspunkt skal visualiseringen sammenligne matricen i `ISelectionId[]` med markeringen i din `visualDataPoints`-matrix og angive de tilsvarende datapunkter som markeret.

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        visualDataPoints.forEach(dataPoint => {
            ids.forEach(bookmarkSelection => {
                if (bookmarkSelection.equals(dataPoint.selectionId)) {
                    dataPoint.selected = true;
                }
            });
        });
    });
);
```

Når datapunkterne er opdateret, afspejler de den aktuelle markeringstilstand, der er gemt i objektet `filter`. Når datapunkterne derefter gengives, vil markeringstilstanden for den brugerdefinerede visualisering matche tilstanden i bogmærket.

### <a name="using-interactivityservice-for-control-selections-in-the-visual"></a>Brug af `InteractivityService` til at styre markeringerne i visualiseringen

Hvis den visualisering bruger `InteractivityService`, behøver du ikke yderligere handlinger for at understøtte bogmærker i din visualisering.

Dette værktøj håndterer visualiseringens markeringstilstand, når brugeren vælger bogmærker.

### <a name="visuals-with-filter"></a>Visualiseringer med filter

Lad os antage, at visualiseringen opretter et filter for data efter datoområde. Det betyder, at `startDate` og `endDate` definerer starten og slutningen på området.
Visualiseringen opretter et avanceret filter og kalder værtsmetoden `applyJsonFilter` for at filtrere data efter de relevante betingelser.
`target` er den tabel, der bruges til filtrering.

```typescript
import { AdvancedFilter } from "powerbi-models";

const filter: IAdvancedFilter = new AdvancedFilter(
    target,
    "And",
    {
        operator: "GreaterThanOrEqual",
        value: startDate
            ? startDate.toJSON()
            : null
    },
    {
        operator: "LessThanOrEqual",
        value: endDate
            ? endDate.toJSON()
            : null
    });

this.host.applyJsonFilter(
    filter,
    "general",
    "filter",
    (startDate && endDate)
        ? FilterAction.merge
        : FilterAction.remove
);
```

Hver gang en bruger klikker på et bogmærke, modtager den brugerdefinerede visualisering et `update`-kald.

Den brugerdefinerede visualisering skal kontrollere filteret i objektet:

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

Hvis `filter`-objektet ikke er null, skal visualiseringen gendanne filterbetingelserne fra objektet:

```typescript
const jsonFilters: AdvancedFilter = this.options.jsonFilters as AdvancedFilter[];

if (jsonFilters
    && jsonFilters[0]
    && jsonFilters[0].conditions
    && jsonFilters[0].conditions[0]
    && jsonFilters[0].conditions[1]
) {
    const startDate: Date = new Date(`${jsonFilters[0].conditions[0].value}`);
    const endDate: Date = new Date(`${jsonFilters[0].conditions[1].value}`);

    // apply restored conditions
} else {
    // apply default settings
}
```

Derefter skal visualiseringen ændre sin interne tilstand – datapunkter og visualiseringsobjekter (linjer, rektangler osv.) – så de afspejler de aktuelle betingelser.

> [!IMPORTANT]
> I scenariet med bogmærker i rapporter skal visualiseringen ikke kalde `applyJsonFilter` for at filtrere andre visualiseringer – de er allerede filtreret af Power BI.

Visualiseringen Tidslinjeudsnitsværktøj skifer områdevælger, så den svarer til dataområderne.

Få mere at vide i [lageret med Tidslinjeudsnitsværktøj](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df).

### <a name="filter-state-to-save-visual-properties-in-bookmarks"></a>Brug af filterState til at gemme visualiseringens egenskaber i bogmærker

Egenskaben `filterState` opretter en egenskab for en del af filtrering. Visualiseringen kan gemme forskellige værdier i bogmærker.

Hvis du vil gemme egenskabens værdi for filtertilstanden, skal objektegenskaben være markeret som `"filterState": true` i `capabilities.json`.

Eksempel: `Timeline Slicer` gemmer værdier for egenskaben `Granularity` i filteret. Desuden giver det mulighed for at ændre den aktuelle kornethed, hvis brugeren ændrer bogmærke.

Få mere at vide i [lageret med Tidslinjeudsnitsværktøj](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334).
