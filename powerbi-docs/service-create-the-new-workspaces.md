---
title: Opret nye arbejdsområder – Power BI
description: Få mere at vide om, hvordan du opretter nye arbejdsområder, samlinger af dashboards, rapporter og sideinddelte rapporter, der er udviklet til at levere vigtige målepunkter for din organisation.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/10/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5c50ec38da65573e085d9e27b0e31524256ac009
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715539"
---
# <a name="create-the-new-workspaces-in-power-bi"></a>Opret nye arbejdsområder i Power BI

Power BI introducerer en ny arbejdsområdeoplevelse. Arbejdsområder er stadig det sted, hvor du samarbejder med kolleger om at oprette samlinger af dashboards, rapporter og sideinddelte rapporter. Derefter kan du gruppere disse samlinger i en *app*, som du kan distribuere til hele organisationen eller til bestemte personer eller grupper. 

Her er forskellene. I de nye arbejdsområder kan du:

- Tildele arbejdsområderoller til brugergrupper: sikkerhedsgrupper, distributionslister, Office 365-grupper og enkeltpersoner.
- Oprette et arbejdsområde i Power BI uden at oprette en Office 365-gruppe.
- Bruge mere detaljerede arbejdsområderoller til administration af mere fleksible tilladelser i et arbejdsområde.

> [!NOTE]
> Hvis du vil gennemtvinge sikkerhed på rækkeniveau for Power BI Pro-brugere, der gennemser indhold i et arbejdsområde, skal du tildele brugerne læseadgang.

Du kan få mere baggrundsviden i artiklen [nye arbejdsområder](service-new-workspaces.md).

## <a name="create-one-of-the-new-workspaces"></a>Opret et af de nye apparbejdsområder

1. Start med at oprette arbejdsområdet. Vælg **Arbejdsområder** > **Opret arbejdsområde**.
   
     ![Opret arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-create.png)

2. Du opretter automatisk et opgraderet arbejdsområde, medmindre du vælger at **gå tilbage til klassisk**.
   
     ![Ny arbejdsområdeoplevelse](media/service-create-the-new-workspaces/power-bi-new-workspace.png)
     
     Hvis du vælger **Gå tilbage til klassisk**, opretter du et [arbejdsområde, der er baseret på en Office 365-gruppe](service-create-workspaces.md). 

2. Giv arbejdsområdet et navn. Hvis navnet ikke er tilgængeligt, skal du redigere det, så der angives et entydigt navn.
   
     Appen til arbejdsområdet har det samme navn og ikon som arbejdsområdet.
   
1. Her er nogle valgfrie elementer, du kan angive for dit arbejdsområde:

    Upload et **billede til arbejdsområdet**. Filer kan være .png- eller .jpg-format. Filstørrelsen skal være mindre end 45 KB.
    
    [Tilføj en **liste over kontakter**](#workspace-contact-list). Administratorer af arbejdsområder er som standard kontakter. 
    
    [Angiv et **OneDrive-arbejdsområde**](#workspace-onedrive) ved blot at skrive navnet på en eksisterende Office 365-gruppe og ikke URL-adressen. Nu kan dette arbejdsområde bruge lagringsplaceringen for Office 365-gruppens filer. 

    ![Angiv en OneDrive-placering](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

    Hvis du vil tildele arbejdsområdet til en **dedikeret kapacitet**, skal du på fanen **Premium** vælge **Dedikeret kapacitet**.
     
    ![Dedikeret kapacitet](media/service-create-the-new-workspaces/power-bi-workspace-premium.png)

1. Vælg **Gem**.

    Power BI opretter arbejdsområdet og åbner det. Det vises på listen over de arbejdsområder, du er medlem af. 

## <a name="workspace-contact-list"></a>Liste over arbejdsområdekontakter

Med listen over kontakter i det nye arbejdsområde kan du angive, hvilke brugere der modtager meddelelser om problemer, der forekommer i arbejdsområdet. Som standard får alle brugere eller grupper, der er angivet som arbejdsområdeadministrator besked, men du kan tilpasse listen. Brugere eller grupper, der er angivet på listen over kontaktpersoner, vises i brugergrænsefladen for at hjælpe brugerne med at få hjælp i forbindelse med arbejdsområdet.

1. Få adgang til den nye indstilling **Liste over kontakter** på en af to måder:

    I ruden **Opret et arbejdsområde**, når du opretter det første gang.

    I navigationsruden til venstre skal du vælge pilen ud for **Arbejdsområder** og vælge ellipsen (...) ud for navnet på arbejdsområdet > **Indstillinger for arbejdsområde**. Ruden **Indstillinger** åbnes.

    ![Indstillinger for arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-new-settings.png)

2. Under **Avanceret** > **Liste over kontakter** skal du acceptere standarden, **Administratorer af arbejdsområde** eller tilføje din egen liste over **Specifikke brugere eller grupper**. 
3. Vælg **Gem**.

## <a name="workspace-onedrive"></a>Arbejdsområde for OneDrive

Funktionen Arbejdsområde for OneDrive giver dig mulighed for at konfigurere en Office 365-gruppe, hvis SharePoint-dokumentbiblioteks fillagring er tilgængelig for arbejdsområdebrugere. Du opretter gruppen uden for Power BI først. 

Power BI synkroniserer ikke tilladelser for brugere eller grupper, der er konfigureret til at have adgang til arbejdsområdet med medlemskabet af Office 365-gruppen. Bedste praksis er at give den samme Office 365-gruppe, hvis fillager du konfigurerer i denne indstilling for Office 365-gruppen, [adgang til arbejdsområdet](#give-access-to-your-workspace). Administrer derefter adgangen til arbejdsområdet ved at administrere medlemskabet af Office 365-gruppen. 

1. Få adgang til den nye indstilling for **OneDrive-arbejdsområdet** på en af to måder:

    I ruden **Opret et arbejdsområde**, når du opretter det første gang.

    I navigationsruden til venstre skal du vælge pilen ud for **Arbejdsområder** og vælge ellipsen (...) ud for navnet på arbejdsområdet > **Indstillinger for arbejdsområde**. Ruden **Indstillinger** åbnes.

    ![Indstillinger for arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-new-settings.png)

2. Under **Avanceret** > **OneDrive-arbejdsområde** skal du skrive navnet på den Office 365-gruppe, du oprettede tidligere. Power BI registrerer automatisk OneDrive for gruppen.

    ![Angiv en OneDrive-placering](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

3. Vælg **Gem**.

### <a name="access-the-workspace-onedrive-location"></a>Få adgang til arbejdsområdets OneDrive-placering

Når du har konfigureret OneDrive-placeringen, kan du få adgang til den fra et par forskellige steder i arbejdsområdet:

- Vælg **Arbejdsområder** > *navn på arbejdsområde* > ellipsemenuen ( **...** ) > **Filer**. 

    ![Placering af filer i arbejdsområde](media/service-new-workspaces/power-bi-new-workspace-files.png)

- Vælg ellipsemenuen ( **...** ) i øverste højre hjørne af arbejdsområdet > **Filer**.

    ![Placering af filer i arbejdsområde](media/service-create-the-new-workspaces/power-bi-new-workspace-files-ellipsis.png)
    
- I oplevelsen **Hent data** > **Filer**. Posten **OneDrive – Business** er dit eget OneDrive for Business. Det andet OneDrive er det, du har tilføjet.

    ![Placering af filer i arbejdsområdet – hent data](media/service-create-the-new-workspaces/power-bi-new-workspace-get-data-onedrive.png)

## <a name="add-content-to-your-workspace"></a>Føj indhold til dit arbejdsområde

Når du har oprettet et arbejdsområde med den nye arbejdsområdeoplevelse, er det tid til at føje indhold til det. Tilføjelse af indhold er ens i de nye og klassiske arbejdsområder. Brug knappen Opret, eller brug Hent data til at føje indhold til dit arbejdsområde.

1. På **Velkomstskærmen** for dit nye arbejdsområde, kan du tilføje indhold. 

    ![Velkomstskærm for nyt arbejdsområde](media/service-create-the-new-workspaces/power-bi-workspace-get-data.png)

1. Vælg f.eks. **Eksempler** > **Eksempel på kunderentabilitet**.

> [!NOTE]
> Du kan ikke føje organisationsindholdspakker eller indholdspakker fra tredjepart til de nye arbejdsområder. Der findes apps til mange indholdspakker fra tredjepart, som du tidligere har brugt. Brug klassiske arbejdsområder, hvis du fortsat har brug for at bruge indholdspakker. Indholdspakker udfases, så det er bedste praksis at bruge apps i stedet.

Når du får vist indhold på indholdslisten for et arbejdsområde, vises navnet på arbejdsområdet som ejeren.

### <a name="connecting-to-third-party-services-in-new-workspaces"></a>Opret forbindelse til tredjepartstjenester i nye arbejdsområder

I den nye arbejdsområdeoplevelse laver vi en ændring for at fokusere på *apps*. Apps til tredjepartstjenester gør det nemt for brugerne at hente data fra de tjenester, de bruger, f.eks. Microsoft Dynamics CRM, Salesforce eller Google Analytics.

I den nye arbejdsområdeoplevelse kan du ikke oprette eller bruge organisationsindholdspakker. Du kan i stedet bruge de apps, der leveres, til at oprette forbindelse til tredjepartstjenester eller bede dine interne teams om at levere apps til en indholdspakke, du bruger i øjeblikket. 

## <a name="give-access-to-your-workspace"></a>Giv adgang til dit arbejdsområde

1. Da du er administrator kan du på indholdslisten for arbejdsområder se en ny handling, **Adgang**.

    ![Indholdsliste for arbejdsområder](media/service-create-the-new-workspaces/power-bi-new-workspace-files-ellipsis.png)

1. Vælg **Adgang**.

1. Føj sikkerhedsgrupper, distributionslister, Office 365-grupper eller enkeltpersoner til disse arbejdsområder som medlemmer, bidragydere eller administratorer. Se [Roller i de nye arbejdsområder](service-new-workspaces.md#roles-in-the-new-workspaces) for at få en forklaring på de forskellige roller.

    ![Arbejdsområder – tilføj medlemmer, administratorer og bidragydere](media/service-create-the-new-workspaces/power-bi-workspace-add-members.png)

9. Vælg **Tilføj** > **Luk**.


## <a name="distribute-an-app"></a>Distribuer en app

Hvis du vil distribuere officielt indhold til en stor målgruppe i din organisation, kan du publicere en app fra dit arbejdsområde.  Når indholdet er klar, skal du vælge, hvilke dashboards og rapporter du vil publicere, og derefter skal du publicere dem som en *app*. Du kan oprette en app fra hvert arbejdsområde.

Læs om [publicering af en app fra de nye arbejdsområder](service-create-distribute-apps.md)

## <a name="next-steps"></a>Næste trin
* Læs om [organisering af arbejde i den nye arbejdsområdeoplevelse i Power BI](service-new-workspaces.md)
* [Opret klassiske arbejdsområder](service-create-workspaces.md)
* [Publicer en app fra de nye arbejdsområder i Power BI](service-create-distribute-apps.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
