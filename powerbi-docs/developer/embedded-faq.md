---
title: Ofte stillede spørgsmål om Power BI Embedded
description: Gennemse en liste med ofte stillede spørgsmål og svar om Power BI Embedded.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 54d768e4d2ad1b2eab4559ee5d9db0705fb55542
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762645"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Ofte stillede spørgsmål om Power BI Embedded

* Hvis du har andre spørgsmål, kan du [prøve at spørge Power BI-community'et](http://community.powerbi.com/).
* Har du stadig problemer? Gå til [supportsiden for Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Generelt

### <a name="what-is-power-bi-embedded"></a>Hvad er Power BI Embedded?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md) gør det muligt for programudviklere at integrere flotte, fuldt interaktive rapporter i programmer, uden at de skal bruge tid og penge på at oprette deres egne datavisualiseringer og -kontrolelementer fra bunden.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Hvem er målgruppen for Power BI Embedded?

Udviklere og softwarefirmaer, der fremstiller deres egne programmer, også kaldet uafhængige softwareleverandører (eller ISV'er).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Hvordan er Power BI Embedded anderledes end Power BI-tjenesten?

Power BI Embedded er beregnet til ISV'er eller udviklere, der fremstiller programmer og vil integrere visualiseringer i disse programmer, der kan hjælpe deres kunder med at træffe beslutninger, uden at de skal bygge analyseløsninger op fra bunden. [Integreret analyse](embedding.md) gør det muligt for virksomhedsbrugere at tilgå virksomhedsdata og udføre forespørgsler for at generere indsigter ved hjælp af disse data i programmet.

Power BI er en software-as-a-service-analyseløsning, der giver virksomheder et enkelt overblik over deres vigtigste virksomhedsdata.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Hvad er forskellen mellem Power BI Premium og Power BI Embedded?

Power BI Premium er kapacitetsmæssigt gearet mod virksomheder, som vil have en komplet BI-løsning, der giver adgang til en enkelt visning af virksomheden, kunderne og leverandørerne. Power BI Premium hjælper din virksomhed med at træffe beslutninger. Power BI Premium er et SaaS-produkt og giver mulighed for brugere at forbruge indhold gennem Power BI-portalen, mobilapp og gennem internt udviklede programmer.

Power BI Embedded er beregnet til ISV'er eller udviklere, der fremstiller programmer, og som vil integrere visualiseringer i de pågældende programmer. Power BI Embedded hjælper dine kunder med at træffe beslutninger, og fordi Power BI Embedded er beregnet til programudviklere, så kan kunderne af det pågældende program forbruge indhold lagret på Power BI Embedded-kapaciteter, herunder alle indenfor og udenfor virksomheden. Kapacitetsindhold i Power BI Embedded kan ikke deles gennem publicering med et enkelt klik til web eller publicering med et enkelt klik til SharePoint, og det understøtter ikke SSRS-rapporter.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Hvad anbefaler Microsoft, når en kunde står over for valget mellem Power BI Premium og Power BI Embedded?

Microsoft anbefaler, at virksomheder køber Power BI Premium, som er en selvbetjent cloudbaseret BI-løsning i virksomhedsklassen, og at ISV'er køber Power BI Embedded, som er cloudbaserede, integrerede analysekomponenter. Kunder kan dog købe begge produkter uden begrænsning.

Der kan være situationer, hvor en ISV (typisk en større) ønsker at bruge en P SKU for at få adgang til yderligere fordele i den færdigpakkede Power BI-tjenesten i virksomheden såvel som at integrere den i programmer. Nogle virksomheder beslutter måske at bruge A SKU'er i Azure, hvis de kun er interesserede i at producere line-of-business-programmer og integrere analyser i dem uden at have interesse i at bruge den færdigpakkede Power BI-tjeneste.

### <a name="how-many-embed-tokens-can-i-create"></a>Hvor mange integreringstokens kan jeg oprette?

Integreringstokens med en PRO-licens er beregnet til udviklingstest, så antallet af integreringstokens, der kan genereres af en Power BI-masterkonto eller [tjenesteprincipal](embed-service-principal.md), er begrænset. [Køb en kapacitet](#technical) for at integrere i et produktionsmiljø. Der er ingen grænse for hvor mange integreringstokens, du kan generere, når der er købt en kapacitet. Gå til [Tilgængelige funktioner](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) for at undersøge den brugsværdi, der angiver brugen af integreringstokens i procent.

## <a name="technical"></a>Tekniske spørgsmål

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Hvad er forskellen mellem A SKU'erne i Azure og EM-SKU'erne i Office 365?

PowerBI.com er en virksomhedsløsning, der indeholder mange funktioner, såsom socialt samarbejde, mailabonnement og andre funktioner i en løsning af typen Software som en tjeneste.

Power BI Embedded er en række API'er, der er tilgængelige for udviklere til produktionen af integrerede analyseløsninger på en Platform-as-a-Service-tjeneste. I forbindelse med scenarier i relation til integrerede analyser hjælper PowerBI.com ISV'er og udviklere med at administrere deres integrerede analyseløsningsindhold og indstillinger på lejerniveau.

Her er en delvis liste over forskelle, som du kan bruge i hver.

| Udvalgt | Power BI Embedded | Power BI Premium-kapacitet | Power BI Premium-kapacitet |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A-SKU'er) | (EM-SKU'er) | (P-SKU'er) |
| Integrer artefakter fra et Power BI-programarbejdsområde | Azure-kapacitet | Office 365-kapacitet | Office 365-kapacitet |
| Forbrug Power BI-rapporter i et integreret program | Ja | Ja | Ja |
| Forbrug Power BI-rapporter i SharePoint | Nej | Ja | Ja |
| Forbrug Power BI-rapporter i Dynamics | Nej | Ja | Ja |
| Forbrug Power BI-rapporter i Teams (omfatter ikke mobilapp) | Nej | Ja | Ja |
| Få adgang til indhold med en GRATIS Power BI-licens på Powerbi.com og i Power BI Mobile | Nej | Nej | Ja |
| Få adgang til indhold med en GRATIS Power BI-licens integreret i MS Office-programmer | Nej | Ja | Ja |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI tilbyder nu tre SKU'er til integration: A-SKU'er, EM-SKU'er og P-SKU'er. Hvilken skal jeg købe til mit scenarie?

|  |A-SKU (Power BI Embedded)  |EM-SKU (Power BI Premium)  |P-SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Køb  |Azure-portal |Office |Office |
|Use cases | Integrer indhold i dit eget program | <li> Integrer indhold i dit eget program <br><br></br> <li> Integrer indhold i MS Office-programmer: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (omfatter ikke mobilapp)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Integrer indhold i dit eget program <br><br></br> <li> Integrer indhold i MS Office-programmer: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (omfatter ikke mobilapp)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br></br> <li> Del indhold med Power BI-brugere via [Power BI-tjenesten](https://powerbi.microsoft.com/)  |
|Fakturering |Pr. time |Månedlig |Månedlig |
|Tilsagn  |Intet tilsagn |Årligt  |Månedligt/årligt |
|Differentiering |Fuld elasticitet, kan skaleres op / ned, pausestille / genoptage ressourcer i Azure-portalen eller gennem API  |Kan bruges til at integrere indhold i SharePoint Online og Microsoft Teams (omfatter ikke mobilapp) |Kombiner integration i programmer og brug Power BI-tjenesten i den samme egenskab |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Hvad er forudsætningerne for at oprette en PBIE-kapacitet i Azure?

* Log på din organisationsmappe (administrerede tjenestekonti understøttes ikke).
* Du skal have en Power BI-lejer, dvs. at mindst én bruger i din mappe har tilmeldt sig Power BI. 
* Du skal have et Azure-abonnement i din organisationsmappe.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Hvordan kan jeg overvåge Power BI Embedded-kapacitetsforbrug?

* Brug [Power BI-administrationsportalen](../service-admin-portal.md#power-bi-embedded).

* Download den [metriske app](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) i Power BI.

* Brug [logføring af Azure-diagnosticering](azure-pbie-diag-logs.md).

### <a name="can-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Kan min kapacitet skaleres automatisk for at blive at justeret i henhold til forbruget af mit program?

Automatisk skalering er ikke muligt i øjeblikket, men alle API'er kan skaleres når som helst.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Hvorfor afbrydes kapaciteten midlertidigt, når man opretter/skalerer/genoptager en kapacitet?

Klargøring af en kapacitet (skalering/genoptagelse/oprettelse) kan mislykkes. Den, som kalder klargøringsopkaldet, skal kontrollere en kapacitets ProvisioningState med Få oplysninger om API: [Kapaciteter – Hent oplysninger](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Kan jeg kun oprette Power BI Embedded-kapaciteter i et bestemt område?

Med [Multi-Geo-funktionen (prøveversion)](embedded-multi-geo.md) kan du købe en [Power BI Embedded-kapacitet](azure-pbie-create-capacity.md) i et andet område end din private lejerplacering i Power BI

### <a name="how-can-i-find-what-is-my-pbi-tenant-region"></a>Hvordan kan jeg se mit PBI-lejerområde?

Du kan bruge PBI-portalen til at finde ud af, hvad er dit PBI-lejerområde er.

https://app.powerbi.com/ > ? > Om Power BI

![Om Power BI](media/embedded-faq/about-01.png)
![Lejerområde](media/embedded-faq/tenant-location-01.png)

### <a name="what-is-supported-by-the-cloud-solution-provider-csp-channel"></a>Hvad understøttes af kanalen Cloud Solution Provider (CSP)?

* Du kan oprette PBIE for din lejer med abonnementstype CSP
* Partnerkonto kan logge på kundelejer og købe PBIE for kundelejeren, angive kundelejerbruger som administrator af Power BI-kapacitet

### <a name="why-do-i-get-an-unsupported-account-message"></a>Hvorfor får jeg en meddelelse om en ikke-understøttet konto?

Power BI kræver, at du tilmelder dig med en organisationskonto. Forsøg på at tilmelde sig til Power BI med en MSA (Microsoft-konto) understøttes ikke.

### <a name="can-i-use-apis-to-create--manage-azure-capacities"></a>Kan jeg bruge API'er til at oprette og administrere Azure-kapaciteter?

Ja. Der er Powershell-cmdlet'er og Azure Resource Manager-API'er, du kan bruge til at oprette og administrere PBIE ressourcer.

* Rest API'er – https://docs.microsoft.com/rest/api/power-bi-embedded/
* PowerShell-cmdlet'er – https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>Hvilken rolle har PBI's integrerede dedikerede kapacitet i en PBI-integreret løsning?

For at [gøre din løsning produktionsklar](https://docs.microsoft.com/power-bi/developer/embedding-content#step-3-promote-your-solution-to-production) har du brug for Power BI-indhold (det programarbejdsområde, du bruger i dit program, som skal tildeles til en Power BI Embedded-kapacitet (A SKU)).

### <a name="what-are-the-azure-regions-pbi-embedded-is-available"></a>Hvilke Azure-områder er tilgængelige i PBI integreret?

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

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Hvilken godkendelsesmodel benyttes i Power BI Embedded?

Power BI Embedded bruger fortsat Azure AD til godkendelse af masterbrugeren (en udpeget Power BI Pro-licenseret bruger) eller [tjenesteprincipalen](embed-service-principal.md) til at godkende programmet i Power BI.  

Godkendelsen og autorisationen af programbrugerne implementeres af ISV'en, og ISV'en kan implementere godkendelse for sine programmer.

Hvis du allerede har en Azure AD-lejer, kan du bruge din eksisterende mappe, eller du kan oprette en ny Azure AD-lejer med henblik på at sørge for dit integrerede programindholds sikkerhed.

Du kan bruge et [Azure Active Directory Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) for at få et AAD-token. Der er klientbiblioteker til flere platforme.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>Mit program allerede bruger AAD til brugergodkendelse. Hvordan kan vi bruge dette id til godkendelse til Power BI i et scenarie, hvor "Bruger ejer Data"?

Det er standard OAuth på vegne af flow (https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#web-application-to-web-api) programmet skal være konfigureret til at kræve tilladelser til Power BI-tjenesten (med de påkrævede områder), og når du har et bruger-token til dit program, skal du bare kalde ADAL API AcquireTokenAsync ved hjælp af brugeradgangstoken og angive Power BI-ressourcens URL-adresse ressource-id. Se kodestykke nedenfor, der viser, hvordan dette kan gøres:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Hvordan er Power BI Embedded anderledes end andre Azure-tjenester?

ISV'en/udvikleren skal have en Power BI-konto før købet af Power BI Embedded i Azure. Din Power BI-konto bestemmes af det område, hvor din Power BI Embedded er udrullet. Administrer din Power BI Embedded-ressource i Azure for at:

* Skalere op/ned
* Tilføje kapacitetsadministratorer
* Pausestille/genoptage tjenesten

Brug PowerBI.com til at tildele/fjerne tildelte arbejdsområder fra Power BI Embedded-kapaciteten.

### <a name="what-deploy-regions-are-supported"></a>Hvilke installationsområder understøttes?

Det sydøstlige Australien, det sydlige Brasilien, det centrale Canada, det østlige USA 2, det vestlige Indien, det østlige Japan, det nordlige-centrale USA, det nordlige Europa, det sydlige-centrale USA, Sydøstasien, det sydlige Storbritannien, Vesteuropa, det vestlige USA og det vestlige USA 2.

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>Hvilken type indholdspakke med data kan integreres?

**Dashboards** og **felter**, der er bygget på baggrund af indholdspakker med datasæt, *kan ikke* integreres, men **rapporter**, der er bygget på baggrund af en indholdspakke med datasæt, *kan* godt integreres.

### <a name="what-is-the-difference-between-using-rls-vs-javascript-filters"></a>Hvad er forskellen mellem at bruge RLS- og JavaScript-filtre?

Ofte er der forvirring om, hvornår du skal bruge RLS i forhold til JavaScript-filtre, da én metode vedrører styring af, hvad en bestemt bruger kan se, og den anden vedrører optimering af brugerens visning.

I forbindelse med RLS kontrollerer ISV-udvikleren datafiltreringen som en del af modeloprettelsen og genereringen af integreringstokens. Slutbrugeren ser kun det, ISV'en tillader brugeren at se. I dette tilfælde kan brugeren vælge at se mindre end det, der filtreres, men vedkommende kan ikke tilsidesætte RLS-konfigurationen og se mere end det, der er tilladt.

ISV'en kan muligvis beslutte, hvad brugeren ser på i første visning på vha. filtreringen på klientsiden (JavaScript), men ISV'en kan ikke styre de ændringer, slutbrugeren eventuelt selv foretager af selve visningen. Selvom datafiltrering kan ske i back-end, udløses den af JavaScript-klientkoden og kan derfor ændres af en slutbruger og anses ikke for at være sikker.

Se under [RLS- i forhold til JavaScript-filtre](embedded-row-level-security.md#using-rls-vs-javascript-filters) for at få flere oplysninger.

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Hvordan administrerer jeg tilladelser for tjenesteprincipaler med Power BI?

Når du aktiverer en [tjenesteprincipal](embed-service-principal.md), der skal bruges med Power BI, er AD-tilladelserne for programmet ikke længere gældende. Tilladelserne for programmet administreres derefter via Power BI-administrationsportalen.

Tjenesteprincipaler nedarver tilladelserne til alle Power BI-lejerindstillinger fra deres sikkerhedsgruppe. Hvis du vil begrænse tilladelserne, skal du oprette en dedikeret sikkerhedsgruppe for tjenesteprincipaler og føje den til listen "Undtagen specifikke sikkerhedsgrupper" for de relevante aktiverede Power BI-indstillinger.

Dette er vigtigt, når du tilføjer tjenesteprincipalen som **administrator** til det nye arbejdsområde. Du kan administrere denne opgave via [API'erne](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) eller Power BI-tjenesten.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>Hvornår skal jeg bruge et program-id i forhold til et objekt-id for en tjenesteprincipal?

**[Program-id'et](embed-sample-for-customers.md#application-id)** bruges til at oprette adgangstokenet, når program-id'et vedtages som godkendelse.

Hvis du vil henvise til en tjenesteprincipal for at udføre handlinger eller foretage ændringer, skal du bruge **[objekt-id'et for tjenesteprincipalen](embed-service-principal.md#how-to-get-the-service-principal-object-id)**, f.eks. ved anvendelse af en tjenesteprincipal som administrator i et arbejdsområde.

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

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Hvad sker der, hvis jeg allerede har købt Power BI Premium, og jeg nu vil have nogle af fordelene i Power BI Embedded i Azure?

Kunder betaler fortsat for alle eksisterende Power BI Premium-køb, indtil udløbet af deres aktuelle aftaleperiode, og kan derefter skifte deres Power BI Premium-køb ud efter behov på det pågældende tidspunkt.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Er jeg stadig nødt til at købe Power BI Premium for at få adgang til Power BI Embedded?

Nej, Power BI Embedded omfatter Azure-baseret kapacitet, som du skal bruge for at installere og distribuere løsningen til kunder.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Hvilke købsbindinger er knyttet til Power BI Embedded?

Kunder kan ændre deres brug på timebasis. Der er ingen månedlig eller årlig binding knyttet til Power BI Embedded-tjenesten.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Hvordan vises forbruget af Power BI Embedded på min regning?

Power BI Embedded fakturerer på en forudsigelig timebaseret rate baseret på typen af node(r), der er installeret. Så længe ressourcen er aktiv, faktureres du, selvom der ikke er noget forbrug. For at stoppe faktureringen skal du aktivt afbryde din ressource midlertidigt.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Hvem har brug for et Power BI Pro-licens til Power BI Embedded og hvorfor?

Alle udviklere, der kræver brug af REST API'er, skal have en Power BI Pro-licens eller en [tjenesteprincipal](embed-service-principal.md). Alle analytikere, der skal føje rapporter til et Power BI-arbejdsområde, kan enten have en Power BI Pro-licens eller bruge en tjenesteprincipal. Alle lejeradministratorer, der skal administrere Power BI-lejeren og -kapaciteten, skal have en Power BI Pro-licens.

Idet Power BI Embedded tillader brugen af Power BI-portalen til administration og validering af integreret indhold, så er Power BI Pro-licens påkrævet for at godkende programmet på PowerBI.com for at få adgang til rapporter i de rette lagre.

Men hvis man vil [oprette/redigere integrerede rapporter](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) i sit eget program, behøver slutbrugeren ikke en Pro-licens, da det ikke er et krav, at slutbrugeren er Power BI-bruger.

### <a name="can-i-get-started-for-free"></a>Kan jeg komme i gang gratis?

Ja, du kan bruge din [Azure-kredit](https://azure.microsoft.com/free/) til Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Kan jeg få adgang til en prøveversion af Power BI Embedded i Azure?

Idet Power BI Embedded er en del af Azure, er det muligt at bruge tjenesten med [kreditten på 200 USD, der modtages ved tilmeldingen til Azure](https://azure.microsoft.com/free/).

### <a name="is-power-bi-embedded-available-for-sovereign-clouds-us-government-germany-china"></a>Er Power BI Embedded tilgængelig for suveræne cloudløsninger (den amerikanske regering, Tyskland, Kina)?

Power BI Embedded er tilgængelig for visse [suveræne cloudløsninger](embed-sample-for-customers-sovereign-clouds.md). Det er stadig **IKKE** tilgængeligt for cloudløsninger i Kina.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Er Power BI Embedded tilgængelig for almennyttige organisationer og uddannelsesinstitutioner?

Almennyttige organisationer og uddannelsesinstitutioner kan købe Azure. Der er ingen særlige priser for disse typer kunder i Azure.

## <a name="power-bi-workspace-collection"></a>Power BI Workspace Collection

### <a name="what-is-power-bi-workspace-collection"></a>Hvad er Power BI Workspace Collection?

**Power BI Workspace Collection** (**Power BI Embedded** Version 1) er en løsning, der er baseret på Azure-ressourcen **Power BI Workspace Collection**. Denne løsning gør det muligt at oprette **Power BI Embedded**-programmer til dine kunder ved hjælp af Power BI-indhold under **Power BI Workspace Collection**-løsningen, dedikerede-API'er og nøgler til arbejdsområdesamlinger til godkendelse af programmet til Power BI.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Kan jeg overføre indhold fra Power BI Workspace Collection til Power BI Embedded?

1. Du kan bruge overførselsværktøjet til at klone indhold fra **Power BI Workspace Collection** til Power BI – https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Start med den **Power BI Embedded**-program-POC, der bruger Power BI-indhold.

3. Når du er klar til produktion, skal du købe en **Power BI Embedded**-dedikeret kapacitet og tildele dit Power BI-indhold (arbejdsområde) til denne kapacitet.

    > [!Note]
    > Du kan fortsætte med at bruge **Power BI Workspace Collection**, når du opretter parallelt med en **Power BI Embedded**-løsning. Når du er klar, kan du flytte kunden til den nye **Power BI Embedded**-løsning og lade **Power BI Workspace Collection**-løsningen udgå.

Du kan finde flere oplysninger under [Sådan overfører du indhold fra Power BI Workspace Collection til Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-path-to-be-deprecated"></a>Frarådes det senere at bruge Power BI Workspace Collection på en sti?

Ja, men kunder, der allerede bruger **Power BI Workspace Collection**-løsningen, kan fortsætte med at bruge den, indtil det frarådes. Kunder kan også oprette nye arbejdsområdesamlinger og alle **Power BI Embedded**-programmer, der stadig bruger **Power BI Workspace Collection**-løsningen.

Det betyder dog også, at der ikke føjes nye funktioner til **Power BI Workspace Collection**-løsninger, og at kunder opfordres til at planlægge overførsel af deres data til den nye **Power BI Embedded**-løsning.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Hvornår ophører support til Power BI Workspace Collection?

Kunder, der allerede bruger **Power BI Workspace Collections**-løsningen, kan fortsætte med at bruge den indtil udgangen af juni 2018 eller indtil udgangen af deres supportaftale.

### <a name="in-what-regions-can-pbi-workspace-collection-be-created"></a>I hvilke områder kan der oprettes PBI-arbejdsområdesamling?

De tilgængelige områder er det sydøstlige Australien, det sydlige Brasilien, det centrale Canada, det østlige USA 2, det østlige Japan, det nordcentrale USA, det nordlige Europa, det sydcentrale USA, Sydøstasien, det sydlige Storbritannien, det vestlige Europa, det vestlige Indien og det vestlige USA.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Hvorfor skal jeg overføre indhold fra PBI Workspace Collection til Power BI Embedded?

Nogle nye funktioner og egenskaber introduceres i **Power BI Embedded**-løsningen, som ikke kan bruges i **Power BI Workspace Collection**.

Nogle af funktionerne er:

* Alle PBI-datakilder understøttes i modsætning til de to datakilder, der er inkluderet i **Power BI Workspace Collection**). 
* Nye funktioner, f.eks. Spørgsmål og svar, opdatering, bogmærker, integrering af dashboards og felter, brugerdefinerede menuer, understøttes kun i **Power BI Embedded**-løsningen.
* Model for fakturering af kapacitet.

## <a name="embedding-setup-tool"></a>Embedding-konfigurationsværktøj

### <a name="what-is-the-embedding-setup-tool"></a>Hvad er konfigurationsværktøjet?

Med [Embedding-konfigurationsværktøjet](https://aka.ms/embedsetup) kan du hurtigt komme i gang og downloade en eksempelapp for at komme i gang med at integrere med Power BI.

### <a name="which-solution-should-i-choose"></a>Hvilken løsning skal jeg vælge?

* Med [Integrering for dine kunder](embedding.md#embedding-for-your-customers) kan du integrere dashboards og rapporter for de brugere, der ikke har en konto til Power BI. Kør løsningen [Integrer for dine kunder](https://aka.ms/embedsetup/AppOwnsData).
* Med [Integrering for din organisation](embedding.md#embedding-for-your-organization) kan du udvide Power BI-tjenesten. Kør løsningen [Integrer for din organisation](https://aka.ms/embedsetup/UserOwnsData).

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Jeg har downloadet eksempelprogrammet. Hvilken løsning skal jeg vælge?

Hvis du arbejder med oplevelsen **Integrer for dine kunder**, skal du gemme og udpakke filen *PowerBI-Developer-Samples.zip*. Derefter skal du åbne mappen *PowerBI-Developer-Samples-master\App Owns Data* og køre filen *PowerBIEmbedded_AppOwnsData.sln*.

Hvis du arbejder med **Embed for your organization**, skal du gemme og udpakke filen *PowerBI-Developer-Samples.zip*. Derefter skal du åbne mappen *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* og køre filen *pbi-saas-embed-report.sln*.

### <a name="how-can-i-edit-my-registered-application"></a>Hvordan kan jeg redigere min registrerede app?

Du kan se, hvordan du redigerer AAD-registrerede programmer [her](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application).

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Hvordan kan jeg redigere Power BI-brugerprofilen eller -dataene?

Du kan se, hvordan du redigerer dine Power BI-data, [her](https://docs.microsoft.com/power-bi/service-basic-concepts).

Du kan finde flere oplysninger under [Fejlfinding af det integrerede program](embedded-troubleshoot.md).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)