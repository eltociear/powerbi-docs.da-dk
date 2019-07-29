---
title: Meddelelser om tjenesteafbrydelser
description: Få mere at vide om, hvordan du modtager meddelelser via mail, når Power BI-tjenesten bliver forstyrret eller forringet.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/19/2019
ms.author: mblythe
ms.openlocfilehash: 0bb78e29cc3e9b9792d5916050179703281aa01a
ms.sourcegitcommit: 850e7883e21190151684e32f4d957beecd08e959
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/20/2019
ms.locfileid: "68366743"
---
# <a name="service-interruption-notifications"></a>Meddelelser om tjenesteafbrydelser

Det er vigtigt at have indsigt i tilgængeligheden af dine missionskritiske virksomhedsprogrammer. Power BI giver besked om hændelser, så du kan vælge at modtage mails, hvis der er en tjenesteafbrydelse eller -forringelse. Selvom serviceniveauaftalen på 99,9 % for Power BI sikrer, at dette sker sjældent, vil vi gerne sikre os, at du får besked om det. På følgende skærmbillede kan du se den type mail, du modtager, hvis du aktiverer meddelelser:

![Meddelelse via mail om opdatering](media/service-interruption-notifications/refresh-notification-email.png)

På nuværende tidspunkt sender vi mails for følgende _pålidelighedsscenarier_:

- Pålidelighed af åben rapport
- Pålidelighed af opdatering af model
- Pålidelighed af opdatering af forespørgsel

Når en hændelse er løst, modtager du en opfølgningsmail.

> [!NOTE]
> Denne funktion er i øjeblikket kun tilgængelig for dedikerede kapaciteter i Power BI Premium. Den er ikke tilgængelig for delt kapacitet.

## <a name="enable-notifications"></a>Aktivér meddelelser

En administrator af Power BI-lejeren aktiverer meddelelser på administrationsportalen:

1. Identificer eller opret en mailaktiveret sikkerhedsgruppe, der skal modtage meddelelserne.

1. På administrationsportalen skal du vælge **lejerindstillinger**. Under **indstillinger for hjælp og support** skal du udvide **Modtag meddelelser via mail for tjenesteafbrydelser eller -hændelser**.

1. Aktivér meddelelser, angiv en sikkerhedsgruppe, og vælg **Anvend**.

    ![Aktivér tjenestemeddelelser](media/service-interruption-notifications/enable-notifications.png)

> [!NOTE]
> Power BI sender meddelelser fra kontoen no-reply-powerbi@microsoft.com. Sørg for, at denne konto er anført på hvidlisten, så meddelelserne ikke ender i en spammappe eller en mappe med uønsket post.

## <a name="next-steps"></a>Næste trin

[Supportmuligheder til Power BI Pro og Power BI Premium](service-support-options.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)