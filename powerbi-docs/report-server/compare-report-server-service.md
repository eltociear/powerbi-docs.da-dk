---
title: Sammenlign Power BI-rapportserveren med Power BI-tjenesten
description: I denne artikel sammenlignes funktionerne i Power BI-rapportserveren og Power BI-tjenesten.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.date: 09/13/2019
ms.openlocfilehash: d2c0ab82a3b262a975c461a4414ed7fd3b1bc060
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/17/2019
ms.locfileid: "71075890"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Sammenlign Power BI-rapportserveren med Power BI-tjenesten

Power BI-rapportserveren og Power BI-tjenesten har mange ligheder og nogle vigtige forskelle. I denne tabel forklares det, hvad der er hvad.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Funktioner i Power BI-rapportserveren og Power BI-tjenesten

| Funktioner | Power BI-rapportserver | Power BI-tjeneste | Noter |
|---------|---------|---------|---------|
| Installation | I det lokale miljø eller i hostet cloud | Cloud | Power BI-rapportserveren kan installeres i Azure VM'er (hostet cloud), hvis det er givet i licens via Power BI Premium |
| Kildedata | Cloud og/eller i det lokale miljø | Cloud og/eller i det lokale miljø |  |
| Licens | Power BI Premium eller SQL Server EE med SA | Power BI Pro-og/eller Power BI Premium | |  
| Livscyklus | Politik for moderne livscyklus | Fuldt administreret tjeneste |  |
| Versionscyklus | En gang hver 4. måned | En gang om måneden | Nyeste funktioner og løsninger optræder først i Power BI-tjenesten. De fleste kernefunktioner findes i Power BI-rapportserveren i de næste par versioner. Nogle funktioner er kun beregnet til Power BI-tjenesten. |
| Opret Power BI-rapporter i Power BI Desktop | Ja | Ja |  |
| Opret Power BI-rapporter i browseren | Nej | Ja |  |
| Gateway påkrævet | Nej | Ja, for datakilder i det lokale miljø |  |
| Streaming i realtid | Nej | Ja | [Streaming i realtid i Power BI](../service-real-time-streaming.md) |
| Dashboards | Nej | Ja | [Dashboards i Power BI-tjenesten](../consumer/end-user-dashboards.md) |
| Distribuer gruppe af rapporter ved hjælp af apps | Nej | Ja | [Opret og udgiv apps med dashboards og rapporter](../service-create-distribute-apps.md) |
| Indholdspakker | Nej | Ja | [Organisationsindholdspakker: Introduktion](../service-organizational-content-pack-introduction.md) |
| Opret forbindelse til tjenester som Salesforce | Ja | Ja | [Opret forbindelse til de tjenester, du bruger](../service-connect-to-services.md) med indholdspakker i Power BI-tjenesten. På Power BI-rapportserveren skal du bruge certificerede connectorer til at oprette forbindelse til tjenester. Du kan finde flere detaljer i [Power BI-rapportdatakilderne på Power BI-rapportserver](data-sources.md). |
| Spørgsmål og svar | Nej | Ja | [Spørgsmål og svar i Power BI-tjenesten og Power BI Desktop](../power-bi-tutorial-q-and-a.md) 
| Hurtig indsigt | Nej | Ja | [Generér automatisk dataindsigt med Power BI](../consumer/end-user-insights.md) |
| Analysér i Excel | Nej | Ja | [Analysér i Excel](../service-analyze-in-excel.md) 
| Sideinddelte rapporter | Ja | Ja | [Sideinddelte rapporter er tilgængelige i Power BI-tjenesten](../paginated-reports-report-builder-power-bi.md) som prøveversion i en Premium-kapacitet |
| Power BI-mobilapps | Ja | Ja | [Oversigt over Power BI-mobilapps](../consumer/mobile/mobile-apps-for-mobile-devices.md) |
| ARC GIS-kort | Nej | Ja | [ArcGIS-kort i Power BI-tjenesten og Power BI Desktop fra Esri](../visuals/power-bi-visualization-arcgis.md) |
| Mailabonnementer på Power BI-rapporter | Nej | Ja | [Meld dig selv eller andre til et abonnement](../service-report-subscribe.md) på en rapport eller et dashboard i Power BI-tjenesten |
| Mailabonnementer på sideinddelte rapporter | Ja | Ja | [Meld dig selv og andre til et abonnement på sideinddelte rapporter i Power BI-tjenesten](../paginated-reports-subscriptions.md)<br><br>[Maillevering i Reporting Services](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  |
| Databeskeder | Nej | Ja | [Databeskeder](../service-set-data-alerts.md) i Power BI-tjenesten
| Sikkerhed på rækkeniveau (RLS) | Ja | Ja | Tilgængelige i både DirectQuery- (datakilde) og importtilstand <br><br>Sikkerhed på rækkeniveau i [Power BI-tjenesten](../service-admin-rls.md) <br><br>Sikkerhed på rækkeniveau i [Power BI-rapportserver](row-level-security-report-server.md) |
| Fuldskærmsvisning | Nej | Ja | [Fuldskærmsvisning](../consumer/end-user-focus.md) i Power BI-tjenesten |
| Avanceret samarbejde i Office 365 | Nej | Ja | [Samarbejd i et apparbejdsområde](../service-collaborate-power-bi-workspace.md) med Office 365 |
| R-visualiseringer | Nej | Ja | [Opret R-visualiseringer](../desktop-r-visuals.md) i Power BI Desktop, og publicer dem i Power BI-tjenesten. Du kan ikke gemme Power BI-rapporter med R-visualiseringer på Power BI-rapportserveren.  |
| Prøveversionsfunktioner | Nej | Ja | [Tilmeld dig prøveversioner af funktioner i Power BI-tjenesten](../consumer/end-user-preview-features.md) |
| Brugerdefinerede visualiseringer | Ja | Ja | [Brugerdefinerede visualiseringer i Power BI](../power-bi-custom-visuals.md) |
| Power BI Desktop | Version, der er optimeret til rapportserveren, kan downloades med rapportserveren | Version, der er optimeret til Power BI-tjenesten, er tilgængelig fra Windows Store | [Power BI Desktop til rapportserveren](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop til Power BI-tjenesten](http://aka.ms/pbidesktopstore) |

## <a name="next-steps"></a>Næste trin

[Installer Power BI-rapportserver](install-report-server.md)
