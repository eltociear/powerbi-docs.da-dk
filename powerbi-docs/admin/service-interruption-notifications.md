---
title: Meddelelser om tjenesteafbrydelser
description: Få mere at vide om, hvordan du modtager meddelelser via mail, når Power BI-tjenesten bliver forstyrret eller forringet.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/11/2020
ms.author: kfollis
ms.openlocfilehash: 43d78710e4b60ed57ac46f713ce7bc787e852f26
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485478"
---
# <a name="service-interruption-notifications"></a>Meddelelser om tjenesteafbrydelser

Det er vigtigt at have indsigt i tilgængeligheden af dine missionskritiske virksomhedsprogrammer. Power BI giver besked om hændelser, så du kan vælge at modtage mails, hvis der er en tjenesteafbrydelse eller -forringelse. Selvom serviceniveauaftalen på 99,9 % for Power BI sikrer, at dette sker sjældent, vil vi gerne sikre os, at du får besked om det. På følgende skærmbillede kan du se den type mail, du modtager, hvis du aktiverer meddelelser:

![Meddelelse via mail om opdatering](media/service-interruption-notifications/refresh-notification-email.png)

På nuværende tidspunkt sender vi mails for følgende _pålidelighedsscenarier_:

- Pålidelighed af åben rapport
- Pålidelighed af opdatering af model
- Pålidelighed af opdatering af forespørgsel

Der sendes meddelelser, når der er en _længere forsinkelse_ i handlinger såsom åbning af rapporter, opdateringer af datasæt eller udførelser af forespørgsler. Når en hændelse er løst, modtager du en opfølgningsmail.

> [!NOTE]
> Denne funktion er i øjeblikket kun tilgængelig for dedikerede kapaciteter i Power BI Premium. Den er ikke tilgængelig til delt eller integreret kapacitet.

## <a name="capacity-and-reliability-notifications"></a>Notifikationer om kapacitet og pålidelighed

Når en Power BI Premium-kapacitet har længere perioder med et stort ressourceforbrug, der kan have indflydelse på pålideligheden, sendes der en notifikation via mail. Eksempler på sådanne indvirkninger omfatter store forsinkelser i handlinger, f.eks. åbning af en rapport, opdatering af datasæt og udførelse af forespørgsler. 

Notifikationen indeholder oplysninger om årsagen til det høje ressourceforbrug, herunder følgende:

* Datasæt-id for det ansvarlige datasæt
* Handlingstype
* Den CPU-tid, der er forbundet med det høje ressourceforbrug

Power BI sender også notifikationer via mail, når der registreres en overbelastning af en Power BI Premium-kapacitet. I mailen forklares den sandsynlige årsag til overbelastningen, hvilke handlinger der har genereret overbelastningen i de seneste 10 minutter, og hvor meget belastning hver handling har genereret. 


Hvis du har mere end én Premium-kapacitet, indeholder mailen oplysninger om disse kapaciteter i den overbelastede periode, så du kan overveje at flytte de arbejdsområder, der indeholder ressourceintensive elementer, til de kapaciteter, der har mindst belastning.

Mailnotifikationerne med oplysninger om overbelastning sendes kun, når overbelastningsgrænsen udløses. Du modtager ikke endnu en mail, når belastningen i den pågældende Premium-kapacitet vender tilbage til et niveau uden overbelastning.

På følgende billede vises et eksempel på en mailnotifikation:

![mail med notifikation om overbelastning af kapacitet](media/service-interruption-notifications/refresh-notification-email-2.png)


## <a name="enable-notifications"></a>Aktivér meddelelser

En administrator af Power BI-lejeren aktiverer meddelelser på administrationsportalen:

1. Identificer eller opret en mailaktiveret sikkerhedsgruppe, der skal modtage meddelelserne.

1. På administrationsportalen skal du vælge **lejerindstillinger**. Under **indstillinger for hjælp og support** skal du udvide **Modtag meddelelser via mail for tjenesteafbrydelser eller -hændelser**.

1. Aktivér meddelelser, angiv en sikkerhedsgruppe, og vælg **Anvend**.

    ![Aktivér tjenestemeddelelser](media/service-interruption-notifications/enable-notifications.png)

> [!NOTE]
> Power BI sender meddelelser fra kontoen no-reply-powerbi@microsoft.com. Sørg for, at denne konto føjes til din liste over sikre afsendere, så meddelelserne ikke ender i en mappe med uønsket mail.

## <a name="next-steps"></a>Næste trin

[Supportmuligheder til Power BI Pro og Power BI Premium](service-support-options.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
