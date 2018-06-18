---
title: Integrer en Power BI-rapport i en app for din organisation
description: Få mere at vide om, hvordan du integrerer en rapport i en webapp ved hjælp af Power BI-API'er.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 032e0ed05d56d2d7f1e2b41cfd922999ff43ea94
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813359"
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Integrer en rapport i en app for din organisation
Få mere at vide om, hvordan du integrerer en rapport i en webapp ved hjælp af REST-API-kald sammen med Power BI JavaScript-API'en, når du integrerer for din organisation.

![Eksempel på en integreret rapport](media/integrate-report/powerbi-embedded-report.png)

Før du begynder denne gennemgang, skal du have en **Power BI**-konto. Hvis du ikke har en konto, kan du [tilmelde dig en gratis Power BI-konto](../service-self-service-signup-for-power-bi.md), eller du kan oprette din egen [Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md), som du kan bruge til testformål.

> [!NOTE]
> Vil du i stedet gerne integrere en rapport for dine kunder ved hjælp af et integreringstoken? Se [Integrer et dashboard, et felt eller en rapport i din app for dine kunder](embed-sample-for-customers.md).
> 
> 

Du integrerer en rapport i en webapp ved hjælp af **Power BI** REST-API'en eller Power BI C#-SDK'en og et **adgangstoken** til Azure AD-godkendelse (Active Directory) for at hente en rapport. Derefter skal du indlæse rapporten ved hjælp af det samme adgangstoken. **Power BI**-API'en leverer programmatisk adgang til visse **Power BI**-ressourcer. Du kan finde flere oplysninger under [Power BI REST-API](https://docs.microsoft.com/rest/api/power-bi/) og [Power BI JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Download eksemplet
I denne artikel vises den kode, der bruges i [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) på GitHub. For at kunne følge med i denne gennemgang skal du downloade eksemplet.

Du kan også gennemgå [Onboarding Experience Tool](https://aka.ms/embedsetup/UserOwnsData) for hurtigt at komme i gang og downloade en eksempelapp.

Hvis du vælger at konfigurere miljøet manuelt, kan du dog fortsætte nedenfor.

## <a name="step-1---register-an-app-in-azure-ad"></a>Trin 1 – Registrer en app i Azure AD
Du skal registrere din app i Azure AD, før du kan foretage REST API-kald. Du kan finde flere oplysninger under [Registrer en Azure AD-app for at integrere Power BI-indhold](register-app.md).

Hvis du har downloadet [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), skal du bruge det **klient-id** og den **klienthemmelighed**, du får efter registreringen, så eksemplet kan godkendes i Azure AD. Du kan konfigurere eksemplet ved at ændre **klient-id'et** og **klienthemmeligheden** i filen *cloud.config*.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Trin 2 – Få et adgangstoken fra Azure AD
I applikationen skal du først hente et **adgangstoken** fra Azure AD, før du kan foretage kald til Power BI REST-API'en. Du kan finde flere oplysninger under [Godkend brugere, og få et Azure AD-adgangstoken til din Power BI-app](get-azuread-access-token.md).

## <a name="step-3---get-a-report"></a>Trin 3 – Hent en rapport
Du henter en **Power BI**-rapport ved at bruge handlingen [Hent rapporter](https://docs.microsoft.com/rest/api/power-bi/reports/getreports), hvorved **Power BI**-rapporter hentes. Du kan få et rapport-id fra listen over rapporter.

### <a name="get-reports-using-an-access-token"></a>Hent rapporter ved hjælp af et adgangstoken
Du kan bruge det **adgangstoken**, du fik under [trin 2](#step-2-get-an-access-token-from-azure-ad), til at kalde handlingen [Hent rapporter](https://docs.microsoft.com/rest/api/power-bi/reports/getreports). Handlingen [Hent rapporter](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) returnerer en liste over rapporter. Du kan få en enkelt rapport på listen over rapporter. Nedenfor finder du en komplet C#-metode til at hente en rapport. 

Du skal inkludere en *godkendelsesheader* i formatet *Bearer {adgangstoken}* for at kunne foretage REST-API-kaldet.

#### <a name="get-reports-with-the-rest-api"></a>Hent rapport ved hjælp af REST-API'en
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>Hent rapporter ved hjælp af .NET-SDK
Du kan bruge .NET-SDK'et til at hente en liste over rapporter i stedet for at kalde REST-API'en direkte.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>Trin 4 – Indlæs en rapport ved hjælp af JavaScript
Du kan bruge JavaScript til at indlæse en rapport i et div-element på din webside.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Hvis du har downloadet og kørt [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), vil eksemplet ligne nedenstående.

![Eksempel på en integreret rapport](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Arbejde med grupper (apparbejdsområder)
Hvis du vil integrere en rapport fra en gruppe (apparbejdsområde), skal du hente listen over alle tilgængelige rapporter på en gruppes dashboard ved hjælp af følgende REST-API-kald. Du kan finde flere oplysninger om dette REST-API-kald under [Hent rapporter](https://docs.microsoft.com/rest/api/power-bi/reports/getreports). Du skal have tilladelser i denne gruppe, for at anmodningen returnerer resultater.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

Den ovenstående API returnerer en liste over tilgængelige rapporter. Hver rapport har egenskaben EmbedUrl, der allerede er defineret til at understøtte gruppeintegration.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Næste trin
Du kan finde en eksempelapp på GitHub, som du kan gennemse. Du kan finde flere oplysninger under [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

Du kan finde flere oplysninger om JavaScript API'en under [Power BI JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

