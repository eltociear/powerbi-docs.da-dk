---
title: "Ofte stillede spørgsmål om Power BI Embedded"
description: "Gennemse en liste med ofte stillede spørgsmål og svar om Power BI Embedded."
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
ms.date: 03/07/2018
ms.author: maghan
ms.openlocfilehash: 52ff1095c063be867354a23e0e8e4908a4b4e1d7
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/08/2018
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Ofte stillede spørgsmål om Power BI Embedded

* Hvis du har andre spørgsmål, kan du [prøve at spørge Power BI-community'et](http://community.powerbi.com/).
* Har du stadig problemer? Besøg [supportsiden for Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Generelt

### <a name="what-is-power-bi-embedded"></a>Hvad er Power BI Embedded?

Microsoft Power BI Embedded tillader programudviklere at integrere flotte, fuldt interaktive rapporter, dashboards og felter i programmer, uden at de skal bruge tid og penge på at oprette deres egne datavisualiseringer og -kontrolelementer fra bunden.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Hvem er målgruppen for Power BI Embedded?

Udviklere og softwarefirmaer, der fremstiller deres egne programmer, også kaldet uafhængige softwareleverandører (eller ISV'er).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Hvordan er Power BI Embedded anderledes end Power BI-tjenesten?

Power BI Embedded er beregnet til ISV'er eller udviklere, der fremstiller programmer og vil integrere visuals i disse programmer, der kan hjælpe deres kunder med at træffe beslutninger, uden at de skal bygge analyseløsninger op fra bunden. Integrerede analyser gør det muligt for virksomhedsbrugere at tilgå virksomhedsdata og udføre forespørgsler for at generere indsigter i at bruge disse data i programmet.

Power BI er på den anden side en såkaldt software-as-a-service-analyseløsning, der giver virksomheder et enkelt overblik over deres vigtigste virksomhedsdata.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Hvad er forskellen mellem Power BI Premium og Power BI Embedded?

Power BI Premium er kapacitetsmæssigt gearet mod virksomheder, som vil have en komplet BI-løsning, der giver adgang til en enkelt visning af virksomheden, kunderne og leverandørerne. Power BI Premium hjælper din virksomhed med at træffe beslutninger. Power BI Premium er et SaaS-produkt og giver mulighed for brugere at forbruge indhold gennem Power BI-portalen, mobil-app og gennem internt udviklede apps.

Power BI Embedded er beregnet til ISV'er eller udviklere, der fremstiller programmer, og som vil integrere visuals i de pågældende programmer. Power BI Embedded hjælper dine kunder med at træffe beslutninger, og fordi Power BI Embedded er beregnet til programudviklere, så kan kunderne af det pågældende program forbruge indhold lagret på Power BI Embedded-kapaciteter, herunder alle indenfor og udenfor virksomheden. Kapacitetsindhold i Power BI Embedded kan ikke deles gennem publicering med et enkelt klik til web eller publicering med et enkelt klik til SharePoint, og det understøtter ikke SSRS-rapporter.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Hvad anbefaler Microsoft, når en kunde står over for valget mellem Power BI Premium eller Power BI Embedded?

Microsoft anbefaler, at virksomheder køber Power BI Premium, en professionel, selvbetjent skybaseret BI-løsning, og at ISV'er køber Power BI Embedded, som er skybaserede integrerede analysekomponenter. Kunder kan dog købe begge produkter uden begrænsning.

Der kan være situationer, hvor en ISV (typisk en større) ønsker at bruge en P SKU for at få adgang til yderligere fordele i den færdigpakkede Power BI-tjenesten i virksomheden såvel som at integrere den i programmer. Desuden kan det naturligvis også være, at nogle virksomheder beslutter at bruge A SKU'er i Azure, hvis de kun er interesserede i at producere line-of-business-programmer og integrere analyser i dem uden interesse for at bruge den færdigpakkede Power BI-tjeneste.

### <a name="how-many-embed-tokens-can-i-create"></a>Hvor mange integrerede tokens kan jeg oprette?

Med en PRO-licens er integrerede tokens kun beregnet til udvikling og udviklingstest, så antallet af integrerede tokens, der kan genereres fra en Power BI-masterkonto, er begrænset. Du skal [købe en kapacitet](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) for at kunne integrere i et produktionsmiljø. Der er ingen grænse for hvor mange integrerede tokens, du kan generere, når der er købt en kapacitet.

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>Hvornår bliver Power BI Embedded tilgængeligt i Azure?

Power BI er tilgængeligt nu.

## <a name="technical"></a>Tekniske spørgsmål

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Hvad er forskellen mellem A SKU'erne i Azure og EM-SKU'erne i Office 365?

PowerBI.com er en virksomhedsløsning, der indeholder mange funktioner som f.eks. socialt samarbejde, mailabonnement, osv. i en SaaS-ydelse

Power BI Embedded er en række API'er, der er tilgængelige for udviklere til produktionen af integrerede analyseløsninger på en Platform-as-a-Service-tjeneste. I forbindelse med scenarier i relation til integrerede analyser skal PowerBI.com bruges til at hjælpe ISV'er og udviklere med at administrere deres integrerede analyseløsningsindhold og indstillinger på lejerniveau.

Her er en delvis liste over forskelle, som du kan bruge i hver.

|Udvalgt  |Power BI Embedded<br>(A-SKU'er) |Power BI Premium-kapacitet<br>(EM-SKU'er)  |
|---------|---------|---------|
|Integrer artefakter fra arbejdsområder i en Power BI-app     |Azure-kapacitet |Office 365-kapacitet |
|Power BI-licens påkrævet for at forbruge rapporter |Nej  |Ja |
|Forbrug Power BI-rapporter i et integreret program |Ja  |Ja |
|Forbrug Power BI-rapporter i SharePoint |Nej |Ja |
|Forbrug Power BI-rapporter i Teams |Nej |Ja |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI omfatter nu tre SKU'er til integration: A-SKU'er og P-SKU'er. Hvilken skal jeg købe til mit scenarie?

|  |A-SKU (Power BI Embedded)  |EM-SKU (Power BI Premium)  |P-SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Køb     |Azure-portal |Office |Office |
|Use cases |* Integrer indhold i dit eget program |* Integrer indhold i dit eget program<br>* Del indhold med Power BI FREE-brugere uden for PowerBI.com og integrer i andre SaaS-programmer (SharePoint, Teams) |* Integrer indhold i dit eget program<br>* Del indhold med Power BI FREE-brugere uden for PowerBI.com og integrer i andre SaaS-programmer (SharePoint, Teams)<br>* Del indhold med Power BI FREE-brugere via PowerBI.com  |
|Fakturering |Pr. time |Månedlig |Månedlig |
|Tilsagn  |Intet tilsagn |Årligt  |Månedligt/årligt |
|Differentiering |Fuld elasticitet, kan skaleres op / ned, pausestille / genoptage ressourcer i Azure-portalen eller gennem API  |Kan bruges til at integrere indhold i SharePoint Online og Microsoft Teams |Kombiner integration i programmer og brug Power BI-tjenesten i den samme egenskab |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Hvad er forudsætningerne for at oprette en PBIE-kapacitet i Azure?

- Du skal logge på din organisationsmappe (MSA-konti understøttes ikke).
- Du skal have en Power BI-lejer, dvs. at mindst én bruger i din mappe har tilmeldt sig Power BI. 
- Du skal have et Azure-abonnement i din organisationsmappe.

### <a name="how-can-i-monitor-capacity-consumption"></a>Hvordan kan jeg overvåge kapacitetsforbrug?

Overvågning vha. Azure er omfattet af køreplanen på kort sigt. Azure-ressourcen, Power BI Embedded, vil omfatte overvågning af KPI'er, der vli vise tilstand og brug.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Vil min kapacitetsskala automatisk justere iht. forbruget af min app?

Selvom der ikke er nogen skalering nu, så er alle API'erne tilgængelige for skalering når som helst.

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Hvilken godkendelsesmodel benyttes i Power BI Embedded?

Power BI Embedded vil fortsat bruge Azure AD til godkendelse af master-brugeren (en udpeget Power BI Pro-licenseret bruger), der godkender programmet internt i Power BI.

Godkendelse og godkendelse af programbrugerne bliver implementeret af ISV'en, ISV'en kan implementere sin egen godkendelse til sine programmer.

Hvis du allerede har en Azure AD-lejer, kan du bruge din eksisterende mappe, eller du kan oprette en ny Azure AD-lejer med henblik på at sørge for dit integrerede programindholds sikkerhed.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Hvordan er Power BI Embedded anderledes end andre Azure-tjenester?

ISV'en/udvikleren skal have en Power BI-konto før købet af Power BI Embedded i Azure. Power BI Embedded-installationens område bestemmes af din Power BI-konto. Administrer din Power BI Embedded-ressource i Azure for at:

* Skalere op/ned
* Tilføje kapacitetsadministratorer
* Pausestille/genoptage tjenesten

Brug PowerBI.com til at tildele/fjerne tildelte arbejdsområder fra Power BI Embedded-kapaciteten.

### <a name="what-deploy-regions-are-supported"></a>Hvilke installationsområder understøttes?

Det sydøstlige Australien, det sydlige Brasilien, det centrale Canada, det østlige USA 2, det vestlige Indien, det østlige Japan, det nordlige-centrale USA, det nordlige Europa, det sydlige-centrale USA, Sydøstasien, det sydlige Storbritannien, Vesteuropa, det vestlige USA og det vestlige USA 2.

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>Hvilken type indholdspakke med data kan integreres?

**Dashboards** og **felter**, der er bygget på baggrund af indholdspakker med datasæt *kan ikke* integreres, men **rapporter** bygget på baggrund af en indholdspakke med datasæt *kan* godt integreres.

## <a name="licensing"></a>Licensering

### <a name="how-do-i-purchase-power-bi-embedded"></a>Hvordan køber jeg Power BI Embedded?

Power BI Embedded fås gennem Azure.

### <a name="how-power-bi-embedded-be-metered"></a>Hvordan bliver Power BI Embedded-forbrugsafregnet?

Power BI Embedded bliver beregnet efter timeforbrug.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Hvordan vises forbruget af Power BI Embedded på min regning?

Power BI Embedded fakturerer på en forudsigelig timebaseret rate baseret på typen af node(r), der er installeret. Bemærk, at så længe ressourcen er aktiv, faktureres du, selvom der ikke er noget forbrug. For at stoppe faktureringen skal du aktivt afbryde din ressource. Midlertidig afbrydelse kan ske via Azure eller ARM-API'er.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Hvad sker der, hvis jeg allerede har købt Power BI Premium, og jeg nu vil have nogle af fordelene i Power BI Embedded i Azure?

Kunder vil fortsætte med at betale for alle eksisterende Power BI Premium-køb, indtil udløbet af deres aktuelle aftaleperiode og kan derefter skifte deres Power BI Premium-køb ud efter behov på det pågældende tidspunkt.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Er jeg stadig nødt til at købe Power BI Premium for at få adgang til Power BI Embedded?

Nej, Power BI Embedded omfatter Azure-baseret kapacitet, som du skal bruge for at installere og distribuere løsningen til kunder.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Hvem har brug for et Power BI Pro-licens til Power BI Embedded og hvorfor?

Det er obligatorisk for alle analytikere, der skal føje rapporter til et Power BI-arbejdsområde, for alle udviklere, der skal bruge REST API'er, for alle lejer-administratorer, der skal administrere Power BI-lejeren og -kapacitet at have en Power BI Pro-licens.

Idet Power BI Embedded tillader brugen af Power BI-portalen til administration og validering af integreret indhold, så er Power BI Pro-licens påkrævet for at godkende App'en internt i PowerBI.com for at få adgang til rapporter i de korrekte lagre.

### <a name="can-i-get-started-for-free"></a>Kan jeg komme i gang gratis?

Ja, du kan bruge din [Azure-kredit](https://azure.microsoft.com/free/) til Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Kan jeg få adgang til en prøveversion af Power BI Embedded i Azure?

Idet Power BI Embedded er en del af Azure, er det muligt at bruge tjenesten med [USD200 kreditten, der modtages ved tilmeldingen til Azure](https://azure.microsoft.com/free/).

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Hvilke købsbindinger er knyttet til Power BI Embedded? 

Kunder kan ændre deres brug på timebasis. Der er ingen månedlig eller årlig binding knyttet til Power BI Embedded-tjenesten.

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>Hvor er Power BI Embedded tilgængelig? USA's regering? Tyskland? Kina? Hvad er tidsindstillingen?

Power BI Embedded er tilgængelig i kommercielle Azure cloudmiljøer og i US Government-cloudmiljøet.  En national cloud bliver tilgængelig i Tyskland og Kina i fremtiden.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Er Power BI Embedded tilgængelig for almennyttige organisationer og uddannelsesinstitutioner?

Almennyttige organisationer og uddannelsesinstitutioner kan købe Azure. Der er ingen særlige priser for disse typer kunder i Azure.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
