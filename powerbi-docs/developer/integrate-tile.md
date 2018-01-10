---
title: Integrer et Power BI-felt i en app for organisationen
description: Gennemgang af integration af et felt i en app, eksempelkode
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 12/19/2017
ms.author: asaxton
ms.openlocfilehash: 70ffefa9845f8440205460ee0083f8dc334b7c81
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/05/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Integrer et felt i en app (brugeren ejer dataene)
Få mere at vide om, hvordan du integrerer et felt i en webapp ved hjælp af REST-API-kald sammen med Power BI JavaScript-API'en, når du integrerer for din organisation.

![Integreret felt i webprogram](media/integrate-tile/powerbi-embedded-tile.png)

Før du begynder denne gennemgang, skal du have en konto til **Power BI**. Hvis du ikke har en konto, kan du [tilmelde dig en gratis Power BI-konto](../service-self-service-signup-for-power-bi.md), eller du kan oprette din egen [Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md), som du kan bruge til testformål.

> [!NOTE]
> Forsøger du at integrere et felt for dine kunder vha. et embedtoken? Se [Integrer et dashboard, et felt eller en rapport i din app for dine kunder](embed-sample-for-customers.md).
> 
> 

Hvis du vil integrere et felt i en webapp, skal du bruge **Power BI** REST-API'en eller Power BI C#-SDK'en og et Azure Active Directory-godkendelses**adgangstoken** for at hente et felt. Derefter skal du indlæse feltet vha. det samme adgangstoken. API'en til **Power BI** leverer programadgang til visse **Power BI**-ressourcer. Du kan finde flere oplysninger under [Oversigt over Power BI REST-API](https://msdn.microsoft.com/library/dn877544.aspx) og [Power BI JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Download eksemplet
I denne artikel vises den kode, der bruges i [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) på GitHub. Hvis du vil følge med i gennemgangen, kan du hente eksemplet.

## <a name="step-1---register-an-app-in-azure-ad"></a>Trin 1 – Registrer en app i Azure AD
Du skal registrere din app i Azure AD, før du kan foretage REST API-kald. Du kan finde flere oplysninger i [Registrer en Azure AD-app for at integrere Power BI-indhold](register-app.md).

Hvis du har hentet [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), skal du bruge det **klient-id** og den **klienthemmelighed**, du får efter registreringen, så eksemplet kan godkendes i Azure AD. Du kan konfigurere eksemplet ved at ændre **klient-id'et** og **klienthemmeligheden** i filen *cloud.config*.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Trin 2 – Få et adgangstoken fra Azure AD
I applikationen skal du først hente et **adgangstoken** fra Azure AD, før du kan foretage kald til Power BI REST-API'en. Du kan finde flere oplysninger i [Godkend brugere, og få et Azure AD-adgangstoken til din Power BI-app](get-azuread-access-token.md).

## <a name="step-3---get-a-tile"></a>Trin 3 – Hent et felt
Hvis du vil hente et **Power BI**-felt, skal du bruge handlingen [Hent felter](https://msdn.microsoft.com/library/mt465741.aspx), som henter en liste over **Power BI**-felter fra et bestemt dashboard. Fra listen over felter kan du få et felt-id og en integreret URL-adresse.

Du skal hente et dashboard-id, før du kan få feltet. Du kan finde oplysninger om, hvordan du henter et dashboard, under [Integrer et dashboard i en app (brugeren ejer dataene)](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Hent felter ved hjælp af et adgangstoken
Du kan bruge det **adgangstoken**, du fik på [trin 2](#step-2-get-an-access-token-from-azure-ad), til at kalde handlingen [Hent felter](https://msdn.microsoft.com/library/mt465741.aspx). Handlingen [Hent felter](https://msdn.microsoft.com/library/mt465741.aspx) returnerer en liste over felter. Du kan få et enkelt felt på listen over felter. Nedenfor finder du en komplet C#-metode til at hente et felt. 

Du skal inkludere en *godkendelsesheader* i formatet *Bearer {adgangstoken}* for at kunne foretage REST-API-kaldet.

#### <a name="get-tiles-with-the-rest-api"></a>Hent felter med REST-API'en
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>Hent felter ved hjælp af .NET-SDK
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
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>Trin 4 – Indlæs et felt ved hjælp af JavaScript
Du kan bruge JavaScript til at indlæse et felt i et div-element på din webside.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

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
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Hvis du har downloadet og kørt [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), vil det se nogenlunde ud som nedenfor.

![Integreret felt i webprogram](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Arbejde med grupper (apparbejdsområder)
Hvis du vil integrere et felt fra en gruppe (apparbejdsområde), skal du hente listen over alle tilgængelige felter på en gruppes dashboard ved hjælp af følgende REST-API-kald. Du kan finde flere oplysninger om dette REST-API-kald under [Hent felter](https://msdn.microsoft.com/library/mt465741.aspx). Du skal have tilladelser til denne gruppe, for at anmodningen returnerer resultater.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

Den ovenstående API returnerer en liste over tilgængelige felter. Hvert felt har egenskaben EmbedUrl, der allerede er defineret til at understøtte gruppeintegration.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Næste trin
[Feltet Integrer](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) i PowerBI-JavaScript Wiki

[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript).

Eksemplet [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) på GitHub.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

