---
title: Opret nye arbejdsområder – Power BI
description: Få mere at vide, hvordan du opretter de nye arbejdsområder, samlinger af dashboards, rapporter og sideinddelte rapporter, der er udviklet til at levere vigtige metrikker til organisationen.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d0c0781ea5d3864f1cf3627cd42d53cca632102d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61141878"
---
# <a name="create-the-new-workspaces-in-power-bi"></a>Opret nye arbejdsområder i Power BI

Powerbi introducerer en ny oplevelse i arbejdsområdet. Arbejdsområder er stadig sted, hvor du samarbejder med kolleger til at oprette samlinger af dashboards, rapporter og sideinddelte rapporter. Så du kan bundte denne samling til en *app* og distribuere den til hele organisationen eller til bestemte personer eller grupper. 

Her er, hvad der er forskellige. I de nye arbejdsområder kan du:

- Tildele arbejdsområderoller til brugergrupper: sikkerhedsgrupper, distributionslister, Office 365-grupper og enkeltpersoner.
- Oprette et arbejdsområde i Power BI uden at oprette en Office 365-gruppe.
- Bruge mere detaljerede arbejdsområderoller til administration af mere fleksible tilladelser i et arbejdsområde.

> [!NOTE]
> Hvis du vil gennemtvinge sikkerhed rækkeniveau (RLS) til Power BI Pro-brugere gennemsyn af indhold i et arbejdsområde, skal du fortsætte med at bruge [klassiske arbejdsområder](service-create-workspaces.md). Vælg den **medlemmer kan få vist Power BI-indhold** indstilling. Du kan også udgive en app i Power BI til disse brugere, eller brug deling for at distribuere indhold. Kommende Fremviser rollen kan dette scenarie i fremtiden i nye arbejdsområde oplevelse arbejdsområder.

Se flere baggrund, for den [nye arbejdsområder](service-new-workspaces.md) artikel.

## <a name="create-one-of-the-new-app-workspaces"></a>Opret et af de nye apparbejdsområder

1. Start med at oprette apparbejdsområdet. Vælg **Arbejdsområder** > **Opret apparbejdsområde**.
   
     ![Opret apparbejdsområde](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. Du opretter automatisk en opgraderet arbejdsområdet, medmindre du vælger at **vende tilbage til klassisk**.
   
     ![Ny oplevelse af arbejdsområde](media/service-create-the-new-workspaces/power-bi-new-workspace.png)
     
     Hvis du vælger **vende tilbage til klassisk**, du opretter et arbejdsområde, der er baseret på en Office 365-gruppe. Brug denne indstilling, hvis du har brug for den **medlemmer kan få vist Power BI-indhold** mulighed for at gennemtvinge sikkerhed på rækkeniveau (RLS) for medlemmer af arbejdsområdet.

2. Giv arbejdsområdet et navn. Hvis navnet er ikke tilgængelig, kan du redigere det og angive et entydigt navn.
   
     Appen til arbejdsområdet har samme navn og ikon som arbejdsområde.
   
1. Her er nogle valgfrie elementer, du kan angive for dit arbejdsområde:

    Upload en **arbejdsområde billede**. Filer, der kan være .png eller .jpg-format. Filstørrelse, der skal være mindre end 45 KB.
    
    [Tilføj en **kontaktliste**](#workspace-contact-list). Administratorer for arbejdsområde er kontakterne, som standard. 
    
    [Angiv en **arbejdsområde OneDrive** ](#workspace-onedrive) ved at skrive navnet på en eksisterende Office 365-gruppe, ikke URL-adressen. Dette arbejdsområde kan nu bruge denne Office 365-gruppe-fil-lagerplacering. 

    ![Angiv en placering i OneDrive](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

    Til at tildele arbejdsområdet til en **dedikerede kapacitet**under den **Premium** fanen Vælg **dedikerede kapacitet**.
     
    ![Dedikeret kapacitet](media/service-create-the-new-workspaces/power-bi-workspace-premium.png)

1. Vælg **Gem**.

    Power BI opretter arbejdsområdet og åbner det. Det vises på listen over de arbejdsområder, du er medlem af. 

## <a name="workspace-contact-list"></a>Liste over kontakter arbejdsområde

Den nye kontaktliste arbejdsområde kan du angive, hvilke brugere modtage besked om problemer, der opstår i arbejdsområdet. Som standard angivet en bruger eller gruppe, som et arbejdsområde administrator får besked, men du kan tilpasse listen. Brugere eller grupper, der er angivet på listen over kontaktpersoner vises i brugergrænsefladen (UI) til at hjælpe brugerne får hjælp, der er relateret til arbejdsområdet.

1. Få adgang til den nye **kontaktliste** indstilling på to måder:

    I den **opretter et arbejdsområde** ruden, når du opretter den.

    I navigationsruden til venstre, skal du vælge pilen ud for **arbejdsområder**, Vælg ellipsen (...) ud for Arbejdsområdenavnet på > **indstillinger for arbejdsområde**. Den **indstillinger** ruden åbnes.

    ![Indstillinger for arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-settings.png)

2. Under **Avanceret** > **kontaktliste**, acceptere standarden, **administratorer for arbejdsområde**, eller tilføje din egen liste over **specifikke brugere eller grupper**. 
3. Vælg **Gem**.

## <a name="workspace-onedrive"></a>Arbejdsområde OneDrive

Funktionen arbejdsområde OneDrive kan du konfigurere en Office 365-gruppe, hvis SharePoint-dokumentbibliotek file storage er tilgængelig for arbejdsområdebrugere. Du oprette først gruppen uden for Power BI. 

Tilladelser for brugere eller grupper, der er konfigureret til at have adgang til arbejdsområde med Office 365 gruppemedlemskabet synkroniserer ikke Powerbi. Den bedste fremgangsmåde er giver den samme Office 365-gruppe, hvis du konfigurerer i denne indstilling for Office 365-gruppe, fillager [adgang til arbejdsområdet](#give-access-to-your-workspace). Derefter administrere adgang til arbejdsområde ved at administrere medlemskabet af gruppen Office 365. 

1. Få adgang til den nye **arbejdsområde OneDrive** indstilling på to måder:

    I den **opretter et arbejdsområde** ruden, når du opretter den.

    I navigationsruden til venstre, skal du vælge pilen ud for **arbejdsområder**, Vælg ellipsen (...) ud for Arbejdsområdenavnet på > **indstillinger for arbejdsområde**. Den **indstillinger** ruden åbnes.

    ![Indstillinger for arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-settings.png)

2. Under **Avanceret** > **arbejdsområde OneDrive**, Skriv navnet på den Office 365-gruppe, du oprettede tidligere. Powerbi statuskontrollen automatisk OneDrive for gruppen.

    ![Angiv en placering i OneDrive](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

3. Vælg **Gem**.

### <a name="access-the-workspace-onedrive-location"></a>Få adgang til arbejdsområdet OneDrive placering

Når du har konfigureret OneDrive-placeringen, kan du hente den fra et par forskellige steder i arbejdsområdet:

- Vælg **arbejdsområder** > *navn på arbejdsområde* > ellipsen ( **...** ) menu > **filer**. 

    ![Placering af arbejdsområde](media/service-new-workspaces/power-bi-new-workspace-files.png)

- Vælg ellipsen ( **...** ) i menuen i øverste højre hjørne af arbejdsområdet > **filer**.

    ![Placering af arbejdsområde](media/service-new-workspaces/power-bi-new-workspace-files-2.png)
    
- I den **Hent Data** > **filer** oplevelse. Den **OneDrive – Business** post er din egen OneDrive for Business. Den anden OneDrive er den computer, du har tilføjet.

    ![Placering af arbejdsområde - Hent data](media/service-new-workspaces/power-bi-new-workspace-get-data-onedrive.png)

## <a name="add-content-to-your-app-workspace"></a>Føj indhold til dit apparbejdsområde

Når du har oprettet et nyt arbejdsområde oplevelse arbejdsområde, er det tid til at føje indhold til den. Tilføjelse af indhold er tilsvarende i de nye og klassiske arbejdsområder. Brug knappen Opret eller bruge Hent Data til at føje indhold til dit arbejdsområde.

1. I den **Velkommen** skærmen til din nye arbejdsområde, kan du føje indhold. 

    ![Velkomstskærm for nyt arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. Vælg f.eks. **Eksempler** > **Eksempel på kunderentabilitet**.

> [!NOTE]
> I de nye arbejdsområder bruge du ikke organisationsindholdspakker eller tredjeparts-indholdspakker. Apps er tilgængelige for alle programmer fra tredjepart indholdspakker du tidligere har brugt. Brug klassiske arbejdsområder, hvis du vil fortsætte med at bruge indholdspakker. Indholdspakker frarådes, så det er bedste praksis at bruge apps i stedet.

Når du får vist indhold på indholdslisten for et apparbejdsområde, vises navnet på apparbejdsområdet som ejeren.

### <a name="connecting-to-third-party-services-in-new-workspaces"></a>Opretter forbindelse til tredjepartstjenester i nye arbejdsområder

I den nye arbejdsområdeoplevelse laver vi en ændring for at fokusere på *apps*. Apps til tredjepartstjenester gør det nemt for brugerne at hente data fra de tjenester, de bruger, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics.

Du kan ikke oprettes eller forbruge organisationsindholdspakker i den nye oplevelse i arbejdsområdet. Du kan i stedet bruge de apps, der leveres, til at oprette forbindelse til tredjepartstjenester eller bede dine interne teams om at levere apps til en indholdspakke, du bruger i øjeblikket. 

## <a name="give-access-to-your-workspace"></a>Giv adgang til dit arbejdsområde

1. På listen arbejdsområde indhold, da du er administrator du se en ny handling, **adgang**.

    ![Listen over indhold i arbejdsområder](media/service-create-the-new-workspaces/power-bi-workspace-content-list.png)

1. Vælg **Adgang**.

1. Føj sikkerhedsgrupper, distributionslister, Office 365-grupper eller enkeltpersoner til disse arbejdsområder som medlemmer, bidragydere eller administratorer. Se [Roller i de nye arbejdsområder](service-new-workspaces.md#roles-in-the-new-workspaces) for at få en forklaring på de forskellige roller.

    ![Arbejdsområder – tilføj medlemmer, administratorer og bidragydere](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. Vælg **Tilføj** > **Luk**.


## <a name="distribute-an-app"></a>Distribuer en app

Hvis du vil distribuere officielle indhold til en stor målgruppe i din organisation, kan du udgive en app fra dit arbejdsområde.  Når indholdet er klar, skal du vælge, hvilke dashboards og rapporter, du vil publicere og derefter publicere den som en *app*. Du kan oprette en app fra hvert arbejdsområde.

Læs om [udgivelse af en app ud fra de nye arbejdsområder](service-create-distribute-apps.md)

## <a name="next-steps"></a>Næste trin
* Læs om [organisering af arbejdet i den nye oplevelse af arbejdsområder i Power BI](service-new-workspaces.md)
* [Opret klassiske arbejdsområder](service-create-workspaces.md)
* [Publicer en app ud fra de nye arbejdsområder i Power BI](service-create-distribute-apps.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
