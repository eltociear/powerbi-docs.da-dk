---
title: Sammenlign Power BI-rapportserveren med Power BI-tjenesten
description: I denne artikel sammenlignes funktionerne i Power BI-rapportserveren og Power BI-tjenesten.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: c47722fda28fc45289858f082a0838f583b53dbb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "34296774"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Sammenlign Power BI-rapportserveren med Power BI-tjenesten

Power BI-rapportserveren og Power BI-tjenesten har mange ligheder og nogle vigtige forskelle. I denne tabel forklares det, hvad der er hvad.

| Funktioner | Power BI Report Server | Power BI Service | Noter
|---------|---------|---------|---------|
| Installation | I det lokale miljø eller i hostet cloud | Cloud | Power BI-rapportserveren kan installeres i Azure VM'er (hostet cloud), hvis det er givet i licens via Power BI Premium
| Kildedata | Cloud og/eller i det lokale miljø | Cloud og/eller i det lokale miljø |  
| Licens | Power BI Premium eller SQL Server EE med SA | Power BI Pro-og/eller Power BI Premium |  
| Livscyklus | Politik for moderne livscyklus | Fuldt administreret tjeneste |  
| Versionscyklus | En gang hver 4. måned | En gang om måneden | Nyeste funktioner og løsninger optræder først i Power BI-tjenesten. De fleste kernefunktioner findes i Power BI-rapportserveren i de næste par versioner. Nogle funktioner er kun beregnet til Power BI-tjenesten.
| Opret Power BI-rapporter i Power BI Desktop | Ja | Ja |  
| Opret Power BI-rapporter i browseren | Nej | Ja |  
| Gateway påkrævet | Nej | Ja, for datakilder i det lokale miljø |  
| Streaming i realtid | Nej | Ja | [Streaming i realtid i Power BI](../service-real-time-streaming.md)
| Dashboards | Nej | Ja | [Dashboards i Power BI-tjenesten](../service-dashboards.md) 
| Distribuer gruppe af rapporter ved hjælp af apps | Nej | Ja | [Opret og udgiv apps med dashboards og rapporter](../service-create-distribute-apps.md) 
| Indholdspakker | Nej | Ja | [Organisationsindholdspakker: Introduktion](../service-organizational-content-pack-introduction.md) 
| Opret forbindelse til tjenester som Salesforce | Nej | Ja | [Opret forbindelse til de tjenester](../service-connect-to-services.md), du bruger med Power BI-tjenesten
| Spørgsmål og svar | Nej | Ja | [Spørgsmål og svar i Power BI-tjenesten og Power BI Desktop](../power-bi-q-and-a.md) 
| Hurtig indsigt | Nej | Ja | [Generér automatisk dataindsigt med Power BI](../service-insights.md) 
| Analysér i Excel | Nej | Ja | [Analysér i Excel](../service-analyze-in-excel.md) 
| Sideinddelte rapporter | Ja | Nej | Sideinddelte rapporter er ikke tilgængelige i Power BI-tjenesten, men du kan [fastgøre elementer i sideinddelte rapporter til Power BI-dashboards](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)
| Power BI-mobilapps | Ja | Ja | [Oversigt over Power BI-mobilapps](../mobile-apps-for-mobile-devices.md) 
| ARC GIS-kort | Nej | Ja | [ArcGIS-kort i Power BI-tjenesten og Power BI Desktop fra Esri](../power-bi-visualization-arcgis.md)
| Mailabonnementer på Power BI-rapporter | Nej | Ja | [Abonner på en rapport eller et dashboard](../service-report-subscribe.md) i Power BI-tjenesten 
| Mailabonnementer på sideinddelte rapporter | Ja | Nej | [Maillevering i Reporting Services](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Databeskeder | Nej | Ja | [Databeskeder](../service-set-data-alerts.md) i Power BI-tjenesten
| Sikkerhed på rækkeniveau | Kun via datakilde i DirectQuery-tilstand | Tilgængelige i både DirectQuery- (datakilde) og importtilstand | [Sikkerhed på rækkeniveau (RLS)](../service-admin-rls.md) med Power BI 
| Fuldskærmsvisning | Nej | Ja | [Fuldskærmsvisning](../service-fullscreen-mode.md) i Power BI-tjenesten 
| Avanceret samarbejde i Office 365 | Nej | Ja | [Samarbejd i et apparbejdsområde](../service-collaborate-power-bi-workspace.md) med Office 365 
| R-visuals | Nej | Ja | [Opret visuelle R-elementer](../service-r-visuals.md) i Power BI-tjenesten  
| Funktioner til eksempelvisning | Nej | Ja | [Tilmeld dig prøveversioner af funktioner i Power BI-tjenesten](../service-preview-features.md) 
| Brugerdefinerede visuelle elementer | Ja | Ja | [Brugerdefinerede visualiseringer i Power BI](../power-bi-custom-visuals.md) 
| Power BI Desktop | Version, der er optimeret til rapportserveren, kan downloades med rapportserveren | Version, der er optimeret til Power BI-tjenesten, er tilgængelig fra Windows Store | [Power BI Desktop til rapportserveren](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop til Power BI-tjenesten](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Næste trin
[Installer Power BI-rapportserver](install-report-server.md)  



