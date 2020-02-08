---
title: 'Selvstudium: Brug Analysér i Excel'
description: I dette selvstudium skal du bruge siden Power BI-datasæt til at importere datasæt til Excel.
author: tejaskulkarni
ms.reviewer: davidiseminger
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 01/27/2020
ms.author: tekulkar
LocalizationGroup: Connect to services
ms.openlocfilehash: a68adccec019e64e554d199d23d7dddd782f56a2
ms.sourcegitcommit: 53c2b5ea4ee1fe2659804d5ccc8e4bb445a8bcad
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921479"
---
# <a name="tutorial-use-analyze-in-excel"></a>Selvstudium: Brug Analysér i Excel

Din organisation bruger Power BI til at dele adgang til data. Brug funktionen Analysér i Excel til at oprette pivottabeller og PivotChart for at få yderligere kontekst i dine analyser eller reducere den tid, det tager at finde og importere relevante datasæt.

Du kommer i gang ved at vælge et datasæt og vælge "Analysér i Excel". Du vejledt i oprettelsen af en pivottabel, der bruger dataene.  

Du kan finde flere datasæt, der deles af din organisation, ved at gå tilbage til siden Datasæt.

Hvis du på et tidspunkt oplever problemer, skal du vælge Nej ved det relevante trin i flowet nedenfor og angive feedback i den formular, der er link til.  

I dette selvstudium lærer du, hvordan du kan:

> [!div class="checklist"]
> * Downloade en ODC-fil fra siden Power BI-datasæt.
> * Aktivere adgang til dit datasæt fra Excel.
> * Begynde at bruge datasættet til at oprette pivottabeller, diagrammer og regneark

## <a name="prerequisites"></a>Forudsætninger

Du skal bruge følgende for at fuldføre dette selvstudium:

* En Power BI-konto. Hvis du ikke er tilmeldt Power BI, kan du [tilmelde dig en gratis prøveversion](https://app.powerbi.com/signupredirect?pbi_source=web), før du begynder.

* Sørg for, at du er fortrolig med alle de trin, der er angivet i selvstudiet [Kom i gang med Power BI-tjenesten](https://docs.microsoft.com/power-bi/service-get-started).

* Du skal bruge et Power BI Premium-datasæt og en Power BI Pro-licens. Du kan finde flere oplysninger under [Hvad er Power BI Premium?](https://docs.microsoft.com/power-bi/service-premium-what-is)

* Du kan finde en komplet liste over forudsætninger i det omfattende dokument til [Analysér i Excel](https://docs.microsoft.com/power-bi/service-analyze-in-excel#requirements).

* Et aktivt [Microsoft Office E5-abonnement](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)

## <a name="get-started"></a>Kom i gang

Start i Excel, vælg muligheden for at oprette pivottabeller med delte data i Power BI, og naviger til siden Power BI-datasæt.

![Siden Datasæt](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-01.png)

Mens du bruger arbejdsprocessen Analysér i Excel, vil du se adskillige prompter, der vejleder dig. Angiv, om du har fuldført hvert trin for at fortsætte. Hvis du oplever problemer ved et hvilket som helst trin, skal du vælge **Nej** og angive feedback i den tilsvarende formular.

![Instruktioner til arbejdsproces](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-02.png)

## <a name="download-and-open-the-odc-file"></a>Download og åbn ODC-filen

Vælg dit datasæt på den tilsvarende liste og i det tilknyttede arbejdsområde, og klik derefter på Analysér i Excel. Power BI opretter en ODC-fil og downloader den fra browseren til din computer.

![Vælg datasæt](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-03.png)

Når du åbner filen i Excel, vises der en tom Pivottabel- og Felt-liste med tabeller, felter og målinger fra Power BI-datasættet. Du kan oprette pivottabeller og diagrammer og analysere dette datasæt på samme måde, som du ville arbejde med et lokalt datasæt i Excel.

## <a name="enable-data-connections"></a>Aktivér dataforbindelser

Hvis du vil analysere Power BI-data i Excel, bliver du måske bedt om at have tillid til forbindelsen. Administratorer kan deaktivere brugen af Analysér i Excel med datasæt i det lokale miljø for Analysis Services-databaser via Power BI-administrationsportalen.

![Aktivér forbindelse](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-04.png)

## <a name="install-updates-and-authenticate"></a>Installér opdateringer, og godkend

Du skal muligvis også godkende med din Power BI-konto, første gang du åbner en ny ODC-fil.  Hvis du har problemer, kan du se det omfattende dokument til [Analysér i Excel](https://docs.microsoft.com/power-bi/service-analyze-in-excel#sign-in-to-power-bi ) for at få flere oplysninger eller klikke på Nej under arbejdsprocessen.

![Aktivér forbindelse](media/service-tutorial-analyze-in-excel/tutorial-analyze-in-excel-05.png)

## <a name="analyze-away"></a>Analysér

Ligesom med andre lokale projektmapper giver Analysér i Excel dig mulighed for at oprette pivottabeller og diagrammer, tilføje data og oprette forskellige regneark med visninger af dine data. Analysér i Excel fremviser alle data på detaljeniveau for alle brugere med tilladelse til datasættet. Du kan gemme denne projektmappe, men du kan ikke publicere eller importere den tilbage til Power BI eller dele den med andre brugere i din organisation. Du kan finde flere oplysninger og andre use cases under [Analysér i Excel](https://docs.microsoft.com/power-bi/service-analyze-in-excel#analyze-away).

## <a name="clean-up-resources"></a>Fjern ressourcer

Interaktioner med Power BI-tjenesten og siden Datasæt bør begrænses til download af ODC-filen og klik igennem arbejdsprocessen. Hvis du har problemer med nogen af disse trin, skal du angive **Nej** ved det relevante trin og angive feedback i den formular, der er link til. Formularen indeholder et link til flere oplysninger om problemet. Gå tilbage til siden Datasæt for at prøve processen igen, eller vælg et andet datasæt.

## <a name="next-steps"></a>Næste trin

Du vil måske også være interesseret i følgende artikler:

* [Brug tværgående detaljeadgang i rapport i Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-cross-report-drill-through)

* [Brug af udsnitsværktøjer i Power BI Desktop](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-slicers)
