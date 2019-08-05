---
title: Ruden Analyse
description: Sådan opretter du dynamiske referencelinjer i Power BI-visualiseringer
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b3b50f8dbcf40a3923e86422e24f8ed020894445
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425522"
---
# <a name="analytics-pane-in-power-bi-visuals"></a>Ruden Analyse i Power BI-visualiseringer

**Ruden Analyse** blev [introduceret til oprindelige visualiseringer](https://docs.microsoft.com/power-bi/desktop-analytics-pane) i november 2018.
Egenskaber i brugerdefinerede visualiseringer med API v2.5.0 kan præsenteres og administreres i **ruden Analyse**.

![Ruden Analyse](./media/visualization-pane-analytics-tab.png)

Den bruges på samme måde som [administration af egenskaber i ruden Format](https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial-format-options) ved at definere et objekt i visualiseringens capabilities.json-fil. 

Forskellene er som følger:

1. Under definitionen for `object` skal du tilføje feltet `objectCategory` med værdien 2.

    > [!NOTE]
    > Feltet `objectCategory` er et valgfrit felt, som blev introduceret i API 2.5.0. Det definerer den del af visualiseringen, som objektet styrer (1 = formatering, 2 = analyse). "Formatering" bruges til udseendet, farver, akser, mærkater osv. "Analyse" bruges til prognoser, tendenslinjer, referencelinjer, osv.
    >
    > `objectCategory` er som standard "Formatering", hvis det udelades.

2. Objektet skal have følgende to egenskaber:
    1. `show` af typen boolesk, hvor standardværdien er false.
    2. `displayName` af typen tekst. Den standardværdi, du vælger, bliver forekomstens indledende viste navn.

```json
{
  "objects": {
    "YourAnalyticsPropertiesCard": {
      "displayName": "Your analytics properties card's name",
      "objectCategory": 2,
      "properties": {
        "show": {
          "type": {
            "bool": true
          }
        },
        "displayName": {
          "type": {
            "text": true
          }
        },
      ... //any other properties for your Analytics card
      }
    }
  ...
  }
}
```

Alle andre egenskaber kan defineres på samme måde som objekter for Format. Optælling af objekter udføres nøjagtigt som i **ruden Format**.

***Kendte begrænsninger og problemer***

  1. Ingen understøttelse af flere forekomster endnu. Objekter kan ikke have en anden [vælger](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector) end statisk (dvs. "vælger": null), og brugerdefinerede visualiseringer kan ikke have flere brugerdefinerede forekomster på et kort.
  2. Egenskaber af typen `integer` vises ikke korrekt. Du kan løse problemet ved at bruge typen `numeric` i stedet.

> [!NOTE]
> Brug kun ruden Analyse til objekter, der tilføjer nye oplysninger eller kaster nyt lys over de præsenterede oplysninger. Det kan f.eks. være dynamiske referencelinjer, der illustrerer vigtige tendenser.
> Alle indstillinger, der styrer visualiseringens udseende, dvs. formateringen, skal bevares i ruden Formatering.
