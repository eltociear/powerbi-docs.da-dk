---
title: Opret klassiske arbejdsområder i Power BI
description: Få mere at vide om, hvordan du opretter arbejdsområder, samlinger af dashboards, rapporter og sideinddelte rapporter, som er udviklet til at levere vigtige målepunkter for din organisation.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/10/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 3153e63685e21a29687c33e702c4ade55324e05c
ms.sourcegitcommit: 7e845812874b3347bcf87ca642c66bed298b244a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/13/2020
ms.locfileid: "79207706"
---
# <a name="create-classic-workspaces-in-power-bi"></a>Opret klassiske arbejdsområder i Power BI

I Power BI kan du oprette *arbejdsområder*, som er steder, hvor du kan samarbejde med kolleger om at oprette og tilpasse samlinger af dashboards, rapporter og sideinddelte rapporter. Derefter kan du gruppere samlingerne i *apps*, som du kan distribuere til hele organisationen eller til bestemte personer eller grupper. 

**Vidste du det?** Power BI tilbyder en ny arbejdsområdeoplevelse, som nu er standard. Læs [Organiser arbejde i de nye arbejdsområder](service-new-workspaces.md) for at få oplysninger om de nye arbejdsområder. 

Når du opretter et klassisk arbejdsområde, opretter du en underliggende tilknyttet Office 365-gruppe. Al administration af arbejdsområder foregår i Office 365. Du kan føje kollegaer til disse arbejdsområder som medlemmer eller administratorer. I arbejdsområdet kan alle samarbejde i dashboards, rapporter og andre artikler, som du vil publicere til en større målgruppe. Alle de brugere, du føjer til et arbejdsområde, skal have en Power BI Pro-licens. 

## <a name="video-apps-and-workspaces"></a>Video: Apps og arbejdsområder
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-classic-workspace-based-on-an-office-365-group"></a>Opret et klassisk arbejdsområde på baggrund af en Office 365-gruppe

Når du opretter et arbejdsområde, oprettes det ud fra en Office 365-gruppe.

[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Bemærk, at når du opretter arbejdsområdet første gang, skal du muligvis vente omkring en time, før det er overført til Office 365. 

### <a name="add-an-image-to-your-office-365-workspace-optional"></a>Føj et billede til dit Office 365-arbejdsområde (valgfrit)
Power BI opretter som standard en lille farvet cirkel for din app med appens forbogstaver. Det kan også være, at du vil tilpasse den med et billede. Hvis du vil tilføje et billede, skal du have en Exchange Online-licens.

1. Vælg **Arbejdsområder**, vælg **Flere indstillinger** (...) ud for navnet på arbejdsområdet og derefter **Medlemmer**. 
   
     ![Vælg medlemmer af arbejdsområdet](media/service-create-workspaces/power-bi-workspace-old-members.png)
   
    Outlook til Office 365-kontoen til arbejdsområdet åbnes i et nyt browservindue.
2. Vælg blyanten **Rediger**.
   
     ![Office 365-blyantsikon](media/service-create-workspaces/power-bi-workspace-old-edit-group.png)
3. Vælg kameraikonet, og find det billede, du vil bruge.
   
     ![Vælg kameraikonet](media/service-create-workspaces/power-bi-workspace-old-camera.png)

     Billeder kan være .png-, .jpg- eller .bmp-filer. Filstørrelsen kan være stor – op til 3 MB. 

4. Vælg **OK** og derefter **Gem**.
   
    Billedet erstatter den farvede cirkel i Office 365 Outlook-vinduet. 
   
     ![Tilpasset billede](media/service-create-workspaces/power-bi-workspace-old-new-image.png)
   
    Efter nogle få minutter vises det også i appen i Power BI.

## <a name="add-content-to-your-workspace"></a>Føj indhold til dit arbejdsområde

Når du har oprettet et arbejdsområde, skal du føje indhold til det. Det foregår på samme måde, som når du føjer indhold til Mit arbejdsområde, bortset fra at andre personer i arbejdsområdet også kan se det og arbejde med det. Den store forskel er, at når du er færdig, kan du publicere indholdet som en app. Når du får vist indhold på indholdslisten for et arbejdsområde, vises navnet på arbejdsområdet som ejeren.

### <a name="connect-to-third-party-services-in-workspaces"></a>Opret forbindelse til tredjepartstjenester i arbejdsområder

Apps leveres til alle de tredjepartstjenester, som Power BI understøtter, hvilket gør det nemt for dig at hente data fra de tjenester, du bruger, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics. Du kan publicere organisationsapps for at give dine brugere de data, de har brug for.

I de aktuelle arbejdsområder kan du også oprette forbindelse via organisationsindholdspakker og indholdspakker fra tredjepart, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics. Du kan overveje at overføre organisationsindholdspakker til apps.

## <a name="distribute-an-app"></a>Distribuer en app

Hvis du vil distribuere officielt indhold til en stor målgruppe i din organisation, kan du publicere en app fra dit arbejdsområde.  Når indholdet er klar, skal du vælge, hvilke dashboards og rapporter du vil publicere, og derefter skal du publicere dem som en *app*. Du kan oprette en app fra hvert arbejdsområde.

På listen Apps i navigationsruden kan du se alle de apps, du har installeret. Dine kollegaer kan hente dine apps på flere måder. 
- De kan finde og installere din app fra Microsoft AppSource
- Du kan sende dem et direkte link. 
- Du kan automatisk installere dem i dine kollegaers Power BI-konti, hvis Power BI-administratoren giver dig tilladelse til det. 

Brugere ser opdateret appindhold automatisk, efter du har publiceret en opdatering fra dit arbejdsområde. Du kan styre, hvor ofte dataene opdateres ved at angive opdateringstidsplanen i de datasæt, der bruges af appindholdet i dit arbejdsområde. Du kan finde flere oplysninger i [Publicer en app fra de nye arbejdsområder i Power BI](service-create-distribute-apps.md).

## <a name="power-bi-classic-apps-faq"></a>Ofte stillede spørgsmål om klassiske apps i Power BI

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Hvordan adskiller apps sig fra organisationsindholdspakker?
Apps er en udviklet form af organisationsindholdspakker. Hvis du allerede har organisationsindholdspakker, vil de fortsætte med at fungere side om side med apps. Der er et par større forskelle mellem apps og indholdspakker. 

* Når forretningsbrugere installerer en indholdspakke, mister den sin grupperede identitet: Den er bare en liste over dashboards og rapporter blandet med andre dashboards og rapporter. Apps bevarer på den anden side deres gruppering og identitet, også efter installationen. Denne gruppering gør det nemt for forretningsbrugere at fortsætte med at navigere til dem hen over tid.
* Du kan oprette flere indholdspakker fra et vilkårligt arbejdsområde, men en app har en en til en-relation til dens arbejdsområde. 
* Vi vil over tid fraråde organisationsindholdspakker, og vi anbefaler derfor, at du begynder at oprette apps fra nu af.  
* Med den nye arbejdsområdeoplevelse tager vi det første skridt mod udfasning af organisationsindholdspakker. Du kan ikke forbruge eller oprette dem i de nye arbejdsområder.

Se [Sådan adskiller de nye arbejdsområder sig fra eksisterende arbejdsområder](service-new-workspaces.md#how-the-new-workspaces-are-different) for at sammenligne de to. 

## <a name="next-steps"></a>Næste trin
* [Installér og brug apps i Power BI](service-create-distribute-apps.md)
- [Opret de nye arbejdsområder](service-create-the-new-workspaces.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
