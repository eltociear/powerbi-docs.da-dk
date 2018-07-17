---
title: PowerShell-cmdlet'er, REST API'er og .NET SDK til administration af Power BI
description: Få mere at vide om de måder, hvorpå du kan administrere Power BI via scripts og programmerings-API'er.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: ffb2ae077add5756af63f07d8f3da830e075e0b4
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945254"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell-cmdlet'er, REST API'er og .NET SDK til administration af Power BI
Power BI gør det muligt for administratorer at scripte almindelige opgaver med PowerShell-cmdlet'er. Den eksponerer også REST API'er og giver en .NET SDK til udvikling af administrative løsninger. Dette emne viser en liste over cmdlet'er og den tilsvarende SDK-metode og REST API-slutpunktet. Her finder du flere oplysninger:

  - PowerShell [download](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) og [dokumentation](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - REST API-[dokumentation](https://docs.microsoft.com/rest/api/power-bi/admin)
  - .NET SDK-[download](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) 


| **Cmdlet-navn** | **SDK-metode** | **REST API-slutpunkt** | **Beskrivelse** |
| --- | --- | --- | --- |
| **Hent-PowerBIDatakilde** | Datasæt\_HentDatakilderSomAdministrator | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Henter datakilderne for et givet datasæt. |
| **Hent-PowerBIDatasæt** | Datasæt\_HentDatasætSomAdministrator | /v1.0/myorg/admin/datasets | Henter den komplette liste over datasæt i en Power BI-lejer. |
| **Hent-PowerBIArbejdsområde** | Grupper\_HentGrupperSomAdministrator | /v1.0/myorg/admin/groups | Henter den komplette liste over arbejdsområder i en Power BI-lejer. |
| **Tilføj PowerBIArbejdsområdeBruger** | Grupper\_TilføjBrugerSomAdministrator | /v1.0/myorg/admin/groups/{groupId}/users | Tilføjer en bruger som medlem af et givet arbejdsområde. |
| **Fjern-PowerBIArbejdsområdeBruger** | Grupper\_SletBrugerSomAdministrator | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Fjerner en bruger fra medlemslisten for et givet arbejdsområde. |
| **Gendan-PowerBIArbejdsområde** | Grupper\_GendanSlettetGruppeSomAdministrator | /v1.0/myorg/admin/groups/{groupId}/restore | Gendanner et slettet arbejdsområde. |
| **Sæt-PowerBIArbejdsområde** | Grupper\_OpdaterGruppeSomAdministrator | /v1.0/myorg/admin/groups/{groupId} | Opdaterer egenskaberne for et givet arbejdsområde. |
| **Hent-PowerBIDatasæt – ArbejdsområdeId** | Grupper\_HentDatassætSomAdministrator | /v1.0/myorg/admin/groups/{group\_id}/datasets | Henter datasættene inden for et givet arbejdsområde. |
| **Eksporter-PowerBIRapport** | Rapporter\_EksporterRapportSomAdministrator | I/T | Eksporterer en given rapport til en lokal fil. |
| **Hent-PowerBIRapport** | Rapporter\_HentRapportSomAdministrator | /v1.0/myorg/admin/reports | Henter den komplette liste over rapporter i en Power BI-lejer. |
| **Hent-PowerBIDashboard** | Dashboards\_HentDashboardsSomAdministrator | /v1.0/myorg/admin/dashboards | Henter den komplette liste over dashboards i en Power BI-lejer. |
| **Hent-PowerBIDashboard – ArbejdsområdeId** | Grupper\_HentDashboardsSomAdministrator | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Henter dashboards inden for et givet arbejdsområde. |
| **Hent-PowerBIFelt – DashboardId** | Dashboards\_HentFelterSomAdministrator | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Henter felterne til et givet dashboard. |
| **Hent-PowerBIReport – ArbejdsområdeId** | Grupper\_HentRapportSomAdministrator | /v1.0/myorg/admin/groups/{group\_id}/reports | Henter rapporterne inden for et givet arbejdsområde. |
| **Hent-PowerBIImport** | Importer\_HenterImporterSomAdministrator | /v1.0/myorg/admin/imports | Henter den komplette liste over importer i en Power BI-lejer. |
| **Opret forbindelse-PowerBIServicekonto** | I/T | I/T | Log på Power BI, og begynd en session. |
| **AfbrydForbindelsen-PowerBIServicekonto** | I/T | I/T | Log af Power BI, og luk den eksisterende session. |
| **Aktivér-PowerBIHvilemetode** | I/T | I/T | Send vilkårlige REST API-kald til Power BI. |
| **Hent-PowerBIAdgangstoken** | I/T | I/T | Få adgangstokenet til Power BI i en session. |
| **Løs-PowerBIFejl** | I/T | I/T | Få detaljerede fejloplysninger for mislykkedes cmdlet-kald. |