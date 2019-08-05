---
title: API til filtre i visualiseringer
description: Sådan filtrerer Power BI-visualiseringer andre visualiseringer
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 50e9601faf497675ebc3f24609a856a600e3bcb1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425039"
---
# <a name="power-bi-visual-filters-api"></a>API til filtre i Power BI-visualiseringer

Med filtre i visualiseringer kan der filtreres efter data. Den største forskel i forhold til markeringer er, at andre visualiseringer filtreres på en hvilken som helst måde, trods understøttelse af fremhævning i andre visualiseringer.

Hvis du vil aktivere filtrering for visualiseringen, skal visualiseringen indeholde objektet `filter` i afsnittet `general` under indholdet capabilities.json.

```json
"objects": {
        "general": {
            "displayName": "General",
            "displayNameKey": "formattingGeneral",
            "properties": {
                "filter": {
                    "type": {
                        "filter": true
                    }
                }
            }
        }
    }
```

Grænsefladerne til API til filtre er tilgængelig i [`powerbi-models`](https://www.npmjs.com/package/powerbi-models)-pakken. Pakken indeholder også klasser til oprettelse af filterforekomster.

```cmd
npm install powerbi-models --save
```

Hvis du bruger ældre versioner af værktøjerne (versioner, der er ældre end 3.x.x), skal du inkludere `powerbi-models` i visualiseringspakken. [Kort vejledning til, hvordan man inkluderer pakken](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

Alle filtre udvider `IFilter`-grænsefladen.

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```

`target` – er en tabelkolonne i datakilden.

## <a name="basic-filter-api"></a>API til grundlæggende filtrering

Grænsefladen til grundlæggende filtrering er

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

`operator` – er optælling med værdierne "In", "NotIn", "All"

`values` – er værdier for betingelse

Eksempel på grundlæggende filtrering:

```typescript
let basicFilter = {
    target: {
        column: "Col1"
    },
    operator: "In",
    values: [1,2,3]
}
```

Filteret betyder, "Giv mig alle rækker, hvor `col1` er lig med en af værdierne 1, 2 eller 3".

De tilsvarende til SQL er

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

Hvis du vil oprette et filter, kan du bruge BasicFilter-klassen i `powerbi-models`.

Hvis du bruger ældre versioner af værktøjerne, skal du hente en forekomst af modeller i vinduesobjektet ved hjælp af `window['powerbi-models']`:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

Visualiseringen aktiverer filteret ved hjælp af metoden applyJsonFilter() på den værtsgrænseflade, som IVisualHost leverede til visualiseringen i konstruktøren.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="advanced-filter-api"></a>API til avanceret filtrering

[API til avanceret filtrering](https://github.com/Microsoft/powerbi-models) muliggør komplekse forespørgsler for markering/filtrering af datapunkter på tværs af visualiseringer baseret på flere kriterier (såsom "LessThan", "Contains", "Is", "IsBlank" osv.).

Filteret blev introduceret i API til visualiseringer 1.7.0.

API til avanceret filtrering kræver også `target` med `table`- og `column`-navn. Men operatorerne for API til avanceret filtrering er `"And" | "Or"`. 

Derudover bruger filteret betingelser i stedet for værdier med grænsefladen:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

Betingelsesoperatorer til parameteren `operator` er `"None" | "LessThan" | "LessThanOrEqual" | "GreaterThan" | "GreaterThanOrEqual" | "Contains" | "DoesNotContain" | "StartsWith" | "DoesNotStartWith" | "Is" | "IsNot" | "IsBlank" | "IsNotBlank"`

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')), // table
    column: categories.source.displayName // col1
};

let conditions: IAdvancedFilterCondition[] = [];

conditions.push({
    operator: "LessThan",
    value: 0
});

let filter: IAdvancedFilter = new window['powerbi-models'].AdvancedFilter(target, "And", conditions);

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

De tilsvarende til SQL er

```sql
SELECT * FROM table WHERE col1 < 0;
```

Du kan finde en komplet eksempelkode til brug af API til avanceret filtrering i [`Sampleslicer visual` lageret](https://github.com/Microsoft/powerbi-visuals-sampleslicer).

## <a name="tuple-filter-api-multi-column-filter"></a>API til tupelfilter (filter til flere kolonner)

API til tupelfilter blev introduceret i API til visualiseringer 2.3.0.

API til tupelfilter ligner det grundlæggende filter, men den muliggør definering af betingelser for flere kolonner og tabeller.

Filteret har grænsefladen: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

`target` er en matrix af kolonner med tabelnavne:

```typescript
declare type ITupleFilterTarget = IFilterTarget[];
```

  Filteret kan håndtere kolonner fra forskellige tabeller.

`$schema` er "http://powerbi.com/product/schema#tuple"

`filterType` er `FilterType.Tuple`

`operator` tillader kun brug af operatoren `"In"`

`values` er en matrix af værditupler, hvor hver tupel repræsenterer én tilladt kombination af værdier for destinationskolonnen 

```typescript
declare type TupleValueType = ITupleElementValue[];

interface ITupleElementValue {
    value: PrimitiveValueType
}
```

Komplet eksempel:

```typescript
let target: ITupleFilterTarget = [
    {
        table: "DataTable",
        column: "Team"
    },
    {
        table: "DataTable",
        column: "Value"
    }
];

let values = [
    [
        // the 1st column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for `Team` column of `DataTable` table
        },
        {
            value: 5 // the value for `Value` column of `DataTable` table
        }
    ],
    [
        // the 2nd column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "http://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

**Rækkefølgen af kolonnenavne og værdier i betingelser er følsomme.**

De tilsvarende til SQL er

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restoring-json-filter-from-dataview"></a>Gendanner JSON-filter fra DataView

Start fra API 2.2 **JSON-filtre** kan gendannes fra **VisualUpdateOptions**

```typescript
export interface VisualUpdateOptions extends extensibility.VisualUpdateOptions {
    viewport: IViewport;
    dataViews: DataView[];
    type: VisualUpdateType;
    viewMode?: ViewMode;
    editMode?: EditMode;
    operationKind?: VisualDataChangeOperationKind;
    jsonFilters?: IFilter[];
}
```

Power BI kalder metoden `update` for visualiseringen, når funktionen Skift bogmærker og visualiseringen modtager det tilsvarende `filter`-objekt.
[Læs mere om understøttelse af bogmærker](bookmarks-support.md)

### <a name="sample-json-filter"></a>Eksempel på JSON-filter

![Skærmbillede af JSON-filter](./media/json-filter.png)

### <a name="clear-json-filter"></a>Ryd JSON-filter

API til filtrering accepterer værdien `null` for filteret som Nulstil eller Ryd.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
