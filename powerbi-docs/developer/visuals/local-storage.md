---
title: API til lokalt lager i Power BI-visualiseringer
description: I artiklen beskrives det, hvordan du bruger API til Power BI-visualiseringer til at få adgang til browserens lokale lager
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 01/21/2019
ms.openlocfilehash: e2cb11ea9be85916e6b5557e7933f6a6b5a7159a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380588"
---
# <a name="local-storage-api"></a>Lokalt lager-API

API'en til det lokale lager er en API, som et brugerdefineret visual kan bruge til at anmode værten om at gemme eller indlæse data fra enhedens lager. Det er isoleret på den måde, at der er en adskillelse af lageradgangen mellem forskellige visualtyper.

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

API'en til lokalt lager er som standard ikke aktiveret for Power BI-visuals. Hvis du vil aktivere den for din Power BI-visual, skal du sende en anmodning til support til Power BI-visuals `pbicvsupport@microsoft.com`.  
**Bemærk, at visualiseringen skal være tilgængelig i [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) og være [certificeret](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/).**
