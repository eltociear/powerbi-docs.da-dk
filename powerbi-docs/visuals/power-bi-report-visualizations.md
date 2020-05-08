---
title: Oversigt over rapportvisualiseringer i Power BI-tjenesten og Desktop
description: Oversigt over rapportvisualiseringer (visuals) i Microsoft Power BI.
author: mihart
ms.author: mihart
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: bd8053123d8a5c2fa0c4362cb2a534021208ba36
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "79381462"
---
# <a name="visualizations-in-power-bi-reports"></a>Visualiseringer i Power BI-rapporter

Visualiseringer (kaldes også visuals) viser indsigt fra dine data. En rapport i Power BI har muligvis en enkelt side med én visual, eller den kan have sider fulde af visuals. I Power BI-tjenesten kan visualiseringer [fastgøres fra rapporter til dashboards](../service-dashboard-pin-tile-from-report.md).

Det er vigtigt at skelne mellem rapporternes *designere* og *forbrugere*.  Hvis du er den person, der opretter eller redigerer rapporten, er du designer.  Designere har tilladelse til at redigere rapporten og dens underliggende datasæt. Det betyder, at du i Power BI Desktop kan åbne datasættet i Datavisning og oprette visuals i Rapportvisning. Det betyder, at du i Power BI-tjenesten kan åbne datasættet eller rapporten i rapporteditoren i [Redigeringsvisning](../consumer/end-user-reading-view.md). Hvis en rapport eller et dashboard er blevet [delt med dig](../consumer/end-user-shared-with-me.md), så er du rapportens *forbruger*. Du kan få vist og interagere med rapporten og dens visualiseringer, men du kan ikke foretage lige så mange ændringer, som en *designer* kan.

Der er mange forskellige typer visualiseringer, der er tilgængelige direkte fra ruden Visualiseringer i Power BI.

![rude med ikoner for hver visualiseringstype](media/power-bi-report-visualizations/power-bi-icons.png)

Du har endnu flere valg, hvis du besøger [webstedet for Microsoft AppSource-community'et](https://appsource.microsoft.com), hvor du kan finde og [downloade](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) [Power BI-visuals](../developer/visuals/custom-visual-develop-tutorial.md), som leveres af Microsoft og community'et.

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Hvis du ikke har erfaring med Power BI, eller hvis du har brug for at opfriske din viden, kan du bruge linkene nedenfor til at lære det grundlæggende om Power BI-visualiseringer.  Alternativt kan du bruge indholdsfortegnelsen (til venstre for denne artikel) til at finde flere praktiske oplysninger.

## <a name="add-a-visualization-in-power-bi"></a>Tilføj en visualisering i Power BI

[Opret visualiseringer](power-bi-report-add-visualizations-i.md) på siderne i dine rapporter. Gennemse [listen over visualiseringer og vores selvstudier om visualiseringer.](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>Upload en brugerdefineret visualisering, og brug den i Power BI

Tilføj en brugerdefineret visualisering, som du selv har oprettet, eller som du har fundet på [webstedet for Microsoft AppSource-community'et](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals). Er du i det kreative hjørne? Dyk ned i kildekoden, og brug vores [udviklerværktøjer](../developer/visuals/custom-visual-develop-tutorial.md) til at oprette en ny visualiseringstype, og [del den med community'et](../developer/visuals/office-store.md). Hvis du vil have mere at vide om udvikling af brugerdefinerede visualiseringer, kan du se [Udvikling af en brugerdefineret visualisering i Power BI](../developer/visuals/custom-visual-develop-tutorial.md).

## <a name="personalize-your-visualization-pane-preview"></a>Tilpas din visualiseringsrude (prøveversion)

Hvis du finder ud at, at du bruger den samme brugerdefinerede visualisering på tværs af mange rapporter, kan du fastgøre den brugerdefinerede visualisering på din visualiseringsrude. Hvis du vil fastgøre visualiseringen, skal du højreklikke på visualiseringen for at fastgøre den til ruden.

![Fastgør til visualiseringsruden](media/power-bi-report-visualizations/power-bi-pin-custom-visual-option.png)

Når en visualisering er blevet fastgjort, flyttes den til liveudgaven sammen med de indbyggede visualiseringer. Denne visualisering er nu knyttet til den konto, du er logget på. Det betyder, at alle nye rapporter, du skaber, automatisk vil have denne visualisering inkluderet, forudsat at du er logget på. Dette gør det meget nemt at standardisere en bestemt visualisering, uden at du behøver at tilføje den i hver enkelt rapport.

![Tilpasset visualiseringsrude](media/power-bi-report-visualizations/power-bi-personalized-visualization-pane.png)

Mens denne funktion er tilgængelig som prøveversion, kan du kun se dine fastgjorte visuals i Power BI Desktop. Desuden skal du være logget på, for at denne funktion er tilgængelig.

## <a name="change-the-visualization-type"></a>Ret visualiseringstypen

Prøv at [vælge en anden type visualisering](power-bi-report-change-visualization-type.md) for at se, hvilken der fungerer bedst med dine data.

## <a name="pin-the-visualization"></a>Fastgør visualiseringen

Når du har fået tilpasset visualiseringen til det, du har brug for i Power BI-tjenesten, kan du [fastgøre den på et dashboard](../service-dashboard-pin-tile-from-report.md) som et felt. Hvis du ændrer visualiseringen, der bruges i rapporten, når du har fastgjort den, så ændres feltet på dashboardet ikke – et kurvediagram forbliver et kurvediagram, selvom du har ændret det til et kransediagram i rapporten.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
- Afhængigt af datakilden og antallet af felter (målinger eller kolonner) kan indlæsningen af en visualisering muligvis gå langsomt.  Det anbefales at begrænse visualiseringer til 10-20 felter i alt – både af hensyn til læsbarheden og ydeevnen. 

- Den øvre grænse for visualiseringer er 100 felter (målinger eller kolonner). Hvis din visualisering ikke kan indlæses, kan du prøve at reducere antallet af felter.   

## <a name="next-steps"></a>De næste trin

* [Typer af visualiseringer i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [Power BI-visuals](../developer/visuals/power-bi-custom-visuals.md)
