---
title: 'Selvstudium: Power BI-integration i Microsoft Flow'
description: "Få mere at vide om, hvordan du opretter Flows udløst af databeskeder i Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: YhmNstC39Mw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: efab2e6be1d376a0da70c13bb66144ba34afa58c
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/17/2017
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow og Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) er en SaaS til automatisering af arbejdsprocesser på tværs af det stigende antal programmer og tjenester, erhvervsbrugere er afhængige af. Med Flow kan du automatisere opgaver ved at integrere dine foretrukne apps og tjenester (herunder Power BI) for at få meddelelser, synkronisere filer, indsamle data og meget mere. Gentagne opgaver bliver nemme med automatisering af arbejdsprocessen.

[Kom i gang med at bruge Flow nu.](https://flow.microsoft.com/documentation/getting-started)

Se, hvordan Sirui opretter et Flow, der sender en detaljeret mail til kollegaer, når der udløses en besked i Power BI. Følg derefter en trinvis vejledning under videoen for at prøve det selv.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Opret et flow, der udløses af databeskeder i Power BI
Denne vejledning viser, hvordan du opretter to forskellige flows; et fra en skabelon og et fra bunden. Følg med ved at [oprette en databesked i Power BI](service-set-data-alerts.md) og [tilmelde dig Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup) (det er gratis!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Opret et flow, der bruger Power BI – fra en skabelon
I denne opgave skal vi bruge en skabelon til at oprette et enkelt flow, der udløses af en databesked i Power BI (meddelelse).

1. Log på Microsoft Flow (flow.microsoft.com).
2. Vælg **Mine flow**.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Vælg **Opret fra skabelon**.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Brug søgefeltet til at finde Power BI-skabeloner, og vælg **Send en meddelelse til en Slack-kanal, når en Power BI-databesked udløses**.
   
    ![](media/service-flow-integration/power-bi-template2.png)
5. Vælg **Brug denne skabelon**.
   
   ![](media/service-flow-integration/power-bi-use-template.png)
6. Hvis du bliver spurgt, skal du oprette forbindelse til Slack og Power BI ved at vælge **Log på** og derefter følge anvisningerne. En grøn markering fortæller dig, om du er logget på.  Når du har bekræftet dine tilslutninger, skal du vælge **Fortsæt**.
   
   ![](media/service-flow-integration/power-bi-flow-signin.png)

### <a name="build-the-flow"></a>Byg flowet
Denne skabelon indeholder en udløser (Power BI-databesked om nye olympiske medaljer til Irland) og en handling (send en meddelelse til Slack). Når du vælger et felt, viser Flow dynamisk indhold, du kan inkludere.  I dette eksempel inkluderer vi feltværdien og feltets URL-adresse i meddelelsens brødtekst.

![](media/service-flow-integration/power-bi-flow-template.png)

1. Vælg Power BI-databeskeden fra rullemenuen i udløseren. Vælg **Ny medalje til Irland**. Hvis du vil vide mere om, hvordan du opretter en besked, skal du læse [Databeskeder i Power BI](service-set-data-alerts.md).
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Hvis du vil sende data til Slack, skal du indtaste et kanalnavn og en meddelelse (du kan også vælge den standardmeddelelse, Flow opretter). Bemærk, det dynamiske indhold vi har medtaget i meddelelsens tekstfelt.
   
   > [!NOTE]
   > Medtag "@" i starten af dit kanalnavn.  Hvis Slack-kanalen f.eks. har navnet "kanalA", skal du indtaste "@channelA" i Flow.
   > 
   > 
   
   ![](media/service-flow-integration/power-bi-flow-slacker.png)
3. Når du er færdig, skal du vælge **Opret flow** eller **Gem flow**.  Flowet er oprettet og vurderet.  Flow giver dig besked, hvis det finder fejl.
4. Hvis der er fundet fejl, skal du vælge **Rediger flow** for at løse dem, ellers skal du vælge **Udført** for at køre det nye flow.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. Åbn din Slack-konto for at få vist meddelelsen.  
   
   ![](media/service-flow-integration/power-bi-slack-message.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Opret et Flow, der bruger Power BI – fra bunden
I denne opgave skal vi oprette et enkelt flow fra bunden, der udløses af en databesked i Power BI (meddelelse).

1. Log på Microsoft Flow.
2. Vælg **Mine flow** > **Opret fra blank**.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Brug søgefeltet til at finde en Power BI-udløser, og vælg **Udløs et flow med en Power BI-datastyret besked**.

### <a name="build-your-flow"></a>Byg dit flow
1. Vælg navnet på beskeden på rullelisten.  Hvis du vil vide mere om, hvordan du opretter en besked, skal du læse [Databeskeder i Power BI](service-set-data-alerts.md).
   
    ![](media/service-flow-integration/power-bi-totalstores.png)
2. Vælg **Nyt trin** > **Tilføj en handling**.
   
   ![](media/service-flow-integration/power-bi-new-step.png)
3. Søg efter **Outlook**, og vælg **Opret begivenhed**.
   
   ![](media/service-flow-integration/power-bi-create-event.png)
4. Udfyld begivenhedens felter. Når du vælger et felt, viser Flow dynamisk indhold, du kan inkludere.
   
   ![](media/service-flow-integration/power-bi-flow-event.png)
5. Vælg **Opret flow**, når du er færdig.  Flow gemmer og vurderer flowet. Vælg **Udført** for at køre dette flow, hvis der ikke er nogen fejl.  Det nye flow er føjet til din side **Mine flow**.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
6. Når flowet udløses af Power BI-databeskeden, modtager du en Outlook-begivenhedsmeddelelse svarende til denne.
   
    ![](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Næste trin
* [Kom i gang med Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Indstil databeskeder i Power BI-tjenesten](service-set-data-alerts.md)
* [Indstil databeskeder på din iPhone](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Indstil databeskeder i Power BI-mobilappen til Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

