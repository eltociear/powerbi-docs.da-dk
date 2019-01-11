---
title: Opret de nye arbejdsområder (prøveversion) – Power BI
description: Få mere at vide om, hvordan du opretter de nye arbejdsområder, der er samlinger af dashboards og rapporter, som er udviklet til at levere vigtige målepunkter for din organisation.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/19/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: a93c676775fe6e826ea83cfad91498b7fe3e2103
ms.sourcegitcommit: 5206651c12f2b91a368f509470b46f3f4c5641e6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/02/2019
ms.locfileid: "53983594"
---
# <a name="create-the-new-workspaces-preview-in-power-bi"></a>Opret de nye arbejdsområder (prøveversion) i Power BI

Power BI introducerer en ny arbejdsområdeoplevelse som en prøveversion. Arbejdsområder er stadig det sted, hvor du skal samarbejde med kollegaer. Her kan du oprette samlinger af dashboards og rapporter, som du kan bundte i *apps* og distribuere til hele organisationen eller til bestemte personer eller grupper. 

![Prøveversion af nye arbejdsområder i Power BI](media/service-create-the-new-workspaces/power-bi-new-workspaces-preview.png)

Med prøveversionen af de nye arbejdsområder kan du nu:

- Tildele arbejdsområderoller til brugergrupper: sikkerhedsgrupper, distributionslister, Office 365-grupper og enkeltpersoner.
- Oprette et arbejdsområde i Power BI uden at oprette en Office 365-gruppe.
- Bruge mere detaljerede arbejdsområderoller til administration af mere fleksible tilladelser i et arbejdsområde.

Du kan få mere baggrundsviden i artiklen [Nye arbejdsområder (prøveversion)](service-new-workspaces.md).

## <a name="create-one-of-the-new-app-workspaces"></a>Opret et af de nye apparbejdsområder

1. Start med at oprette apparbejdsområdet. Vælg **Arbejdsområder** > **Opret apparbejdsområde**.
   
     ![Opret apparbejdsområde](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. I **eksempelvisningen af forbedrede arbejdsområder** skal du vælge **Prøv nu**.
   
     ![Eksempelvisning af forbedrede arbejdsområder](media/service-create-the-new-workspaces/power-bi-preview-improved-workspaces.png)

2. Giv arbejdsområdet et navn. Hvis navnet ikke er tilgængeligt, skal du redigere det, så der angives et entydigt id.
   
     Appen har samme navn som arbejdsområdet.
   
1. Tilføj eventuelt et billede. Filstørrelsen skal være mindre end 45 KB.
 
    ![Navngiv arbejdsområdet, og tilføj et billede](media/service-create-the-new-workspaces/power-bi-name-workspace.png)

1. Vælg **Gem**.

    Her på **velkomst**skærmen for dit nye arbejdsområde kan du tilføje data. 

    ![Velkomstskærm for nyt arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. Vælg f.eks. **Eksempler** > **Eksempel på kunderentabilitet**.

    På listen over indhold på arbejdsområdet kan du nu se **Ny eksempelvisning for arbejdsområder**. Da du er administrator, kan du også se den nye handling **Adgang**.

    ![Liste over indhold i eksempelvisning af arbejdsområder](media/service-create-the-new-workspaces/power-bi-workspaces-preview-content-list.png)

1. Vælg **Adgang**.

1. Føj sikkerhedsgrupper, distributionslister, Office 365-grupper eller enkeltpersoner til disse arbejdsområder som medlemmer, bidragydere eller administratorer. Se [Roller i de nye arbejdsområder](#roles-in-the-new-workspaces) senere i denne artikel for at få en forklaring på de forskellige roller.

    ![Arbejdsområder – tilføj medlemmer, administratorer og bidragydere](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. Vælg **Tilføj** > **Luk**.

1. Power BI opretter arbejdsområdet og åbner det. Det vises på listen over de arbejdsområder, du er medlem af. Da du er administrator, kan du vælge ellipsen (…) for at gå tilbage og ændre indstillinger for arbejdsområdet, tilføje nye medlemmer eller ændre deres tilladelser.

     ![Rediger indstillinger og adgang til et arbejdsområde](media/service-create-the-new-workspaces/power-bi-edit-workspace.png)

## <a name="add-content-to-your-app-workspace"></a>Føj indhold til dit apparbejdsområde

Når du har oprettet et apparbejdsområde i den nye stil, skal du føje indhold til det. Du tilføjer indhold på samme måde i de nye og gamle arbejdsområder med en enkelt undtagelse. Fra begge apparbejdsområder kan du uploade eller oprette forbindelse til filer på samme måde som i Mit arbejdsområde. I de nye arbejdsområder kan du ikke oprette forbindelse til organisationsindholdspakker eller indholdspakker fra tredjepart, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics. I de aktuelle arbejdsområder kan du oprette forbindelse til indholdspakker.

Når du får vist indhold på indholdslisten for et apparbejdsområde, vises navnet på apparbejdsområdet som ejeren.

### <a name="connecting-to-third-party-services-in-new-workspaces-preview"></a>Opret forbindelse til tredjepartstjenester i nye arbejdsområder (prøveversion)

I den nye arbejdsområdeoplevelse laver vi en ændring for at fokusere på *apps*. Apps til tredjepartstjenester gør det nemt for brugerne at hente data fra de tjenester, de bruger, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics.
Organisationsapps giver dine brugere de interne data, de har brug for. Vi har planer om at føje funktioner til organisationsapps, så brugere kan tilpasse det indhold, som de finder i appsene. Denne funktion fjerner behovet for indholdspakker. 

Med prøveversionen af nye arbejdsområder kan du ikke oprette eller forbruge organisationsindholdspakker. Du kan i stedet bruge de apps, der leveres, til at oprette forbindelse til tredjepartstjenester eller bede dine interne teams om at levere apps til en indholdspakke, du bruger i øjeblikket. 

## <a name="distribute-an-app"></a>Distribuer en app

Når indholdet er klar, skal du vælge, hvilke dashboards og rapporter du vil publicere, og derefter skal du publicere det som en *app*. Du kan oprette en app fra hvert arbejdsområde. Dine kollegaer kan hente dine apps på flere måder. Du kan automatisk installere dem i dine kollegaers Power BI-konti, hvis Power BI-administratoren giver dig tilladelse til det. Ellers kan de søge efter og installere dine apps fra Microsoft AppSource, eller du kan sende dem et direkte link. De får automatisk opdateringer, og du kan styre, hvor ofte dataene opdateres. Se [Publicer apps med dashboards og rapporter i Power BI](service-create-distribute-apps.md) for at få flere oplysninger.

## <a name="convert-old-app-workspaces-to-new-app-workspaces"></a>Konvertér gamle apparbejdsområder til nye apparbejdsområder

I prøveperioden kan du ikke automatisk konvertere dine gamle apparbejdsområder til nye. Du kan dog oprette et nyt apparbejdsområde og publicere dit indhold på den nye placering. 

Når de nye arbejdsområder er offentligt tilgængelige, kan du vælge at overføre de gamle automatisk. På et tidspunkt efter den offentlige tilgængelighed er du nødt til at overføre dem.

## <a name="next-steps"></a>Næste trin
* Læs mere om at [organisere arbejde i nye arbejdsområder (prøveversion) i Power BI](service-new-workspaces.md)
* [Opret de aktuelle arbejdsområder](service-create-workspaces.md)
* [Installér og brug apps i Power BI](service-create-distribute-apps.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
