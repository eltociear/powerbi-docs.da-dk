---
title: Fejlfinding af det integrerede program
description: Denne artikel beskriver nogle almindelige problemer, som kan opstå under integrationen af indhold fra Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/03/2018
ms.author: maghan
ms.openlocfilehash: b3c9599ea3ce01094bb75d9b036fb25b1ca7109a
ms.sourcegitcommit: 627918a704da793a45fed00cc57feced4a760395
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/10/2018
ms.locfileid: "37926553"
---
# <a name="troubleshooting-your-embedded-application"></a>Fejlfinding af det integrerede program

Denne artikel beskriver nogle almindelige problemer, som kan opstå under integrationen af indhold fra Power BI.

## <a name="tools-for-troubleshooting"></a>Værktøjer til fejlfinding

### <a name="fiddler-trace"></a>Fiddler-sporing

[Fiddler](http://www.telerik.com/fiddler) er et gratis værktøj fra Telerik, der overvåger HTTP-trafik.  Du kan se det, der sendes frem og tilbage vha. Power BI-API'er fra klientcomputeren. Dette kan vise fejl og andre relaterede oplysninger.

![Fiddler-sporing](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>F12 i browser for front-end fejlløsning

F12 starter udviklervinduet i din browser. Dette giver adgang til at se netværkstrafik og andre oplysninger.

![F12 Browser-fejlfinding](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>Udtrækker oplysninger om fejl fra Power BI-svar

Dette kodestykke viser, hvordan du udtrækker fejloplysninger fra HTTP-undtagelse:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
Vi anbefaler, at du logfører anmodnings-id'er (og fejloplysninger med henblik på fejlfinding).
Du bedes angive anmodnings-id'et, når du henvender dig til Microsoft Support.

## <a name="app-registration"></a>Programregistrering

**Fejl ved programregistrering**

Fejlmeddelelser internt på Azure-portalen eller Power BI-programmets registreringsside angiver utilstrækkelige rettigheder. Hvis du vil registrere et program, skal du være administrator i Azure AD-lejeren, eller programregistreringer skal være aktiveret for brugere uden administratorstatus.

**Power BI-tjenesten vises ikke i Azure-portalen under registrering af et nyt program**

Mindst en bruger skal være tilmeldt Power BI. Hvis du ikke kan se **Power BI-tjeneste** på listen i API-listen, er ingen brugere tilmeldt Power BI.

## <a name="rest-api"></a>REST API

**API-opkald returnerer 401**

En fiddler-optagelse kan være påkrævet med henblik på yderligere efterforskning. Det påkrævede tilladelsesomfang kan være utilstrækkeligt for det registrerede program internt i Azure AD. Bekræft, at det påkrævede omfang er til stede i programregistreringen til Azure AD internt på Azure-portalen.

**API-opkald returnerer 403**

En fiddler-optagelse kan være påkrævet med henblik på yderligere efterforskning. Der kan være flere grunde til en 403-fejl.

* Brugeren har overskredet det antal integrerede tokens, der kan genereres på en delt kapacitet. Du skal købe Azure-kapacitet for at generere integrerede tokens og tildele arbejdsområdet til den pågældende kapacitet. Se [Opret Power BI Embedded-kapacitet på Azure Portal](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity).
* Azure AD auth-tokenet kan være udløbet.
* Den godkendte bruger er ikke medlem af gruppen (programarbejdsområde).
* Den godkendte bruger er ikke en administrator af gruppen (programarbejdsområde).
* Godkendelsesheaderen kan være angivet forkert. Kontroller for tastefejl.

Programmets backend skal muligvis opdatere godkendelsestokenet før kaldet til GenerateToken.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

## <a name="authentication"></a>Godkendelse

### <a name="authentication-failed-with-aadsts70002-or-aadsts50053"></a>Godkendelsen mislykkedes med AADSTS70002 eller AADSTS50053

**(AADSTS70002: Fejl under validering af legitimationsoplysninger. AADSTS50053: Du har prøvet at logge på for mange gange med forkert bruger-ID eller adgangskode)**

Hvis du bruger Power BI Embedded, Azure AD Direkte godkendelse og modtager meddelelser, når du logger ind, såsom ***fejl: uautoriseret_klient, fejlbeskrivelse:AADSTS70002: Fejl under validering af legitimationsoplysninger. AADSTS50053: Du har prøvet at logge på for mange gange med forkert bruger-ID eller adgangskode***, fordi direkte godkendelse er blevet slået fra, fra og med 14/6/2018.

Vi anbefaler, at du bruger [betinget adgang til Azure AD – Microsoft Azure Active Directory](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/07/azure-ad-conditional-access-support-for-blocking-legacy-auth-is-in-public-preview/), der understøtter af blokering af ældre godkendelse, eller [gennemgående godkendelse fra Azure AD Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).

Dette kan dog aktiveres igen ved hjælp af en [Azure AD-politik](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/configure-authentication-for-federated-users-portal#enable-direct-authentication-for-legacy-applications), der enten kan begrænses til organisationen eller være en [tjenesteprincipal](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-application-objects#service-principal-object).

**_Vi anbefaler, at du kun aktiverer for dent enkelte program og udelukkende som en løsning._**

Hvis du vil oprette denne politik, skal du være **Global Administrator** for den mappe, hvor du opretter politikken og tildelingen. Her er et eksempel på et script til oprettelse af politikken og tildeling af den til SP for dette program:

1. Installér [Azure AD PowerShell-modulet som prøveversion](https://docs.microsoft.com/en-us/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).

2. Kør følgende powershell-kommandoer linje for linje (Sørg for, at variablen $sp ikke har mere end 1 program som resultat).

```powershell
Connect-AzureAD
```

```powershell
$sp = Get-AzureADServicePrincipal -SearchString "Name_Of_Application"
```

```powershell
$policy = New-AzureADPolicy -Definition @("{`"HomeRealmDiscoveryPolicy`":{`"AllowCloudPasswordValidation`":true}}") -DisplayName EnableDirectAuth -Type HomeRealmDiscoveryPolicy -IsOrganizationDefault $false
```

```powershell
Add-AzureADServicePrincipalPolicy -Id $sp.ObjectId -RefObjectId $policy.Id 
```

Efter tildeling af politikken skal du vente ca. 15-20 sekunder for overførsel inden afprøvning.

**Generering af token mislykkes ved angivelse af effektiv identitet**

GenerateToken kan mislykkes af forskellige grunde, når effektiv identitet er angivet.

* Datasæt understøtter ikke effektiv identitet
* Brugernavn blev ikke angivet
* Rolle blev ikke angivet
* DatasetId blev ikke angivet
* Brugeren har ikke de korrekte tilladelser

Du kan benytte følgende metoder for at bekræfte årsagen:

* Kør [get dataset](https://docs.microsoft.com/rest/api/power-bi/datasets). Er egenskaben IsEffectiveIdentityRequired sand?
* Brugernavn er obligatorisk for enhver EffectiveIdentity.
* Hvis IsEffectiveIdentityRolesRequired er sandt, så er Rolle påkrævet.
* DatasetId er obligatorisk for enhver EffectiveIdentity.
* For Analysis Services skal den overordnede bruger være en gateway-administrator.

### <a name="aadsts90094-the-grant-requires-admin-permission"></a>AADSTS90094: Tildelingen kræver administratorrettigheder

**_Symptomer:_**</br>
Når en ikke-administratorbruger forsøger at logge på et program første gang og giver samtykke, får hun følgende fejl:
* ConsentTest skal have tilladelse til at få adgang til ressourcer i din organisation, som kun en administrator kan tildele. Bed en administrator om at give tilladelse til dette program, før du kan bruge det.
* AADSTS90094: Tildelingen kræver administratorrettigheder.

    ![Samtykketest](media/embedded-troubleshoot/consent-test-01.png)

En administratorbruger kan logge på og give samtykke.

**_Hovedårsag:_**</br>
Brugersamtykke er deaktiveret for lejeren.

**_Der er flere mulige fejlrettelser:_**

*Aktivere brugersamtykke for hele lejeren (alle brugere, alle programmer)*
1. I Azure-portal, gå til "Azure Active Directory" = > "Brugere og grupper" = > "Brugerindstillinger"
2. Aktivér "Brugerne må give samtykke til, at apps får adgang til virksomhedsdata på deres vegne", og gem ændringerne

    ![Fejlrettelse af samtykketest](media/embedded-troubleshoot/consent-test-02.png)

*Tildel tilladelser af en administrator* Tildel tilladelser til programmet af en administrator – enten til hele lejeren eller til en bestemt bruger.

## <a name="data-sources"></a>Datakilder

**ISV vil have andre legitimationsoplysninger til den samme datakilde**

En datakilde kan have et enkelt sæt legitimationsoplysninger til én overordnet bruger. Hvis du har brug for at oprette andre legitimationsoplysninger, skal du oprette andre overordnede brugere. Derefter skal du tildele de andre legitimationsoplysninger til hver af den overordnede brugers kontekst og integrere vha. den pågældende brugers Azure AD-token.

## <a name="content-rendering"></a>Indholdsgengivelse

**Gengivelse eller forbrug af integreret indhold mislykkes eller får timeout**

Sørg for, at det integrerede token ikke er udløbet. Sørg for at kontrollere den integrerede tokens udløb og opdatere den. Du kan få flere oplysninger under [Opdatér token ved hjælp af JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Rapport eller dashboard indlæses ikke**

Hvis brugeren ikke kan se rapporten eller dashboardet, skal du sørge for, at rapporten eller dashboardet indlæses korrekt i powerbi.com. Rapporten eller dashboardet fungerer ikke internt i programmet, hvis det ikke indlæses internt i powerbi.com.

**Rapport- eller dashboard-ydeevne er langsom**

Åbn filen fra Power BI Desktop, eller internt i powerbi.com, og bekræft, at ydeevnen er acceptabel for at udelukke, at der er problemer med dit program eller integrations-API'er.

## <a name="onboarding-experience-tool-for-embedding"></a>Onboarding Experience Tool til integration

Du kan gennemgå [Onboarding Experience Tool](https://aka.ms/embedsetup) for hurtigt at downloade en eksempelapp. Derefter kan du sammenligne din app med eksemplet.

### <a name="prerequisites"></a>Forudsætninger

Kontrollér, at du opfylder de krævede forudsætninger, før du bruger Onboarding Experience Tool. Du skal have en **Power BI Pro**-konto og et **Microsoft Azure**-abonnement.

* Hvis du ikke er tilmeldt **Power BI Pro**, kan du [tilmelde dig en gratis prøveversion](https://powerbi.microsoft.com/en-us/pricing/), før du begynder.
* Hvis du ikke har et Azure-abonnement, skal du oprette en [gratis konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), før du begynder.
* Du skal have din egen konfiguration af [Azure Active Directory-lejer](create-an-azure-active-directory-tenant.md).
* Du skal have [Visual Studio](https://www.visualstudio.com/) installeret (version 2013 eller nyere).

### <a name="common-issues"></a>Almindelige problemer

Nogle af de mest almindelige problemer, som du kan støde på med Onboarding Experience Tool, er:

#### <a name="using-the-embed-for-your-customers-sample-application"></a>Brug af eksempelappen Embed for your customers

Hvis du arbejder med **Embed for your customers**, skal du gemme og udpakke filen *PowerBI-Developer-Samples.zip*. Derefter skal du åbne mappen *PowerBI-Developer-Samples-master\App Owns Data* og køre filen *PowerBIEmbedded_AppOwnsData.sln*.

Når du vælger **Grant permissions**, får du vist følgende fejl:

    AADSTS70001: Application with identifier <client ID> was not found in the directory <directory ID>

Du kan løse fejlen ved at lukke pop op-vinduet, vente nogle sekunder og prøve igen. Det kan være nødvendigt at gentage dette nogle gange. Et tidsinterval er årsag til problemet, hvor programregistreringsprocessen ikke kan fuldføres, når den er tilgængelig for eksterne API'er.

Følgende fejlmeddelelse vises, når eksempelappen køres:

    Password is empty. Please fill password of Power BI username in web.config.

Denne fejl opstår, fordi den eneste værdi, der ikke bliver overført til eksempelappen, er din brugeradgangskode. Åbn filen Web.config i løsningen, og udfyld feltet pbiPassword med din brugeradgangskode.

#### <a name="using-the-embed-for-your-organization-sample-application"></a>Brug af eksempelappen Embed for your organization

Hvis du arbejder med **Embed for your organization**, skal du gemme og udpakke filen *PowerBI-Developer-Samples.zip*. Derefter skal du åbne mappen *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* og køre filen *pbi-saas-embed-report.sln*.

Når du kører eksempelappen **Embed for your organization**, får du følgende fejl:

    AADSTS50011: The reply URL specified in the request does not match the reply URLs configured for the application: <client ID>

Dette skyldes, at den URL-adresse til omdirigering, der er angivet for webserverprogrammet, er forskellig fra URL-adressen i eksemplet. Hvis du vil registrere eksempelappen, skal du bruge `http://localhost:13526/` som URL-adresse til omdirigering.

Hvis du vil redigere det registrerede program, skal du lære at redigere den [AAD-registrerede app](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application), så appen kan give adgang til web-API'erne.

Hvis du vil redigere Power BI-brugerprofilen eller -dataene, skal du lære, hvordan du redigere dine [Power BI-data](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts).

Du kan finde flere oplysninger under [Ofte stillede spørgsmål om Power BI Embedded](embedded-faq.md).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)