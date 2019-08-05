---
title: Start-URL-adresse
description: URL-adresser kan åbnes på en ny fane i Power BI-visualiseringer
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1a7002c3b45f341c0cbc0db683bc4f8a113e21f9
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424855"
---
# <a name="launch-url"></a>Start-URL-adresse

Med Start-URL-adresser er det muligt at åbne en ny browserfane (eller et vindue) ved at delegere det reelle arbejde til Power BI.

## <a name="sample"></a>Eksempel

```typescript
   this.host.launchUrl('https://powerbi.microsoft.com');
```

## <a name="usage"></a>Forbrug

Brug API-kaldet `host.launchUrl()`, hvilket videregiver din destinations-URL-adresse som et strengargument:

```typescript
this.host.launchUrl('http://some.link.net');
```

## <a name="restrictions"></a>Begrænsninger

* Brug kun absolutte stier og ikke relative stier. `http://some.link.net/subfolder/page.html` er fin, men `/page.html` åbnes ikke.
* I øjeblikket er det kun protokollerne `http` og `https`, der understøttes. Undgå `ftp`, `mailto` osv.

## <a name="best-practices"></a>Bedste praksis

1. I de fleste tilfælde er det bedst kun at åbne et link som et svar på en brugers eksplicitte handling. Gør det nemt for brugeren at forstå, at der åbnes en ny fane, når der klikkes på linket eller knappen. Det kan være forvirrende eller frustrerende for brugeren, hvis der udløses et `launchUrl()`-kald, uden at brugeren har foretaget en handling.
2. Hvis linket ikke er essentielt for en korrekt fungerende visualisering, anbefales det at give forfatteren af rapporten mulighed for at deaktivere og gemme linket. Dette er især relevant for særlige Power BI-brugssager, f.eks. integrering af en rapport i et tredjepartsprogram eller publicering af den på internettet.
3. Undgå at udløse et `launchUrl()`-kald fra en løkke, visualiseringens `update`-funktion eller andre ofte tilbagevendende koder.

## <a name="step-by-step-example"></a>Trinvist eksempel

### <a name="adding-a-link-launching-element"></a>Tilføjelse af et element til start af et link

Følgende linjer blev føjet til visualiseringens `constructor`-funktion:

```typescript
    this.helpLinkElement = this.createHelpLinkElement();
    options.element.appendChild(this.helpLinkElement);
```

Og der blev tilføjet en privat funktion, som opretter og tilknytter ankerelementet:

```typescript
private createHelpLinkElement(): Element {
    let linkElement = document.createElement("a");
    linkElement.textContent = "?";
    linkElement.setAttribute("title", "Open documentation");
    linkElement.setAttribute("class", "helpLink");
    linkElement.addEventListener("click", () => {
        this.host.launchUrl("https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial");
    });
    return linkElement;
};
```

Til sidst definerer en post i filen visual.less typografien for linkelementet:

```less
.helpLink {
    position: absolute;
    top: 0px;
    right: 12px;
    display: block;
    width: 20px;
    height: 20px;
    border: 2px solid #80B0E0;
    border-radius: 20px;
    color: #80B0E0;
    text-align: center;
    font-size: 16px;
    line-height: 20px;
    background-color: #FFFFFF;
    transition: all 900ms ease;

    &:hover {
        background-color: #DDEEFF;
        color: #5080B0;
        border-color: #5080B0;
        transition: all 250ms ease;
    }

    &.hidden {
        display: none;
    }
}
```

### <a name="adding-a-toggling-mechanism"></a>Tilføjelse af en til/fra-mekanisme

Dette kræver, at du tilføjer et statisk objekt (se [selvstudiet om statiske objekter](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties)), så forfatteren af rapporten kan skifte synligheden af linkelementet (det er som standard angivet til skjult).
Et boolesk statisk objekt af typen `showHelpLink` blev føjet til objektposten `capabilities.json`:

```typescript
"objects": {
    "generalView": {
            "displayName": "General View",
            "properties":
                "showHelpLink": {
                    "displayName": "Show Help Button",
                    "type": {
                        "bool": true
                    }
                }
            }
        }
    }
```

![Til/fra af Start-URL-adresse](./media/launchurl-toggle.png)

Og i visualiseringens `update`-funktion blev følgende linjer tilføjet:

```typescript
if (settings.generalView.showHelpLink) {
    this.helpLinkElement.classList.remove("hidden");
} else {
    this.helpLinkElement.classList.add("hidden");
}
```

Klassen `hidden` er defineret i visual.less til at styre visningen af elementet.
