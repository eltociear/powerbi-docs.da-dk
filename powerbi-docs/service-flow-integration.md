---
title: Power BI-integration i Microsoft Flow
description: Få mere at vide om, hvordan du opretter Flows udløst af databeskeder i Power BI.
author: mgblythe
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mblythe
LocalizationGroup: Get started
ms.openlocfilehash: a5b5a34e7cd61ac9d197faa0ef4410cd9558f597
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881851"
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow og Power BI

[Microsoft Flow](https://flow.microsoft.com/documentation/getting-started) er en SaaS til automatisering af arbejdsprocesser på tværs af det stigende antal programmer og tjenester, erhvervsbrugere er afhængige af. Med Flow kan du automatisere opgaver ved at integrere dine foretrukne apps og tjenester (herunder Power BI) for at få meddelelser, synkronisere filer, indsamle data og meget mere. Gentagne opgaver bliver nemme med automatisering af arbejdsprocessen.

[Kom i gang med at bruge Flow nu.](https://flow.microsoft.com/documentation/getting-started)

Se, hvordan Sirui opretter et Flow, der sender en detaljeret mail til kollegaer, når der udløses en besked i Power BI. Følg derefter en trinvis vejledning under videoen for at prøve det selv.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Opret et flow, der udløses af databeskeder i Power BI

### <a name="prerequisites"></a>Forudsætninger
Denne vejledning viser, hvordan du opretter to forskellige flows; et fra en skabelon og et fra bunden. Hvis du vil følge med, [skal du oprette en databesked i Power BI](service-set-data-alerts.md), oprette en gratis Slack-konto og [tilmelde dig Microsoft Flow](https://flow.microsoft.com/#home-signup) (det er gratis!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Opret et flow, der bruger Power BI – fra en skabelon
I denne opgave skal vi bruge en skabelon til at oprette et enkelt flow, der udløses af en databesked i Power BI (meddelelse).

1. Log på Microsoft Flow (flow.microsoft.com).
2. Vælg **Mine flow**.
   
   ![Menulinjen Flow](media/service-flow-integration/power-bi-my-flows.png)
3. Vælg **Opret fra skabelon**.
   
    ![Menulinjen Mine flows](media/service-flow-integration/power-bi-template.png)
4. Brug søgefeltet til at finde Power BI-skabeloner, og vælg **Send en mail til en målgruppe, når en Power BI-databesked udløses > Fortsæt**.
   
    ![søgeresultater](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Byg flowet
Denne skabelon indeholder en udløser (Power BI-databesked om nye olympiske medaljer til Irland) og en handling (send en mail). Når du vælger et felt, viser Flow dynamisk indhold, du kan inkludere.  I dette eksempel inkluderer vi feltværdien og feltets URL-adresse i meddelelsens brødtekst.

![flowskabelon](media/service-flow-integration/power-bi-template1.png)

1. Vælg Power BI-databeskeden fra rullemenuen i udløseren. Vælg **Ny medalje til Irland**. Hvis du vil vide mere om, hvordan du opretter en besked, skal du læse [Databeskeder i Power BI](service-set-data-alerts.md).
   
   ![rulleliste for vigtig besked](media/service-flow-integration/power-bi-trigger-flow.png)
2. Angiv en eller flere gyldige mailadresser, og vælg derefter **Rediger** (vist nedenfor) eller **Tilføj dynamisk indhold**. 
   
   ![Skærmbilledet Send en mail](media/service-flow-integration/power-bi-flow-email.png)

3. Flow opretter en titel og meddelelse for dig, som du kan beholde eller ændre. Alle de værdier, du angav, da du oprettede beskeden i Power BI, er tilgængelige til brug – du skal bare placere markøren og vælge i det område, der er fremhævet med gråt. 

   ![Skærmbilledet Send en mail](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Hvis du f.eks. har oprettet en beskedtitel i Power BI af typen **Vi har vundet endnu en medalje**, kan du vælge **Beskedtitel** for at føje teksten til emnefeltet i din mail.

    ![opret mailteksten](media/service-flow-integration/power-bi-flow-message.png)

    Du kan også acceptere standardbrødteksten i mailen eller oprette din egen. Ovenstående eksempel indeholder nogle få ændringer af meddelelsen.

1. Når du er færdig, skal du vælge **Opret flow** eller **Gem flow**.  Flowet er oprettet og vurderet.  Flow giver dig besked, hvis det finder fejl.
2. Hvis der er fundet fejl, skal du vælge **Rediger flow** for at løse dem, ellers skal du vælge **Udført** for at køre det nye flow.
   
   ![meddelelse om fuldførelse](media/service-flow-integration/power-bi-flow-running.png)
5. Når databeskeden udløses, sendes der en mail til de angivne adresser.  
   
   ![mail med vigtig besked](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Opret et Flow, der bruger Power BI – fra bunden
I denne opgave skal vi oprette et enkelt flow fra bunden, der udløses af en databesked i Power BI (meddelelse).

1. Log på Microsoft Flow.
2. Vælg **Mine flow** > **Opret fra blank**.
   
   ![Menulinje øverst i Flow](media/service-flow-integration/power-bi-my-flows.png)
3. Brug søgefeltet til at finde en Power BI-udløser, og vælg **Power BI – når en datadrevet besked udløses**.

### <a name="build-your-flow"></a>Byg dit flow
1. Vælg navnet på beskeden på rullelisten.  Hvis du vil vide mere om, hvordan du opretter en besked, skal du læse [Databeskeder i Power BI](service-set-data-alerts.md).
   
    ![vælg navnet på den vigtige besked](media/service-flow-integration/power-bi-totalstores2.png)
2. Vælg **Nyt trin** > **Tilføj en handling**.
   
   ![tilføj et nyt trin](media/service-flow-integration/power-bi-new-step.png)
3. Søg efter **Outlook**, og vælg **Opret begivenhed**.
   
   ![Byg flowet](media/service-flow-integration/power-bi-create-event.png)
4. Udfyld begivenhedens felter. Når du vælger et felt, viser Flow dynamisk indhold, du kan inkludere.
   
   ![fortsæt med at bygge flowet](media/service-flow-integration/power-bi-flow-event.png)
5. Vælg **Opret flow**, når du er færdig.  Flow gemmer og vurderer flowet. Vælg **Udført** for at køre dette flow, hvis der ikke er nogen fejl.  Det nye flow er føjet til din side **Mine flow**.
   
   ![Fuldfør flowet](media/service-flow-integration/power-bi-flow-running.png)
6. Når flowet udløses af Power BI-databeskeden, modtager du en Outlook-begivenhedsmeddelelse svarende til denne.
   
    ![Flowet udløser en Outlook-meddelelse](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Næste trin
* [Kom i gang med Microsoft Flow](https://flow.microsoft.com/documentation/getting-started/)
* [Indstil databeskeder i Power BI-tjenesten](service-set-data-alerts.md)
* [Indstil databeskeder på din iPhone](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* [Indstil databeskeder i Power BI-mobilappen til Windows 10](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

