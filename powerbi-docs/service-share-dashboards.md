---
title: "Del dashboards med kollegaer og andre – Power BI"
description: "Sådan deler du Power BI-dashboards med kollegaer i og uden for din organisation, og hvad du skal vide om at dele."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: monitoring
qualitydate: 08/14/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/11/2017
ms.author: maggies
ms.openlocfilehash: 276f663b8454ef0938222576cec13fcfb073e2cf
ms.sourcegitcommit: bb577045145b2e6e5807622a53cefa2d46574618
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/12/2017
---
# <a name="share-your-power-bi-dashboards-with-coworkers-and-others"></a>Del dine Power BI-dashboards med kollegaer og andre
*Deling* er velegnet til at give nogle få personer adgang til dine dashboards og rapporter. Power BI har [flere måder at samarbejde og distribuere dine dashboards på](service-how-to-collaborate-distribute-dashboards-reports.md), og deling er bare én.

![Delingsikon på en liste over dashboards](media/service-share-dashboards/power-bi-share-dash.png)

Uanset om du deler indhold i eller uden for din organisation, skal du og dine modtagere med deling bruge en [Power BI Pro-licens](service-free-vs-pro.md), eller indholdet skal være i en [Premium-kapacitet](service-premium.md). Forslag? Power BI-teamet er altid interesseret i din feedback, så gå til [webstedet for Power BI-community'et](https://community.powerbi.com/).

Du kan dele et dashboard fra dit eget Mit arbejdsområde eller fra et apparbejdsområde. Når du deler et dashboard, kan de personer, du deler det med, få det vist og interagere med det, men ikke redigere det. De kan se de samme data, som du kan se, i dashboardet og rapporterne, medmindre [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md) anvendes. De kollegaer, du deler det med, kan dele dashboardet med deres kollegaer, hvis du tillader det. Personer uden for organisationen kan også få vist og interagere med dashboardet, men kan ikke dele det. 

Du kan også [dele et dashboard fra en vilkårlig Power BI-mobilapp](mobile-share-dashboard-from-the-mobile-apps.md). Du kan dele dashboards fra Power BI-tjenesten og Power BI-mobilapperne, men ikke fra Power BI Desktop.

## <a name="video-share-a-dashboard"></a>Video: Del et dashboard
Se Amanda dele sit dashboard med kollegaer i og uden for sin virksomhed. Følg derefter den trinvise vejledning under videoen for selv at prøve det.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard"></a>Del et dashboard
1. I dit Mit arbejdsområdet eller i et apparbejdsområde skal du åbne et dashboard og vælge **Del** ![Delingsikon](media/service-share-dashboards/power-bi-share-icon.png).
2. Angiv i det øverste felt de komplette mailadresser til enkeltpersoner, distributionsgrupper eller sikkerhedsgrupper. Du kan ikke dele med dynamiske distributionslister. 
   
   Du kan dele med brugere, hvis adresser er uden for din organisation, men du får vist en advarsel.
   
   ![Advarsel om ekstern deling](media/service-share-dashboards/power-bi-share-dialog-warning.png)  
3. Tilføj en meddelelse, hvis du vil. Det er valgfrit.
4. Hvis du vil tillade dine kollegaer at dele dit dashboard med andre, skal du markere **Tillad, at modtagerne må dele dette dashboard**.
   
   Det kaldes *gendeling* at give andre tilladelse til at dele. Hvis du giver dem tilladelse, kan de dele igen fra Power BI-tjenesten og mobilapperne eller videresende mailinvitationen til andre i din organisation. Invitationen udløber efter én måned. Personer uden for din organisation kan ikke dele igen. Som ejeren af dashboardet kan du deaktivere gendeling eller tilbagekalde gendeling på individuel basis. Se [Stop deling af et dashboard, eller forhindr andre i at dele](service-share-dashboards.md#stop-sharing-a-dashboard-or-stop-others-from-sharing) herunder.
5. Vælg **Del**.
   
   ![Vælg knappen Del](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI sender en mailinvitation til personerne, men ikke til grupper, med et link til det delte dashboard. Du kan se en beskeden **Udført**. 
   
   Når modtagere i din organisation klikker på linket, føjer Power BI dashboardet til deres side med listen **Delt med mig**. De kan vælge dit navn for at få vist alle de dashboards, du har delt. 
   
   ![Side med listen Delt med mig](media/service-share-dashboards/power-bi-shared-with-me-list-page.png)
   
   Når modtagere uden for din organisation klikker på linket, kan de se dashboardet, men ikke på den sædvanlige Power BI-portal. Se [Del et dashboard med personer uden for din organisation](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) nedenfor for at få flere oplysninger.

## <a name="who-has-access-to-a-dashboard-you-shared"></a>Hvem har adgang til et dashboard, som du har delt?
Du kan undertiden få brug for at se de personer, du har delt et dashboard med, og hvem de har delt det med.

1. Vælg **Del** ![Delingsikon](media/service-share-dashboards/power-bi-share-icon.png) på listen over dashboards eller i selve dashboardet. 
2. Vælg **Adgang** i dialogboksen **Del dashboard**.
   
    ![Dialogboksen Del dashboard, fanen Adgang](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Personer uden for din organisation er anført som **Gæst**.

## <a name="stop-sharing-a-dashboard-or-stop-others-from-sharing"></a>Stop deling af et dashboard, eller forhindr andre i at dele
Kun ejeren af dashboardet kan slå gendeling til og fra.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Hvis du ikke har sendt invitationen til deling endnu
* Fjern markeringen i afkrydsningsfeltet **Tillad, at modtagerne må dele dette dashboard** nederst i invitationen, før du sender den.

### <a name="if-youve-already-shared-the-dashboard"></a>Hvis du allerede har delt dashboardet
1. Vælg **Del** ![Delingsikon](media/service-share-dashboards/power-bi-share-icon.png) på listen over dashboards eller i selve dashboardet. 
2. Vælg **Adgang** i dialogboksen **Del dashboard**.
   
    ![Dialogboksen Del dashboard, fanen Adgang](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Vælg ellipsen (**...** ) ud for **Læs og del igen**, og vælg:
   
   ![Ellipse for læsning og deling igen](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Læs** for at forhindre vedkommende i at dele med andre.
   * **Fjern adgang** for at forhindre vedkommende i overhovedet at se dashboardet.

4. I dialogboksen **Fjern adgang** skal du beslutte, om du også vil fjerne adgangen til relateret indhold, som f.eks. rapporter og datasæt. Hvis du fjerner elementer med et advarselsikon ![Power BI-advarselsikon](media/service-share-dashboards/power-bi-warning-icon.png), er det bedst at fjerne relateret indhold, fordi det ikke kan vises korrekt.

## <a name="share-a-dashboard-with-people-outside-your-organization"></a>Del et dashboard med personer uden for din organisation
Når du deler med personer uden for din organisation, modtager de en mail med et link til det delte dashboard, og de skal logge på Power BI for at få vist dashboardet. Hvis de ikke har en licens til Power BI Pro, kan de tilmelde sig en, når de klikker på linket.

Når de har logget på, kan de se det delte dashboard i sit eget browservindue uden den venstre navigationsrude og ikke på deres normale Power BI-portal. De skal bogmærke linket for at få adgang til dette dashboard i fremtiden.

De kan ikke redigere indhold i dette dashboard eller rapporten. De kan interagere med diagrammerne i rapporten (tværgående fremhævning) og ændre tilgængelige filtre/udsnit i de rapporter, der er forbundet med dashboardet, men kan ikke gemme ændringerne.

Kun dine direkte modtagere kan se det delte dashboard. Hvis du f.eks. har sendt mailen til Vicki@contoso.com, kan kun Vicki se dashboardet. Ingen andre kan se dette dashboard, selvom de har linket, og Vicki skal bruge den samme mailadresse til at få adgang til dashboardet. Hun kan heller ikke få adgang til dashboardet, hvis hun tilmelder sig med en anden mailadresse.

Personer uden for din organisation kan slet ikke se nogen data, hvis sikkerhed på rolle- eller rækkeniveau er implementeret på Analysis Services-tabelmodeller i det lokale miljø.

Hvis du sender et link fra en Power BI-mobilapp til personer uden for din organisation, åbnes dashboardet i en browser, når de klikker på linket, og ikke i Power BI-mobilappen.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Ting, du skal være opmærksom på angående deling af dashboards:

* Generelt set kan se du og dine kollegaer se de samme data i dashboardet. Hvis du derfor har tilladelse til at se flere data, end de kan, vil de kunne se alle dine data i dit dashboard. Men hvis [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md) er anvendt på datasættet, der er underliggende for et dashboard, bruges legitimationsoplysningerne for hver person til at afgøre, hvilke data de kan få adgang til.
* Alle, som du deler dashboardet med, kan se det og interagere med dine rapporter i [Læsevisning](service-report-open-in-reading-view.md). De kan ikke oprette rapporter eller gemme ændringer af eksisterende rapporter.
* Ingen kan se eller hente datasættet.
* Alle kan manuelt [opdatere dashboardets data](refresh-data.md).
* Hvis du bruger Office 365 til mail, kan du dele med medlemmer af en distributionsgruppe ved at angive den mailadresse, der er knyttet til distributionsgruppen.
* Kollegaer, der har det samme maildomæne som du, og kollegaer, hvis domæner er anderledes, men registreret i den samme lejer, kan dele dashboardet med andre. Lad os for eksempel antage, at domænerne contoso.com og contoso2.com er registreret i den samme lejer. Hvis din mailadresse er konrads@contoso.com, kan både ravali@contoso.com og gustav@contoso2.com dele, så længe du har givet dem tilladelse til at dele.
* Hvis dine kollegaer allerede har adgang til et bestemt dashboard, kan du sende et direkte link til dette dashboard ved blot at kopiere URL-adressen, når du er på dashboardet. Eksempel: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Hvis dine kolleger allerede har adgang til et bestemt dashboard, kan du på samme måde [sende et direkte link til den underliggende rapport](service-share-reports.md). 

## <a name="troubleshoot-sharing"></a>Fejlfinding af deling

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Mine dashboardmodtagere ser et låseikon i et felt eller en meddelelse med "Tilladelse påkrævet"

Hvis de personer, du deler med, kan se et felt, der er låst i et dashboard eller en meddelelse med "Tilladelse påkrævet", når de forsøger at få vist en rapport, skal du give dem tilladelse til det underliggende datasæt. Sådan gør du:

1. Gå til fanen **Datasæt** på listen over indhold.

1. Vælg ellipsen (**...** ) ud for datasættet > **Administrer tilladelser**.

    ![Administrer tilladelser](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. Vælg **Tilføj bruger**.

    ![Vælg Tilføj bruger](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Angiv de komplette mailadresser til enkeltpersoner, distributionsgrupper eller sikkerhedsgrupper. Du kan ikke dele med dynamiske distributionslister.

    ![Tilføj mailadresser](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. Vælg **Tilføj**

### <a name="i-cant-share-a-dashboard"></a>Jeg kan ikke dele et dashboard

For at dele et dashboard skal du have tilladelse til at dele det underliggende indhold igen – alle relaterede rapporter og datasæt. Hvis du ser en meddelelse, hvor der står, du ikke må dele, skal du bede rapportens forfatter om at give dig tilladelse til at dele rapporterne og datasættene igen.


## <a name="next-steps"></a>Næste trin
* Har du feedback? Kom med dine forslag på [webstedet for Power BI-community'et](https://community.powerbi.com/).
* [Hvordan kan jeg samarbejde på og dele dashboards og rapporter?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Del kun en Power BI-rapport](service-share-reports.md)
* Har du spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/).

