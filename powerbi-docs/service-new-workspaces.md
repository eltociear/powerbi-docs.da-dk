---
title: Organiser arbejde i nye arbejdsområder – Power BI
description: Få mere at vide om de nye arbejdsområder, der er samlinger af dashboards og rapporter, der er udviklet til at levere vigtige metrikker til organisationen.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 9f5dfaa5a23ae46fef131a52355531b5fbde3051
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100682"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Organiser arbejde i nye arbejdsområder i Power BI

 *Arbejdsområder* er steder at samarbejde med kolleger til at oprette samlinger af dashboards, rapporter og sideinddelte rapporter. Den nye oplevelse arbejdsområde hjælper dig med bedre at administrere adgang til indhold. Denne artikel beskrives de nye arbejdsområder, og hvordan de adskiller sig fra de klassiske arbejdsområder.  Som med klassiske arbejdsområder bruge du stadig dem til at oprette og distribuere apps. Læs om, hvordan du [oprette en ny oplevelse arbejdsområde](service-create-the-new-workspaces.md).

Den nye oplevelse i arbejdsområdet har nået generel tilgængelighed (GA), og er nu standardarbejdsområdet. Du kan stadig fortsætte med at oprette og bruge [klassiske arbejdsområder](service-create-workspaces.md) baseret på Office 365-grupper. 

> [!NOTE]
> Hvis du vil gennemtvinge sikkerhed rækkeniveau (RLS) til Power BI Pro-brugere gennemsyn af indhold i et arbejdsområde, skal du fortsætte med at bruge [klassiske arbejdsområder](service-create-workspaces.md). Vælg den **medlemmer kan få vist Power BI-indhold** indstilling. Du kan også udgive en app i Power BI til disse brugere, eller brug deling for at distribuere indhold. Kommende Fremviser rollen kan dette scenarie i fremtiden i nye arbejdsområde oplevelse arbejdsområder.

Med de nye arbejdsområder kan du:

- Tildele arbejdsområderoller til brugergrupper: sikkerhedsgrupper, distributionslister, Office 365-grupper og enkeltpersoner.
- Oprette et arbejdsområde i Power BI uden at oprette en Office 365-gruppe.
- Bruge mere detaljerede arbejdsområderoller til administration af mere fleksible tilladelser i et arbejdsområde.

Når du opretter et af de nye arbejdsområder, opretter du ikke en underliggende tilknyttet Office 365-gruppe. Al administration af arbejdsområder sker i Power BI, ikke i Office 365. Du kan nu føje en Office 365-gruppe for at fortsætte med at administrere brugeradgang til indhold via Office 365-grupper på listen over arbejdsområde adgang i den nye oplevelse i arbejdsområdet.

## <a name="administering-new-workspace-experience-workspaces"></a>Administration af nye arbejdsområde oplevelse arbejdsområder
Administration for nye arbejdsområder til oplevelse af arbejdsområde er nu i Power BI, Power BI-administratorer beslutte, hvem der i en organisation kan oprette arbejdsområder. De kan også administrere og genoprette arbejdsområde. For at gøre dette, de skal bruge Power BI-administrationsportalen eller PowerShell-CmdLets. Klassisk arbejdsområder, der er baseret på Office 365-grupper, administration, der fortsætter med at opstå i Office 365-administrationsportalen og Azure Active Directory.

I **indstillinger for arbejdsområde** i administrationsportalen, administratorer kan bruge Opret arbejdsområder (nyt arbejdsområde experience) indstilling for at tillade alle eller ingen i en organisation for at oprette nyt arbejdsområde oplevelse arbejdsområder. De kan også begrænse oprettelse til medlemmer af bestemte sikkerhedsgrupper.

> [!NOTE]
> Opret arbejdsområder (nyt arbejdsområde experience), angive standarder til kun at tillade brugere, der kan oprette en Office 365-grupper for at oprette nye arbejdsområder i Power BI. Husk at angive en værdi i Power BI-administrationsportalen til at sikre, at relevante brugere kan oprette nyt arbejdsområde oplevelse arbejdsområder.

![Indstillinger for arbejdsområde i administrationsportalen](media/service-new-workspaces/power-bi-workspace-admin-settings.png)

Den [arbejdsområder liste er tilgængelige](service-admin-portal.md#workspaces) i Power BI-administrationsportalen. 

![Liste over arbejdsområder](media/service-admin-portal/workspaces-list.png)

## <a name="new-workspaces-side-by-side-with-classic-workspaces"></a>Nye arbejdsområder side om side med klassiske arbejdsområder

Opgraderede arbejdsområder, der er nye og eksisterende klassiske arbejdsområder samtidige ved siden af hinanden, og du kan oprette enten. Den nye oplevelse arbejdsområde er arbejdsområde standardtypen. Powerbi fortsætter med at opstille alle Office 365-grupper, som brugeren er medlem af i Power BI for at undgå at ændre eksisterende arbejdsprocesser. Hvis du vil vide, hvordan du opretter et nyt arbejdsområde, kan du læse [opretter et nyt arbejdsområde](service-create-the-new-workspaces.md). For at få mere for at vide, hvordan du opretter et klassisk arbejdsområde, kan du læse [oprette de klassiske arbejdsområder](service-create-workspaces.md).

## <a name="roles-in-the-new-workspaces"></a>Roller i de nye arbejdsområder

For at give adgang til et nyt arbejdsområde, Tilføj brugergrupper eller personer til én af rollerne arbejdsområde: medlemmer, bidragydere eller administratorer. Alle i en brugergruppe får den rolle, du har defineret. Hvis en person, der er i flere brugergrupper, får de det højeste niveau af tilladelse, der leveres af de roller, de er tildelt.

Du kan bruge roller til at administrere, hvem der kan gøre hvad i et arbejdsområde, så teams kan samarbejde. Nye arbejdsområder gør det muligt at tildele roller til enkeltpersoner og til brugergrupper: sikkerhedsgrupper, Office 365-grupper og distributionslister. 

Når du tildeler roller til en brugergruppe, har enkeltpersoner i gruppen adgang til indhold. Hvis du indlejrer brugergrupper, har alle brugere i grupperne tilladelse. En bruger, der er medlem af flere brugergrupper med forskellige roller, får tildelt det højeste tilladelsesniveau. 

De nye arbejdsområder tilbyder tre roller: administratorer, medlemmer og bidragydere.

|Egenskab   | Administrator  | Medlem  | Bidragyder  | 
|---|---|---|---|
| Opdatere og slette arbejdsområdet.  | X  |   |   |
| Tilføje/fjerne personer, herunder andre administratorer.  | X  |   |   |
| Tilføje medlemmer eller andre med lavere tilladelser.  |  X | X  |   |
| Publicer og opdater en app. |  X | X  |   |
| Del et element, eller del en app. |  X | X  |   |
| Give andre tilladelse til at dele elementer igen. |  X | X  |   |
| Oprette, redigere og slette indhold i arbejdsområdet.  |  X | X  | X  |
| Publicere rapporter til arbejdsområdet, slette indhold. |  X | X  | X  |
 
 
## <a name="licensing"></a>Licensering
Alle de brugere, du føjer til et arbejdsområde, skal have en Power BI Pro-licens. I arbejdsområdet kan disse brugere samarbejde om dashboards og rapporter, som du vil publicere til en større målgruppe eller måske til hele organisationen. Hvis du vil distribuere indhold til andre i din organisation, kan du tildele Power BI Pro-licenser til disse brugere eller anbringe arbejdsområdet i en Power BI Premium-kapacitet.

> [!NOTE]
> Publicerer rapporter til nye arbejdsområde oplevelse har strengere håndhævelse, der eksisterende licenser regler. Brugere, der forsøger at udgive fra Power BI Desktop eller andre klienter værktøjer uden en Pro-licens se fejlmeddelelsen "kun brugere med Power BI Pro-licenser kan publicere til dette arbejdsområde."

## <a name="how-are-the-new-workspaces-different-from-current-workspaces"></a>Hvordan adskiller de nye arbejdsområder sig fra de aktuelle arbejdsområder?

Med de nye arbejdsområder giver vi nogle af funktionerne et nyt design. Her er de ændringer, du kan forvente at være permanent. 

* Oprettelse af disse arbejdsområder ikke kunne oprette Office 365-grupper, som deler klassiske arbejdsområder. Du kan nu bruge en Office 365-gruppe, til at give brugere adgang til dit arbejdsområde ved at tildele den en rolle. 
* I klassiske arbejdsområder, kan du tilføje kun enkeltpersoner til medlems- og administratorlisterne. I de nye arbejdsområder kan du føje flere Active Directory-sikkerhedsgrupper, distributionslister eller Office 365-grupper til disse lister for at lette administrationen af brugere. 
- Du kan oprette en organisationsindholdspakke fra et klassisk arbejdsområde. Du kan ikke oprette en ud fra de nye arbejdsområder.
- Du kan bruge en organisationsindholdspakke fra et klassisk arbejdsområde. Du kan ikke forbruge en fra nye arbejdsområder.

## <a name="workspace-contact-list"></a>Liste over kontakter arbejdsområde
Den nye **kontaktliste** funktion gør det muligt at angive, hvilke brugere modtager en meddelelse om problemer, der opstår i arbejdsområdet. Som standard angivet en bruger eller gruppe, som et arbejdsområde administrator får besked, men du kan tilpasse listen. Brugere eller grupper, der er angivet på listen over kontaktpersoner vises i brugergrænsefladen (UI) til at hjælpe brugerne får hjælp, der er relateret til arbejdsområdet. 

Læs mere om den [angive den liste over kontaktpersoner i arbejdsområdet](service-create-the-new-workspaces.md#workspace-contact-list).

## <a name="workspace-onedrive"></a>Arbejdsområde OneDrive
Funktionen arbejdsområde OneDrive kan du konfigurere en Office 365-gruppe, hvis SharePoint-dokumentbibliotek file storage er tilgængelig for arbejdsområdebrugere. Gruppen skal være oprettet uden for Power BI. 

Tilladelser for brugere eller grupper, der er konfigureret til at have adgang til arbejdsområde med Office 365 gruppemedlemskabet synkroniserer ikke Powerbi. Den bedste fremgangsmåde er at administrere adgang til arbejdsområde via den samme Office 365-gruppe, du konfigurerer i denne indstilling fillager. 

Læs om, hvordan du [angivet, og få adgang til arbejdsområdet OneDrive](service-create-the-new-workspaces.md#workspace-onedrive).  
   
## <a name="auditing"></a>Overvågning
Følgende aktiviteter, der overvåges af Power BI for nye arbejdsområder til oplevelse af arbejdsområde.

| Brugervenligt navn |   Handlingsnavn |
|---|---|
| Power BI-mappe er oprettet | CreateFolder |
| Power BI-mappe er slettet | DeleteFolder |
| Power BI-mappe er opdateret | UpdateFolder |
| Adgang til Power BI-mappe er opdateret| UpdateFolderAccess |

Læs mere om [overvågning af Power BI](service-admin-auditing.md#activities-audited-by-power-bi).

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Begrænsninger, du skal være opmærksom på:

- Arbejdsområder kan indeholde op til 1.000 datasæt eller 1.000 rapporter pr. datasæt. 
- En person med en Power BI Pro-licens kan være medlem af en maksimal 1.000 arbejdsområder.
- Power BI publisher til Excel understøttes ikke.

## <a name="workspace-features-that-work-differently"></a>Funktioner for arbejdsområder, som fungerer anderledes

Nogle funktioner fungerer anderledes i forhold til aktuelle arbejdsområder i de nye arbejdsområder. Disse forskelle er tilsigtet, baseret på feedback, vi har modtaget fra kunder og aktivere en mere fleksibel tilgang til at samarbejde med arbejdsområder:

- Håndhævelse af licenser: Publicerer rapporter til nye arbejdsområde oplevelse gennemtvinger eksisterende licenser regler, der kræver en Power BI Pro-licens til brugere samarbejde i arbejdsområder eller Deling af indhold til andre i Power BI-tjenesten. Brugere uden en Pro-licens se fejlmeddelelsen "kun brugere med Powre BI Pro-licenser kan publicere til dette arbejdsområde."
- Medlemmer kan eller kan ikke dele igen: erstattet af rollen som bidragyder
- Skrivebeskyttede arbejdsområder: I stedet for at tildele brugere skrivebeskyttet adgang til et arbejdsområde skal du tildele brugere en kommende Fremviser-rolle, hvilket gør det muligt for lignende skrivebeskyttet adgang til indholdet i et arbejdsområde.
- Knappen **Forlad arbejdsområde** findes ikke.

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

**Er links til eksisterende indhold, der er berørt af det nye arbejdsområde opleve den offentligt tilgængelige version**

Nej. Links til eksisterende elementer i klassiske arbejdsområder, påvirkes ikke af den nye oplevelse i arbejdsområdet. Den generelle tilgængelighed (GA) af den nye oplevelse arbejdsområde ændringer standardarbejdsområdet du opretter, men ikke ændre eksisterende arbejdsområder. 

**Arbejdsområder, der er opgraderet til den nye arbejdsområde oplevelse med GA er eksisterende.**

Nej. Den nye oplevelse GA arbejdsområde ændres kun standardtypen arbejdsområde til den nye oplevelse i arbejdsområdet. Eksisterende klassiske arbejdsområder, der er baseret på Office 365-grupper forbliver uændrede.

**Arbejdsområder stadig oprettes automatisk for Office 365-grupper**

Ja. Da vi understøtter begge typer arbejdsområder ved siden af hinanden, fortsætter vi med at opstille alle Office 365-grupper, som brugeren har adgang til arbejdsområder på listen.

## <a name="next-steps"></a>Næste trin
* [Opret nye arbejdsområder i Power BI](service-create-the-new-workspaces.md)
* [Opret klassiske arbejdsområder](service-create-workspaces.md)
* [Installér og brug apps i Power BI](service-create-distribute-apps.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
