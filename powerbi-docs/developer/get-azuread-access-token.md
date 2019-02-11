---
title: Godkend brugere, og få et Azure AD-adgangstoken til dit program
description: Få mere at vide om, hvordan du registrerer et program i Azure Active Directory, som skal bruges til at integrere Power BI-indhold.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 7b2249964f2fff26bc68fea19fd0010d8990110b
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762530"
---
# <a name="get-an-azure-ad-access-token-for-your-power-bi-application"></a>Få et Azure AD-adgangstoken til dit Power BI-program

Få mere at vide om, hvordan du godkender brugere i dit Power BI-program og henter et adgangstoken, der skal bruges sammen med REST-API'en.

Før du kan kalde Power BI REST-API'en, skal du have et Azure AD-**adgangstoken** til godkendelse (Azure Active Directory). Et **adgangstoken** bruges til at give dit program adgang til **Power BI**-dashboards, -felter og -rapporter. Du kan finde flere oplysninger om flowet for Azure Active Directory-**adgangstoken** under [Flowet for tildeling af Azure AD-godkendelseskode](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Adgangstokenet hentes på forskellige måder, afhængigt af hvordan du integrerer indhold. I denne artikel bruges to forskellige metoder.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Adgangstoken til Power BI-brugere (brugeren ejer data)

Dette eksempel er relateret til, når brugerne manuelt logger på Azure AD med deres organisationslogon. Denne opgave bruges i forbindelse med integrering af indhold for Power BI-brugere, der tilgår indhold med adgang til Power BI-tjenesten.

### <a name="get-an-authorization-code-from-azure-ad"></a>Hent en godkendelseskode fra Azure AD

Det første trin til at få et **adgangstoken** er at få en godkendelseskode fra **Azure AD**. Konstruer en forespørgselsstreng med følgende egenskaber, og omdiriger til **Azure AD**.

#### <a name="authorization-code-query-string"></a>Forespørgselsstreng til godkendelseskode

```csharp
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

I redirect.aspx.cs kaldes [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) for at generere tokenet.

#### <a name="get-authorization-code"></a>Hent godkendelseskode

```csharp
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
    // AADAuthorityUri = https://login.microsoftonline.net/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Få et adgangstoken fra en godkendelseskode

Du bør nu have en godkendelseskode fra Azure AD. Når **Azure AD** omdirigerer tilbage til dit webprogram med en **godkendelseskode**, skal du bruge **godkendelseskoden** til at få et adgangstoken. Nedenfor er et C#-eksempel, som du kan bruge på omdirigeringssiden og i Page_Load-hændelsen til siden default.aspx.

Navneområdet **Microsoft.IdentityModel.Clients.ActiveDirectory** kan hentes fra NuGet-pakken i [biblioteket til Active Directory-godkendelse](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

```powershell
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

#### <a name="redirectaspxcs"></a>Redirect.aspx.cs

```csharp
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

#### <a name="defaultaspx"></a>Default.aspx

```csharp
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

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Adgangstoken til brugere, der ikke har Power BI (programmet ejer data)

Denne metode bruges typisk til programmer af ISV-typen, hvor programmet ejer adgang til dataene. Brugerne er ikke nødvendigvis Power BI-brugere, og programmet styrer godkendelse og adgang for slutbrugerne.

### <a name="access-token-with-a-master-account"></a>Adgangstoken med en masterkonto

Til denne metode skal du bruge en enkelt *masterkonto*, der er en Power BI Pro-bruger. Legitimationsoplysningerne for denne konto er gemt i programmet. Programmet godkender til Azure AD med disse gemte legitimationsoplysninger. Den viste eksempelkode nedenfor kommer fra [eksemplet, hvor programmet ejer data](https://github.com/guyinacube/PowerBI-Developer-Samples)

### <a name="access-token-with-service-principal"></a>Adgangstoken med tjenesteprincipal

I denne fremgangsmåde bruger du en [tjenesteprincipal](embed-service-principal.md), som er et **kun program**-token. Programmet godkender til Azure AD med tjenesteprincipalen. Den viste eksempelkode nedenfor kommer fra [eksemplet, hvor programmet ejer data](https://github.com/guyinacube/PowerBI-Developer-Samples)

#### <a name="embedservicecs"></a>EmbedService.cs

```csharp
var authenticationContext = new AuthenticationContext(AuthorityUrl);
       AuthenticationResult authenticationResult = null;
       if (AuthenticationType.Equals("MasterUser"))
       {
              // Authentication using master user credentials
              var credential = new UserPasswordCredential(Username, Password);
              authenticationResult = authenticationContext.AcquireTokenAsync(ResourceUrl, ApplicationId, credential).Result;
       }
       else
       {
             // Authentication using app credentials
             var credential = new ClientCredential(ApplicationId, ApplicationSecret);
             authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, credential);
       }


m_tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

## <a name="next-steps"></a>Næste trin

Nu, hvor du har et adgangstoken, kan du kalde Power BI REST-API'en for at integrere indhold. Du kan finde flere oplysninger om, hvordan du integrerer indhold under [Sådan integrerer du Power BI-indhold](embed-sample-for-customers.md#embed-content-within-your-application).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)