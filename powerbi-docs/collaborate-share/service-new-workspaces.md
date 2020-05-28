---
title: Organiser arbejde i nye arbejdsområder i Power BI
description: Få mere at vide om de nye arbejdsområder, der er samlinger af dashboards og rapporter, som er udviklet til at levere vigtige målepunkter for din organisation.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/07/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 701f478ce4dd59d77c1722b1386cd79ad3fbf2a0
ms.sourcegitcommit: 250242fd6346b60b0eda7a314944363c0bacaca8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/20/2020
ms.locfileid: "83693792"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Organiser arbejde i nye arbejdsområder i Power BI

*Arbejdsområder* er steder, hvor du kan samarbejde med kolleger om at oprette samlinger af dashboards, rapporter, datasæt og sideinddelte rapporter. Den nye arbejdsområdeoplevelse hjælper dig med bedre at administrere adgang til indhold. I denne artikel beskrives de nye arbejdsområder, og hvordan de adskiller sig fra de klassiske arbejdsområder.  På samme måde som med klassiske arbejdsområder bruges arbejdsområder stadig til at oprette og distribuere apps. Er du parat til at oprette et nyt arbejdsområde? Læs [Opret en ny arbejdsområdeoplevelse](service-create-the-new-workspaces.md).

Nye opgraderede arbejdsområder og eksisterende klassiske arbejdsområder eksisterer side om side. Den nye arbejdsområdeoplevelse er standardtypen for arbejdsområder. Du kan stadig oprette og bruge [klassiske arbejdsområder](service-create-workspaces.md), der er baseret på Microsoft 365 Grupper, hvis du har brug for det. Er du klar til at overføre dit klassiske arbejdsområde? Se [Opgrader klassiske arbejdsområder til de nye arbejdsområder i Power BI](service-upgrade-workspaces.md) for at få flere oplysninger.

Med de nye arbejdsområder kan du:

- Tildele arbejdsområderoller til brugergrupper: sikkerhedsgrupper, distributionslister, Microsoft 365-grupper og enkeltpersoner.
- Oprette et arbejdsområde i Power BI uden at oprette en underliggende tilknyttet Microsoft 365-gruppe. Al administration af arbejdsområder sker i Power BI, ikke i Microsoft 365.
- Fortsætte med at administrere brugeradgang til indhold via Microsoft 365-grupper, hvis du vil det. Du skal blot tilføje en Microsoft 365-gruppe på adgangslisten for arbejdsområdet.
- Bruge mere detaljerede arbejdsområderoller til administration af mere fleksible tilladelser i et arbejdsområde.

Power BI fortsætter med at vise alle Microsoft 365-grupper, som du er medlem af. Dette forhindrer, at eksisterende arbejdsprocesser ændres.

## <a name="new-and-classic-workspace-differences"></a>Forskelle på det nye og det klassiske arbejdsområde

Vi har givet nogle af funktionerne i de nye arbejdsområder et nyt design. Her er de væsentligste forskelle.

- Oprettelse af disse arbejdsområder opretter ikke Microsoft 365-grupper på samme måde som klassiske arbejdsområder. Du kan dog nu bruge en Microsoft 365-gruppe til at give brugere adgang til dit arbejdsområde ved at tildele området en rolle.
- I de klassiske arbejdsområder kan du kun føje enkeltpersoner til medlems- og administratorlisterne. I de nye arbejdsområder kan du føje flere Active Directory-sikkerhedsgrupper, distributionslister eller Microsoft 365-grupper til disse lister for at lette administrationen af brugere.
- Du kan oprette en organisationsindholdspakke ud fra et klassisk arbejdsområde. Du kan ikke oprette en ud fra de nye arbejdsområder.
- Du kan forbruge en organisationsindholdspakke ud fra et klassisk arbejdsområde. Du kan ikke forbruge en fra de nye arbejdsområder.

### <a name="workspace-features-that-work-differently"></a>Funktioner for arbejdsområder, som fungerer anderledes

Nogle funktioner fungerer anderledes i forhold til aktuelle arbejdsområder i de nye arbejdsområder. Disse forskelle er bevidst og er baseret på den feedback, vi har modtaget fra kunder. De giver mulighed for en mere fleksibel tilgang til samarbejde med arbejdsområder.

- **Håndhævelse af licenser**: Publicering af rapporter til den nye arbejdsområdeoplevelse sker på baggrund af de eksisterende licensregler. Brugere, der samarbejder i arbejdsområder eller deler indhold med andre i Power BI-tjenesten, skal bruge en Power BI Pro-licens. Brugere uden en Pro-licens får vist fejlmeddelelsen "Kun brugere med Power BI Pro-licenser kan publicere til dette arbejdsområde".
- **Medlemmer kan enten dele eller ikke dele igen**: Rollen som bidragyder erstatter denne indstilling.
- **Skrivebeskyttede arbejdsområder**: I stedet for at give brugere skrivebeskyttet adgang til et arbejdsområde, kan du tildele dem rollen Seer. Det giver tilsvarende skrivebeskyttet adgang til indholdet i et arbejdsområde.
- **Brugere med en Pro-licens** kan få adgang til arbejdsområdet, hvis det er i en Power BI Premium-kapacitet, men kun hvis de har rollen Seer.
- **Tillad brugere at eksportere data**: Brugere med rollen Seer kan eksportere data, hvis de har tilladelse til at oprette for datasættene i arbejdsområdet. Læs mere om [tilladelsen Opret for datasæt](../connect-data/service-datasets-build-permissions.md).
- Knappen **Forlad arbejdsområde** findes ikke.

### <a name="workspace-contact-list"></a>Liste over arbejdsområdekontakter

Den nye **kontaktlistefunktion** gør det muligt at angive, hvilke brugere der modtager en meddelelse om de problemer, der opstår i arbejdsområdet. Som standard får alle brugere eller grupper, der er angivet som arbejdsområdeadministrator besked, men du kan tilpasse listen. Brugere eller grupper, der er angivet på listen over kontaktpersoner, vises i brugergrænsefladen for at hjælpe brugerne med at få hjælp i forbindelse med arbejdsområdet. 

Læs mere om [angivelse af listen over kontaktpersoner i arbejdsområdet](service-create-the-new-workspaces.md#workspace-contact-list).

### <a name="workspace-onedrive"></a>Arbejdsområde for OneDrive

Funktionen Arbejdsområde for OneDrive giver dig mulighed for at konfigurere en Microsoft 365-gruppe, hvis fillager for SharePoint-dokumentbibliotek er tilgængeligt til brugere af arbejdsområdet. Du opretter gruppen uden for Power BI.

Power BI synkroniserer ikke tilladelser for brugere eller grupper, der er konfigureret til at have adgang til arbejdsområdet med medlemskabet af Microsoft 365-gruppen. Bedste praksis er at administrere adgang til arbejdsområdet via den samme Microsoft 365-gruppe, hvis fillager du konfigurerer i denne indstilling.

Læs mere om, hvordan du [angiver og får adgang til Arbejdsområde for OneDrive](service-create-the-new-workspaces.md#workspace-onedrive).  

## <a name="roles-in-the-new-workspaces"></a>Roller i de nye arbejdsområder

Hvis du vil give adgang til et nyt arbejdsområde, skal du føje brugergrupper eller enkeltpersoner til en af arbejdsområderollerne: administratorer, medlemmer, bidragydere eller seere. Alle i en brugergruppe får den rolle, du har defineret. Hvis en person er i flere brugergrupper, får personen det højeste tilladelsesniveau, der er angivet for den rolle, personen er blevet tildelt.

Du kan bruge roller til at administrere, hvem der kan gøre hvad i et arbejdsområde, så teams kan samarbejde. Nye arbejdsområder gør det muligt at tildele roller til enkeltpersoner og til brugergrupper: sikkerhedsgrupper, Microsoft 365-grupper og distributionslister.

Når du tildeler roller til en brugergruppe, har enkeltpersoner i gruppen adgang til indhold. Hvis du indlejrer brugergrupper, har alle brugere i grupperne tilladelse.

[!INCLUDE [power-bi-workspace-roles-table](../includes/power-bi-workspace-roles-table.md)]

> [!NOTE]
> Hvis du vil gennemtvinge sikkerhed på rækkeniveau (RLS) for brugere, der gennemser indhold i et arbejdsområde, kan du bruge rollen Seer. Hvis du vil gennemtvinge RLS uden at give adgang til arbejdsområdet, kan du publicere en Power BI-app til disse brugere eller bruge deling til at distribuere indhold.

## <a name="licensing"></a>Licensering
Alle de brugere, du føjer til et arbejdsområde i den delte kapacitet, skal have en Power BI Pro-licens. I arbejdsområdet kan disse brugere samarbejde om dashboards og rapporter, som du vil publicere til en større målgruppe eller måske til hele organisationen. 

Hvis du vil distribuere indhold til andre i din organisation, kan du tildele Power BI Pro-licenser til disse brugere eller anbringe arbejdsområdet i en Power BI Premium-kapacitet.

Når arbejdsområdet er i en Power BI Premium-kapacitet, kan brugere med rollen som Seer få adgang til arbejdsområdet, også selvom de ikke har en Power BI Pro-licens. Men hvis du tildeler disse brugere en rolle på et højere niveau som f.eks. administrator, medlem eller bidragyder, vil de blive bedt om at starte en Pro-prøveversion, når de forsøger at få adgang til arbejdsområdet. Hvis du vil bruge rollen Seer til brugere uden Pro-licens, skal du sørge for, at de ikke har andre arbejdsområderoller, enten individuelt eller via en brugergruppe.

> [!NOTE]
> Publicering af rapporter til den nye arbejdsområdeoplevelse har strengere håndhævelse af eksisterende licensregler. Hvis du forsøger at udgive fra Power BI Desktop eller andre klientværktøjer uden en Pro-licens, får du vist fejlmeddelelsen "Kun brugere med Power BI Pro-licenser kan publicere til dette arbejdsområde".

## <a name="administering-new-workspace-experience-workspaces"></a>Administration af arbejdsområder i den nye arbejdsområdeoplevelse

Arbejdsområder til administration af nye arbejdsområder er nu på plads i Power BI-administrationsportalen. Power BI-administratorer bestemmer, hvem i en organisation der kan oprette arbejdsområder og distribuere apps. Administratorer kan se status for alle arbejdsområder i deres organisation. De kan også administrere og genoprette arbejdsområder. Læs mere om [Oprettelse af nye arbejdsområder](../admin/service-admin-portal.md#create-the-new-workspaces) i artiklen om administrationsportalen.

## <a name="guest-users"></a>Gæstebrugere

[Azure AD B2B-gæstebrugere](../admin/service-admin-azure-ad-b2b.md) kan som standard ikke få adgang til arbejdsområder. Power BI-administratorer kan [tillade, at eksterne brugere kan redigere og administrere indhold i organisationen](../admin/service-admin-azure-ad-b2b.md#guest-users-who-can-edit-and-manage-content). Brugere, der er gæstebrugere, kan få adgang til de arbejdsområder, de har tilladelse til.

## <a name="auditing"></a>Overvågning

Følgende aktiviteter overvåges af Power BI for arbejdsområder i den nye arbejdsområdeoplevelse.

| Brugervenligt navn | Handlingsnavn |
|---|---|
| Power BI-mappe er oprettet | CreateFolder |
| Power BI-mappe er slettet | DeleteFolder |
| Power BI-mappe er opdateret | UpdateFolder |
| Adgang til Power BI-mappe er opdateret| UpdateFolderAccess |

Læs mere om [overvågning i Power BI](../admin/service-admin-auditing.md).

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Begrænsninger, du skal være opmærksom på:

- Arbejdsområder kan indeholde op til 1.000 datasæt eller 1.000 rapporter pr. datasæt. 
- En person med en Power BI Pro-licens kan være medlem af maks. 1.000 arbejdsområder.
- Power BI Publisher til Excel understøttes ikke.

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

**Påvirkes links til eksisterende indhold af den offentligt tilgængelige version af den nye arbejdsområdeoplevelse?**

Nej. Links til eksisterende elementer i de klassiske arbejdsområder påvirkes ikke af den nye arbejdsområdeoplevelse. Den generelle tilgængelighed af den nye arbejdsområdeoplevelse ændrer det standardarbejdsområde, som du opretter, men ikke eksisterende arbejdsområder. 

**Opgraderes eksisterende arbejdsområder til den nye arbejdsområdeoplevelse i forbindelse med, at den bliver generelt tilgængelig?**

Nej. Den nye generelt tilgængelige arbejdsområdeoplevelse ændrer kun standardtypen for arbejdsområder til den nye arbejdsområdeoplevelse. Eksisterende klassiske arbejdsområder, der er baseret på Microsoft 365 Grupper, forbliver uændrede.

**Oprettes der stadig automatisk arbejdsområder for Microsoft 365 Grupper?**

Ja. Da vi understøtter begge typer arbejdsområder samtidig, fortsætter vi med at vise alle de Microsoft 365-grupper, som du har adgang til, på listen over arbejdsområder.

## <a name="next-steps"></a>Næste trin

* [Opret nye arbejdsområder i Power BI](service-create-the-new-workspaces.md)
* [Opret klassiske arbejdsområder](service-create-workspaces.md)
* [Installér og brug apps i Power BI](service-create-distribute-apps.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

