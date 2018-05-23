---
title: Integrer et dashboard i en app for din organisation
description: Få mere at vide om, hvordan du kan integrere et dashboard i en webapp ved hjælp af API'er til Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 979b76350b9867bbc684a70bd89a82f88993e625
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Integrer et dashboard i en app for din organisation
Få mere at vide om, hvordan du integrerer et dashboard i en webapp ved hjælp af REST-API-kald sammen med Power BI JavaScript-API'en, når du integrerer for din organisation.

![Integreret dashboard](media/integrate-dashboard/powerbi-embed-dashboard.png)

Før du begynder, skal du have en **Power BI**-konto. Hvis du ikke har en konto, kan du [oprette en Power BI-konto](../service-self-service-signup-for-power-bi.md), eller du kan oprette din egen [Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md), som du kan bruge til test.

> [!NOTE]
> Forsøger du at integrere et dashboard til dine kunder ved hjælp af et embed-token? Se [Integrer et dashboard, et felt eller en rapport i din app til dine kunder](embed-sample-for-customers.md).
> 
> 

Hvis du vil integrere et dashboard i en webapp, skal du bruge **Power BI** REST-API'en eller Power BI C#-SDK'en og et Azure Active Directory-godkendelses**adgangstoken** for at hente et dashboard. Derefter skal du indlæse dashboardet ved hjælp af det samme adgangstoken. **Power BI**-API'en giver programmeringsmæssig adgang til visse **Power BI**-ressourcer. Du kan finde flere oplysninger under [Oversigt over Power BI REST-API](https://msdn.microsoft.com/library/dn877544.aspx) og [Power BI JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Hent eksemplet
I denne artikel vises den kode, der bruges i [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) på GitHub. Hvis du vil følge med i gennemgangen, kan du hente eksemplet.

## <a name="step-1---register-an-app-in-azure-ad"></a>Trin 1 – Registrer en app i Azure AD
Du skal registrere din app i Azure AD, før du kan foretage REST API-kald. Du kan finde flere oplysninger i [Registrer en Azure AD-app for at integrere Power BI-indhold](register-app.md).

Hvis du har hentet [eksemplet Integrate a dashboard](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), skal du bruge det **klient-id** og den **klienthemmelighed**, du får efter registreringen, så eksemplet kan godkendes i Azure AD. Du kan konfigurere eksemplet ved at ændre **klient-id'et** og **klienthemmeligheden** i filen *cloud.config*.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Trin 2 – Få et adgangstoken fra Azure AD
I applikationen skal du først hente et **adgangstoken** fra Azure AD, før du kan foretage kald til Power BI REST-API'en. Du kan finde flere oplysninger i [Godkend brugere, og hent et Azure AD-adgangstoken til din Power BI-app](get-azuread-access-token.md).

## <a name="step-3---get-a-dashboard"></a>Trin 3 – hent et dashboard
Hvis du vil hente et **Power BI**-dashboard, skal du bruge handlingen [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx), som henter en liste over **Power BI**-dashboards. Du kan hente et dashboard-id fra listen over dashboards.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Hent dashboards ved hjælp af et adgangstoken
Du kan bruge det **adgangstoken**, du fik på [trin 2](#step-2-get-an-access-token-from-azure-ad), til at kalde handlingen [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx). Handlingen [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) returnerer en liste over dashboards. Du kan hente et enkelt dashboard på listen over dashboards. Nedenfor finder du en komplet C#-metode til at hente et dashboard. 

Du skal inkludere en *godkendelsesheader* i formatet *Bearer {adgangstoken}* for at kunne foretage REST-API-kaldet.

#### <a name="get-dashboards-with-the-rest-api"></a>Hent dashboards med REST-API'en
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>Hent dashboards ved hjælp af .NET-SDK'en
Du kan bruge .NET-SDK'et til at hente en liste over dashboards i stedet for at kalde REST-API'en direkte.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>Trin 4 – indlæs et dashboard ved hjælp af JavaScript
Du kan bruge JavaScript til at indlæse et dashboard i et div-element på din webside.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Hvis du har downloadet og kørt [eksemplet Integrate a dashboard](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), vil det nogenlunde se ud som nedenfor.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>Hændelser ved klik på felter
I eksemplet ovenfor har du muligvis bemærket, at du kan administrere, hvad der sker, når der klikkes på feltet på dashboardet. Du kan finde flere oplysninger om hændelser under [Håndtering af hændelser i JavaScript-API'en](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

Hvis du har downloadet og kørt [eksemplet Integrate a dashboard](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app), vil der blive vist tekst under dashboardet, når der klikkes på et felt. Teksten vil se nogenlunde ud som følgende. Det vil gøre det muligt for dig at registrere, at der er blevet klikket på et felt, så du kan sende brugeren til det rette sted.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Arbejde med grupper (apparbejdsområder)
Hvis du vil integrere et dashboard fra en gruppe (apparbejdsområde), skal du hente listen over alle tilgængelige dashboards i en gruppe ved hjælp af følgende REST-API-kald. Du kan finde flere oplysninger om dette REST-API-kald under [Hent dashboards](https://msdn.microsoft.com/library/mt465739.aspx). Du skal have tilladelser til denne gruppe, for at anmodningen returnerer resultater.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

Den ovenstående API returnerer en liste over tilgængelige dashboards. Hvert dashboard har egenskaben EmbedUrl, der allerede er defineret til at understøtte gruppeintegration.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Begrænsninger
* De slutbrugere, der skal bruge de integrerede dashboards, skal have en Power BI-konto og have adgang til dashboardet. Enten skal personen selv eje dashboardet, eller dashboardet skal deles med brugeren.
* Spørgsmål og svar understøttes i øjeblikket ikke i integrerede dashboards.
* Der er en midlertidig begrænsning: Når du deler et dashboard med sikkerhedsgrupper, skal brugeren først have adgang til alle dashboards på PowerBI.com, før vedkommende får det vist som integreret.

## <a name="next-steps"></a>Næste trin
Du kan finde en prøveapp på GitHub, som du kan gennemse. Ovenstående eksempler er baseret på denne prøveapp. Du kan finde flere oplysninger under [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

Du kan finde flere oplysninger om JavaScript-API'en i [Power BI JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

