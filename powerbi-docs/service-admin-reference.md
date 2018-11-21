---
title: PowerShell-cmdlet'er, REST-API'er og .NET SDK til administratorer
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
ms.openlocfilehash: 1ed4298e4ed4cddcdf965bd427c654cab6adf1e6
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157005"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell-cmdlet'er, REST API'er og .NET SDK til administration af Power BI
Power BI gør det muligt for administratorer at scripte almindelige opgaver med PowerShell-cmdlet'er. Den eksponerer også REST API'er og giver en .NET SDK til udvikling af administrative løsninger. Dette emne viser en liste over cmdlet'er og den tilsvarende SDK-metode og REST API-slutpunktet. Her finder du flere oplysninger:

- PowerShell [download](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) og [dokumentation](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API-[dokumentation](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK-[download](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

| **Cmdlet-navn** | **Aliasser** | **SDK-metode** | **REST API-slutpunkt** | **Beskrivelse** |
| --- | --- | --- | --- | --- |
| **Hent-PowerBIDatakilde** | I/T | Datasæt\_HentDatakilderSomAdministrator | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Henter datakilderne for et givet datasæt. |
| **Hent-PowerBIDatasæt** | I/T | Datasæt\_HentDatasætSomAdministrator | /v1.0/myorg/admin/datasets | Henter den komplette liste over datasæt i en Power BI-lejer. |
| **Hent-PowerBIArbejdsområde** | **Hent-PowerBIGruppe** | Grupper\_HentGrupperSomAdministrator | /v1.0/myorg/admin/groups | Henter den komplette liste over arbejdsområder i en Power BI-lejer. |
| **Tilføj-PowerBIArbejdsområdebruger** | **Tilføj-PowerBIGruppebruger** |Grupper\_TilføjBrugerSomAdministrator | /v1.0/myorg/admin/groups/{groupId}/users | Tilføjer en bruger som medlem af et givet arbejdsområde. |
| **Fjern-PowerBIArbejdsområdebruger** | **Fjern-PowerBIGruppebruger** | Grupper\_SletBrugerSomAdministrator | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Fjerner en bruger fra medlemslisten for et givet arbejdsområde. |
| **Gendan-PowerBIArbejdsområde** |**Gendan-PowerBIGruppe** | Grupper\_GendanSlettetGruppeSomAdministrator | /v1.0/myorg/admin/groups/{groupId}/restore | Gendanner et slettet arbejdsområde. |
| **Angiv-PowerBIArbejdsområde** |**Angiv-PowerBIGruppe** | Grupper\_OpdaterGruppeSomAdministrator | /v1.0/myorg/admin/groups/{groupId} | Opdaterer egenskaberne for et givet arbejdsområde. |
| **Hent-PowerBIDatasæt – ArbejdsområdeId** | I/T | Grupper\_HentDatassætSomAdministrator | /v1.0/myorg/admin/groups/{group\_id}/datasets | Henter datasættene inden for et givet arbejdsområde. |
| **Eksporter-PowerBIRapport** | I/T | Rapporter\_EksporterRapportSomAdministrator | I/T | Eksporterer en given rapport til en lokal fil. |
| **Hent-PowerBIRapport** | I/T | Rapporter\_HentRapportSomAdministrator | /v1.0/myorg/admin/reports | Henter den komplette liste over rapporter i en Power BI-lejer. |
| **Hent-PowerBIDashboard** | I/T | Dashboards\_HentDashboardsSomAdministrator | /v1.0/myorg/admin/dashboards | Henter den komplette liste over dashboards i en Power BI-lejer. |
| **Hent-PowerBIDashboard** | I/T | Grupper\_HentDashboardsSomAdministrator | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Henter dashboards inden for et givet arbejdsområde. |
| **Hent-PowerBIFelt** | **Hent-PowerBIDashboardfelt** | Dashboards\_HentFelterSomAdministrator | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Henter felterne til et givet dashboard. |
| **Hent-PowerBIRapport** | I/T | Grupper\_HentRapportSomAdministrator | /v1.0/myorg/admin/groups/{group\_id}/reports | Henter rapporterne inden for et givet arbejdsområde. |
| **Hent-PowerBIImport** | I/T | Importer\_HenterImporterSomAdministrator | /v1.0/myorg/admin/imports | Henter den komplette liste over importer i en Power BI-lejer. |
| **Opret forbindelse-PowerBIServicekonto** | **Logon-PowerBI** &  **Logon-PowerBITjenestekonto** | I/T | I/T | Log på Power BI, og begynd en session. |
| **AfbrydForbindelsen-PowerBIServicekonto** | **Logout-PowerBI** & **Logout-PowerBITjenestekonto** | I/T | I/T | Log af Power BI, og luk den eksisterende session. |
| **Aktivér-PowerBIHvilemetode**| I/T | I/T | I/T | Send vilkårlige REST API-kald til Power BI. |
| **Hent-PowerBIAdgangstoken**| I/T | I/T | I/T | Få adgangstokenet til Power BI i en session. |
| **Løs-PowerBIFejl**| I/T | I/T | I/T | Få detaljerede fejloplysninger for mislykkedes cmdlet-kald. |