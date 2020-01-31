---
title: API til lokalt lager i Power BI-visualiseringer
description: I artiklen beskrives det, hvordan du bruger API til Power BI-visualiseringer til at få adgang til browserens lokale lager
author: uve
ms.author: v-grniki
ms.reviewer: KesemSharabi
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 01/21/2019
ms.openlocfilehash: 85517fcd7ec773f947135614c94c0c4e4638ea48
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/23/2020
ms.locfileid: "76539319"
---
# <a name="local-storage-api"></a>Lokalt lager-API

API'en til det lokale lager er en API, som en brugerdefineret visualisering kan bruge til at anmode værten om at gemme eller indlæse data fra enhedens lager. Det er isoleret på den måde, at der er en adskillelse af lageradgangen mellem forskellige visualiseringstyper.

## <a name="sample"></a>Eksempel

Hvis den brugerdefinerede visualisering skal øge en tæller, hver gang opdateringsmetoden kaldes, men tællerværdien også skal bevares og ikke nulstilles ved hver visuelle start:

```typescript
export class Visual implements IVisual {
        // ...
        private updateCountName: string = 'updateCount';
        private updateCount: number;
        private storage: ILocalVisualStorageService;
        // ...

        constructor(options: VisualConstructorOptions) {
            // ...
            this.storage = options.host.storageService;
            // ...

            this.storage.get(this.updateCountName).then(count =>
            {
                this.updateCount = +count;
            })
            .catch(() =>
            {
                this.updateCount = 0;
                this.storage.set(this.updateCountName, this.updateCount.toString());
            });
            // ...
        }

        public update(options: VisualUpdateOptions) {
            // ...
            this.updateCount++;
            this.storage.set(this.updateCountName, this.updateCount.toString());
            // ...
        }
}
```

## <a name="known-limitations-and-issues"></a>Kendte begrænsninger og problemer

API'en til lokalt lager er ikke aktiveret for brugerdefinerede visualiseringer som standard. Hvis du vil aktivere den for din brugerdefinerede visualisering, skal du sende en anmodning til support til Power BI-visualiseringer `pbicvsupport@microsoft.com`.  
**Bemærk, at visualiseringen skal være tilgængelig i [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) og være [certificeret](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/).**
