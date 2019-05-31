---
title: Integreret analyse for at integrere Power BI-indhold i dit program for dine kunder
description: Få mere at vide om, hvordan du integrerer en rapport, et dashboard eller et felt i et program ved hjælp af Power BI-API'er for at bruge integreret analyse for dine kunder. Få mere at vide om, hvordan du integrerer Power BI i dit program ved hjælp af software til integreret analyse, integrerede analyseværktøjer eller integrerede værktøjer til business intelligence.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: nishalit
ms.topic: tutorial
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: seodec18
ms.date: 04/02/2019
ms.openlocfilehash: e945e19505d7342cf3ba2236b4811e87a69730ab
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710961"
---
# <a name="tutorial-embed-power-bi-content-into-an-application-for-your-customers"></a>Selvstudium: Integrer Power BI-indhold i en app til dine kunder

Med **Power BI Embedded i Azure** kan du integrere rapporter, dashboards eller felter i et program ved hjælp af funktionen "appen ejer data". **App owns data** handler om at have et program, der bruger Power BI som sin integrerede analyseplatform. Som **ISV-udvikler** kan du oprette Power BI-indhold, der viser rapporter, dashboards eller felter i et program, som er fuldt integreret og interaktivt, uden at brugerne skal have en Power BI-licens. I dette selvstudium kan du se, hvordan du integrerer en rapport i et program ved hjælp af Power BI .NET SDK med Power BI JavaScript-API'en, når du bruger **Power BI Embedded i Azure** for dine kunder.

![Integrer Power BI-rapport](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

I dette selvstudium lærer du, hvordan du kan:
> [!div class="checklist"]
> * Registrere en app i Azure.
> * Integrer en Power BI-rapport i et program.

## <a name="prerequisites"></a>Forudsætninger

Du skal have følgende for at komme i gang:

* En [Power BI Pro-konto](../service-self-service-signup-for-power-bi.md) (en masterkonto med et brugernavn og en adgangskode, som bruges til at logge på Power BI Pro-kontoen) eller en [tjenesteprincipal (kun program-token)](embed-service-principal.md).
* Et [Microsoft Azure](https://azure.microsoft.com/)-abonnement.
* Du skal have din egen konfiguration af [Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md).

Hvis du ikke er tilmeldt **Power BI Pro**, kan du [tilmelde dig en gratis prøveversion](https://powerbi.microsoft.com/pricing/), før du begynder.

Hvis du ikke har et Azure-abonnement, skal du oprette en [gratis konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), før du begynder.

## <a name="set-up-your-embedded-analytics-development-environment"></a>Konfigurer dit integrerede analyseudviklingsmiljø

Før du begynder at integrere rapporter, dashboards eller felter i dit program, skal du sikre dig, at du kan integrere med Power BI i dit miljø.

Du kan gennemgå [værktøjet til konfiguration af integrering](https://aka.ms/embedsetup/AppOwnsData) for hurtigt at komme i gang med og downloade et eksempelprogram, der hjælper dig med at oprette et miljø og integrere en rapport.

Hvis du vælger at konfigurere miljøet manuelt, kan du dog fortsætte nedenfor.

### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Registrer et program i Azure Active Directory (Azure AD)

[Registrer dit program](register-app.md) med Azure Active Directory for at give dit program adgang til [REST API'erne til Power BI](https://docs.microsoft.com/rest/api/power-bi/). Når du registrerer dit program, får du mulighed for at oprette en identitet for programmet og angive tilladelser til Power BI REST-ressourcer. Den måde, du kommer i gang med at registrere et program på, afhænger af, om du vil bruge en masterkonto eller en [tjenesteprincipal](embed-service-principal.md).

Den valgte metode påvirker, hvilken programtype du registrerer i Azure.

Hvis du fortsætter med en masterkonto, skal du registrere et **oprindeligt** program. Du bruger et oprindeligt program, fordi du arbejder med et logon, der ikke er interaktivt.

Hvis du derimod fortsætter med en tjenesteprincipal, skal du registrere et **serverbaseret webprogram**. Du registrerer et serverbaseret webprogram for at oprette en programhemmelighed.

## <a name="set-up-your-power-bi-environment"></a>Konfigurer dit Power BI-miljø

### <a name="create-an-app-workspace"></a>Opret et apparbejdsområde

Hvis du integrerer rapporter, dashboards eller felter for dine kunder, skal du placere dit indhold i et apparbejdsområde. Der er forskellige typer arbejdsområder, som du kan konfigurere: [traditionelle arbejdsområder](../service-create-workspaces.md) eller [nye arbejdsområder](../service-create-the-new-workspaces.md). Hvis du bruger en *master*konto, er det ligegyldigt, hvilken type arbejdsområde du bruger. Men hvis du bruger en *[tjenesteprincipal](embed-service-principal.md)* til at logge på dit program, skal du bruge de nye arbejdsområder. I begge scenarier skal både *master*kontoen og *tjenesteprincipalen* være administrator af programarbejdsområderne for dit program.

### <a name="create-and-publish-your-reports"></a>Opret og udgiv dine rapporter

Du kan oprette rapporter og datasæt ved hjælp af Power BI Desktop og derefter udgive disse rapporter til et apparbejdsområde. Du kan opnå dette på to måder: Som slutbruger kan du publicere rapporter i et traditionelt programarbejdsområde med en masterkonto (Power BI Pro-licens). Hvis du bruger en tjenesteprincipal, kan du publicere rapporter i de nye arbejdsområder ved hjælp af [REST API'erne til Power BI](https://docs.microsoft.com/rest/api/power-bi/imports/postimportingroup).

Nedenstående trin viser, hvordan man publicerer en PBIX-rapport i et Power BI-arbejdsområde.

1. Download eksemplet [Blogdemo](https://github.com/Microsoft/powerbi-desktop-samples) fra GitHub.

    ![eksempelrapport](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. Åbn PBIX-eksempelrapporten i **Power BI Desktop**.

   ![PBI-skrivebordsrapport](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. Publicer i **programarbejdsområder**. Denne proces varierer, afhængigt af om du bruger en masterkonto (Power Pro-licens) eller en tjenesteprincipal. Hvis du bruger en masterkonto, kan du publicere din rapport via Power BI Desktop.  Hvis du bruger en tjenesteprincipal, skal du bruge REST API'erne til Power BI.

## <a name="embed-content-using-the-sample-application"></a>Integrer indhold ved hjælp af eksempelprogrammet

Dette eksempel er med vilje enkelt, da det kun skal bruges til demonstrationen. Det er op til dig eller dine udviklere at beskytte programhemmeligheden eller legitimationsoplysningerne til masterkontoen.

Følg nedenstående trin for at begynde at integrere indhold ved hjælp af eksempelprogrammet.

1. Download [Visual Studio](https://www.visualstudio.com/) (version 2013 eller nyere). Sørg for at downloade den nyeste [NuGet-pakke](https://www.nuget.org/profiles/powerbi).

2. Download [eksemplet, hvor appen ejer data,](https://github.com/Microsoft/PowerBI-Developer-Samples) fra GitHub for at komme i gang.

    ![Appen ejer data-programeksempel](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

3. Åbn filen **Web.config** i eksempelprogrammet. Der er nogle felter, du skal udfylde, for at køre programmet. Du kan vælge **MasterUser** eller **ServicePrincipal** som **AuthenticationType**. Du skal udfylde forskellige felter, afhængigt af hvilken type godkendelsesmetode du vælger.

    > [!Note]
    > **Standardgodkendelsestypen** i dette eksempel er MasterUser.

    <center>

    | **MasterUser** <br> (Power BI Pro-licenser) | **ServicePrincipal** <br> (kun program-token)|
    |---------------|-------------------|
    | [applicationId](#application-id) | [applicationId](#application-id) |
    | [workspaceId](#workspace-id) | [workspaceId](#workspace-id) |
    | [reportId](#report-id) | [reportId](#report-id) |
    | [pbiUsername](#power-bi-username-and-password) |  |
    | [pbiPassword](#power-bi-username-and-password) |  |
    |  | [applicationsecret](#application-secret) |
    |  | [tenant](#tenant) |

   </center>

    ![Web Config-fil](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

### <a name="application-id"></a>Program-id

Denne attribut er påkrævet for begge AuthenticationTypes (masterkonto og [tjenesteprincipal](embed-service-principal.md)).

Udfyld oplysningerne om **applicationId** med **program-id'et** fra **Azure**. **Program-id'et** bruges af programmet til at identificere sig selv over for de brugere, du anmoder om tilladelser fra.

Hvis du vil hente **applicationId**, skal du følge disse trin:

1. Log på [Azure-portalen](https://portal.azure.com).

2. Vælg **Alle tjenester** i navigationsruden til venstre, og vælg **Appregistreringer**.

    ![Søg efter programregistrering](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

3. Vælg programmet, der skal bruge **applicationId**.

    ![Vælg app](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

4. Der er angivet et **program-id** som GUID. Brug dette **Program-id** som **applicationId** for programmet.

    ![applicationId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)

### <a name="workspace-id"></a>Id for arbejdsområde

Denne attribut er påkrævet for begge AuthenticationTypes (masterkonto og [tjenesteprincipal](embed-service-principal.md)).

Udfyld oplysningerne for **workspaceId** med GUID for programarbejdsområdet fra Power BI. Du kan få disse oplysninger enten fra URL-adressen, når du er logget på Power BI-tjenesten, eller ved hjælp af Powershell.

URL-adresse <br>

![workspaceId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

PowerShell <br>

```powershell
Get-PowerBIworkspace -name "App Owns Embed Test"
```

   ![workspaceId fra powershell](media/embed-sample-for-customers/embed-sample-for-customers-031-ps.png)

### <a name="report-id"></a>Rapport-id

Denne attribut er påkrævet for begge AuthenticationTypes (masterkonto og [tjenesteprincipal](embed-service-principal.md)).

Udfyld **reportId** med GUID for rapporten fra Power BI. Du kan få disse oplysninger enten fra URL-adressen, når du er logget på Power BI-tjenesten, eller ved hjælp af Powershell.

URL-adresse<br>

![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

PowerShell <br>

```powershell
Get-PowerBIworkspace -name "App Owns Embed Test" | Get-PowerBIReport
```

![reportId fra powershell](media/embed-sample-for-customers/embed-sample-for-customers-032-ps.png)

### <a name="power-bi-username-and-password"></a>Brugernavn og adgangskode til Power BI

Disse attributter er kun påkrævet til masterkontoen som AuthenticationType.

Hvis du bruger en [tjenesteprincipal](embed-service-principal.md) til at godkende, behøver du ikke udfylde attributterne for brugernavn og adgangskode.

* Udfyld **pbiUsername** med masterkontoen til Power BI.
* Udfyld **pbiPassword** med adgangskoden til masterkontoen til Power BI.

### <a name="application-secret"></a>Programhemmelighed

Denne attribut bruges kun til [tjenesteprincipalen](embed-service-principal.md) som AuthenticationType.

Udfyld oplysningerne for **ApplicationSecret** ud fra sektionen **Nøgler** i sektionen **Appregistreringer** i **Azure**.  Denne attribut fungerer, når du bruger [tjenesteprincipal](embed-service-principal.md).

Hvis du vil hente **ApplicationSecret**, skal du følge disse trin:

1. Log på [Azure Portal](https://portal.azure.com).

2. Vælg **Alle tjenester** i navigationsruden til venstre, og vælg derefter **Programregistreringer**.

    ![Søg efter programregistrering](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

3. Vælg programmet, der skal bruge **ApplicationSecret**.

    ![Vælg en app](media/embed-sample-for-customers/embed-sample-for-customers-0038.png)

4. Vælg **certifikater og hemmeligheder** under **Administrer**.

5. Vælg **nye klient hemmeligheder**.

6. Angiv et navn i feltet **Beskrivelse**, og vælg en varighed. Vælg derefter **Gem** for at hente **værdien** til dit program. Når du lukker ruden **Nøgler** efter at have gemt nøgleværdien, vises feltet med værdien kun som skjult. På det tidspunkt kan du ikke hente nøgleværdien. Hvis du mister nøgleværdien, skal du oprette en ny i Azure Portal.

    ![Nøgleværdi](media/embed-sample-for-customers/embed-sample-for-customers-042.png)

### <a name="tenant"></a>Lejer

Denne attribut bruges kun til [tjenesteprincipalen](embed-service-principal.md) som AuthenticationType.

Udfyld oplysningerne om **tenant** med dit lejer-id til Azure. Du kan få disse oplysninger fra [Azure AD Administration](/onedrive/find-your-office-365-tenant-id), når du er logget på Power BI-tjenesten, eller ved hjælp af Powershell.

### <a name="run-the-application"></a>Kør programmet

1. Vælg **Kør** i **Visual Studio**.

    ![Kør programmet](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

2. Vælg derefter **Integrer rapport**. Afhængigt af hvilket indhold du vælger at udføre test med – rapporter, dashboards eller felter – skal du vælge den pågældende indstilling i programmet.

    ![Vælg indhold](media/embed-sample-for-customers/embed-sample-for-customers-034.png)

3. Du kan nu se rapporten i eksempelprogrammet.

    ![Se program](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="embed-content-within-your-application"></a>Integrer indhold i dit program

Selvom trinnene til at integrere indhold udføres ved hjælp af [REST API'er til Power BI](https://docs.microsoft.com/rest/api/power-bi/), oprettes de eksempelkoder, der er beskrevet i denne artikel, med **.NET-SDK'en**.

Hvis du integrerer for dine kunder i dit program, skal du have et **adgangstoken** til din masterkonto eller en [tjenesteprincipal](embed-service-principal.md) fra **Azure AD**. Du skal have et [Azure AD-adgangstoken](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) til dit Power BI-program, før du kan foretage kald til [REST API'erne til Power BI](https://docs.microsoft.com/rest/api/power-bi/).

Hvis du vil oprette Power BI-klienten med dit **adgangstoken**, skal du oprette dit Power BI klientobjekt, som gør det muligt for dig at interagere med [REST API'erne til Power BI](https://docs.microsoft.com/rest/api/power-bi/). Du kan oprette dit Power BI-klientobjekt ved at omgive **AccessToken** med objektet ***Microsoft.Rest.TokenCredentials***.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. it's used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Hent det indholdselementet, du vil integrere

Du kan bruge Power BI-klientobjektet til at hente en reference til det element, du vil integrere.

Her er et kodeeksempel på, hvordan du henter den første rapport fra et givent arbejdsområde.

*Du kan se et eksempel på, hvordan du henter et indholdselement, uanset om det er en rapport, et dashboard eller et felt, du vil integrere, i filen Services\EmbedService.cs i [eksempelprogrammet](https://github.com/Microsoft/PowerBI-Developer-Samples).*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the workspaceId where the dashboard resides.
ODataResponseListReport reports = await client.Reports.GetReportsInGroupAsync(workspaceId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Opret integrationstokenet

Genererede et integreringstoken, som kan bruges fra JavaScript API'en. Dette integreringstoken er specifikt for det element, du er ved at integrere. Hver gang du integrerer Power BI-indhold, skal du oprette et nyt integrationstoken for det. Du kan finde flere oplysninger, herunder hvilket **adgangsniveau** du skal bruge, i [GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx).

*Du kan se et eksempel på, hvordan du opretter et integreringstoken til en rapport, et dashboard eller et felt i filen Services\EmbedService.cs i [eksempelprogrammet](https://github.com/Microsoft/PowerBI-Developer-Samples).*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(workspaceId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```

Der oprettes en klasse for **EmbedConfig** og **TileEmbedConfig**. Du kan finde et eksempel i filen **Models\EmbedConfig.cs** og filen **Models\TileEmbedConfig.cs**.

### <a name="load-an-item-using-javascript"></a>Indlæs et element ved hjælp af JavaScript

Du kan bruge JavaScript til at indlæse en rapport i et div-element på din webside.

Hvis du vil se et komplet eksempel, hvor JavaScript API'en bruges, kan du bruge [værktøjet Playground](https://microsoft.github.io/PowerBI-JavaScript/demo). Med værktøjet Playground kan du hurtigt prøve dig frem med forskellige typer af eksempler på Power BI Embedded. Du kan også få flere oplysninger om JavaScript-API'en ved at gå til siden [Wiki for PowerBI-JavaScript](https://github.com/Microsoft/powerbi-javascript/wiki).

Her er et eksempel, der anvender modellen **EmbedConfig** og modellen **TileEmbedConfig** sammen med visninger for en rapport.

*Et eksempel på tilføjelse af en visning for en rapport, et dashboard eller et felt er tilgængeligt i Views\Home\EmbedReport.cshtml, Views\Home\EmbedDashboard.cshtml eller Views\Home\Embedtile.cshtml filer i [eksempelprogrammet](#embed-content-using-the-sample-application).*

```javascript
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

    // Embed configuration used to describe what and how to embed.
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

## <a name="move-to-production"></a>Flyt til produktion

Nu, hvor du er færdig med at udvikle dit program, er tiden kommet til at underbygge dit arbejdsområde med en dedikeret kapacitet. 

> [!Important]
> Dedikeret kapacitet er påkrævet for at flytte til produktionen.

### <a name="create-a-dedicated-capacity"></a>Opret en dedikeret kapacitet

Når du opretter en dedikeret kapacitet, kan du drage fordel af at have en dedikeret ressource for din kunde. Du kan købe en dedikeret kapacitet på [Microsoft Azure-portalen](https://portal.azure.com). Du kan finde flere oplysninger om, hvordan du opretter en kapacitet til Power BI Embedded, under [Opret kapacitet til Power BI Embedded på Azure-portalen](azure-pbie-create-capacity.md).

Brug tabellen nedenfor til at bestemme, hvilken kapacitet til Power BI Embedded der passer bedst til dine behov.

| Kapacitetsnode | Kerner i alt<br/>*(Backend + frontend)* | Backendkerner | Frontendkerner | Grænser for DirectQuery/liveforbindelser|
| --- | --- | --- | --- | --- | --- |
| A1 |1 v-kerne(r) |0,5 kerne(r), 3 GB RAM |0,5 kerne |0-5 pr. sekund |
| A2 |2 v-kerne(r) |1 kerne(r), 5 GB RAM |1 kern(e) | 10 pr. sekund |
| A3 |4 v-kerne(r) |2 kerne(r), 10 GB RAM |2 kerne(r) | 15 pr. sekund |
| A4 |8 v-kerne(r) |4 kerne(r), 25 GB RAM |4 kerne(r) |30 pr. sekund |
| A5 |16 v-kerne(r) |8 kerne(r), 50 GB RAM |8 kerne(r) |60 pr. sekund |
| A6 |32 v-kerne(r) |16 kerne(r), 100 GB RAM |16 kerne(r) |120 pr. sekund |

**_Med A-SKU'er kan du ikke få adgang til Power BI-indhold med en GRATIS Power BI-licens._ **

Brug af integreringstokens med en PRO-licens er beregnet til udviklingstest, så antallet af integreringstokens, der kan genereres af en Power BI-masterkonto eller tjenesteprincipal, er begrænset. En dedikeret kapacitet kræver integrering i et produktionsmiljø. Der er ingen grænse for, hvor mange integreringstokens du kan generere med en dedikeret kapacitet. Gå til [Tilgængelige funktioner](https://docs.microsoft.com/rest/api/power-bi/availablefeatures/getavailablefeatures) for at undersøge den brugsværdi, der angiver brugen af integrerede tokens i procent. Forbrugsbeløbet er baseret på overordnet konto.

Du kan finde flere oplysninger i [Whitepaper om kapacitetsplanlægning af integreret analyse](https://aka.ms/pbiewhitepaper).

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Tildel et apparbejdsområde til en dedikeret kapacitet

Når du opretter en dedikeret kapacitet, kan du tildele dit apparbejdsområde til den dedikerede kapacitet.

Hvis du vil tildele en dedikeret kapacitet til et arbejdsområde ved hjælp af en [tjenesteprincipal](embed-service-principal.md), skal du bruge [REST API'er til Power BI](https://docs.microsoft.com/rest/api/power-bi/capacities/groups_assigntocapacity). Når du bruger REST API'er til Power BI, skal du sørge for at bruge [objekt-id'et for tjenesteprincipalen](embed-service-principal.md#how-to-get-the-service-principal-object-id).

Følg nedenstående trin for at tildele en dedikeret kapacitet til et arbejdsområde ved hjælp af en **masterkonto**.

1. I **Power BI-tjenesten** skal du udvide arbejdsområder og vælge ellipsen for det arbejdsområde, du bruger til at integrere dit indhold i. Vælg derefter **Rediger arbejdsområder**.

    ![Rediger arbejdsområde](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. Udvid **Avanceret**, aktivér derefter **Dedikeret kapacitet**, og vælg derefter den dedikerede kapacitet, du har oprettet. Vælg derefter **Gem**.

    ![Tildel dedikeret kapacitet](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

3. Når du har valgt **Gem**, kan du se en **rombe** ud for navnet på apparbejdsområdet.

    ![arbejdsområde knyttet til en kapacitet](media/embed-sample-for-customers/embed-sample-for-customers-037.png)

## <a name="next-steps"></a>Næste trin

I dette selvstudium har du lært, hvordan du integrerer Power BI-indhold i en app for dine kunder. Du kan også prøve at integrere Power BI-indhold til din organisation.

> [!div class="nextstepaction"]
>[Integrer til din organisation](embed-sample-for-your-organization.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
