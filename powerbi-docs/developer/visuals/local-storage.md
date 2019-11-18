---
title: API til lokalt lager i Power BI-visualiseringer
description: I artiklen beskrives det, hvordan du bruger API til Power BI-visualiseringer til at få adgang til browserens lokale lager
author: uve
ms.author: v-grniki
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: f69a3c8928b8079f79b8a6dd5f5b132235a7089c
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879894"
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

API'en til lokalt lager er ikke aktiveret for brugerdefinerede visualiseringer som standard. Hvis du vil aktivere den for din brugerdefinerede visualisering, skal du sende en anmodning til support til Power BI-visualiseringer `pbicvsupport@microsoft.com`
