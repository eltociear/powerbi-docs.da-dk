---
title: Angiv kontaktoplysninger for rapporter og dashboards
description: Få mere at vide om, hvordan du angiver kontaktoplysninger for rapporter og dashboards.
author: LukaszPawlowski-MS
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/08/2010
ms.author: lukaszp
LocalizationGroup: Common tasks
ms.openlocfilehash: bb98f7bbb92b72512f880513ec94ccb55d64fc67
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73872142"
---
# <a name="set-contact-information-for-reports-and-dashboards-in-the-power-bi-service"></a>Angiv kontaktoplysninger for rapporter og dashboards i Power BI-tjenesten
I denne artikel kan du se, hvordan du angiver kontaktoplysninger for et dashboard eller en rapport i Power BI-tjenesten.

> [!NOTE]
> Der kan angives kontaktoplysninger for elementer i et klassisk eller nyt arbejdsområde. Du kan ikke angive kontaktoplysninger for elementer i Mit arbejdsområde. Infokortet vises, når man får vist en rapport eller et dashboard i det [nye udseende](service-new-look.md).

Du kan føje flere brugere eller grupper til kontakten for et element. De kan være:
* En person
* En Office 365-gruppe
* En mailaktiveret sikkerhedsgruppe
* En distributionsliste

Den person, der opretter en ny rapport eller et nyt dashboard, er som standard kontakten for den eller det. Hvis du angiver en værdi, tilsidesætter den standarden. Du kan naturligvis fjerne alle personer eller grupper fra listen over kontakter. Når du gør det, vises Office 365-gruppen for arbejdsområdet for klassiske arbejdsområder. For arbejdsområder med den nye arbejdsområdeoplevelse bruges [listen over kontakter for arbejdsområdet](service-create-the-new-workspaces.md#workspace-contact-list). Hvis listen over kontakter for arbejdsområdet ikke er angivet, vises administratorerne af arbejdsområdet.

Kontaktoplysningerne vises for folk, når de får vist elementet. 

 ![kontakt til tjenesterapport](media/service-item-contact/service-report-contact.png)

Når du klikker på listen over kontakter, oprettes der en mail, så du kan stille spørgsmål eller få hjælp. 

 ![mail til tjenestekontakt](media/service-item-contact/service-contact-email.png)
 
Oplysningerne på listen over kontakter bruges også andre steder. Den vises f.eks. i nogle fejlscenarier i dialogboksen for fejl. Automatiserede mails, der er relateret til elementet, f.eks. adgangsanmodninger, sendes til listen over kontakter. 

> [!NOTE]
> Når du publicerer en app, angives de kontaktoplysninger, der er angivet for de enkelte elementer, for den person, der publicerede eller opdaterede appen. Du kan angive URL-adressen for appsupport, så brugerne af appen får den hjælp, de har brug for.

## <a name="set-contact-information-for-a-report"></a>Angiv kontaktoplysninger for en rapport
1. Vælg fanen **Rapporter** i dit arbejdsområde.
2. Find den ønskede rapport, og vælg ikonet **Indstillinger**.
3. Find inputfeltet **Kontakt**, og angiv en værdi.

     ![indstillinger for kontakt til tjenesterapport](media/service-item-contact/service-report-contact-setting.png)

## <a name="set-contact-information-for-a-dashboard"></a>Angiv kontaktoplysninger for et dashboard
1. Vælg fanen **Dashboards** i dit arbejdsområde.
2. Find det ønskede dashboard, og vælg ikonet **Indstillinger**
3. Find inputfeltet **Kontakt**, og angiv en værdi.

     ![indstillinger for kontakt til tjenestedashboard](media/service-item-contact/service-dashboard-contact-setting.png)

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
* Kontakten er automatisk angivet for nye elementer, der oprettes i Power BI-tjenesten. Eksisterende elementer viser standarden for arbejdsområdet.
* Du kan angive en hvilken som helst bruger eller gruppe på listen over kontakter, men de får ikke automatisk tildelt tilladelse til elementet. Brug deling, eller giv den bruger, der har brug for det, adgang til arbejdsområdet via en rolle. 


## <a name="next-steps"></a>Næste trin

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
