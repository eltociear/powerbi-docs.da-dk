---
title: Opret klassiske arbejdsområder i Power BI
description: Få mere at vide, hvordan du kan oprette arbejdsområder, samlinger af dashboards, rapporter og sideinddelte rapporter, der er udviklet til at levere vigtige metrikker til organisationen.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: dcf9b8befabfec98fcae154e6276f8e698b3ddc2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61150829"
---
# <a name="create-classic-workspaces-in-power-bi"></a>Opret klassiske arbejdsområder i Power BI

I Power BI, kan du oprette *arbejdsområder*, placerer for at samarbejde med kolleger til at oprette og afgrænse samlinger af dashboards, rapporter og sideinddelte rapporter. Så du kan bundte samlingen sammen i *apps* , som du kan distribuere til hele organisationen eller til bestemte personer eller grupper. 

**Vidste du det?** Powerbi tilbyder en ny arbejdsområde, som nu er standard. Læs [organisere arbejde i nye arbejdsområder](service-new-workspaces.md) for at få oplysninger om de nye arbejdsområder. 

Når du opretter et klassisk arbejdsområde, opretter du et underliggende, tilknyttede Office 365-gruppe. Al administration af arbejdsområder foregår i Office 365. Du kan føje kollegaer til disse arbejdsområder som medlemmer eller administratorer. I arbejdsområdet kan alle samarbejde i dashboards, rapporter og andre artikler, som du vil publicere til en større målgruppe. Alle de brugere, du føjer til et apparbejdsområde, skal have en Power BI Pro-licens. 

## <a name="video-apps-and-app-workspaces"></a>Video: Apps og apparbejdsområder
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-classic-app-workspace-based-on-an-office-365-group"></a>Opret en klassisk app-arbejdsområde, der er baseret på en Office 365-gruppe

Når du opretter et apparbejdsområde, oprettes det ud fra en Office 365-gruppe.

[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Bemærk, at når du opretter arbejdsområdet første gang, skal du muligvis vente omkring en time, før det er overført til Office 365. 

### <a name="add-an-image-to-your-office-365-app-workspace-optional"></a>Føj et billede til dit Office 365-apparbejdsområde (valgfrit)
Power BI opretter som standard en lille farvet cirkel for din app med appens forbogstaver. Det kan også være, at du vil tilpasse den med et billede. Hvis du vil tilføje et billede, skal du have en Exchange Online-licens.

1. Vælg **Arbejdsområder**, vælg de tre prikker (...) ud for navnet på arbejdsområdet og derefter **Medlemmer**. 
   
     ![Vælg medlemmer af arbejdsområdet](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    Outlook til Office 365-kontoen til arbejdsområdet åbnes i et nyt browservindue.
2. Når du peger på den farvede cirkel øverst til venstre, bliver den til et blyantsikon. Vælg det.
   
     ![Office 365-blyantsikon](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Vælg blyantsikonet igen, og find det billede, du vil bruge.
   
     ![Vælg blyanten igen](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)

     Billeder kan være .png, .jpg eller .bmp filer. Deres filstørrelsen kan være stor, op til 3 MB. 

4. Vælg **Gem**.
   
     ![Vælg Gem](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    Billedet erstatter den farvede cirkel i Office 365 Outlook-vinduet. 
   
     ![Tilpasset billede](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    Efter nogle få minutter vises det også i appen i Power BI.
   
     ![Tilpasset billede](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="add-content-to-your-app-workspace"></a>Føj indhold til dit apparbejdsområde

Når du har oprettet et apparbejdsområde, skal du føje indhold til det. Det foregår på samme måde, som når du føjer indhold til Mit arbejdsområde, bortset fra at andre personer i arbejdsområdet også kan se det og arbejde med det. Den store forskel er, at når du er færdig, kan du publicere indholdet som en app. Når du får vist indhold på indholdslisten for et apparbejdsområde, vises navnet på apparbejdsområdet som ejeren.

### <a name="connect-to-third-party-services-in-app-workspaces"></a>Opret forbindelse til tredjepartstjenester i apparbejdsområder

Apps leveres til alle de tredjepartstjenester, som Power BI understøtter, hvilket gør det nemt for dig at hente data fra de tjenester, du bruger, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics. Du kan publicere organisationsapps for at give dine brugere de data, de har brug for.

I de aktuelle arbejdsområder kan du også oprette forbindelse via organisationsindholdspakker og indholdspakker fra tredjepart, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics. Du kan overveje at overføre organisationsindholdspakker til apps.

## <a name="distribute-an-app"></a>Distribuer en app

Hvis du vil distribuere officielle indhold til en stor målgruppe i din organisation, kan du udgive en app fra dit arbejdsområde.  Når indholdet er klar, skal du vælge, hvilke dashboards og rapporter, du vil publicere og derefter publicere den som en *app*. Du kan oprette en app fra hvert arbejdsområde.

Listen over Apps på navigationslinjen til venstre viser alle de apps, du har installeret. Dine kollegaer kan hente dine apps på flere måder. 
- De kan finde og installere din app fra Microsoft AppSource
- Du kan sende dem et direkte link. 
- Du kan automatisk installere dem i dine kollegaers Power BI-konti, hvis Power BI-administratoren giver dig tilladelse til det. 

Brugere se opdateret appindhold automatisk, når du har udgivet en opdatering fra dit arbejdsområde. Du kan styre, hvor ofte dataene opdateres ved at angive tidsplanen for opdatering i de datasæt, der bruges af appindhold i dit arbejdsområde. Se [Publicer en app ud fra de nye arbejdsområder i Power BI](service-create-distribute-apps.md) for at få oplysninger.

## <a name="power-bi-classic-apps-faq"></a>Power BI-klassiske apps ofte stillede spørgsmål

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Hvordan adskiller apps sig fra organisationsindholdspakker?
Apps er en udviklet form af organisationsindholdspakker. Hvis du allerede har organisationsindholdspakker, vil de fortsætte med at fungere side om side med apps. Der er et par større forskelle mellem apps og indholdspakker. 

* Når forretningsbrugere installerer en indholdspakke, mister den sin grupperede identitet: Den er bare en liste over dashboards og rapporter blandet med andre dashboards og rapporter. Apps bevarer på den anden side deres gruppering og identitet, også efter installationen. Denne gruppering gør det nemt for forretningsbrugere at fortsætte med at navigere til dem hen over tid.
* Du kan oprette flere indholdspakker fra et vilkårligt arbejdsområde, men en app har en en til en-relation til dens arbejdsområde. 
* Vi vil over tid fraråde organisationsindholdspakker, og vi anbefaler derfor, at du begynder at oprette apps fra nu af.  
* Med den nye prøveversion af arbejdsområdeoplevelsen tager vi det første skridt mod udfasning af organisationsindholdspakker. Du kan ikke forbruge eller oprette dem i arbejdsområder i prøveversion.

Se [Sådan adskiller de nye apparbejdsområder sig fra eksisterende apparbejdsområder](service-new-workspaces.md#how-are-the-new-workspaces-different-from-current-workspaces) for at sammenligne de to. 

## <a name="next-steps"></a>Næste trin
* [Installér og brug apps i Power BI](service-create-distribute-apps.md)
- [Opret de nye arbejdsområder (prøveversion)](service-create-the-new-workspaces.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
