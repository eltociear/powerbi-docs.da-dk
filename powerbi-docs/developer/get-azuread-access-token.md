---
title: "Godkend brugere, og få et Azure AD-adgangstoken til din applikation"
description: "Få mere at vide om, hvordan du registrerer et program i Azure Active Directory, som skal bruges til at integrere Power BI-indhold."
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
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: 3ff0fa3c83654ac577e98e730dc68ce3686e1198
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Godkend brugere, og få et Azure AD-adgangstoken til din Power BI-app
Få mere at vide om, hvordan du kan godkende brugere i din Power BI-applikation og hente et adgangstoken, der skal bruges sammen med REST-API'en.

Før du kan kalde Power BI REST-API'en, skal du have et Azure AD-**adgangstoken** til godkendelse (Azure Active Directory). Et **adgangstoken** bruges til at give din app adgang til **Power BI**-dashboards, -felter og -rapporter. Du kan finde flere oplysninger om flowet for Azure Active Directory-**adgangstoken** under [Flowet for tildeling af Azure AD-godkendelseskode](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Adgangskoden hentes på forskellige måder, afhængigt af hvordan du integrerer indhold. To forskellige metoder bruges i denne artikel.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Adgangstoken til Power BI-brugere (brugeren ejer data)
Dette eksempel er relateret til, når brugerne manuelt logger på Azure AD med deres organisationslogon. Dette bruges i forbindelse med integrering af indhold for Power BI-brugere, der skal have adgang til indhold, som de har adgang til i Power BI-tjenesten.

### <a name="get-an-authorization-code-from-azure-ad"></a>Hent en godkendelseskode fra Azure AD
Det første trin til at få et **adgangstoken** er at få en godkendelseskode fra **Azure AD**. Det gør du ved at konstruere en forespørgselsstreng med følgende egenskaber og omdirigere til **Azure AD**.

**Forespørgselsstreng til godkendelseskode**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Når du har konstrueret en forespørgselsstreng, omdirigerer du til **Azure AD** for at hente en **godkendelseskode**.  Nedenfor kan du se en komplet C#-metode til at konstruere en forespørgselsstreng til en **godkendelseskode** og omdirigere til **Azure AD**. Når du har fået godkendelseskoden, får du et **adgangstoken** ved hjælp af **godkendelseskoden**.

I redirect.aspx.cs kaldes [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) derefter for at generere dette token.

**Hent godkendelseskode**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.windows.net/common/oauth2/authorize/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Få et adgangstoken fra en godkendelseskode
Du bør nu have en godkendelseskode fra Azure AD. Når **Azure AD** omdirigerer tilbage til din webapp med en **godkendelseskode**, skal du bruge **godkendelseskoden** til at få et adgangstoken. Nedenfor er et C#-eksempel, som du kan bruge på omdirigeringssiden og i Page_Load-hændelsen til siden default.aspx.

Navneområdet **Microsoft.IdentityModel.Clients.ActiveDirectory** kan hentes fra NuGet-pakken i [biblioteket til Active Directory-godkendelse](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Adgangstoken til brugere, der ikke har Power BI (appen ejer data)
Denne metode bruges typisk til programmer af ISV-typen, hvor appen ejer adgang til dataene. Brugerne bliver ikke nødvendigvis Power BI-brugere, og applikationen styrer godkendelse og adgang for slutbrugerne.

Til denne metode skal du bruge en enkelt *master*konto, der er en Power BI Pro-bruger. Legitimationsoplysningerne for denne konto er gemt i applikationen. Applikationen godkender til Azure AD med disse gemte legitimationsoplysninger. Den viste eksempelkode nedenfor kommer fra [eksemplet, hvor appen ejer data](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

Du kan finde oplysninger om, hvordan du bruger **await** under [await (C#-reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)

## <a name="next-steps"></a>Næste trin
Nu, hvor du har et adgangstoken, kan du kalde Power BI REST-API'en for at integrere indhold. Du kan finde oplysninger om, hvordan du integrerer dit indhold under [Sådan integrerer du Power BI-dashboards, -rapporter og -felter](embedding-content.md#step-2-embed-your-content).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

