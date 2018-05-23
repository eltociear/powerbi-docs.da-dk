---
title: Hent et adgangstoken til godkendelse
description: Gennemgang til push af data – hent et adgangstoken til godkendelse
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 640c6dac9a896cff55bddad46ceef8bce7ccae14
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="step-2-get-an-authentication-access-token"></a>Trin 2: Hent et adgangstoken til godkendelse
Denne artikel er en trinvis gennemgang af, hvordan du kan [pushe data til et datasæt](walkthrough-push-data.md).

På **trin 1** i Push data til et datasæt, [Registrer appen med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md), registrerede du en klientapp i Azure AD. På dette trin henter du et adgangstoken til godkendelse. Power BI-apps er integreret med **Azure AD** for at give sikker logon og godkendelse til din app. Du kan bruge et token til at godkende til **Azure AD** og få adgang til Power BI-ressourcer.

Sådan henter du et adgangstoken til godkendelse.

## <a name="get-an-authentication-access-token"></a>Hent et adgangstoken til godkendelse
> **Bemærk!** Inden du går i gang, skal du sikre, at du har fulgt de tidligere trin i gennemgangen [Push data til et datasæt](walkthrough-push-data.md).
> 
> 

1. Opret et projekt med et **konsolprogram** i Visual Studio 2015.
2. Installér [Azure AD-godkendelsesbiblioteket til .NET NuGet-pakker](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Du skal bruge denne pakke til at hente et sikkerhedstoken til godkendelse i en .NET-app. Sådan installerer du pakken:
   
     a. Vælg **Tools** > **NuGet Package Manager** > **Package Manager Console** i Visual Studio 2015.
   
     b. I **Package Manager Console** skal du angive Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Tilføj koden herunder i klassen Program {...}.
4. Erstat "{ClientID}" med det **klient-id**, du fik, da du registrerede appen. Se [Registrer appen med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. Når du har installeret pakken Microsoft.IdentityModel.Clients.ActiveDirectory, skal du tilføje **using Microsoft.IdentityModel.Clients.ActiveDirectory;** i Program.cs.
6. Kør konsolprogrammet, og log på din Power BI-konto. Der skulle blive vist en tokenstreng i konsolvinduet.

**Eksempelkode til at hente et sikkerhedstoken til godkendelse**

Tilføj denne kode i Program {...}.

* En tokenvariabel til kald:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* In static void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Tilføj metoden GetToken():

```
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Når du har hentet et godkendelsestoken, kan du kalde enhver Power BI-handling. På næste trin kan du se, hvordan du kalder handlingen [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx) for at oprette et datasæt, der kan pushe dataene til et dashboard.

På næste trin kan du se, hvordan du [opretter et datasæt i Power BI](walkthrough-push-data-create-dataset.md).

Herunder kan du se den [komplette kode](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Komplet kodeliste
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion

        }
    }


[Næste trin >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Næste trin
[Opret et datasæt i Power BI](walkthrough-push-data-create-dataset.md)  
[Registrer en app med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Azure AD-godkendelsesbibliotek til .NET NuGet-pakke](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Push data til et Power BI-datasæt](walkthrough-push-data.md)  
[Oversigt over Power BI REST-API'en](overview-of-power-bi-rest-api.md)  
[Power BI REST-API-reference](https://msdn.microsoft.com/library/mt147898.aspx)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

