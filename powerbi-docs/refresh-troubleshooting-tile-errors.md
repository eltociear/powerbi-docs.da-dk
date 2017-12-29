---
title: Fejlfinding af feltfejl
description: "Almindelige fejl, der kan opstå, når et felt forsøger at opdatere"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: d54e9daadd2df0e78b5c098f83d8e8a19960c45d
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
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

Vi kunne ikke få adgang til dine data, fordi datakilden ikke var tilgængelig. Det kan ske, hvis datakilden blev fjernet, omdøbt, flyttet, er offline, eller tilladelserne er blevet ændret. Kontrollér, at kilden stadig er på den placering, vi peger på, og at du stadig har tilladelse til at få adgang til den. Hvis det ikke er problemet, kan kilden muligvis være langsom. Prøv igen på et senere tidspunkt, når belastningen på kilden er mindre. Hvis det er en lokal kilde, kan ejeren af datakilden muligvis give flere oplysninger.

**Du har ikke tilladelse til at få vist dette felt eller åbne projektmappen.**

Kontakt ejeren af dashboardet for at sikre, at datakilderne og modellen eksisterer og er tilgængelige for din konto.

**Dataformer skal indeholde mindst én gruppe eller beregning med data som output. Kontakt ejeren af dashboardet.**

Vi har ikke nogen data, der kan vises, fordi forespørgslen er tom. Prøv at føje nogle felter fra feltlisten til det visuelle element og fastgøre det igen.

**Dataene kan ikke vises, da Power BI ikke kan fastslå relationen mellem to eller flere felter.**

Du forsøger at bruge to eller flere felter fra tabeller, der ikke er relateret. Du skal fjerne de ikke-relaterede felter fra det visuelle element og derefter oprette en relation mellem tabellerne. Når du har gjort dette, kan du igen føje felterne til det visuelle element. Det kan gøres i Power BI Desktop eller Power Pivot til Excel. [Få mere at vide](desktop-create-and-manage-relationships.md)

**Grupperne på den primære og den sekundære akse overlapper hinanden. Grupperne på den primære akse må ikke have samme nøgler som grupperne på den sekundære akse.**

Det er normalt et midlertidigt problem. Det sker typisk, når du flytter grupper fra rækker til kolonner. I dette tilfælde skal fejlen forsvinde, når du er færdig med at flytte alle grupperne. Hvis meddelelsen stadig vises, skal du forsøge at skifte mellem rækkerne og kolonnerne eller akseforklaringen eller fjerne felter fra det visuelle element.  

**Dette visuelle element har overskredet de tilgængelige ressourcer. Prøv at filtrere for at mindske mængden af data, der vises.**

Det visuelle element har forsøgt at forespørge på for mange data, og vi kan ikke fuldføre resultatet med de tilgængelige ressourcer. Prøv at filtrere det visuelle element for at mindske mængden af data i resultatet.

**Vi kan ikke identificere følgende felter: {0}. Opdater det visuelle element med felter, der findes i datasættet.**

Feltet blev sandsynligvis slettet eller omdøbt. Du kan fjerne det ødelagte felt fra det visuelle element, tilføje et andet felt og fastgøre det igen.

**Dataene kunne ikke hentes for dette visuelle element. Prøv igen senere.**

Det er normalt et midlertidigt problem. Hvis du prøver igen senere, og du stadig ser denne meddelelse, skal du kontakte supporten.

## <a name="contact-support"></a>Kontakt support
Hvis du stadig har et problem, skal du [kontakte supporten](https://support.powerbi.com) for at undersøge yderligere.

## <a name="next-steps"></a>Næste trin
[Fejlfinding af datagateway i det lokale miljø](service-gateway-onprem-tshoot.md)  
[Fejlfinding af Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)
