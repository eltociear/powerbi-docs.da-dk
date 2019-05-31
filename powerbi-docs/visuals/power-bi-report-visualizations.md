---
title: Oversigt over rapportvisualiseringer i Power BI-tjenesten og Desktop
description: Oversigt over rapportvisualiseringer (visuals) i Microsoft Power BI.
author: mihart
ms.author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: d470a262bd8a5e6590746fb07889b1230f5cfc25
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375656"
---
# <a name="visualizations-in-power-bi-reports"></a>Visualiseringer i Power BI-rapporter

Visualiseringer (dvs. visuals) viser indsigter, der er blevet registreret i dataene. En rapport i Power BI har muligvis en enkelt side med én visual, eller den kan have sider fulde af visuals. I Power BI-tjenesten kan visuals [fastgøres fra rapporter til dashboards](../service-dashboard-pin-tile-from-report.md).

Det er vigtigt at skelne mellem rapporters *designere* og rapport *forbrugere* Hvis du er den person, der opretter eller redigerer rapporten, så du er en designer.  Designere har redigeringsrettigheder til rapporten og dens underliggende datasæt. Det betyder, at du i Power BI Desktop kan åbne datasættet i Datavisning og oprette visuals i Rapportvisning. I Power BI-tjenesten, betyder det, du kan åbne datasæt eller rapporter i rapporteditoren i [redigeringsvisning](../consumer/end-user-reading-view.md). Hvis en rapport eller et dashboard er blevet [delt med dig](../consumer/end-user-shared-with-me.md), så er du rapportens **forbruger**. Du vil kunne se og interagere med rapporten og dens visuelle elementer, men du kan ikke gemme større ændringer.

Der er mange forskellige typer visuals, der fås direkte fra ruden VISUALISERINGER i Power BI.

![](media/power-bi-report-visualizations/power-bi-templates.png)

Du kan desuden se mangle flere valgmuligheder ved at besøge [webstedet for Microsoft AppSource-community'et](https://appsource.microsoft.com), hvor du kan finde og [downloade](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) [brugerdefinerede visualiseringer](../developer/custom-visual-develop-tutorial.md) leveret af Microsoft og community'et.

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


  Hvis du ikke har erfaring med Power BI, eller hvis du har brug for at opfriske din viden, kan du bruge linkene nedenfor til at lære det grundlæggende om Power BI-visualiseringer.  Alternativt kan du bruge indholdsfortegnelsen (til venstre for denne artikel) til at finde flere praktiske oplysninger.

## <a name="add-a-visualization-in-power-bi"></a>Tilføj en visualisering i Power BI

[Opret visualiseringer](power-bi-report-add-visualizations-i.md) på siderne i dine rapporter. Gennemse [listen over visualiseringer og vores selvstudier om visualiseringer.](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>Upload en brugerdefineret visualisering, og brug den i Power BI

Tilføj en brugerdefineret visualisering, som du selv har oprettet, eller som du har fundet på [webstedet for Microsoft AppSource-community'et](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals). Er du i det kreative hjørne? Dyk ned i kildekoden, og brug vores [udviklerværktøjer](../developer/custom-visual-develop-tutorial.md) til at oprette en ny visualiseringstype, og [del den med community'et](../developer/office-store.md). Hvis du vil have mere at vide om udvikling af brugerdefinerede visualiseringer, kan du se [Udvikling af en brugerdefineret visualisering i Power BI](../developer/custom-visual-develop-tutorial.md).

## <a name="change-the-visualization-type"></a>Ret visualiseringstypen

Prøv at [vælge en anden type visualisering](power-bi-report-change-visualization-type.md) for at se, hvilken der fungerer bedst med dine data.

## <a name="pin-the-visualization"></a>Fastgør visualiseringen

Når du har fået tilpasset visualiseringen til det, du har brug for i Power BI-tjenesten, kan du [fastgøre den på et dashboard](../service-dashboard-pin-tile-from-report.md) som et felt. Hvis du ændrer visualiseringen, der bruges i rapporten, når du har fastgjort den, så ændres feltet på dashboardet ikke – et kurvediagram forbliver et kurvediagram, selvom du har ændret det til et kransediagram i rapporten.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
- Afhængigt af datakilden og antallet af felter (målinger eller kolonner), et visuelt element indlæses muligvis langsomt.  Det anbefales at begrænse visuelle elementer til 10-20 samlede felter, både med hensyn til læsbarheden og ydeevne. 

- Den øvre grænse for visuelle elementer er 100 felter (målinger eller kolonner). Hvis dit visual ikke indlæses, reducere antallet af felter.   

## <a name="next-steps"></a>Næste trin

* [Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [Brugerdefinerede visualiseringer](../power-bi-custom-visuals.md)