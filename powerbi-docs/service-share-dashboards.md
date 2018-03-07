---
title: Del Power BI-dashboards og -rapporter med kolleger og andre
description: "Sådan deler du Power BI-dashboards og -rapporter med kolleger i og uden for din organisation, og det du skal vide om at dele."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: lukaszp
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
ms.date: 01/18/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 4e8750078e36dad3c3b9b784ad88d12ac3b6fd7d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="share-your-power-bi-dashboards-and-reports-with-coworkers-and-others"></a>Del dine Power BI-dashboards og -rapporter med kolleger og andre
*Deling* er velegnet til at give nogle få personer adgang til dine dashboards og rapporter. Med Power BI får du også [adskillige andre måder at samarbejde om og distribuere dashboards og rapporter på](service-how-to-collaborate-distribute-dashboards-reports.md).

![Delingsikon på en liste over favoritdashboards](media/service-share-dashboards/power-bi-share-dash-report-favorites.png)

Du skal bruge en [Power BI Pro-licens](service-free-vs-pro.md), uanset om du deler indhold i eller uden for din organisation. Dine modtagere skal også bruge en Power BI Pro-licens, ellers skal indholdet være i en [Premium-kapacitet](service-premium.md). 

Du kan dele dashboards og rapporter fra de fleste steder i Power BI-tjenesten: Favoritter, Seneste, Delt med mig (hvis ejeren tillader det), Mit arbejdsområde eller andre arbejdsområder. Når du deler et dashboard eller en rapport, kan de personer, du deler med, få det/den vist og interagere med det/den, men ikke redigere det/den. De kan se de samme data som dig i dashboardet eller rapporten, medmindre [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md) anvendes. De kolleger, du deler med, kan også dele med deres kolleger, hvis du giver dem lov til det. Personer uden for organisationen kan også få vist og interagere med dashboardet eller rapporten, men kan ikke dele det/den. 

Du kan også [dele et dashboard fra en vilkårlig Power BI-mobilapp](mobile-share-dashboard-from-the-mobile-apps.md). Du kan dele dashboards fra Power BI-tjenesten og Power BI-mobilapperne, men ikke fra Power BI Desktop.

## <a name="video-share-a-dashboard"></a>Video: Del et dashboard
Se Amanda dele sit dashboard med kollegaer i og uden for sin virksomhed. Følg derefter den trinvise vejledning under videoen for at prøve det selv.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard-or-report"></a>Del et dashboard eller en rapport

1. Vælg **Del** ![Delingsikonet](media/service-share-dashboards/power-bi-share-icon.png) på en liste over dashboards eller rapporter eller i et åbent dashboard eller en åben rapport.

1. Angiv i det øverste felt de komplette mailadresser til enkeltpersoner, distributionsgrupper eller sikkerhedsgrupper. Du kan ikke dele med dynamiske distributionslister. 
   
   Du kan dele med brugere, hvis adresser er uden for din organisation, men du får vist en advarsel.
   
   ![Advarsel om ekstern deling](media/service-share-dashboards/power-bi-share-dialog-warning.png) 
 
3. Tilføj en meddelelse, hvis du vil. Det er valgfrit.
4. Hvis du vil tillade dine kolleger at dele dit indhold med andre, skal du markere **Tillad, at modtagerne må dele dette dashboard/rapport**.
   
   Det kaldes *gendeling* at give andre tilladelse til at dele. Hvis du giver dem tilladelse, kan de dele igen fra Power BI-tjenesten og mobilapperne eller videresende mailinvitationen til andre i din organisation. Invitationen udløber efter én måned. Personer uden for din organisation kan ikke dele igen. Som ejer af indholdet kan du slå videredeling fra eller tilbagekalde videredeling individuelt. Se [Stop deling eller stop andres deling](service-share-dashboards.md#stop-sharing-or-stop-others-from-sharing) nedenfor.

5. Vælg **Del**.
   
   ![Vælg knappen Del](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI sender en mailinvitation til enkeltpersoner, men ikke til grupper, med et link til det delte indhold. Du kan se meddelelse om, at handlingen**blev udført**. 
   
   Når modtagere i din organisation klikker på linket, føjer Power BI dashboardet eller rapporten til siden med listen **Delt med mig**. De kan vælge dit navn for at få vist alt det indhold, du har delt med dem. 
   
   ![Side med listen Delt med mig](media/service-share-dashboards/power-bi-shared-with-me-dashboards-reports.png)
   
   Når modtagere uden for din organisation klikker på linket, kan de se dashboardet eller rapporten, men ikke på den sædvanlige Power BI-portal. Se [Del med personer uden for din organisation](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) nedenfor for at få flere oplysninger.

## <a name="who-has-access-to-a-dashboard-or-report-you-shared"></a>Hvem har adgang til et dashboard eller en rapport, som du har delt?
Du har nogle gange brug for at få vist de personer, du har delt med, og hvem de har videredelt med.

1. Vælg **Del** ![Delingsikon](media/service-share-dashboards/power-bi-share-icon.png) på listen over dashboards og rapporter eller på selve dashboardet eller i selve rapporten. 
2. Vælg **Adgang** i dialogboksen **Del dashboard/rapport**.
   
    ![Dialogboksen Del dashboard, fanen Adgang](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Personer uden for din organisation er anført som **Gæst**.

## <a name="stop-sharing-or-stop-others-from-sharing"></a>Stop deling eller stop andres deling
Det er kun ejeren af dashboardet eller rapporten, der kan slå videredeling til og fra.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Hvis du ikke har sendt invitationen til deling endnu
* Fjern markeringen i afkrydsningsfeltet **Tillad, at modtagerne må dele dit dashboard/din rapport** nederst i invitationen, før du sender den.

### <a name="if-youve-already-shared-the-dashboard-or-report"></a>Hvis du allerede har delt dashboardet eller rapporten
1. Vælg **Del** ![Delingsikon](media/service-share-dashboards/power-bi-share-icon.png) på listen over dashboards og rapporter eller på selve dashboardet eller i selve rapporten. 
2. Vælg **Adgang** i dialogboksen **Del dashboard/rapport**.
   
    ![Dialogboksen Del dashboard, fanen Adgang](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Vælg ellipsen (**...** ) ud for **Læs og del igen**, og vælg:
   
   ![Ellipse for læsning og deling igen](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Læs** for at forhindre vedkommende i at dele med andre.
   * **Fjern adgang** for at forhindre vedkommende i overhovedet at se det delte indhold.

4. I dialogboksen **Fjern adgang** skal du beslutte, om du også vil fjerne adgangen til relateret indhold, som f.eks. rapporter og datasæt. Hvis du fjerner elementer med et advarselsikon ![Power BI-advarselsikon](media/service-share-dashboards/power-bi-warning-icon.png), er det bedst at fjerne relateret indhold, fordi det ikke kan vises korrekt.

## <a name="share-a-dashboard-or-report-with-people-outside-your-organization"></a>Del et dashboard eller en rapport med personer uden for din organisation
Når du deler med personer uden for din organisation, modtager de en mail med et link til det delte dashboard eller den delte rapport, og de skal logge på Power BI for at få det/den vist. Hvis de ikke har en Power BI Pro-licens, kan de tilmelde sig en, når de klikker på linket.

Når de har logget på, kan de se det delte dashboard eller den delte rapport i et separat browservindue uden den venstre navigationsrude og ikke på deres normale Power BI-portal. De skal bogmærke linket for at få adgang til dashboardet eller rapporten i fremtiden.

De kan ikke redigere indhold i dette dashboard eller rapporten. De kan interagere med diagrammerne og skifte filtre eller udsnit i rapporten, men de kan ikke gemme ændringer.

Det er kun dine direkte modtagere, der kan se det delte dashboard eller den delte rapport. Hvis du f.eks. har sendt mailen til Vicki@contoso.com, kan kun Vicki se dashboardet. Ingen andre kan se dette dashboard, selvom de har linket, og Vicki skal bruge den samme mailadresse til at få adgang til dashboardet. Hun kan heller ikke få adgang til dashboardet, hvis hun tilmelder sig med en anden mailadresse.

Personer uden for din organisation kan slet ikke se nogen data, hvis sikkerhed på rolle- eller rækkeniveau er implementeret på Analysis Services-tabelmodeller i det lokale miljø.

Hvis du sender et link fra en Power BI-mobilapp til personer uden for din organisation, åbnes dashboardet i en browser, når de klikker på linket, og ikke i Power BI-mobilappen.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Ting, du skal være opmærksom på angående deling af dashboards og rapporter:

* Generelt kan se du og dine kolleger se de samme data på dashboardet eller i rapporten. Hvis du derfor har tilladelse til at se flere data, end de har, vil de kunne se alle dine data på dashboardet eller i rapporten. Men hvis [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md) er anvendt på datasættet, der er underliggende for et dashboard eller en rapport, bruges legitimationsoplysningerne for hver person til at afgøre, hvilke data vedkommende kan få adgang til.
* Alle, som du deler dashboardet med, kan se det og interagere med de relaterede rapporter i [Læsevisning](service-reading-view-and-editing-view.md). De kan ikke oprette rapporter eller gemme ændringer af eksisterende rapporter.
* Ingen kan se eller hente datasættet.
* Alle kan manuelt [opdatere dataene](refresh-data.md).
* Hvis du bruger Office 365 til mail, kan du dele med medlemmer af en distributionsgruppe ved at angive den mailadresse, der er knyttet til distributionsgruppen.
* Kollegaer, der har det samme maildomæne som du, og kollegaer, hvis domæner er anderledes, men registreret i den samme lejer, kan dele dashboardet med andre. Lad os for eksempel antage, at domænerne contoso.com og contoso2.com er registreret i den samme lejer. Hvis din mailadresse er konrads@contoso.com, kan både ravali@contoso.com og gustav@contoso2.com dele, så længe du har givet dem tilladelse til at dele.
* Hvis dine kolleger allerede har adgang til et bestemt dashboard eller en bestemt rapport, kan du sende et direkte link ved blot at kopiere URL-adressen, når du er på dashboardet eller i rapporten. Eksempel: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Hvis dine kolleger allerede har adgang til et bestemt dashboard, kan du på samme måde [sende et direkte link til den underliggende rapport](service-share-reports.md). 

## <a name="troubleshoot-sharing"></a>Fejlfinding af deling

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Mine dashboardmodtagere ser et låseikon i et felt eller en meddelelse med "Tilladelse påkrævet"

De personer, du deler med, kan få vist et låst felt i et dashboard eller meddelelsen "Tilladelse påkrævet", når de forsøger at få vist en rapport.

![Låst felt i Power Bi](media/service-share-dashboards/power-bi-locked_tile_small.png)

Her er du nødt til at give brugerne tilladelse til at tilgå det underliggende datasæt. Sådan gør du:

1. Gå til fanen **Datasæt** på listen over indhold.

1. Vælg ellipsen (**...** ) ud for datasættet > **Administrer tilladelser**.

    ![Administrer tilladelser](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. Vælg **Tilføj bruger**.

    ![Vælg Tilføj bruger](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Angiv de komplette mailadresser til enkeltpersoner, distributionsgrupper eller sikkerhedsgrupper. Du kan ikke dele med dynamiske distributionslister.

    ![Tilføj mailadresser](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. Vælg **Tilføj**

### <a name="i-cant-share-a-dashboard-or-report"></a>Jeg kan ikke dele et dashboard eller en rapport

Hvis du vil dele et dashboard eller en rapport, skal du have tilladelse til at dele det underliggende indhold igen – alle relaterede rapporter og datasæt. Hvis du ser en meddelelse, hvor der står, du ikke må dele, skal du bede rapportens forfatter om at give dig tilladelse til at dele rapporterne og datasættene igen.


## <a name="next-steps"></a>Næste trin
* Har du feedback? Kom med dine forslag på [webstedet for Power BI-community'et](https://community.powerbi.com/).
* [Hvordan kan jeg samarbejde på og dele dashboards og rapporter?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Del en filtreret Power BI-rapport](service-share-reports.md)
* Har du spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/).

