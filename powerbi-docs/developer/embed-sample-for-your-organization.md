---
title: Integreret analyse for at integrere Power BI-indhold i dit program for din organisation
description: Få mere at vide om, hvordan du integrerer en rapport, et dashboard eller et felt i et program ved hjælp af Power BI-API'er for at bruge integreret analyse for din organisation. Få mere at vide om, hvordan du integrerer Power BI i dit program ved hjælp af software til integreret analyse, integrerede analyseværktøjer eller integrerede værktøjer til business intelligence.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: tutorial
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: 3f2d0913095d61999bb85979770c69725b9f9b88
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54283638"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>Selvstudium: Integrer en rapport, et dashboard eller et felt i Power BI i et program for din organisation

I **Power BI** kan du integrere rapporter, dashboards eller felter i et program ved hjælp af funktionen "brugeren ejer data". Ved hjælp af funktionen **brugeren ejer data** kan programmet udvide Power BI-tjenesten til at bruge integreret analyse. Dette selvstudium viser, hvordan du integrerer en rapport i et program. Du kan bruge Power BI .NET SDK med Power BI JavaScript-API'en til at integrere Power BI i et program for din organisation.

![Integrer Power BI-rapport](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

I dette selvstudium får du at vide, hvordan du udfører følgende opgaver:
> [!div class="checklist"]
> * Registrere en app i Azure.
> * Integrer en Power BI-rapport i et program.

## <a name="prerequisites"></a>Forudsætninger

For at komme i gang skal du have en Power BI Pro-konto og et Microsoft Azure-abonnement:

* Hvis du ikke er tilmeldt Power BI Pro, kan du [tilmelde dig en gratis prøveversion](https://powerbi.microsoft.com/en-us/pricing/), før du begynder.
* Hvis du ikke har et Azure-abonnement, skal du oprette en [gratis konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), før du begynder.
* Konfigurer din egen [Microsoft Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md).
* Installér [Visual Studio](https://www.visualstudio.com/), version 2013 eller nyere.

## <a name="set-up-your-embedded-analytics-development-environment"></a>Konfigurer dit integrerede analyseudviklingsmiljø

Før du begynder at integrere rapporter, dashboards eller felter i din app, skal du kontrollere, at du kan integrere i dit miljø. Som en del af installationen, skal du udføre en af disse handlinger:

* Du kan gennemgå [værktøjet til konfiguration af integrering](https://aka.ms/embedsetup/UserOwnsData) for hurtigt at komme i gang med og downloade et eksempelprogram, hvor du kan se, hvordan du opretter et miljø og integrerer en rapport.

* Hvis du vælger at konfigurere miljøet manuelt, kan du udføre trinnene i følgende afsnit:

### <a name="register-an-application-in-azure-active-directory"></a>Registrer et program i Microsoft Azure Active Directory

Registrer dit program i Microsoft Azure Active Directory, så det får adgang til Power BI REST-API'er. Derefter kan du oprette et id for dit program og angive tilladelser til Power BI REST-ressourcer.

1. Acceptér [vilkårene for Microsoft Power BI-API](https://powerbi.microsoft.com/api-terms).

2. Log på [Azure Portal](https://portal.azure.com).

    ![Azure-dashboard](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. Vælg **Alle tjenester** i navigationsruden til venstre, og vælg **Appregistreringer**. Vælg derefter **Registrering af nyt program**.

    ![Søg efter programregistrering](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>

    ![Registrering af nyt program](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. Følg prompterne, og opret et nyt program. I forbindelse med **brugeren ejer dataene** skal du bruge **Webapp/API** som **Programtype**. Angiv en **URL-adresse til logon**, som Azure AD bruger til at returnere tokensvar. Angiv en værdi, der er specifik for dit program. Et eksempel er `http://localhost:13526/`.

    ![Opret en app](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Anvend tilladelser til dit program i Azure Active Directory

Aktivér tilladelser for dit program foruden det, der er angivet på siden til appregistrering. Log på med en global administrator-konto for at aktivere tilladelser.

### <a name="use-the-azure-active-directory-portal"></a>Brug Azure Active Directory-portalen

1. Gå til [App registrations](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) (Appregistreringer) i Azure Portal, og vælg den app, du bruger til at integrere.

    ![Vælg en app](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. Vælg **Indstillinger**. Vælg **Required permissions** (Påkrævede tilladelser) under **API Access** (API-adgang).

    ![Påkrævede tilladelser](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. Vælg **Windows Azure Active Directory**. Kontrollér derefter, at **Åbn mappen som den bruger, der er logget på** er valgt. Vælg **Gem**.

    ![Windows Azure Active Directory-tilladelser](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. Vælg **Tilføj**

    ![Tilføj tilladelser](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. Vælg **Vælg en API**.

    ![Tilføj API-adgang](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. Vælg **Power BI-tjeneste**. Vælg derefter **Vælg**.

    ![Vælg Power BI-tjeneste](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. Vælg alle tilladelser under **Delegated Permission** (Delegerede tilladelser). Vælg dem én for én for at gemme valgene. Vælg **Gem**, når du er færdig.

    ![Vælg delegerede tilladelser](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="set-up-your-power-bi-environment"></a>Konfigurer dit Power BI-miljø

### <a name="create-an-app-workspace"></a>Opret et apparbejdsområde

Hvis du integrerer rapporter, dashboards eller felter til dine kunder, skal du placere dit indhold i et apparbejdsområde:

1. Start med at oprette arbejdsområdet. Vælg **Arbejdsområder** > **Opret apparbejdsområde**. I dette arbejdsområde placerer du det indhold, som dit program skal have adgang til.

    ![Opret et arbejdsområde](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. Giv arbejdsområdet et navn. Hvis det tilsvarende **Arbejdsområde-id** ikke er tilgængeligt, skal du redigere det og angive et entydigt id. Dette navn skal også være navnet på appen.

    ![Navngiv et arbejdsområde](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. Du kan angive nogle forskellige indstillinger. Hvis du vælger **Offentligt** kan alle i din organisation se, hvad arbejdsområdet indeholder. **Privat** betyder, at det kun er medlemmerne af arbejdsområdet, der kan se indholdet.

    ![Vælg Privat eller Offentlig](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    Du kan ikke ændre indstillingen Offentlig eller Privat, efter at du har oprettet gruppen.

4. Du kan også vælge, om medlemmer har adgang til at redigere eller har skrivebeskyttet adgang.

    ![Vælg medlemsadgang](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. Tilføj mailadresser på de personer, du vil give adgang til arbejdsområdet, og vælg **Tilføj**. Du kan ikke tilføje gruppealiasser. Kun enkeltpersoner.

6. Beslut, om hver person skal være medlem eller administrator. Administratorer kan redigere selve arbejdsområdet, herunder tilføje andre medlemmer. Medlemmer kan redigere indholdet i arbejdsområdet, medmindre de har skrivebeskyttet adgang. Både administratorer og medlemmer kan udgive appen.

    Du kan nu se det nye arbejdsområde. Power BI opretter arbejdsområdet og åbner det. Det vises på listen over de arbejdsområder, du er medlem af. Da du er administrator, kan du vælge de tre prikker (…) for at gå tilbage og ændre arbejdsområdet, tilføje nye medlemmer eller ændre deres tilladelser.

    ![Opret apparbejdsområde](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>Opret og udgiv dine rapporter

Du kan oprette dine rapporter og datasæt ved hjælp af Power BI Desktop. Du kan derefter udgive rapporterne i et apparbejdsområde. Den slutbruger, der udgiver rapporterne, skal have en Power BI Pro-licens for at kunne udgive til et apparbejdsområde.

1. Download eksemplet [Blogdemo](https://github.com/Microsoft/powerbi-desktop-samples) fra GitHub.

    ![Download demoen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. Åbn .pbix-eksempelrapporten i Power BI Desktop.

   ![Power BI Desktop-eksempelrapport](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. Udgiv til apparbejdsområdet.

   ![Udgiv en Power BI Desktop-rapport](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    Nu kan du se rapporten online i Power BI-tjenesten.

   ![Få vist en Power BI Desktop-rapport](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-by-using-the-sample-application"></a>Integrer dit indhold ved hjælp af eksempelprogrammet

Følg disse trin for at integrere dit indhold ved hjælp af et eksempelprogram:

1. Download [eksemplet Brugeren ejer dataene](https://github.com/Microsoft/PowerBI-Developer-Samples) fra GitHub for at komme i gang. Der er tre forskellige eksempelprogrammer: et til [rapporter](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), et til [dashboards](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) og et til [felter](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app). Denne artikel henviser til programmet **Rapporter**.

    !["Brugeren ejer dataene"-programeksempel](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. Åbn filen **Cloud.config** i eksempelprogrammet. Der er et par felter, du skal udfylde for at køre programmet: **ApplicationID** og **ApplicationSecret**.

    ![Filen Cloud.config](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    Udfyld oplysningerne om **ApplicationID** med **program-id'et** fra Azure. **ApplicationID** bruges af programmet til at identificere sig selv over for de brugere, som du anmoder om tilladelser fra.

    Hvis du vil hente **ApplicationID**, skal du følge disse trin:

    1. Log på [Azure Portal](https://portal.azure.com).

       ![Azure Portal-dashboard](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    2. Vælg **Alle tjenester** i navigationsruden til venstre, og vælg **Appregistreringer**.

       ![Søg efter programregistrering](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    3. Vælg programmet, der skal bruge **ApplicationID**.

       ![Vælg en app](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    4. Du kan se et **program-id**, der er angivet som et GUID. Brug dette **Program-id** som **ApplicationID** for programmet.

        ![ApplicationID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    Udfyld oplysningerne for **ApplicationSecret** ud fra sektionen **Nøgler** i sektionen **Appregistreringer** i **Azure**.

    Hvis du vil hente **ApplicationSecret**, skal du følge disse trin:

    1. Log på [Azure Portal](https://portal.azure.com).

       ![Azure-portal](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    2. Vælg **Alle tjenester** i navigationsruden til venstre, og vælg **Appregistreringer**.

       ![Søg efter programregistrering](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    3. Vælg programmet, der skal bruge **ApplicationSecret**.

       ![Vælg en app](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    4. Vælg **Indstillinger**.

       ![Vælg Indstillinger](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

    5. Vælg **Nøgler**.

       ![Vælg Nøgler](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

    6. Angiv et navn i feltet **Beskrivelse**, og vælg en varighed. Vælg derefter **Gem** for at hente **værdien** til dit program. Når du lukker ruden **Nøgler** efter at have gemt nøgleværdien, vises feltet med værdien kun som skjult. På det tidspunkt kan du ikke hente nøgleværdien. Hvis du mister nøgleværdien, skal du oprette en ny i Azure Portal.

          ![Nøgleværdi](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

    7. Udfyld **groupId** med apparbejdsområde-GUID'et fra Power BI.

       ![Angiv groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    8. Udfyld **reportId** med rapport-GUID'et fra Power BI.

       ![Angiv reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. Kør programmet:

    Vælg **Kør** i **Visual Studio**.

    ![Kør programmet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    Vælg derefter **Hent rapport**.

    ![Vælg indhold](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    Du kan nu se rapporten i eksempelprogrammet.

    ![Få vist rapporten i programmet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>Integrer dit indhold i dit program

Selvom trinnene til at integrere dit indhold kan gøres med [Power BI REST-API'er](https://docs.microsoft.com/rest/api/power-bi/), oprettes de eksempelkoder, der er beskrevet i denne artikel, med .NET-SDK'en.

Hvis du vil integrere en rapport i en webapp, kan du bruge Power BI REST-API'en eller Power BI C#-SDK'en. Du kan også bruge et adgangstoken til godkendelse af Microsoft Azure Active Directory til at hente en rapport. Derefter skal du indlæse rapporten ved hjælp af det samme adgangstoken. Power BI REST-API'en leverer programmatisk adgang til bestemte Power BI-ressourcer. Du kan finde flere oplysninger under [Power BI REST-API'er](https://docs.microsoft.com/rest/api/power-bi/) og [Power BI JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

### <a name="get-an-access-token-from-azure-ad"></a>Hent et adgangstoken fra Azure AD

I programmet skal du hente et adgangstoken fra Microsoft Azure Active Directory, før du kan foretage kald til Power BI REST-API'en. Du kan finde flere oplysninger under [Godkend brugere, og få et Azure AD-adgangstoken til din Power BI-app](get-azuread-access-token.md).

### <a name="get-a-report"></a>Hent en rapport

Du henter en Power BI-rapport ved at bruge handlingen [Hent rapporter](https://docs.microsoft.com/rest/api/power-bi/reports/getreports), hvilket bevirker, at der hentes en liste over Power BI-rapporter. Du kan få et rapport-id fra listen over rapporter.

### <a name="get-reports-by-using-an-access-token"></a>Hent rapporter ved hjælp af et adgangstoken

Handlingen [Hent rapporter](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) returnerer en liste over rapporter. Du kan få en enkelt rapport på listen over rapporter.

Du skal inkludere en *godkendelsesheader* i formatet *Bearer {adgangstoken}* for at kunne foretage REST-API-kaldet.

#### <a name="get-reports-with-the-rest-api"></a>Hent rapport ved hjælp af REST-API'en

I følgende kodeeksempel kan du se, hvordan du henter rapporter med **REST-API'en**:

> [!NOTE]  
> Du kan se et eksempel på, hvordan du henter et indholdselement, du ønsker at integrere, i filen **Default.aspx.cs** i [eksempelprogrammet](#embed-your-content-using-the-sample-application). Eksempler er en rapport, et dashboard eller et felt.

```csharp
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

#### <a name="get-reports-by-using-the-net-sdk"></a>Hent rapporter ved hjælp af .NET-SDK

Du kan bruge .NET-SDK'et til at hente en liste over rapporter i stedet for at kalde REST-API'en direkte. Følgende kodeeksempel viser, hvordan du får vist en liste over rapporter:

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-by-using-javascript"></a>Indlæs en rapport ved hjælp af JavaScript

Du kan bruge JavaScript til at indlæse en rapport i et div-element på din webside. Her er et kodeeksempel på, hvordan du henter en rapport fra et givet arbejdsområde:

> [!NOTE]  
> Du kan se et eksempel på, hvordan du indlæser et indholdselement, du ønsker at integrere, i filen **Default.aspx.cs** i [eksempelprogrammet](#embed-your-content-using-the-sample-application). Eksempler er en rapport, et dashboard eller et felt.

```javascript
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

#### <a name="sitemaster"></a>Site.master

```javascript
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
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>Ved brug af en dedikeret kapacitet fra Power BI Premium

Nu, hvor du er færdig med at udvikle dit program, er tiden kommet til at underbygge dit arbejdsområde med en dedikeret kapacitet.

### <a name="create-a-dedicated-capacity"></a>Opret en dedikeret kapacitet

Når du opretter en dedikeret kapacitet, kan du drage fordel af at have en dedikeret ressource for indholdet i dit apparbejdsområde. Du kan oprette en dedikeret kapacitet ved hjælp af [Power BI Premium ](../service-premium.md).

I tabellen nedenfor kan du se en oversigt over de Power BI Premium-SKU'er, der er tilgængelige i [Microsoft Office 365](../service-admin-premium-purchase.md):

| Kapacitetsnode | Samlet antal vCores<br/>(back-end + front-end) | Back end-vCores | Front-end-vCores | Grænser for DirectQuery/liveforbindelser |
| --- | --- | --- | --- | --- | --- |
| EM1 |1 vCore |0,5 vCore, 10 GB RAM |0,5 vCore |3.75 pr. sekund |
| EM2 |2 vCores |1 vCore, 10 GB RAM |1 vCores |7.5 pr. sekund |
| EM3 |4 vCores |2 vCores, 10 GB RAM |2 vCores |15 pr. sekund |
| P1 |8 vCores |4 vCores, 25 GB RAM |4 vCores |30 pr. sekund |
| P2 |16 vCores |8 vCores, 50 GB RAM |8 vCores |60 pr. sekund |
| P3 |32 vCores |16 vCores, 100 GB RAM |16 vCores |120 pr. sekund |
| P4 |64 vCores |32 vCores, 200 GB RAM |32 vCores |240 pr. sekund |
| P5 |128 vCores |64 vCores, 400 GB RAM |64 vCores |480 pr. sekund |
> [!NOTE]
> - Når du forsøger at integrere med Microsoft Office-apps, kan du bruge EM-SKU'er til at få adgang til indhold med en gratis Power BI-licens. Men du kan ikke få adgang til indhold med en gratis Power BI-licens, når du bruger Powerbi.com eller Power BI – Mobil.
> - Når du forsøger at integrere med Microsoft Office-apps ved hjælp af Powerbi.com eller Power BI – Mobil, kan du få adgang til indhold med en gratis Power BI-licens.

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Tildel et apparbejdsområde til en dedikeret kapacitet

Når du opretter en dedikeret kapacitet, kan du tildele dit apparbejdsområde til den dedikerede kapacitet. Gennemgå følgende trin for at udføre denne handling:

1. I Power BI-tjenesten skal du udvide arbejdsområder og vælge ellipsen for det arbejdsområde, du bruger til integrering af dit indhold. Vælg derefter **Rediger arbejdsområder**.

    ![Rediger et arbejdsområde](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. Udvid **Avanceret**, og aktiver **Dedikeret kapacitet**. Vælg den dedikerede kapacitet, du har oprettet. Vælg derefter **Gem**.

    ![Tildel en dedikeret kapacitet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. Når du har valgt **Gem**, kan du se en rombe ud for navnet på apparbejdsområdet.

    ![Apparbejdsområde knyttet til en kapacitet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="admin-settings"></a>Administratorindstillinger

Globale administratorer, eller Power BI-tjenesteadministratorer, kan slå muligheden for at bruge REST-API'erne til eller fra for en lejer. Power BI-administratorer kan angive denne indstilling for hele organisationen eller for enkelte sikkerhedsgrupper. Den er som standard aktiveret for hele organisationen. Du kan foretage disse ændringer i [Power BI-administrationsportalen](../service-admin-portal.md).

## <a name="next-steps"></a>Næste trin

I dette selvstudium har du fået at vide, hvordan du integrerer Power BI-indhold i et program ved hjælp af din Power BI-organisationskonto. Nu kan du prøve at integrere Power BI-indhold i et program ved hjælp af apps. Du kan også prøve at integrere Power BI-indhold for din kunder:

> [!div class="nextstepaction"]
> [Integrer fra apps](embed-from-apps.md)

> [!div class="nextstepaction"]
>[Integrer indhold for dine kunder](embed-sample-for-customers.md)

Hvis du har flere spørgsmål, kan du [prøve at spørge Power BI-community'et](http://community.powerbi.com/).
