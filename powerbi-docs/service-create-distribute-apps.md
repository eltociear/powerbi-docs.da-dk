---
title: Publicer en app i Power BI
description: Få mere at vide om, hvordan du publicerer de nye apps, der er samlinger af dashboards og rapporter med indbygget navigation.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: eccda071b6c6abc92640024c3587bafa71038dee
ms.sourcegitcommit: c122c1a8c9f502a78ccecd32d2708ab2342409f0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/11/2019
ms.locfileid: "66826638"
---
# <a name="publish-an-app-in-power-bi"></a>Publicer en app i Power BI

I Power BI kan du oprette officielt pakket indhold og derefter distribuere det til en bred målgruppe som en *app*. Du opretter apps i *apparbejdsområder*, hvor du kan samarbejde om Power BI-indhold med dine kollegaer. Du kan derefter publicere de færdige apps til store grupper af personer i din organisation. 

![Power BI-apps](media/service-create-distribute-apps/power-bi-new-apps.png)

Forretningsbrugere har ofte brug for flere Power BI-dashboards og -rapporter for at kunne drive deres virksomhed. Med Power BI-apps kan du oprette samlinger af dashboards og rapporter og publicere disse apps til hele organisationen eller til bestemte personer eller grupper. Hvis du er forfatter af rapporten eller administrator, gør apps det nemmere for dig at administrere tilladelser til disse samlinger.

Forretningsbrugere kan få dine apps på flere måder:

- De kan finde og installere din app fra Microsoft AppSource
- Du kan sende dem et direkte link.
- Du kan automatisk installere dem i dine kollegaers Power BI-konti, hvis Power BI-administratoren giver dig tilladelse til det.

Du kan oprette appen med tilpasset, indbygget navigation, så brugerne nemt kan finde rundt i dit indhold. De kan ikke ændre indholdet af appen. De kan interagere med det enten i Power BI-tjenesten eller en af mobilappsene – og selv filtrere, markere og sortere data. De får automatisk opdateringer, og du kan styre, hvor ofte dataene opdateres. Læs mere om [appoplevelsen for forretningsbrugere](consumer/end-user-apps.md).

## <a name="licenses-for-apps"></a>Licenser til apps
Hvis du vil oprette eller opdatere en app, skal du have en Power BI Pro-licens. Der er to muligheder for *forbrugere*.

* Mulighed 1: Alle forretningsbrugere skal have licens til **Power BI Pro** for at få vist din app. 
* Mulighed 2: Hvis dit apparbejdsområde er placeret i en Power BI Premium-kapacitet, kan gratisbrugere i din organisation få vist appindhold. Læs [Hvad er Power BI Premium?](service-premium.md) for at få flere oplysninger.

## <a name="publish-your-app"></a>Publicer din app
Når dashboards og rapporter i dit arbejdsområde er klar, skal du vælge, hvilke dashboards og rapporter du vil publicere, og derefter publicerer du dem som en app. 

1. I listevisning i arbejdsområdet bestemmer du, hvilke dashboards og rapporter der skal **medtages i appen**.

     ![Vælg dashboardet, der skal publiceres](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     Hvis du vælger ikke at inkludere en rapport, der har et relateret dashboard, får du vist en advarsel ud for rapporten. Du kan stadig publicere appen, men det relaterede dashboard mangler delene fra den pågældende rapport.

     ![Advarsel om relateret dashboard](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Vælg knappen **Publicer app** øverst til højre for at starte processen til oprettelse og publicering af en app fra arbejdsområdet.
   
     ![Publicer app](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. Under **Installation** skal du angive navnet og en beskrivelse, så brugerne nemmere kan finde appen. Du kan angive en temafarve for at gøre den personlig. Du kan også tilføje et link til et supportwebsted.
   
     ![Byg din app](media/service-create-distribute-apps/power-bi-apps-build-your-apps.png)

4. Under **Navigation** skal du vælge det indhold, der skal publiceres som en del af appen. Derefter kan du tilføje appnavigation for at organisere indholdet i sektioner. Se [Design navigationsoplevelsen til din app](#design-the-navigation-experience-for-your-app) i denne artikel for at få flere oplysninger.
   
     ![Appnavigation](media/service-create-distribute-apps/power-bi-apps-navigation.png)

5. Under **Tilladelser** skal du bestemme, hvem der har adgang til appen, og hvad de kan gøre med den. 
    - I [klassiske arbejdsområder](service-create-workspaces.md): alle i din organisation, bestemte personer eller ADD-sikkerhedsgrupper (Azure Active Directory).
    - I [arbejdsområder med den nye oplevelse](service-create-the-new-workspaces.md): bestemte personer, AAD-sikkerhedsgrupper og -distributionslister samt Office 365 Grupper. Alle brugere af arbejdsområdet får automatisk adgang til appen for arbejdsområdet.
    - Du kan give brugere af appen tilladelse til at oprette forbindelse til appens underliggende datasæt ved hjælp af tilladelsen Opret. Disse datasæt vises i søgeoplevelserne for datasættet.
    - Du kan give brugerne af appen tilladelse til at lave en kopi af rapporter i denne app til deres Mit arbejdsområde. 
    
    >[!IMPORTANT]
    >Hvis din app er afhængig af datasæt fra andre arbejdsområder, er det dit ansvar at sikre, at alle brugere af appen har adgang til de underliggende datasæt.
> 
>     


6. Du kan installere appen automatisk for modtagerne, hvis din Power BI-administrator har aktiveret denne indstilling for dig på Power BI-administrationsportalen. Læs mere om, hvordan du [installerer en app automatisk](#automatically-install-apps-for-end-users), i denne artikel.

     ![Apptilladelser](media/service-create-distribute-apps/power-bi-apps-permissions.png)

7. Når du vælger **Publicer app**, får du vist en meddelelse med en bekræftelse af, at den er klar til at blive publiceret. I dialogboksen **Del denne app** kan du kopiere den URL-adresse, der er et direkte link til denne app.
   
     ![Afslutning af appen](media/service-create-distribute-apps/power-bi-apps-success.png)

Du kan sende dette direkte link til de personer, du har delt den med, eller de kan finde din app under fanen Apps ved at gå til **Download og udforsk flere apps fra AppSource**. Læs mere om [appoplevelsen for forretningsbrugere](consumer/end-user-apps.md).

## <a name="change-your-published-app"></a>Skift din publicerede app
Når du publicerer din app, vil du muligvis ændre eller opdatere den. Det er nemt at opdatere den, hvis du er administrator eller medlem af det nye apparbejdsområde. 

1. Åbn apparbejdsområdet, der svarer til appen. 
   
     ![Åbn arbejdsområde](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)

2. Foretag de ønskede ændringer i dashboards eller rapporter.
 
     Apparbejdsområdet er dit testområde, så dine ændringer sendes ikke live i appen, før du publicerer igen. Her kan du foretage ændringer, uden at det påvirker publicerede apps.  
 
    > [!IMPORTANT]
    > Hvis du fjerner en rapport og opdaterer appen, mister dine appforbrugere alle tilpasninger, f.eks. bogmærker, kommentarer osv., også selvom du tilføjer rapporten i appen igen.  
 
3. Gå tilbage til apparbejdsområdets liste over indhold, og vælg **Opdater app** i hjørnet øverst til højre.
   
1. Opdater evt. **Installation**, **Navigation** og **Tilladelser**, og vælg derefter **Opdater app**.
   
De personer, du har publiceret appen for, får automatisk vist den opdaterede version af appen. 

## <a name="design-the-navigation-experience-for-your-app"></a>Design navigationsoplevelsen til din app
Du kan bruge indstillingen **Ny navigationsgenerator** til at udvikle brugerdefineret navigation til din app. Den brugerdefinerede navigation gør det nemmere for dine brugere at finde og bruge indhold i appen. For eksisterende apps er denne indstilling slået fra, og for nye apps er indstillingen som standard slået til.

Når indstillingen er slået fra, kan du vælge, at **App-landingsside** enten skal angives til **Specifikt indhold**, f.eks. et dashboard eller en rapport, eller vælge **Ingen** for at vise brugeren en grundlæggende oversigt over indhold.

Når du slår **Ny navigationsgenerator** til, kan du designe brugerdefineret navigation. Alle de rapporter, dashboards og Excel-projektmapper, du har medtaget i din app, vises som standard som en flad liste. 

![Appnavigation](media/service-create-distribute-apps/power-bi-apps-navigation.png)

Du kan tilpasse appnavigationen yderligere på følgende måde:
* Omarranger elementer ved hjælp af pil op/ned. 
* Omdøb elementer i **Rapportdetaljer**, **Dashboarddetaljer** og **Projektmappedetaljer**.
* Skjul bestemte elementer i navigationen.
* Brug indstillingen **Ny** til at føje **afsnit** til grupperelateret indhold.
* Brug indstillingen **Ny** til at tilføje et **link** til en ekstern ressource i venstre navigation. 

Når du tilføjer et **link**, kan du vælge, hvor linket åbnes, i **Link-detaljer**. Links åbnes som standard under den **aktuelle fane**, men du kan vælge **Ny fane** eller **Indholdsområde**. 

### <a name="considerations-for-using-the-new-navigation-builder-option"></a>Overvejelser ved brug af den nye navigationsgenerator
Her er nogle generelle ting, du skal huske på, når du bruger den nye navigationsgenerator:
* Rapportsider vises i appens navigationsområde som en sektion, der kan udvides
* Hvis du slår den nye navigationsgenerator fra og derefter publicerer eller opdaterer din app, mister du de tilpasninger, du har foretaget. Du mister f.eks. alle sektioner, angivelser af rækkefølge, links og brugerdefinerede navne for navigationselementer.

Når du tilføjer links til din appnavigation og vælger indstillingen Indholdsområde:
* Sørg for, at linket kan integreres. Nogle tjenester blokerer for integrering af deres indhold på tredjepartswebsteder, som f.eks. Power BI.
* Integration af Power BI-tjenesteindhold, f.eks. rapporter eller dashboards, i andre arbejdsområder understøttes ikke. 
* Integrer indhold på Power BI-rapportserveren via det oprindelige integrerings-URL-indhold fra en udrulning i det lokale miljø. Udfør trinnene i [Opret URL-adressen til Power BI-rapportserveren](https://docs.microsoft.com/power-bi/report-server/quickstart-embed#creating-the-power-bi-report-server-report-url) for at få URL-adressen. Vær opmærksom på, at der er gældende godkendelsesregler, så hvis du vil have vist indholdet, skal du have en VPN-forbindelse til serveren i det lokale miljø. 
* Der vises en sikkerhedsadvarsel øverst i det integrerede indhold for at gøre opmærksom på, at indholdet ikke er i Power BI.



## <a name="automatically-install-apps-for-end-users"></a>Installér automatisk apps for slutbrugere
Hvis en administrator giver dig tilladelser, kan du installere apps automatisk og *pushe* dem til slutbrugere. Denne pushfunktionalitet gør det lettere at distribuere de rette apps til de rette personer eller grupper. Din app vises automatisk på dine slutbrugeres liste over appindhold. De behøver ikke at søge efter den i Microsoft AppSource eller at følge et installationslink. Se, hvordan administratorer gør det muligt at [pushe apps til slutbrugerne](service-admin-portal.md#push-apps-to-end-users), i artiklen på Power BI-administrationsportalen.

### <a name="how-to-push-an-app-automatically-to-end-users"></a>Sådan pusher du automatisk en app til slutbrugere
Når administratoren har givet dig tilladelser, har du en ny indstilling, hvor du kan **installere appen automatisk**. Når du markerer afkrydsningsfeltet og vælger **Publicer app** (eller **Opdater app**), pushes appen til alle de brugere eller grupper, der er defineret i sektionen **Tilladelser** under fanen **Adgang** i appen.

![Aktivér push af apps](media/service-create-distribute-apps//power-bi-apps-access.png)

### <a name="how-users-get-the-apps-that-you-push-to-them"></a>Sådan får brugerne de apps, du pusher til dem
Når du har pushet en app, vises den automatisk på deres appliste. På denne måde kan du levere de apps, som specifikke brugere eller jobroller i organisationen har brug for at have lige ved hånden.

![Aktivér push af apps](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Overvejelser i forbindelse med automatisk installation af apps
Her er nogle ting, du skal huske på, når du pusher apps til slutbrugerne:

* Automatisk installation af en app til brugerne kan tage tid. De fleste apps installeres for brugerne med det samme, men det kan tage tid at pushe apps.  Det afhænger af antallet af elementer i appen og antallet af personer med adgang. Vi anbefaler, at apps pushes efter almindelig arbejdstid, hvor der er god tid til, brugerne skal bruge dem. Få bekræftelse hos flere brugere, før du sender en generel meddelelse til alle om, at appsene er tilgængelige.

* Opdater browseren. Det kan være nødvendigt for en bruger at opdatere eller lukke og genåbne browseren, før vedkommende kan se den pushede app på Apps-listen.

* Hvis brugerne ikke kan se appen på applisten med det samme, skal browseren opdateres eller lukkes og genåbnes.

* Prøv ikke at overvælde brugerne. Pas på ikke at pushe for mange apps, da brugerne skal have en opfattelse af, at de forudinstallerede apps er nyttige for dem. Det er bedst at kontrollere, hvem der kan pushe apps til slutbrugerne, for at koordinere timingen. Etabler et kontaktpunkt i organisationen i forbindelse med push af apps til slutbrugerne.

* Gæstebrugere, der ikke har accepteret en invitation, får ikke installeret apps automatisk.  

## <a name="allowing-users-to-connect-to-the-apps-underlying-datasets"></a>Giv brugere tilladelse til at oprette forbindelse til appens underliggende datasæt
Når du markerer indstillingen for at give brugerne tilladelse til at oprette forbindelse til appens underliggende datasæt, modtager brugerne af appen tilladelsen Opret for det underliggende datasæt. Dette giver brugerne mulighed for at [bruge datasættet for appen på tværs af arbejdsområder](service-datasets-across-workspaces.md) til at søge efter disse datasæt i Power BI Desktop og tjenesten at hente dataoplevelse samt til at oprette rapporter og dashboards ved hjælp af disse datasæt. 

Når du fjerner markeringen af denne indstilling, får nye brugere, du føjer til appen, ikke længere tilladelsen Opret. Eksisterende tilladelser for de underliggende datasæt ændres dog ikke. Du kan bruge den angivne brugergrænseflade til at fjerne tilladelsen Opret manuelt fra brugere af appen, som ikke længere skal have den. Læs mere om [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets).

## <a name="allowing-users-to-make-a-copy-of-the-reports-in-the-app"></a>Giv brugerne tilladelse til at lave en kopi af rapporterne i appen
Når du markerer indstillingen **Giv brugerne tilladelse til at lave en kopi af rapporterne i denne app**, giver du brugerne tilladelse til at gemme rapporterne i appen i deres Mit arbejdsområde. De kan derefter tilpasse rapporterne til deres unikke behov. Denne indstilling kræver, at **Giv alle brugere tilladelse til at oprette forbindelse til appens underliggende datasæt ved hjælp af tilladelsen Opret** aktiveres. Denne funktionalitet fungerer som den nye funktionalitet [Kopiér rapporter fra andre arbejdsområder](service-datasets-copy-reports.md).

## <a name="unpublish-an-app"></a>Annuller publicering af en app
Et medlem af et apparbejdsområde kan annullerer publicering af appen.

>[!IMPORTANT]
>Når du annullerer publiceringen af en app, mister app-brugere deres tilpasninger. De mister alle personlige bogmærker, kommentarer eller abonnementer, der er knyttet til indholdet i appen. Annuller kun publicering af en app, hvis du har brug at fjerne den.
> 
> 

* I et apparbejdsområde skal du vælge de tre prikker ( **...** ) i øverste højre hjørne > **Annuller publicering af app**.
  
     ![Annuller publicering af app](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Denne handling fjerner installationen af appen for alle, du har udgivet den til, så de ikke længere har adgang til den. Den sletter ikke apparbejdsområdet eller dets indhold.

## <a name="view-your-published-app"></a>Se din publicerede app

Når forbrugerne af din app åbner din app, kan de se den navigation, du har oprettet, i stedet for Power BI-standardnavigationsruden til venstre. Appnavigationen indeholder en liste over rapporter og dashboards i de sektioner, du har defineret. Den viser også de enkelte sider i de enkelte rapporter og ikke kun navnet på rapporten.

![App med navigation](media/service-create-distribute-apps/power-bi-new-apps-navigation.png)

## <a name="next-steps"></a>Næste trin
* [Opret et apparbejdsområde](service-create-workspaces.md)
* [Installér og brug apps i Power BI](consumer/end-user-apps.md)
* [Power BI-apps til eksterne tjenester](service-connect-to-services.md)
* [Power BI-administrationsportal](https://docs.microsoft.com/power-bi/service-admin-portal)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
