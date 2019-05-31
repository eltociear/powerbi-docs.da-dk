---
title: Ofte stillede spørgsmål om Power BI Embedded
description: Gennemse en liste med ofte stillede spørgsmål og svar om Power BI Embedded.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222182"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Ofte stillede spørgsmål om Power BI Embedded

* Hvis du har andre spørgsmål, kan du [prøve at spørge Power BI-community'et](http://community.powerbi.com/).
* Har du stadig problemer? Gå til [supportsiden for Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Generelt

### <a name="what-is-power-bi-embedded"></a>Hvad er Power BI Embedded?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md) tillader programudviklere at integrere flotte, interaktive rapporter i deres programmer, uden at skulle oprette deres egne datavisualiseringer og kontrolelementer fra bunden.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Hvem er målgruppen for Power BI Embedded?

Udviklere og softwarefirmaer, også kaldet uafhængige softwareleverandører (ISV'er), kodning programmer.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Hvordan er Power BI Embedded anderledes end Power BI-tjenesten?

Power BI er en software-as-a-service-analyseløsning, der giver virksomheder et enkelt overblik over deres vigtigste virksomhedsdata.

Microsoft udviklet Power BI Embedded for uafhængige softwareleverandører vil integrere visuals i deres programmer til at hjælpe deres kunder analytisk beslutninger. Dette betyder mindre ISV'er fra at oprette deres egne analyseløsning sig selv. [Integreret analyse](embedding.md) gør det muligt for virksomhedsbrugere adgang til virksomhedsdata og udføre forespørgsler på den for at generere indsigt i programmet.


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Hvad er forskellen mellem Power BI Premium og Power BI Embedded?

Power BI Premium er gearet mod virksomheder, der ønsker en komplet BI-løsning, der leverer en enkelt visning af den organisation, partnere, kunder og leverandører. Power BI Premium hjælper din virksomhed med at træffe beslutninger. Power BI Premium er et SaaS-produkt, der gør det muligt for brugere at forbruge indhold via mobilapps, internt udviklede apps, eller på Power BI-portalen.

Power BI Embedded er for uafhængige softwareleverandører, der vil integrere visuals i deres programmer. Power BI Embedded hjælper dine kunder med at træffe beslutninger, og fordi Power BI Embedded er beregnet til programudviklere, så kan kunderne af det pågældende program forbruge indhold lagret på Power BI Embedded-kapaciteter, herunder alle indenfor og udenfor virksomheden. Du kan ikke dele Power BI Embedded kapacitetsindhold via et enkelt klik Publicer på internettet eller et enkelt klik Udgiv i SharePoint.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Hvad anbefaler Microsoft, når en kunde står over for valget mellem Power BI Premium og Power BI Embedded?

Microsoft anbefaler, at virksomheder køber Power BI Premium, en professionel, selvbetjent skybaseret BI-løsning. Vi anbefaler, at ISV'er køber Power BI Embedded for dens cloud-integrerede analysekomponenter. En kunde har dog ingen begrænsning på hvilket produkt til at købe.

Der kan være situationer, hvor en ISV (typisk en større), ud over app integrerer, ønsker at bruge en P SKU for at få de yderligere fordele ved den færdigpakkede Power BI-tjenesten i virksomheden. Nogle virksomheder beslutter måske at bruge A SKU'er i Azure, hvis de kun er interesserede i at producere line-of-business-programmer og integrere analyser i dem uden at have interesse i at bruge den færdigpakkede Power BI-tjeneste.

### <a name="how-many-embed-tokens-can-i-create"></a>Hvor mange integrerede tokens kan jeg oprette?

Integrer tokens med PRO-licens er beregnet til udviklingstest, så en Power BI hovedkontoen eller [tjenesteprincipal](embed-service-principal.md) kan kun generere et begrænset antal tokens. [Køb en kapacitet](#technical) for at integrere i et produktionsmiljø. Der er ingen grænse for hvor mange integrerede tokens, kan du generere, når du køber en kapacitet. Gå til [Tilgængelige funktioner](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) for at undersøge den brugsværdi, der angiver brugen af integrerede tokens i procent.

## <a name="technical"></a>Tekniske spørgsmål

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Hvad er forskellen mellem A SKU'erne i Azure og EM-SKU'erne i Office 365?

PowerBI.com er en virksomhed Software som en Service (SaaS)-løsning med mange funktioner, f.eks sociale samarbejde, abonnement på mail og andre funktioner. PowerBI.com hjælper ISV'er med at administrere deres integrerede analyseløsninger indhold og lejerindstillinger niveau.

Power BI Embedded er en Platform som en Service (PaaS), der er angivet af API'er til udviklere kan bruge til at oprette integrerede analyseløsninger.

Her er en ufuldstændig liste over funktionsforskelle.

| Udvalgt | Power BI Embedded | Power BI Premium-kapacitet | Power BI Premium-kapacitet |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A-SKU'er) | (EM-SKU'er) | (P-SKU'er) |
| Integrer artefakter fra et Power BI-programarbejdsområde | Azure-kapacitet | Office 365-kapacitet | Office 365-kapacitet |
| Forbrug Power BI-rapporter i en integreret app | Ja | Ja | Ja |
| Forbrug Power BI-rapporter i SharePoint | Nej | Ja | Ja |
| Forbrug Power BI-rapporter i Dynamics | Nej | Ja | Ja |
| Forbrug Power BI-rapporter i Teams (omfatter ikke mobilapp) | Nej | Ja | Ja |
| Få adgang til indhold med en GRATIS Power BI-licens på Powerbi.com og i Power BI Mobile | Nej | Nej | Ja |
| Få adgang til indhold med en GRATIS Power BI-licens integreret i MS Office-apps | Nej | Ja | Ja |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI tilbyder nu tre SKU'er til integration: A-SKU'er, EM-SKU'er og P-SKU'er. Hvilken skal jeg købe til mit scenarie?

|  |A-SKU (Power BI Embedded)  |EM-SKU (Power BI Premium)  |P-SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Køb  |Azure-portal |Office |Office |
|Use cases | Integrer indhold i din egen app | <li> Integrer indhold i din egen app <br><br><br> <li> Integrer indhold i MS Office-programmer: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (omfatter ikke mobilapp)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Integrer indhold i din egen app <br><br><br> <li> Integrer indhold i MS Office-programmer: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (omfatter ikke mobilapp)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> Del indhold med Power BI-brugere via [Power BI-tjenesten](https://powerbi.microsoft.com/)  |
|Fakturering |Pr. time |Månedlig |Månedlig |
|Tilsagn  |Intet tilsagn |Årligt  |Månedligt/årligt |
|Differentiering |Fuld elasticitet, kan skaleres op / ned, pausestille / genoptage ressourcer i Azure-portalen eller gennem API  |Du kan bruge til at integrere indhold i SharePoint Online og Microsoft Teams (udelukker mobilappen) |Kombiner integration i programmer og brug Power BI-tjenesten i den samme egenskab |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Hvad er forudsætningerne for at oprette en PBIE-kapacitet i Azure?

* Log på din organisationsmappe (Microsoft-konti ikke understøttes).
* Du skal have en Power BI-lejer, og det vil sige, mindst én bruger i din mappe har tilmeldt Power BI. 
* Du skal have et Azure-abonnement i din organisationsmappe.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Hvordan kan jeg overvåge Power BI Embedded-kapacitetsforbrug?

* Brug [Power BI-administrationsportalen](../service-admin-portal.md#power-bi-embedded).

* Download den [metriske app](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) i Power BI.

* Brug [logføring af Azure-diagnosticering](azure-pbie-diag-logs.md).

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>Kan min kapacitetsskala automatisk justere til min app-forbrug?

Mens det er ikke automatisk skalering nu, er alle API'erne tilgængelige for skalering når som helst.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Hvorfor afbrydes kapaciteten midlertidigt, når man opretter/skalerer/genoptager en kapacitet?

Kapacitet klargøring (skalering/genoptage/oprette) kan mislykkes. Du kan bruge få oplysninger om API'EN til at kontrollere en kapacitet ProvisioningState: [Kapaciteter – Hent oplysninger](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Kan jeg kun oprette Power BI Embedded-kapaciteter i et bestemt område?

Med [Multi-Geo-funktionen (prøveversion)](embedded-multi-geo.md) kan du købe en [Power BI Embedded-kapacitet](azure-pbie-create-capacity.md) i et andet område end din private lejerplacering i Power BI

### <a name="how-can-i-find-my-pbi-tenant-region"></a>Hvordan kan jeg finde mit PBI lejer område?

Du kan bruge PBI portal til at finde dit lejer PBI-område.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Om Power BI

![Om Power BI](media/embedded-faq/about-01.png)
![Lejerområde](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>Det understøtter kanalen Cloud Solution Provider (CSP)?

* Du kan oprette PBIE for din lejer med abonnementstype CSP
* Partnerkonto kan logge på kundelejer og købe PBIE for kundelejeren, angive kundelejerbruger som administrator af Power BI-kapacitet

### <a name="why-do-i-get-an-unsupported-account-message"></a>Hvorfor får jeg en meddelelse om en ikke-understøttet konto?

Power BI kræver, at du tilmelder dig med en organisationskonto. Forsøget på at tilmelde sig Power BI ved hjælp af en Microsoft-konto, understøttes ikke.

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>Kan jeg bruge API'er til at oprette og administrere Azure-kapaciteter?

Ja, der er Powershell-cmdlet'er og Azure Resource Manager REST API'er, som du kan bruge til at oprette og administrere PBIE-ressourcer.

* [Rest-API'er](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [PowerShell-cmdlet'er](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>Hvilken rolle har PBI's integrerede dedikerede kapacitet i en PBI-integreret løsning?

Til [gør din løsning produktionsklar](embed-sample-for-customers.md#move-to-production), skal du tildele Power BI-indhold (apparbejdsområde) dit program bruger en Power BI Embedded (A-SKU) kapacitet.

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>I hvilke Azure-områder er PBI Embedded tilgængelig?

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) – se produkttilgængelighedsstyringen

Tilgængelige områder (16 – samme områder som Power BI)

* USA (6) – Det østlige USA, Det østlige USA 2, Det nordcentrale USA, Det sydcentrale USA, Det vestlige USA, Det vestlige USA 2
* Europa (2) – Det nordlige Europa, Det vestlige Europa
* Asien og Stillehavsområdet (2) – Det sydøstlige Asien, Det østlige Asien
* Brasilien (1) – Det sydlige Brasilien
* Japan (1) – Østjapan
* Australien (1) – Det sydøstlige Australien
* Indien (1) – Vestindien
* Canada (1) – Det centrale Canada
* Storbritannien (1) – Det sydlige Storbritannien

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Hvad er Power BI Embedded godkendelsesmodel?

Power BI Embedded fortsætter med at bruge Azure AD til godkendelse af master-brugeren (en udpeget Power BI Pro-licenseret bruger) eller med [tjenesteprincipal](embed-service-principal.md) for godkender programmet internt i Power BI.  

 En ISV kan implementere deres egne godkendelse og autorisation af deres programmer.

Du kan bruge din eksisterende mappe, hvis du allerede har en Azure AD-lejer. Du kan også oprette en ny Azure AD-lejer for dit integrerede programindholds sikkerhed.

Du kan bruge et [Azure Active Directory Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) for at få et AAD-token. Der er klientbiblioteker til flere platforme.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>Mit program allerede bruger AAD til brugergodkendelse. Hvordan kan vi bruge dette id til godkendelse til Power BI i et scenarie, hvor "Bruger ejer Data"?

Det er standard OAuth på vegne af flow (<https://docs.microsoft.com/azure/active-directory/develop/web-api>). Du skal konfigurere dit program kræver tilladelser i Power BI-tjenesten (med de påkrævede områder). Når du har et bruger-token til din app, du skal du bare kalde til ADAL API AcquireTokenAsync ved hjælp af brugeradgang tokenet, og Angiv URL-adressen til Power BI-ressource som ressource-ID:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>Det objekt-ID er service principal objekt-ID'ET?

Den *objekt-ID* er objekt-ID'ET for app, fra det primære skærmbillede i en app, der er registreret.

Det objekt-ID fundet i den *administrerede program i en lokal mappe > egenskaber* sektion er service principal objekt-ID'ET skal du bruge. Dette objekt-ID er at referere til en tjenesteprincipal til handlinger eller foretage ændringer i serviceobjektet principal-id'et. F.eks anvendelse af en tjenesteprincipal til et arbejdsområde som administrator.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Hvordan er Power BI Embedded anderledes end andre Azure-tjenester?

Du skal have en Power BI-konto, før du køber Power BI Embedded i Azure. Dit Power BI Embedded installeret område bestemmer din Power BI-konto. Administrer din Power BI Embedded-ressource i Azure for at:

* Skalere op/ned
* Tilføje kapacitetsadministratorer
* Pausestille/genoptage tjenesten

Brug PowerBI.com til at tildele/fjerne tildelte arbejdsområder fra Power BI Embedded-kapaciteten.

### <a name="what-are-the-supported-deploy-regions"></a>Hvad er de understøttede udrulle områder?

Det sydøstlige Australien, det sydlige Brasilien, det centrale Canada, det østlige USA 2, det vestlige Indien, det østlige Japan, det nordlige-centrale USA, det nordlige Europa, det sydlige-centrale USA, Sydøstasien, det sydlige Storbritannien, Vesteuropa, det vestlige USA og det vestlige USA 2.

### <a name="what-content-pack-data-types-can-you-embed"></a>Hvilke datatyper-indholdspakken kan du integrere?

Du *kan* integrere **Dashboards** og **felter** bygget fra indholdspakker med datasæt. Men du *kan* integrere **rapporter** bygget fra en indholdspakke med datasæt.

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>Hvad er forskellen mellem at bruge i forhold til sikkerhed på rækkeniveau (RLS). JavaScript-filtre?

Er der ofte forvirring omkring når bruge RLS i forhold til JavaScript filtre, da én metode om styring af hvad der kan se en bestemt bruger, og den anden er om optimering af brugerens visning.

I forbindelse med RLS kontrollerer ISV-udvikleren datafiltreringen som en del af modeloprettelsen og genereringen af integrerede tokens. Slutbrugeren ser kun det, ISV'en tillader brugeren at se. I dette tilfælde kan brugeren vælge at se mindre end det, der filtreres, men vedkommende kan ikke tilsidesætte RLS-konfigurationen og se mere end det, der er tilladt.

ISV kan beslutte, hvad brugeren ser på den oprindelige visning på klientsiden filtrering (JavaScript), men de kan ikke styre, slutbrugeren kan gælde for selve visningen. Da du bruger Javascript-klient-kode kan udløse datofiltrering back-end, den kan ikke tages i betragtning sikker.

Se under [RLS- i forhold til JavaScript-filtre](embedded-row-level-security.md#using-rls-vs-javascript-filters) for at få flere oplysninger.

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Hvordan administrerer jeg tilladelser for tjenesteprincipaler med Power BI?

Når du aktiverer [tjenesteprincipal](embed-service-principal.md) for at bruge med Power BI, tilladelser for programmets AD ikke træde i kraft længere. Tilladelserne for programmet administreres derefter via Power BI-administrationsportalen.

Tjenesteprincipaler nedarver tilladelserne til alle Power BI-lejerindstillinger fra deres sikkerhedsgruppe. Opret en dedikeret sikkerhedsgruppe til tjenesteprincipaler for at begrænse tilladelser, og føje den til den **undtagen specifikke sikkerhedsgrupper** listen for de relevante aktiveret Power BI-indstillinger.

Dette er vigtigt, når du tilføjer tjenesteprincipalen som **administrator** til det nye arbejdsområde. Du kan administrere denne opgave via [API'erne](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) eller Power BI-tjenesten.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>Hvornår skal jeg bruge et program-id i forhold til et objekt-id for en tjenesteprincipal?

**[Program-id'et](embed-sample-for-customers.md#application-id)** bruges til at oprette adgangstokenet, når program-id'et vedtages som godkendelse.

Hvis du vil henvise til en tjenesteprincipal for at udføre handlinger eller foretage ændringer, skal du bruge **[objekt-id'et for tjenesteprincipalen](embed-service-principal.md#how-to-get-the-service-principal-object-id)** , f.eks. ved anvendelse af en tjenesteprincipal som administrator i et arbejdsområde.

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>Kan man administrere en datagateway i det lokale miljø med en tjenesteprincipal?

Du kan ikke administrere en datagateway i det lokale miljø (datagateway) ved hjælp af en [tjenesteprincipal](embed-service-principal.md), som du kan med en masterkonto.

Med en masterkonto kan du installere en datagateway, føje brugere til gatewayen, oprette forbindelse til datakilder og udføre andre administrative opgaver.

Med en tjenesteprincipal kan du konfigurere [sikkerhed på rækkeniveau](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview) ved hjælp af en datakilde i det lokale miljø med direkte forbindelse via SQL Server Analysis Services (SSAS). På denne måde kan du administrere brugere og deres adgang til data i SSAS, når du integrerer med **Power BI Embedded** ved hjælp af en tjenesteprincipal.

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>Kan man logge på Power BI-tjenesten med en tjenesteprincipal?

Nej. Du kan ikke logge på Power BI ved hjælp af en tjenesteprincipal.

Du kan desuden ikke bruge indhold som en bruger i eksterne programmer (SaaS-integrering). Det kan du kun, når du genererer et integreringstoken.

### <a name="what-are-the-best-practices-to-improve-performance"></a>Hvad er de bedste fremgangsmåder til at forbedre ydeevnen?

[Ydeevnen i Power BI Embedded](embedded-performance-best-practices.md)

## <a name="licensing"></a>Licensering

### <a name="how-do-i-purchase-power-bi-embedded"></a>Hvordan køber jeg Power BI Embedded?

Power BI Embedded fås gennem Azure.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>Hvad sker der, hvis jeg allerede har købt Power BI Premium, og nu vil jeg nogle Power BI Embedded i Azure-fordele?

Kunder fortsat betale for alle eksisterende Power BI Premium-køb, indtil udløbet af deres aktuelle aftaleperiode og, på dette tidspunkt kan derefter skifte deres Power BI Premium-køb ud efter behov.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Er jeg stadig nødt til at købe Power BI Premium for at få adgang til Power BI Embedded?

Nej, Power BI Embedded omfatter Azure-baseret kapacitet, som du skal bruge for at installere og distribuere løsningen til kunder.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Hvilke købsbindinger er knyttet til Power BI Embedded?

Kunder kan ændre deres brug på timebasis. Der er ingen månedlig eller årlig binding knyttet til Power BI Embedded-tjenesten.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Hvordan vises forbruget af Power BI Embedded på min regning?

Power BI Embedded fakturerer på en forudsigelig timebaseret rate baseret på typen af node(r), der er installeret. Du faktureres, så længe ressourcen er aktiv, selvom der ikke er noget forbrug. Du har brug at afbryde din ressource for at stoppe faktureringen.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Hvem har brug for et Power BI Pro-licens til Power BI Embedded og hvorfor?

Du har brug for en Power BI Pro-licens eller [tjenesteprincipal](embed-service-principal.md) du bruger REST API'er. Hvis du vil føje rapporter til en Power BI-arbejdsområde, skal en analytiker enten en Power BI Pro-licens eller service principal. For at administrere Power BI-lejer og kapacitet, der kræves en administrator har en Power BI Pro-licens.

Da Power BI Embedded tillader Power BI administrationsportalen bruges til administration og validering af integreret indhold, påkrævet Power BI Pro-licens for at godkende app'en internt i PowerBI.com til at få adgang til rapporter, der i de korrekte lagre.

Men hvis man vil [oprette/redigere integrerede rapporter](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) i sit eget program, behøver slutbrugeren ikke en Pro-licens, da det ikke er et krav, at slutbrugeren er Power BI-bruger.

### <a name="can-i-get-started-for-free"></a>Kan jeg komme i gang gratis?

Ja, du kan bruge din [Azure-kredit](https://azure.microsoft.com/free/) til Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Kan jeg få adgang til en prøveversion af Power BI Embedded i Azure?

Da Power BI Embedded er en del af Azure, det er muligt at bruge tjenesten med den [kredit på 200 USD modtages ved tilmeldingen til Azure](https://azure.microsoft.com/free/).

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Er Power BI Embedded tilgængelig til nationale cloudmiljøer (US Government, Tyskland, Kina)?

Power BI Embedded er også tilgængelige for [nationale clouds](embed-sample-for-customers-national-clouds.md).

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Er Power BI Embedded tilgængelig for almennyttige organisationer og uddannelsesinstitutioner?

Der er ingen særlige Azure-prissætning for Almennyttige organisationer og uddannelsesinstitutioner.

## <a name="power-bi-workspace-collection"></a>Power BI Workspace Collection

### <a name="what-is-power-bi-workspace-collection"></a>Hvad er Power BI Workspace Collection?

**Power BI Workspace Collection** (**Power BI Embedded** Version 1) er en løsning, der er baseret på den **Power BI Workspace Collection** Azure-ressource. Denne løsning gør det muligt at oprette **Power BI Embedded**-programmer til dine kunder ved hjælp af Power BI-indhold under **Power BI Workspace Collection**-løsningen, dedikerede-API'er og nøgler til arbejdsområdesamlinger til godkendelse af programmet til Power BI.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Kan jeg overføre indhold fra Power BI Workspace Collection til Power BI Embedded?

1. Du kan bruge overførselsværktøjet til at klone indhold fra **Power BI Workspace Collection** til Power BI – https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Start med den **Power BI Embedded**-program-POC, der bruger Power BI-indhold.

3. Når du er klar til produktion, skal du købe en **Power BI Embedded**-dedikeret kapacitet og tildele dit Power BI-indhold (arbejdsområde) til denne kapacitet.

    > [!Note]
    > Du kan fortsætte med at bruge **Power BI Workspace Collection**, når du opretter parallelt med en **Power BI Embedded**-løsning. Når du er klar, kan du flytte kunden til den nye **Power BI Embedded**-løsning og lade **Power BI Workspace Collection**-løsningen udgå.

Du kan finde flere oplysninger under [Sådan overfører du indhold fra Power BI Workspace Collection til Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Power BI Workspace Collection er en frarådet sti?

Ja, men kunder, der allerede bruger den **Power BI Workspace Collection** løsning kan fortsætte med at bruge den indtil frarådes. Kunder kan også oprette nye arbejdsområdesamlinger og alle **Power BI Embedded**-programmer, der stadig bruger **Power BI Workspace Collection**-løsningen.

Men det betyder også, at der ikke er tilføjet nye funktioner til en **Power BI Workspace Collection** løsninger. Vi opfordrer kunder til at planlægge deres overførsel til den nye **Power BI Embedded** løsning.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Hvornår ophører support til Power BI Workspace Collection?

Kunder, der allerede bruger **Power BI Workspace Collections**-løsningen, kan fortsætte med at bruge den indtil udgangen af juni 2018 eller indtil udgangen af deres supportaftale.

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>I hvilke områder kan jeg oprette en PBI Workspace Collection?

De tilgængelige områder er det sydøstlige Australien, det sydlige Brasilien, det centrale Canada, det østlige USA 2, det østlige Japan, det nordcentrale USA, det nordlige Europa, det sydcentrale USA, Sydøstasien, det sydlige Storbritannien, det vestlige Europa, det vestlige Indien og det vestlige USA.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Hvorfor skal jeg overføre indhold fra PBI Workspace Collection til Power BI Embedded?

Der er nogle nye **Power BI Embedded** løsning funktioner og egenskaber, som du ikke kan gøre med **Power BI Workspace Collection**.

Nogle af funktionerne er:
* Alle PBI datakilder understøttes. Kun to **Power BI Workspace Collection** datakilder understøttes. 
* Nye funktioner, f.eks. Spørgsmål og svar, opdatering, bogmærker, integrering af dashboards og felter, brugerdefinerede menuer, understøttes kun i **Power BI Embedded**-løsningen.
* Model for fakturering af kapacitet.

## <a name="embedding-setup-tool"></a>Embedding-konfigurationsværktøj

### <a name="what-is-the-embedding-setup-tool"></a>Hvad er konfigurationsværktøjet?

Med [Embedding-konfigurationsværktøjet](https://aka.ms/embedsetup) kan du hurtigt komme i gang og downloade en eksempelapp for at komme i gang med at integrere med Power BI.

### <a name="which-solution-should-i-choose"></a>Hvilken løsning skal jeg vælge?

* [Embedding for your customers](embedding.md#embedding-for-your-customers) giver mulighed for at integrere dashboards og rapporter for de brugere, der ikke har en Power BI-konto. Kør løsningen [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData).
* Med [Embedding for your organization](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Kør løsningen [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData).

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Jeg har downloadet eksempelappen. Hvilken løsning skal jeg vælge?

Hvis du arbejder med oplevelsen **Embed for your customers**, skal du gemme og udpakke filen *PowerBI-Developer-Samples.zip*. Derefter skal du åbne mappen *PowerBI-Developer-Samples-master\App Owns Data* og køre filen *PowerBIEmbedded_AppOwnsData.sln*.

Hvis du arbejder med **Embed for your organization**, skal du gemme og udpakke filen *PowerBI-Developer-Samples.zip*. Derefter skal du åbne mappen *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* og køre filen *pbi-saas-embed-report.sln*.

### <a name="how-can-i-edit-my-registered-application"></a>Hvordan kan jeg redigere min registrerede app?

Du kan få mere at vide om, hvordan du redigerer Azure AD-registrerede apps under [Hurtig start: Opdater et program i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app).

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Hvordan kan jeg redigere Power BI-brugerprofilen eller -dataene?

Du kan se, hvordan du redigerer dine Power BI-data, [her](https://docs.microsoft.com/power-bi/service-basic-concepts).

Du kan finde flere oplysninger under [Fejlfinding af det integrerede program](embedded-troubleshoot.md).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
