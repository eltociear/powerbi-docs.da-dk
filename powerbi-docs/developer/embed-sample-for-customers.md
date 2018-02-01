---
title: Integrer Power BI-indhold i en app til dine kunder
description: "Få mere at vide om, hvordan du kan integrere et dashboard, et felt eller en rapport i en webapp ved hjælp af API'er til Power BI til dine kunder."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/11/2018
ms.author: maghan
ms.openlocfilehash: c6b9edb929934a80886874fe421f11cc7462dbd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>Integrer Power BI-dashboards, -felter eller -rapporter i din app
Få mere at vide om, hvordan du integrerer et dashboard, et felt eller en rapport i en webapp ved hjælp af Power BI .NET SDK sammen med Power BI JavaScript API, når du integrerer til dine kunder. Dette er det typiske ISV-scenario.

![Integreret dashboard](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

Før du begynder, skal du have en **Power BI Pro**-konto. Hvis du ikke har en konto, kan du [oprette en gratis Power BI-konto](../service-self-service-signup-for-power-bi.md) og derefter tilmelde dig og modtage en [Power BI Pro-prøveversion](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial), eller du kan oprette din egen [Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md) til testbrug.

> [!NOTE]
> Vil du integrere et dashboard for din organisation i stedet? Se i [Integrer et dashboard i en app for din organisation](integrate-dashboard.md).
> 
> 

Hvis du vil integrere et dashboard i en webapp, skal du bruge API'en til **Power BI** og et **adgangstoken** til Azure Active Directory for at hente et dashboard. Derefter skal du indlæse dashboardet ved hjælp af et integrationstoken. API'en til **Power BI** leverer programadgang til visse **Power BI**-ressourcer. Du kan finde flere oplysninger i [Oversigt over Power BI REST API](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp) og [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Hent eksemplet
I denne artikel vises den kode, der bruges i [eksemplet Embedding for your organization](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) på GitHub. Hvis du vil følge med i gennemgangen, kan du hente eksemplet.

## <a name="step-1---register-an-app-in-azure-ad"></a>Trin 1 – Registrer en app i Azure AD
Du skal registrere din app i Azure AD, før du kan foretage REST API-kald. Du kan finde flere oplysninger i [Registrer en Azure AD-app for at integrere Power BI-indhold](register-app.md).

Hvis du har hentet [eksemplet Embedding for your organization](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data), skal du bruge det **klient-id**, du får efter registreringen, så det kan godkendes i Azure AD. Du kan konfigurere prøveappen ved at ændre **clientId** i filen *web.config*.

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Trin 2: Få en adgangstoken fra Azure AD
I applikationen skal du først hente et **adgangstoken** fra Azure AD, før du kan foretage kald til Power BI REST-API'en. Du kan finde flere oplysninger i [Godkend brugere, og få et Azure AD-adgangstoken til din Power BI-app](get-azuread-access-token.md).

Du kan se eksempler på dette i hver indholdselementopgave i **Controllers\HomeController.cs**.

## <a name="step-3---get-a-content-item"></a>Trin 3: Hent et indholdselement
Før du integrerer dit Power BI-indhold, er der nogle ting, du skal gøre for at sikre, at det bliver korrekt integreret. Selvom alle disse trin kan udføres direkte med REST API, er .NET SDK blevet brugt til prøveappen og eksemplerne her.

### <a name="create-the-power-bi-client-with-your-access-token"></a>Opret Power BI-klienten med dit eget adgangstoken
Brug dit adgangstoken til at oprette dit Power BI-klientobjekt, som gør det muligt for dig at interagere med API'erne til Power BI. Det gør du ved at omgive AccessToken med objektet *Microsoft.Rest.TokenCredentials*.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Hent det indholdselementet, du vil integrere
Du kan bruge Power BI-klientobjektet til at hente en reference til det element, du vil integrere. Du kan integrere dashboards, felter eller rapporter. Her er et eksempel på, hvordan du henter det første dashboard, felt eller den første rapport fra et givent arbejdsområde.

Du kan finde et eksempel på dette i **Controllers\HomeController.cs** i [prøveappen App Owns Data](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Dashboard**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**Felt**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**Rapport**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Opret integrationstokenet
Du skal oprette et integrationstoken, som kan bruges fra JavaScript API'en. Dette integrationstoken er specifikt for det element, du er ved at integrere. Det betyder, at hver gang du integrere Power BI-indhold, skal du oprette et nyt integrationstoken for det. Du kan finde flere oplysninger, herunder hvilket **adgangsniveau** du skal bruge, i [GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx).

> [!IMPORTANT]
> Da integrerede tokens kun er beregnet til udviklingstest, er antallet af integrerede tokens, der kan genereres fra en Power BI-masterkonto, begrænset. Der [skal købes en kapacitet](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) til integrerede produktionsscenarier. Der er ingen grænse for generering af integrerede tokens, når der er købt en kapacitet.

Du kan finde et eksempel på dette i **Controllers\HomeController.cs** i [prøveappen Embedding for your organization](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Dette forudsætter, at der oprettes en klasse for **EmbedConfig** og **TileEmbedConfig**. Du kan finde et eksempel på dette i **Models\EmbedConfig.cs** og **Models\TileEmbedConfig.cs**.

**Dashboard**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**Felt**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**Rapport**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```



## <a name="step-4---load-an-item-using-javascript"></a>Trin 4: Indlæs et element, ved hjælp af JavaScript
Du kan bruge JavaScript til at indlæse et dashboard i et div-element på din webside. Modellen EmbedConfig/TileEmbedConfig bruges sammen med visninger for et dashboard, et felt eller en rapport i dette eksempel. Hvis du vi se et komplet eksempel, hvor JavaScript API'en bruges, kan du bruge [prøveappen Microsoft Power BI Embedded](https://microsoft.github.io/PowerBI-JavaScript/demo).

Du kan finde et eksempel på dette i [prøveappen Embedding for your organization](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>Næste trin
Du kan finde en prøveapp på GitHub, som du kan gennemse. Ovenstående eksempler er baseret på denne prøveapp. Du kan finde flere oplysninger i [Prøveappen Embedding for your organization](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Du kan finde flere oplysninger om JavaScript API'en i [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

