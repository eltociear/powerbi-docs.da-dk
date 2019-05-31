---
title: Fejlfinding af feltfejl
description: Almindelige fejl, der kan opstå, når et felt forsøger at opdatere i Power BI
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c1df7e6293db703922f37c3f28546bb296d1a46a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051006"
---
# <a name="troubleshooting-tile-errors"></a>Fejlfinding af feltfejl
Nedenfor er de mest almindelige fejl, der kan opstå med felter, sammen med en forklaring.

> [!NOTE]
> Hvis der opstår en fejl, der ikke er angivet nedenfor, og det medfører problemer for dig, kan du bede om yderligere hjælp på [community-webstedet](http://community.powerbi.com/), eller du kan oprette en [supportbillet](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="errors"></a>Fejl
**Der opstod en uventet fejl i Power BI under indlæsning af modellen. Prøv igen senere.**
eller **Datamodellen kunne ikke hentes. Kontakt ejeren af dashboardet for at sikre, at datakilderne og modellen eksisterer og er tilgængelige.**

Vi kunne ikke få adgang til dine data, fordi datakilden ikke var tilgængelig. Dette kan ske, hvis datakilden blev fjernet, omdøbt, flyttet, er offline, eller hvis tilladelserne er blevet ændret. Kontrollér, at kilden stadig er på den placering, vi peger på, og at du stadig har tilladelse til at få adgang til den. Hvis det ikke er problemet, kan kilden muligvis være langsom. Prøv igen på et senere tidspunkt, når belastningen på kilden er mindre. Hvis det er en lokal kilde, kan ejeren af datakilden muligvis give flere oplysninger.

**Du har ikke tilladelse til at få vist dette felt eller åbne projektmappen.**

Kontakt ejeren af dashboardet for at sikre, at datakilderne og modellen findes og er tilgængelige for din konto.

**Brugerdefinerede visualiseringer er blevet deaktiveret af din administrator.**

Din Power BI-administrator har deaktiveret brugen af brugerdefinerede visualiseringer for din organisation eller sikkerhedsgruppe. Du kan ikke bruge brugerdefinerede visualiseringer fra [Microsoft Marketplace](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) eller importere private visualiseringer fra en fil. Du kan kun bruge de foruddefinerede pakkede sæt af visualiseringer.


**Dataformer skal indeholde mindst én gruppe eller beregning med data som output. Kontakt ejeren af dashboardet.**

Vi har ikke nogen data, der kan vises, fordi forespørgslen er tom. Prøv at føje nogle felter fra feltlisten til det visuelle element og fastgøre det igen.

**Dataene kan ikke vises, da Power BI ikke kan fastslå relationen mellem to eller flere felter.**

Du forsøger at bruge to eller flere felter fra tabeller, der ikke er relateret. Du skal fjerne de ikke-relaterede felter fra det visuelle element og derefter oprette en relation mellem tabellerne. Når du har ændret dette, kan du igen føje felterne til visualiseringen. Det kan gøres i Power BI Desktop eller Power Pivot til Excel. [Få mere at vide](desktop-create-and-manage-relationships.md)

**Grupperne på den primære og den sekundære akse overlapper hinanden. Grupperne på den primære akse må ikke have samme nøgler som grupperne på den sekundære akse.**

Det er som regel et midlertidigt problem. Det sker typisk, når du flytter grupper fra rækker til kolonner. I dette tilfælde skal fejlen forsvinde, når du er færdig med at flytte alle grupperne. Hvis meddelelsen stadig vises, skal du forsøge at skifte mellem rækkerne og kolonnerne eller akseforklaringen eller fjerne felter fra det visuelle element.  

**Dette visuelle element har overskredet de tilgængelige ressourcer. Prøv at filtrere for at mindske mængden af data, der vises.**

Det visuelle element har forsøgt at forespørge på for mange data, og vi kan ikke fuldføre resultatet med de tilgængelige ressourcer. Prøv at filtrere det visuelle element for at mindske mængden af data i resultatet.

**Vi kan ikke identificere følgende felter: {0}. Opdater det visuelle element med felter, der findes i datasættet.**

Feltet blev sandsynligvis slettet eller omdøbt. Du kan fjerne det ødelagte felt fra det visuelle element, tilføje et andet felt og fastgøre det igen.

**Dataene kunne ikke hentes for dette visuelle element. Prøv igen senere.**

Det er normalt et midlertidigt problem. Hvis du prøver igen senere, og du stadig får vist denne meddelelse, skal du kontakte support.

**Felter, der fortsat viser ufiltrerede data efter aktivering af enkeltlogon (SSO).**

Dette kan ske, hvis det underliggende datasæt er konfigureret til at bruge DirectQuery-tilstand eller en direkte forbindelse til Analysis Services via en datagateway i det lokale miljø. I dette tilfælde fortsætte felterne til at vise ufiltrerede dataene efter aktivere SSO til datakilden, indtil den næste opdatering af dashboardfelt er forfalden. Power BI bruger SSO, som er konfigureret på den næste opdatering af felter, og felterne, der viser de data, der er filtreret i henhold til brugerens identitet. 

Hvis du vil se de filtrerede data med det samme, du kan gennemtvinge en opdatering af feltet ved at vælge ellipsen (...) i øverste højre hjørne af et dashboard og vælge **Opdater dashboardfelter**.

Du kan også ændre opdateringshyppigheden felt og angive den til 15 minutter at sætte skub i opdatering af felter som datasætejer af et. Vælg tandhjulsikonet i øverste højre hjørne af Power BI-tjenesten og derefter vælge **indstillinger**. På den **indstillinger** side, Vælg den **datasæt** fanen. Udvid **planlagt cacheopdatering** og ændre **opdateringshyppighed**. Kontrollér, at du nulstille konfigurationen oprindelige opdateringshyppigheden, når Power BI udfører den næste opdatering af felter.

> [!NOTE]
> Den **planlagt cacheopdatering** afsnit er kun tilgængelig for datasæt i tilstanden DirectQuery/LiveConnection. Datasæt i Import-tilstand kræver ikke en opdatering af separate felter, fordi felterne opdateres automatisk i løbet af den næste planlagte opdatering.

## <a name="contact-support"></a>Kontakt support
Hvis du stadig har et problem, skal du [kontakte support](https://support.powerbi.com) for at undersøge det yderligere.

## <a name="next-steps"></a>Næste trin
[Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  
[Fejlfinding af Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

