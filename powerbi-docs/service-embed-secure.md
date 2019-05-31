---
title: Integrer en rapport på en sikker portal eller et websted
description: Power BI integreres funktion giver brugerne mulighed for let og at integrere sikkert rapporter i interne webportaler.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
LocalizationGroup: Share your work
ms.openlocfilehash: bf9d7bcdf6ddaf7d0063843a5314233989b2dadd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222251"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>Integrer en rapport på en sikker portal eller et websted

Med den nye **Integrer** mulighed for at Power BI-rapporter, kan du nemt og sikkert integrere rapporter i interne webportaler. Disse portaler kan være **cloudbaserede** eller **hostes i det lokale miljø**, f.eks SharePoint 2019. Integrerede rapporter overholde alle element tilladelser og datasikkerhed via [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md). De leverer uden kode integrere i en hvilken som helst portal, der accepterer en URL-adresse eller en iFrame. 

Den **Integrer** indstillingen understøtter [URL-filtre](service-url-filters.md) og indstillinger for URL-adresse. Det giver dig mulighed at integrere med ved hjælp af en kode på lavt tilgang, der kræver kun grundlæggende HTML og JavaScript-viden.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Sådan **integrerer** du Power BI-rapporter på portaler

1. Den nye indstilling **Integrer** er tilgængelig på menuen **Filer** til rapporter i Power BI-tjenesten.

    ![Indstillingen Integrer på rullelisten](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. Vælg den **Integrer** mulighed for at åbne en dialogboks, der indeholder et link og en iFrame, du kan bruge til at integrere rapporten på en sikker måde.

    ![Dialogboksen til indstillingen Integrer](media/service-embed-secure/secure-embed-code-dialog.png)

3. Uanset om en bruger åbner en URL-adresse til rapporten direkte, eller en integreret i en webportal, kræver adgang til rapporten godkendelse. På følgende skærm vises, hvis en bruger ikke har logget på Power BI i deres browser-session. Når de vælger **logon**, et nyt browservindue eller fanen kunne åbnes. Få dem med at finde blokeringer, hvis de ikke bliver bedt om at logge på.

    ![Log på for at få vist rapporten](media/service-embed-secure/secure-embed-sign-in.png)

4. Når brugeren har logget på, åbnes rapporten, så Sidenavigation og indstilling for filter og viser dataene. Kun brugere, der har visningstilladelse kan få vist rapporten i Power BI. Alle [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md) regler, der også anvendes. Desuden skal brugeren have en korrekt licens – det kræver enten en Power BI Pro-licens, eller at rapporten er placeret i et arbejdsområde, der har Power BI Premium-kapacitet. Brugeren skal logge på hver gang de åbner et nyt browservindue. Men når du er logget på, andre rapporter indlæses automatisk.

    ![Integrer rapport](media/service-embed-secure/secure-embed-report.png)

5. Når du bruger en iFrame, skal du kan redigere den **højde** og **bredde** at det kunne passe ind i din portal webside.

    ![Angiv højde og bredde](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-report-access"></a>Tildeling af adgang til rapporten

Den **Integrer** indstilling tillader ikke automatisk brugere kan få vist rapporten. Visningstilladelser er angivet i Power BI-tjenesten.

I Power BI-tjenesten, kan du dele integrerede rapporter med brugere, der kræver adgang. Hvis du bruger en Office 365-gruppe, kan du angive brugeren som medlem af app-arbejdsområde. Du kan finde flere oplysninger i Sådan [Administrer dit apparbejdsområde i Power BI og Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md).

## <a name="licensing"></a>Licensering

For at få vist den integrerede rapport, skal brugerne enten en Power BI Pro-licens, eller indholdet skal være i et arbejdsområde, der er i en [Power BI Premium-kapacitet (EM eller P SKU)](service-admin-premium-purchase.md).

## <a name="customize-your-embed-experience-using-url-settings"></a>Tilpas din integrerede oplevelse ved hjælp af URL-indstillinger

Du kan tilpasse brugeroplevelsen ved hjælp af indstillinger for integrerede URL-adressens input. I den angivne iFrame, du kan opdatere URL-adressens **src** indstillinger.

| Egenskab  | Beskrivelse  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | Du kan bruge den **pageName** streng forespørgselsparameter for at angive, hvilken rapportside åbner. Du kan finde denne værdi for enden af rapporten URL-adressens når du får vist en rapport i Power BI-tjenesten, som vist nedenfor. |  |  |  |
| URL-filtre  | Du kan bruge [URL-filtre](service-url-filters.md) i den integrerede URL-adresse, du har modtaget fra Power BI-Brugergrænsefladen til at filtrere det integrerede indhold. På denne måde kan du skabe integrationer, der kun kræver begrænset kode og helt grundlæggende erfaring med HTML og JavaScript.  |  |  |  |

## <a name="set-which-page-opens-for-an-embedded-report"></a>Angiv, hvilke siden åbnes for en integreret rapport 

Du kan finde den **pageName** værdi enden rapport URL-adressens, når du får vist en rapport i Power BI-tjenesten.

1. Åbn rapporten fra Power BI-tjenesten i din webbrowser, og derefter kopiere URL-adresse søjle.

    ![Rapportsektion](media/service-embed-secure/secure-embed-report-section.png)

2. Tilføj indstillingen **pageName** i slutningen af URL-adressen.

    ![Tilføj pageName i slutningen](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>Filtrer rapportens indhold ved hjælp af URL-filtre 

Du kan bruge [URL-filtre](service-url-filters.md) til at give forskellige rapportvisninger. I eksemplet nedenfor filtrerer URL-adressen rapporten, så der kun vises data for energibranchen.

Der kan opnås en stor effekt ved at kombinere **pageName** og [URL-filtre](service-url-filters.md). Du kan skabe specifikke oplevelser ved hjælp af grundlæggende HTML og JavaScript.

Her er f.eks. en knap, du kan føje til en HTML-side:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

Når du har valgt, kalder knappen en funktion for at opdatere din iFrame med en opdateret URL-adresse, som omfatter energi branche filteret.

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![Filtrer](media/service-embed-secure/secure-embed-filter.png)

Du kan tilføje lige så mange knapper, du vil, og på den måde skabe en brugerdefineret oplevelse med begrænset kode. 

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* Understøtter ikke eksterne gæstebrugere med Azure business-to-business (B2B).

* Sikker integration fungerer for rapporter, der er publiceret til Power BI-tjenesten.

* Brugeren skal logge på at få vist rapporten, hver gang de åbner et nyt browservindue.

* Visse browsere kræve, at du at opdatere siden efter logon, især når du bruger InPrivate- eller Inkognito-tilstand.

* Til at opnå en enkelt-logon-oplevelse, brug integrerede i SharePoint Online-indstillingen, eller Byg en brugerdefineret integration ved hjælp af den [brugeren ejer dataene](developer/embed-sample-for-your-organization.md) integrerer metode. 

* Muligheden for automatisk godkendelse, der er tilgængelig med indstillingen **Integrer** fungerer ikke sammen med Power BI JavaScript API. Til Power BI JavaScript API, kan du bruge den [brugeren ejer dataene](developer/embed-sample-for-your-organization.md) integrerer metode. 

## <a name="next-steps"></a>Næste trin

* [Forskellige måder at dele dit arbejde i Power BI](service-how-to-collaborate-distribute-dashboards-reports.md)

* [Filtrer en rapport med forespørgselsstrengparametre i URL-adressen](service-url-filters.md)

* [Integrer med rapportwebdelen i SharePoint Online](service-embed-report-spo.md)

* [Publicer på internettet fra Powerbi](service-publish-to-web.md)