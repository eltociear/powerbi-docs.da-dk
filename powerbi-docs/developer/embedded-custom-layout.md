---
title: Brugerdefinerede layout med Power BI-integreret indhold
description: Få mere at vide om brugerdefinerede layout, når du integrerer Power BI-indhold i dit program.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: fc684ebdf6b1ccb53bdd7794b19c1120ece635a3
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="custom-layouts"></a>Brugerdefinerede layout


Brug et brugerdefineret layout til at integrere en rapport med et andet layout end i den oprindelige rapport. Du kan definere et nyt layout ved kun at definere en sidestørrelse eller styre de visuelle størrelser eller placering og synlighed.

Du definerer et brugerdefineret layout ved at definere et brugerdefineret layoutobjekt og sende det til indstillingerne for objektet i den integrerede konfiguration. Herudover skal du angive LayoutType til Brugerdefineret. Du kan få mere at vide under [Integrer konfigurationsoplysninger](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Objektdefinition

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: Brug sidestørrelsen til at styre canvasområdets størrelse (dvs. det hvide rapportområde).
- `displayOptions`: Mulige værdier er: FitToWidth, FitToPage eller ActualSize. Den styrer skaleringen af canvasset, så det passer til iframe.
- `pagesLayout`: Styrer layoutet for det enkelte visuelle element. se PagesLayout for at få flere oplysninger.

## <a name="pages-layout"></a>Layout for sider

Når du definerer et layout for sider, definerer du i bund og grund et layout for hver side, og for hver side definerer du et layout for det enkelte visuelle element.
PageLayout er valgfri. Hvis du ikke angiver et layout for en side, benyttes standardlayoutet (der er gemt i rapporten).

pagesLayout er et kort fra sidenavn til PageLayout-objektet. Definition:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout indeholder et visuelt layoutkort, der knytter det enkelte visuelle element til en visuelt layoutobjekt:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Visuelt layout

Du definerer et visuelt layout ved at sende en ny placering og størrelse samt en ny synlighedsstatus.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: Definerer det visuelle elements nye placering.
- `width`, højde: Definerer det visuelle elements nye størrelse.
- `displayState`: Definerer det visuelle elements synlighed.


## <a name="update-layout"></a>Opdater layout

Du kan bruge metoden updateSettings til at opdatere rapportlayoutet, mens rapporten er indlæst. Se [Indstillinger for opdatering](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Eksempel på en kode

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>Se også

[Integrer dine Power BI-dashboards, -rapporter og -felter](embedding-content.md)   
[Spørg Power BI-community'et](https://community.powerbi.com/)

