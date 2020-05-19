---
title: Ændringslog for visualiserings-API i Power BI
description: I denne artikel beskrives vigtige ændringer i forskellige versioner af visualiserings-API'en i Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/13/2019
ms.openlocfilehash: fa8759d7edb519240140263bcd01bfdddd9c7d86
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141066"
---
# <a name="power-bi-visuals-api-changelog"></a>Ændringslog for visualiserings-API i Power BI
Denne side indeholder en hurtig oversigt over API-versionerne. De versioner, der er angivet her, anses som stabile og ændres ikke.

## <a name="api-v26"></a>API v 2.6
  * Tilføjer **isInFocus** til opdateringsindstilling og metoden **switchFocusModeState** til visuel vært
  * Understøtter tilpasning af **subtotaler**

## <a name="api-v25"></a>API v 2.5
  * Understøtter **[ruden Analyse](./analytics-pane.md)**
  * Understøtter metoderne `SelectionIdBuilder` **withMatrixNode** og **withTable**
  * Understøtter ikke længere `DataRepetitionSelector`-grænsefladen, som er erstattet med `data.CustomVisualOpaqueIdentity`-grænsefladen

## <a name="api-v23"></a>API v 2.3
  * **[Landingsside-API](./landing-page.md)**
  * **[Lokalt lager-API](./local-storage.md)**
  * **[API til tupelfilter (filter til flere kolonner)](./filter-api.md#the-tuple-filter-api-multi-column-filter)**
  * **[API til gengivelse af hændelser](./event-service.md#render-events-in-power-bi-visuals)**

## <a name="api-v22"></a>API v 2.2
  * Understøtter **[gendannelse af JSON-filter fra DataView](./filter-api.md#restore-the-json-filter-from-the-data-view)**
  * **[ContextMenu-API](./context-menu.md)**

## <a name="api-v21"></a>API v 2.1
  * Forbedret ydeevne:
    * Hurtigere indlæsningstider
    * Mindre hukommelsesforbrug
    * Optimerede data- og hændelsestransaktioner  

**Produktbemærkninger**
* Refactored Filtering-API'er vil være tilgængelige i API 2.2 og understøttes ikke i API 2.1.
* Visualiseringer kan kun modtage den dataView-type, der er angivet i deres egenskaber. Visualiseringer, der bruger flere dataView-typer, vil blive brudt som følge af denne opdatering.
* Understøtter ikke længere `DataViewScopeIdentity`-grænsefladen, som er erstattet med `data.DataRepetitionSelector`-grænsefladen. Hvis du har brugt nøgleegenskaben for grænsefladen `DataViewScopeIdentity`, kan du erstatte den med `JSON.stringify(identity)`
* `undefined` erstattes med `null` i dataView. Når der gentages over en matrix ved hjælp af `var item in myArray`, springes den over ved `undefined`, men ikke ved `null`. Visualiseringer, der bruger dette mønster, kan blive ødelagt af denne opdatering. Sørg for at se efter `null` i matricer:
   ```typescript
   for (var item in myArray) {
     if (!item) {
       continue;
     }
     console.log(item);
   }
   ```
* Egenskaben `proto` gemmer ikke længere skjulte metadata\data i dataView. Visualiseringer, som får adgang til egenskaber via `proto`, kan blive ødelagt af denne opdatering.

## <a name="api-v113"></a>API v 1.13
* Understøtter **[Synkroniser udsnit](./enable-sync-slicers.md)** . Bemærk, at dette kun fungerer for enkelte feltudsnit på grund af den aktuelle PBI-kodetilstand, [læs mere](/power-bi/desktop-slicers).
* Tilgængelighed: [Understøttelse af høj kontrast](./high-contrast-support.md) 
* Tilgængelighed: Tillad tastaturfokusflag

## <a name="api-v112"></a>API v 1.12
* Understøtter temaer
* Understøtter **[fetchMoreData](./fetch-more-data.md)** . Bemærk, at **Hent flere data-API'en** overskrider den maksimale grænse på 30.000 datapunkter
* **[API til værktøjstip til lærred](./add-tooltips.md#add-report-page-tooltips)**

## <a name="api-v111"></a>API v 1.11
* **[FilterManager-API](./filter-api.md)**
* Understøtter **[bogmærker](./bookmarks-support.md)** 

## <a name="api-v110"></a>API v 1.10
* Tilføjer `ILocalizationManager`
* **Godkendelses-API**

## <a name="api-v19"></a>API v 1.9
* **[launchUrl-API](./launch-url.md)**

## <a name="api-v18"></a>API v 1.8
* Understøtter den nye type **fillRule** (graduering) i egenskabsskemaer
* Understøtter **regel**egenskab i skemaegenskaber for objektegenskaber

## <a name="api-v17"></a>API v 1.7
* Understøtter **[RESJSON](./localization.md#resource-file)**

## <a name="api-v162"></a>API v 1.6.2
* Understøtter **[redigeringstilstand](./advanced-edit-mode.md)** , for at visualiseringer kan redigeres i selve visualiseringen
* Understøtter **[Interaktive (HTML) R Power BI-visualiseringer](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** , der er baseret på HTML

## <a name="api-v150"></a>API v 1.5.0
* Understøtter **[Tillad interaktioner](./visuals-interactions.md)** for visuel interaktivitet

## <a name="api-v140"></a>API v 1.4.0
* Understøtter **[lokalisering](./localization.md)**

## <a name="api-v130"></a>API v 1.3.0
* Understøtter **[værktøjstip](./add-tooltips.md)**

## <a name="api-v120"></a>API v 1.2.0
* Tilføjer **colorPalette** til at styre de farver, der bruges i din visualisering.
* Understøtter **Flere markeringer** – selectionManager kan acceptere en matrix af `SelectionId`.
* Understøtter **[R-visualiseringer](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** ved hjælp af R-scripts

## <a name="api-v110"></a>API v 1.1.0
* Understøtter fejlfinding af visualisering i iFrame
* Tilføjer let sandkasse med hurtigere initialisering af iFrame
* Løser problemet med, at [Capabilities.objects ikke understøtter "tekst"-typen](https://github.com/Microsoft/PowerBI-visuals-tools/issues/12)
* Understøtter `pbiviz update` til opdatering af definitioner og skema for visualiserings-API-typer
* Understøtter flaget `--api-version` i `pbiviz new` til at oprette visualiseringer med en bestemt API-version
* Understøtter alfa-udgivelse af API v 1.2.0

**Visuel vært**
* Tilføjer **createSelectionIdBuilder** til at oprette entydige id'er, der bruges til datavalg
* Tilføjer **createSelectionManager** til at administrere valgtilstanden for visualiseringen og kommunikerer ændringer til den visuelle vært
* Tilføjer en matrix af **standardfarver** til brug i visualiseringer

## <a name="api-v100"></a>API v 1.0.0
* Indledende API-version
