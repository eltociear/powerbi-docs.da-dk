---
title: Opret og publicer apps med dashboards og rapporter i Power BI
description: "Få mere at vide om, hvordan du opretter og publicerer apps, der er samlinger af dashboards og rapporter, som er udviklet til at levere vigtige målepunkter for din organisation."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/22/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d711e2276f2ac170ed54152d54c023261ca9c0bc
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-publish-apps-with-dashboards-and-reports-in-power-bi"></a>Opret og publicer apps med dashboards og rapporter i Power BI

I Power BI kan du oprette *apps* for at samle relaterede dashboards og rapporter på én placering og derefter publicere dem til større persongrupper i din organisation. Du kan også oprette forbindelse til [Power BI apps til eksterne tjenester](service-connect-to-services.md), f.eks. Google Analytics og Microsoft Dynamics CRM.

![Power BI-apps](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

Forretningsbrugere har ofte brug for flere Power BI-dashboards og -rapporter for at kunne drive deres virksomhed. Apps kombinerer alle delene, så brugerne ikke behøver at huske på navne og placeringer for alle disse dashboards.  

Med Power BI-apps, der nu findes i prøveversion, kan du oprette samlinger af dashboards og rapporter og publicere disse apps til hele organisationen eller til bestemte personer eller grupper. Som forfatter til rapporten eller administrator gør apps det nemmere for dig at administrere tilladelser til samlinger af dashboards.

Forretningsbrugere kan få dine apps på flere måder. Hvis Power BI-administratoren giver dig tilladelse, kan du automatisk installere dem i dine kollegers Power BI-konti. Ellers kan de installere dine apps fra Microsoft AppSource, eller du kan sende dem et direkte link. De kan nemt finde og vende tilbage til dit indhold, fordi det hele er samlet på ét sted. De får automatisk opdateringer, og du kan styre, hvor ofte dataene opdateres. Læs mere om [appoplevelsen for forretningsbrugere](service-install-use-apps.md).

### <a name="licenses-for-apps"></a>Licenser til apps
Som udvikler af apps skal du bruge en licens til Power BI Pro. Der er to muligheder for din appbrugere.

* Mulighed 1: Alle forretningsbrugere skal have licens til **Power BI Pro** for at få vist din app. 
* Mulighed 2: Gratisbrugere i din organisation kan få vist appindhold, hvis din app er placeret i Power BI Premium-kapacitet. Læs [Hvad er Power BI Premium?](service-premium.md) for at få flere oplysninger.

### <a name="apps-and-organizational-content-packs"></a>Apps og organisationsindholdspakker
Apps er en udviklet form af organisationsindholdspakker. Hvis du allerede har organisationsindholdspakker, vil de fortsætte med at fungere side om side med apps.

Nu, hvor du har fået overblik over apps, kan vi gennemgå *apparbejdsområder*, hvor du kan oprette apps. 

## <a name="video-apps-and-app-workspaces"></a>Video: Apps og apparbejdsområder
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="app-workspaces"></a>Apparbejdsområder
*Apparbejdsområder* er de steder, hvor du opretter apps, så du skal oprette et apparbejdsområde, før du opretter appen. Hvis du har prøvet at arbejde i et gruppearbejdsområde i Power BI, kender du allerede til apparbejdsområder. De er en udviklet form af gruppearbejdsområder – midlertidige områder og beholdere til indhold i appen. 

Du kan føje kollegaer til disse arbejdsområder som medlemmer eller administratorer. Alle medlemmer af apparbejdsområdet og administratorer skal have licens til Power BI Pro. I arbejdsområdet kan alle samarbejde i dashboards, rapporter og andre artikler, som du vil publicere til en større målgruppe eller endda hele organisationen. 

Når indholdet er klar, skal du vælge, hvilke dashboards og rapporter, som du ønsker at udgive, og derefter skal du udgive appen. Du kan sende et direkte link til denne større målgruppe, eller de kan finde din app under fanen Apps ved at gå til **Download and explore more apps from AppSource** (Download og udforsk flere apps fra AppSource). Disse personer kan ikke ændre indholdet af appen, men de kan interagere med det enten i Power BI-tjenesten eller en af mobilappsene – og selv filtrere, markere og sortere data. 

## <a name="create-an-app-workspace"></a>Opret et apparbejdsområde
[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Det er tomt, så nu skal du føje indhold til det. Bemærk, at når du opretter arbejdsområdet første gang, skal du muligvis vente omkring en time, før det er overført til Office 365. 

Tilføjelse af indhold foregår på samme måde, som når du føjer indhold til Mit arbejdsområde, bortset fra at andre personer i arbejdsområdet også kan se det og arbejde med det. Den store forskel er, at når du er færdig, kan du publicere indholdet som en app. Fra apparbejdsområdet kan du uploade eller oprette forbindelse til filer, eller du kan oprette forbindelse til tjenester fra tredjepart på samme måde som i Mit arbejdsområde. Eksempel:

* [Opret forbindelse til services](service-connect-to-services.md) som f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics.
* [Hent data fra filer](service-get-data-from-files.md) f.eks. Excel-, CSV- eller Power BI Desktop-filer (PBIX).

Når du får vist indhold i et apparbejdsområde, vises ejeren som navnet på apparbejdsområdet.

## <a name="add-an-image-to-your-app-optional"></a>Føj et billede til din app (valgfrit)
Power BI opretter som standard en lille farvet cirkel for din app med appens forbogstaver. Det kan også være, at du vil tilpasse den med et billede. Hvis du vil tilføje et billede, skal du have en Exchange Online-licens.

1. Vælg **Arbejdsområder**, vælg de tre prikker (...) ud for navnet på arbejdsområdet og derefter **Medlemmer**. 
   
     ![Vælg medlemmer af arbejdsområdet](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    Outlook til Office 365-kontoen til arbejdsområdet åbnes i et nyt browservindue.
2. Når du peger på den farvede cirkel øverst til venstre, bliver den til et blyantsikon. Vælg det.
   
     ![Office 365-blyantsikon](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Vælg blyantsikonet igen, og find det billede, du vil bruge.
   
     ![Vælg blyanten igen](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)
4. Vælg **Gem**.
   
     ![Vælg Gem](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    Billedet erstatter den farvede cirkel i Office 365 Outlook-vinduet. 
   
     ![Tilpasset billede](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    Efter nogle få minutter vises det også i appen i Power BI.
   
     ![Tilpasset billede](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="publish-your-app"></a>Publicer din app
Når dashboards og rapporter i apparbejdsområdet er klar, kan du publicere dem som en app. Husk, at du ikke behøver at publicere alle rapporter og dashboards i arbejdsområdet. Du kan nøjes med at publicere dem, der er klar.

1. I listevisning i arbejdsområdet bestemmer du, hvilke dashboards og rapporter der skal medtages i appen.

     ![Vælg dashboardet, der skal publiceres](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     Hvis du vælger ikke at publicere en rapport, får du vist en advarsel ud for rapporten og dens relaterede dashboard. Du kan stadig publicere appen, men det relaterede dashboard mangler felterne fra den pågældende rapport.

     ![Advarsel om relateret dashboard](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Vælg knappen **Publicer app** øverst til højre for at starte processen til deling af alt indhold i dette arbejdsområde.
   
     ![Publicer app](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. Under **Detaljer** skal du udfylde beskrivelsen, som skal hjælpe brugerne med at finde appen. Du kan angive en baggrundsfarve for at tilpasse den.
   
     ![Appdetaljer](media/service-create-distribute-apps/power-bi-apps-details.png)

4. Under **Indhold** får du vist det indhold, der skal publiceres som del af appen – alt det, du har valgt i dette arbejdsområde. Du kan også konfigurere appens landingsside – det dashboard eller den rapport, som brugere får vist først, når de går til din app. Du kan vælge **Ingen**. Brugere føres i så fald til en liste over alt indholdet i appen. 
   
     ![Appindhold](media/service-create-distribute-apps/power-bi-apps-content.png)

5. Under **Adgang** skal du beslutte, hvem der skal have adgang til appen: enten alle i organisationen, specifikke personer eller Active Directory-sikkerhedsgrupper. Hvis du har de rette tilladelser, kan du vælge at installere appen til modtagerne automatisk. Du kan aktivere denne indstilling på [Power BI-administrationsportal](#how-to-enable-pushing-apps). Du kan få mere at vide om overvejelser i forbindelse med [push af en app](#how-to-enable-pushing-apps).

    ![Appadgang](media/service-create-distribute-apps/power-bi-apps-access.png)

6. Når du vælger **Udfør**, får du vist en meddelelse med en bekræftelse af, at den er klar til at blive publiceret. I dialogboksen, der vises efter udførelse, kan du indsætte URL-adressen, der er et direkte link til denne app, og sende den til personer, som du har delt den med.
   
     ![Afslutning af appen](media/service-create-distribute-apps/power-bi-apps-success.png)

De forretningsbrugere, som du har publiceret appen til, kan finde den på flere forskellige måder. Hvis du kan installere den automatisk, vises den under Apps på deres Power BI-konto. Du kan sende dem det direkte link til appen, eller de kan søge efter det i Microsoft AppSource, hvor de kan se alle de apps, de har adgang til. Når de efterfølgende går til Apps, får de vist denne app på deres liste, uanset, hvordan de får den.

Læs mere om [appoplevelsen for forretningsbrugere](service-install-use-apps.md).

## <a name="change-your-published-app"></a>Skift din publicerede app
Når du publicerer din app, vil du muligvis ændre eller opdatere den. Det er nemt at opdatere den, hvis du er administrator eller medlem af apparbejdsområdet. 

1. Åbn apparbejdsområdet, der svarer til appen. 
   
     ![Åbn arbejdsområde](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)
2. Åbn dashboardet eller rapporten. Du kan se, at du kan foretage alle de ændringer, du vil.
   
     Apparbejdsområdet er dit testområde, så dine ændringer ikke sendes live til appen, før du publicerer igen. Her kan du foretage ændringer, uden at det påvirker publicerede apps.  
 
3. Gå tilbage til apparbejdsområdets liste over indhold, og vælg **Opdater app**.
   
     ![Knappen Opdater app](media/service-create-distribute-apps/power-bi-app-update-button.png)

4. Opdater **Oplysninger**, **Indhold** og **Adgang**, hvis du vil, og vælg derefter **Opdater app**.
   
     ![Knappen Opdater app](media/service-create-distribute-apps/power-bi-app-update-complete.png)

De personer, du har publiceret appen for, får automatisk vist den opdaterede version af appen. 

# <a name="automatically-install-apps-for-end-users"></a>Installér automatisk apps for slutbrugere
Du kan installere apps automatisk for slutbrugere, hvilket gør det lettere at distribuere de rette apps til de rette personer eller grupper.

Apps leverer data, som dine slutbrugere har behov for for at udføre deres job. Nu kan du installere disse apps automatisk på Apps-indholdslisten i stedet for, at du skal finde dem i Microsoft AppSource eller følge et installationslink. Det gør det lettere for dig at rulle Power BI-standardindhold ud til dine brugere.

## <a name="how-to-install-an-app-automatically-for-end-users"></a>Sådan installerer du automatisk en app for slutbrugere
Når administratoren har aktiveret funktionen, er det muligt for appudgivere automatisk at vælge den nye indstilling **Installér appen automatisk**. Når afkrydsningsfeltet er ***markeret***, og appudgiveren vælger **Afslut** (eller **Opdater app** for eksisterende apps), pushes appen til alle de brugere eller grupper, der er defineret i sektionen **Tilladelser** på fanen **Adgang** i appen.

![Aktivér push af apps](media/service-create-distribute-apps/power-bi-apps-access.png)

## <a name="how-users-get-the-apps-that-were-pushed-to-them"></a>Sådan får brugerne de apps, der er pushet til dem
Når du har pushet en app, vises den automatisk på Apps-listen. Du kan levere de apps, som en bruger eller jobrolle i organisationen har brug for at have lige ved hånden.

![Aktivér push af apps](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Overvejelser i forbindelse med automatisk installation af apps
Her er nogle ting, du skal huske på, når du pusher apps til slutbrugerne:

* Automatisk installation af en app til brugerne kan tage tid. De fleste apps installeres for brugerne med det samme, men det kan tage tid at pushe apps.  Det afhænger af antallet af elementer i appen og antallet af personer med adgang. Vi anbefaler, at apps pushes efter almindelig arbejdstid, hvor der er god tid til, brugerne skal bruge dem. Få bekræftelse hos flere brugere, før du sender en generel meddelelse til alle om, at appsene er tilgængelige.

* Opdater browseren. Det kan være nødvendigt for en bruger at opdatere eller lukke og genåbne browseren, før vedkommende kan se den pushede app på Apps-listen.

* Hvis brugeren ikke kan se appen på Apps-listen med det samme, skal browseren opdateres eller lukkes og genåbnes.

* Prøv ikke at overvælde brugerne. Pas på ikke at pushe for mange apps, da brugerne skal have en opfattelse af, at de forudinstallerede apps er nyttige for dem. Det er bedst at kontrollere, hvem der kan pushe apps til slutbrugerne, for at koordinere timingen. Du kan etablere en kontakt i organisationen i forbindelse med push af apps til slutbrugerne.

## <a name="unpublish-an-app"></a>Annuller publicering af en app
Et medlem af et apparbejdsområde kan annullerer publicering af appen.

* I et apparbejdsområde skal du vælge de tre prikker (**...** ) i øverste højre hjørne > **Annuller publicering af app**.
  
     ![Annuller publicering af app](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Denne handling fjerner installationen af appen for alle, du har udgivet den til, så de ikke længere har adgang til den. Den sletter ikke apparbejdsområdet eller dets indhold.

## <a name="power-bi-apps-faq"></a>Ofte stillede spørgsmål om Power BI-apps
### <a name="how-are-app-workspaces-different-from-group-workspaces"></a>Hvordan adskiller apparbejdsområder sig fra gruppearbejdsområder?
Fra og med denne version har vi omdøbt alle gruppearbejdsområder til apparbejdsområder. Du kan publicere en app fra et hvilken som helst af disse arbejdsområder. Funktionaliteten forbliver i de fleste tilfælde på samme niveau som i gruppearbejdsområder. Vi planlægger følgende forbedringer af apparbejdsområder i løbet af de kommende måneder: 

* Oprettelse af apparbejdsområder vil ikke føre til oprettelse af tilsvarende objekter i Office 365, som det f.eks. sker med gruppearbejdsområder. Du kan derfor oprette så mange apparbejdsområder, du vil, uden at bekymre dig om, at der oprettes forskellige Office 365-grupper i baggrunden (du kan stadig benytte en Office 365-gruppes OneDrive for Business til lagring af filer). 
* I dag kan du kun føje enkeltpersoner til medlems- og administratorlisterne. Du vil snart kunne føje flere AD-sikkerhedsgrupper eller moderne grupper til disse lister, så administrationen bliver nemmere.  

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Hvordan adskiller apps sig fra organisationsindholdspakker?
Apps er en udvikling og forenkling af indholdspakker med nogle få større forskelle. 

* Når forretningsbrugere installerer en indholdspakke, mister den sin grupperede identitet: Den er bare en liste over dashboards og rapporter blandet med andre dashboards og rapporter. Apps bevarer på den anden side deres gruppering og identitet, også efter installationen. Det gør det nemt for forretningsbrugere at fortsætte med at navigere til dem hen over tid.
* Du kan oprette flere indholdspakker fra et vilkårligt arbejdsområde, men en app har en en til en-relation til dens arbejdsområde. Vi mener, at det gør det lettere at forstå apps og vedligeholde dem i det lange løb. Se oversigtsafsnittet i Power BI-bloggen, hvis du vil vide mere om, hvordan vi planlægger at forbedre dette område. 
* Vi vil over tid fraråde organisationsindholdspakker, og vi anbefaler derfor, at du begynder at oprette apps fra nu af.  

### <a name="what-about-read-only-members-in-groups"></a>Hvad med medlemmer af grupper, som kun har læseadgang?
I grupper kan du tilføje medlemmer med læseadgang, som kun kan få vist indholdet. Hovedproblemet med denne indfaldsvinkel var, at det ikke var mulige at tilføje sikkerhedsgrupper som medlemmer. 

Med apps kan du publicere en skrivebeskyttet version af dit apparbejdsområdet til større målgrupper, herunder sikkerhedsgrupper. Du kan teste dine ændringer af dashboards og rapporter i appen, uden at det påvirker slutbrugerne. Vi anbefaler, at du fremover bruger apps på denne måde. Vi vil på sigt også fraråde medlemmer med læseadgang til arbejdsområder.  

## <a name="next-steps"></a>Næste trin
* [Installér og brug apps i Power BI](service-install-use-apps.md)
* [Power BI-apps til eksterne tjenester](service-connect-to-services.md)
* [Power BI-administrationsportal](https://docs.microsoft.com/en-us/power-bi/service-admin-portal)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)