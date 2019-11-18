---
title: Integrer rapporter eller dashboards fra apps
description: Lær, hvordan du integrerer en rapport eller et dashboard fra en Power BI-app og ikke fra et arbejdsområde.
author: rkarlin
ms.author: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: mvc
manager: kfile
ms.date: 11/27/2018
ms.openlocfilehash: 1883d82b47c32f3c7f03e55a177429d09ce337a2
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/01/2019
ms.locfileid: "73430844"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Integrer rapporter eller dashboards fra apps

I Power BI kan du oprette apps for at samle relaterede dashboards og rapporter på ét sted. Du kan derefter publicere dem til store grupper af personer i din organisation. Brugen af disse apps er relevant, når alle dine brugere er Power BI-brugere. Så kan du dele indhold med dem ved hjælp af Power BI-apps. Denne artikel indeholder et par hurtige trin til, hvordan du integrerer indhold fra en publiceret Power BI-app i et tredjepartsprogram.

## <a name="grab-a-report-embedurl-for-embedding"></a>Hent en rapports embedURL for at integrere den

1. Opret en forekomst af programmet i et brugerarbejdsområde, **Mit arbejdsområde**. Du kan enten dele med dig selv eller guide en anden bruger gennem dette forløb.

2. Åbn den ønskede rapport i Power BI-tjenesten.

3. Gå til **Filer** > **Integrer i SharePoint Online**, og hent rapportens embedURL. På øjebliksbilledet herunder kan du se et eksempel på en embedURL. Du kan også kalde REST-API'en for GetReports/GetReport og udtrække det tilsvarende felt for rapportens embedURL fra svaret. REST-kaldet må ikke indeholde et arbejdsområde-id som en del af URL-adressen, da appen blev oprettet i brugerens arbejdsområde.

    ![Integrer fra apps](media/embed-from-apps/embed-from-app.png)

4. Brug den embedURL, der er hentet i trin 3 med JavaScript SDK.

## <a name="grab-a-dashboard-embedurl-for-embedding"></a>Hent et dashboards embedURL for at integrere det

1. Opret en forekomst af programmet i et brugerarbejdsområde, **Mit arbejdsområde**. Du kan enten dele med dig selv eller guide en anden bruger gennem dette forløb.

2. Kald GetDashboards REST-API'en, og udtræk det tilsvarende felt til dashboardets embedURL fra svaret. REST-kaldet må ikke indeholde et arbejdsområde-id som en del af URL-adressen, da appen blev oprettet i brugerens arbejdsområde.

3. Brug den embedURL, der er hentet i trin 2 med JavaScript SDK.

## <a name="next-steps"></a>Næste trin

Gennemse, hvordan du integrerer fra arbejdsområder for dine tredjepartskunder og din organisation:

> [!div class="nextstepaction"]
>[Integrer for tredjepartskunder](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Integrer for din organisation](embed-sample-for-your-organization.md)
