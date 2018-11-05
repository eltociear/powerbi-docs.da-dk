---
title: Publicer apps med dashboards og rapporter i Power BI
description: Få mere at vide om, hvordan du publicerer apps, der er samlinger af dashboards og rapporter, som er udviklet til at levere vigtige målepunkter for din organisation.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 3881e37fa5e97939265e9bb9362cee65a1030e67
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/25/2018
ms.locfileid: "50100812"
---
# <a name="publish-apps-with-dashboards-and-reports-in-power-bi"></a>Publicer apps med dashboards og rapporter i Power BI

I Power BI kan du publicere *apps* med samlinger af relaterede dashboards og rapporter. Du opretter apps i *apparbejdsområder*, hvor du kan samarbejde om Power BI-indhold med dine kollegaer. Du kan derefter publicere de færdige apps til store grupper af personer i din organisation. Læs mere om [oprettelse af apparbejdsområder](service-create-workspaces.md).

![Power BI-apps](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

Forretningsbrugere har ofte brug for flere Power BI-dashboards og -rapporter for at kunne drive deres virksomhed. Med Power BI-apps kan du oprette samlinger af dashboards og rapporter og publicere disse apps til hele organisationen eller til bestemte personer eller grupper. Hvis du er forfatter af rapporten eller administrator, gør apps det nemmere for dig at administrere tilladelser til disse samlinger.

Forretningsbrugere kan få dine apps på flere måder. Hvis Power BI-administratoren giver dig tilladelse, kan du automatisk installere apps i dine kollegaers Power BI-konti. Ellers kan de installere dine apps fra Microsoft AppSource, eller du kan sende dem et direkte link. De kan nemt finde og vende tilbage til dit indhold, fordi det hele er samlet på ét sted. De kan ikke ændre indholdet af appen, men de kan interagere med det enten i Power BI-tjenesten eller en af mobilappsene – og selv filtrere, markere og sortere data. De får automatisk opdateringer, og du kan styre, hvor ofte dataene opdateres. Læs mere om [appoplevelsen for forretningsbrugere](consumer/end-user-apps.md).

**Vidste du det?** Power BI udgiver en ny prøveversion af arbejdsområdeoplevelsen. Læs [Opret nye arbejdsområder (prøveversion)](service-create-the-new-workspaces.md) for at se, hvordan arbejdsområder ændres i fremtiden. 

## <a name="apps-and-organizational-content-packs"></a>Apps og organisationsindholdspakker
Apps er en udviklet form af organisationsindholdspakker. Indholdspakker er ikke tilgængelige i prøveversionen af de nye arbejdsområdeoplevelser. Når den nye arbejdsområdeoplevelse er offentligt tilgængelig, kan du ikke bruge indholdspakker i arbejdsområder, du opretter derefter. Hvis du ikke allerede har gjort det, kan du begynde at overføre dine indholdspakker til apps.

## <a name="video-apps-and-app-workspaces"></a>Video: Apps og apparbejdsområder
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="licenses-for-apps"></a>Licenser til apps
Alle medlemmer af et apparbejdsområde skal have en Power BI Pro-licens. Der er to muligheder for appbrugere.

* Mulighed 1: Alle forretningsbrugere skal have licens til **Power BI Pro** for at få vist din app. 
* Mulighed 2: Hvis din app er placeret i en Power BI Premium-kapacitet, kan gratisbrugere i din organisation få vist appindhold. Læs [Hvad er Power BI Premium?](service-premium.md) for at få flere oplysninger.

## <a name="publish-your-app"></a>Publicer din app
Når dashboards og rapporter i dit arbejdsområde er klar, skal du vælge, hvilke dashboards og rapporter du vil publicere, og derefter publicerer du dem som en app. Du kan sende et direkte link til denne større målgruppe, eller de kan finde din app under fanen Apps ved at gå til **Download and explore more apps from AppSource** (Download og udforsk flere apps fra AppSource). 

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

5. Under **Adgang** skal du beslutte, hvem der skal have adgang til appen: enten alle i organisationen, specifikke personer eller Active Directory-sikkerhedsgrupper. Hvis du har de rette tilladelser, kan du vælge at installere appen til modtagerne automatisk. En Power BI-administrator kan aktivere denne indstilling på Power BI-administrationsportal. Læs mere om [automatisk installation af en app](#how-to-install-an-app-automatically-for-end-users).

    ![Appadgang](media/service-create-distribute-apps/power-bi-apps-access.png)

6. Når du vælger **Udfør**, får du vist en meddelelse med en bekræftelse af, at den er klar til at blive publiceret. I dialogboksen, der vises efter udførelse, kan du indsætte URL-adressen, der er et direkte link til denne app, og sende den til personer, som du har delt den med.
   
     ![Afslutning af appen](media/service-create-distribute-apps/power-bi-apps-success.png)

Læs mere om [appoplevelsen for forretningsbrugere](consumer/end-user-apps.md).

## <a name="change-your-published-app"></a>Skift din publicerede app
Når du publicerer din app, vil du muligvis ændre eller opdatere den. Det er nemt at opdatere den, hvis du er administrator eller medlem af apparbejdsområdet eller bidragyder i et nyt apparbejdsområde. 

1. Åbn apparbejdsområdet, der svarer til appen. 
   
     ![Åbn arbejdsområde](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)
2. Åbn dashboardet eller rapporten. Du kan se, at du kan foretage alle de ændringer, du vil.
   
     Apparbejdsområdet er dit testområde, så dine ændringer sendes ikke live i appen, før du publicerer igen. Her kan du foretage ændringer, uden at det påvirker publicerede apps.  
 
3. Gå tilbage til apparbejdsområdets liste over indhold, og vælg **Opdater app**.
   
     ![Knappen Opdater app](media/service-create-distribute-apps/power-bi-app-update-button.png)

4. Opdater **Oplysninger**, **Indhold** og **Adgang**, hvis du vil, og vælg derefter **Opdater app**.
   
     ![Knappen Opdater app](media/service-create-distribute-apps/power-bi-app-update-complete.png)

De personer, du har publiceret appen for, får automatisk vist den opdaterede version af appen. 

## <a name="automatically-install-apps-for-end-users"></a>Installér automatisk apps for slutbrugere
Apps leverer data, som dine slutbrugere har behov for for at udføre deres job. Hvis en administrator giver dig tilladelse til det, kan du automatisk installere apps for slutbrugere, hvilket gør det lettere at distribuere de rette apps til de rette personer eller grupper. Din app vises automatisk på dine slutbrugeres appindholdsliste, så de ikke behøver at søge efter dem i Microsoft AppSource eller følge et installationslink. Det gør det lettere for dig at rulle Power BI-standardindhold ud til dine brugere.

### <a name="how-to-install-an-app-automatically-for-end-users"></a>Sådan installerer du automatisk en app for slutbrugere
Når administratoren har givet dig tilladelser, har du en ny indstilling, hvor du kan **installere appen automatisk**. Når du markerer afkrydsningsfeltet og vælger **Afslut** (eller **Opdater app** for eksisterende apps), pushes appen til alle de brugere eller grupper, der er defineret i sektionen **Tilladelser** under fanen **Adgang** i appen.

![Aktivér push af apps](media/service-create-distribute-apps//power-bi-apps-access.png)

### <a name="how-users-get-the-apps-that-were-pushed-to-them"></a>Sådan får brugerne de apps, der er pushet til dem
Når du har pushet en app, vises den automatisk på Apps-listen. Du kan levere de apps, som specifikke brugere eller jobroller i organisationen har brug for at have lige ved hånden.

![Aktivér push af apps](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Overvejelser i forbindelse med automatisk installation af apps
Her er nogle ting, du skal huske på, når du pusher apps til slutbrugerne:

* Automatisk installation af en app til brugerne kan tage tid. De fleste apps installeres for brugerne med det samme, men det kan tage tid at pushe apps.  Det afhænger af antallet af elementer i appen og antallet af personer med adgang. Vi anbefaler, at apps pushes efter almindelig arbejdstid, hvor der er god tid til, brugerne skal bruge dem. Få bekræftelse hos flere brugere, før du sender en generel meddelelse til alle om, at appsene er tilgængelige.

* Opdater browseren. Det kan være nødvendigt for en bruger at opdatere eller lukke og genåbne browseren, før vedkommende kan se den pushede app på Apps-listen.

* Hvis brugeren ikke kan se appen på Apps-listen med det samme, skal browseren opdateres eller lukkes og genåbnes.

* Prøv ikke at overvælde brugerne. Pas på ikke at pushe for mange apps, da brugerne skal have en opfattelse af, at de forudinstallerede apps er nyttige for dem. Det er bedst at kontrollere, hvem der kan pushe apps til slutbrugerne, for at koordinere timingen. Du kan etablere en kontakt i organisationen i forbindelse med push af apps til slutbrugerne.

* Gæstebrugere, der ikke har accepteret en invitation, får ikke installeret apps automatisk.  

## <a name="unpublish-an-app"></a>Annuller publicering af en app
Et medlem af et apparbejdsområde kan annullerer publicering af appen.

* I et apparbejdsområde skal du vælge de tre prikker (**...** ) i øverste højre hjørne > **Annuller publicering af app**.
  
     ![Annuller publicering af app](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Denne handling fjerner installationen af appen for alle, du har udgivet den til, så de ikke længere har adgang til den. Den sletter ikke apparbejdsområdet eller dets indhold.

## <a name="next-steps"></a>Næste trin
* [Opret et apparbejdsområde](service-create-workspaces.md)
* [Installér og brug apps i Power BI](consumer/end-user-apps.md)
* [Power BI-apps til eksterne tjenester](service-connect-to-services.md)
* [Power BI-administrationsportal](https://docs.microsoft.com/power-bi/service-admin-portal)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
