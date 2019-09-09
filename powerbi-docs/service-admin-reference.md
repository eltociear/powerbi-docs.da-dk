---
title: PowerShell-cmdlet'er, REST-API'er og .NET SDK til administratorer
description: Få mere at vide om de måder, hvorpå du kan administrere Power BI via scripts og programmerings-API'er.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: da19eaffff7abfd8edd745cdb58c008ea40eee8a
ms.sourcegitcommit: 9665997274301b228f45aa7250ba557e90164a4d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/06/2019
ms.locfileid: "70751491"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell-cmdlet'er, REST API'er og .NET SDK til administration af Power BI
Power BI gør det muligt for administratorer at scripte almindelige opgaver med PowerShell-cmdlet'er. Den eksponerer også REST API'er og giver en .NET SDK til udvikling af administrative løsninger. Dette emne viser en liste over cmdlet'er og den tilsvarende SDK-metode og REST API-slutpunktet. Her finder du flere oplysninger:

- PowerShell [download](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) og [dokumentation](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API-[dokumentation](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK-[download](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

> Nedenstående cmdlet'er skal kaldes vha. `-Scope Organization` for at fungere i forhold til administration af lejeren.

| **Cmdlet-navn** | **Aliasser** | **SDK-metode** | **REST API-slutpunkt** | **Beskrivelse** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | I/T | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Henter datakilderne for et givet datasæt. |
| `Get-PowerBIDataset` | I/T | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | Henter den komplette liste over datasæt i en Power BI-lejer. |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | Henter den komplette liste over arbejdsområder i en Power BI-lejer. |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | Tilføjer en bruger som medlem af et givet arbejdsområde. |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Fjerner en bruger fra medlemslisten for et givet arbejdsområde. |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | Gendanner et slettet arbejdsområde. |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId} | Opdaterer egenskaberne for et givet arbejdsområde. |
| `Get-PowerBIDataset -WorkspaceId` | I/T | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/datasets | Henter datasættene inden for et givet arbejdsområde. |
| `Get-PowerBIReport` | I/T | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | Henter den komplette liste over rapporter i en Power BI-lejer. |
| `Get-PowerBIDashboard` | I/T | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | Henter den komplette liste over dashboards i en Power BI-lejer. |
| `Get-PowerBIDashboard -WorkspaceId` | I/T | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Henter dashboards inden for et givet arbejdsområde. |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Henter felterne til et givet dashboard. |
| `Get-PowerBIReport` | I/T | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/reports | Henter rapporterne inden for et givet arbejdsområde. |
| `Get-PowerBIImport` | I/T | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | Henter den komplette liste over importer i en Power BI-lejer. |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | I/T | I/T | Log på Power BI, og begynd en session. |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | I/T | I/T | Log af Power BI, og luk den eksisterende session. |
| `Invoke-PowerBIRestMethod`| I/T | I/T | I/T | Send vilkårlige REST API-kald til Power BI. |
| `Get-PowerBIAccessToken`| I/T | I/T | I/T | Få adgangstokenet til Power BI i en session. |
| `Resolve-PowerBIError`| I/T | I/T | I/T | Få detaljerede fejloplysninger for mislykkedes cmdlet-kald. |
