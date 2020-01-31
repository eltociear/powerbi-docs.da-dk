---
title: Konfigurer indstillinger for rapportinteraktion
description: Få mere at vide om, hvordan du tilsidesætter standardindstillingerne for interaktion for rapporter.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: painbar
ms.openlocfilehash: fee89c65328b70e1f312b39fbad75d7148bd92f2
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/23/2020
ms.locfileid: "76542283"
---
# <a name="configure-report-interaction-settings"></a>Konfigurer indstillinger for rapportinteraktion

## <a name="overview"></a>Oversigt

Power BI-mobilappen har en række konfigurerbare indstillinger for "interaktion", som giver dig mulighed for at styre, hvordan du interagerer med dine data, og for at definere, hvordan nogle af elementerne i Power BI-mobilappen fungerer. Der er i øjeblikket indstillinger for
* [Interaktion via enkelttryk i forhold til dobbelttryk på rapportvisualiseringer](#single-tap)
* [Forankret i forhold til dynamisk rapportfod](#docked-report-footer-android-phones) (Android)
* [Opdatering af rapport ved at trykke på en knap i forhold til at trække](#report-refresh-android-phones) (Android)

Hvis du vil have vist interaktionsindstillingerne, skal du trykke på dit profilbillede for at åbne [sidepanelet](./mobile-apps-home-page.md#header), vælge **Indstillinger** og finde sektionen **Interaktion**.

![Interaktionsindstillinger](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-section.png)

>[!NOTE]
>Interaktionsindstillinger for knappen Opdater og for forankring af rapportfoden har i øjeblikket ingen effekt på Rapportserver-rapporter. Dette ændres med udgivelsen af Rapportserver januar 2020.

## <a name="interaction-settings"></a>Interaktionsindstillinger

### <a name="single-tap"></a>Enkelttryk
Når du downloader Power BI-mobilappen, er den angivet til interaktion med enkelttryk. Det betyder, at når du trykker på en visualisering for at udføre en handling, f.eks. markering af et udsnitselement, tværgående fremhævning, klik på et link eller en knap osv., vælges det visuelle element, når du trykker, og samtidig udføres den handling, du ønsker.

Hvis du foretrækker det, kan du slå interaktion med enkelttryk fra. Du har derefter interaktion med dobbelttryk. Hvis du vælger interaktion med dobbelttryk, skal du først trykke på et visuelt element for at markere det og derefter trykke på det visuelle element igen for at udføre den ønskede handling.

### <a name="docked-report-footer-android-phones"></a>Forankret rapportfod (Android-telefoner)

Indstillingen for den forankrede rapportfod bestemmer, om rapportfoden forbliver forankret (dvs. fastgjort og altid synlig) nederst i rapporten, eller om den skjules og vises igen på baggrund af dine handlinger i rapporten, f.eks. rulning.

På Android-telefoner er indstillingen for den forankrede rapportfod som standard slået **til**, hvilket betyder, at rapportfoden er forankret og altid synlig nederst i rapporten. Skift indstillingen til **fra**, hvis du foretrækker en dynamisk rapportfod, der vises og forsvinder afhængigt af dine handlinger i rapporten.

### <a name="report-refresh-android-phones"></a>Rapportopdatering (Android-telefoner)

Indstillingen for rapportopdatering definerer, hvordan du starter rapportopdateringer. Du kan enten vælge at have en Opdater-knap i alle rapportoverskrifter eller at bruge træk-handlingen (trække en smule fra toppen til bunden) på rapportsiden for at opdatere rapporten. I figuren nedenfor vises de to alternativer. 

![Opdater-knap i forhold til træk for at opdatere](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-refresh-button-versus-pull.png)

På Android-telefoner tilføjes der som standard en opdateringsknap.

Hvis du vil ændre indstillingen for rapportopdatering, skal du gå til elementet for rapportopdatering i interaktionsindstillingerne. Den aktuelle indstilling vises. Tryk på værdien for at åbne et pop op-vindue, hvor du kan vælge en ny værdi.

![Angiv opdatering](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-set-refresh.png)

## <a name="remote-configuration"></a>Fjernkonfiguration

Interaktioner kan også konfigureres eksternt af en administrator ved hjælp af et MDM-værktøj med en fil til konfiguration af en app. På denne måde er det muligt at standardisere rapportens interaktionsoplevelse i hele organisationen eller for bestemte grupper af brugere i organisationen. Se [Konfigurer interaktion ved hjælp af administration af mobilenheder](./mobile-app-configuration.md) for at få flere oplysninger.


## <a name="next-steps"></a>Næste trin
* [Arbejde med rapporter](./mobile-reports-in-the-mobile-apps.md#interact-with-reports)
* [Konfigurer interaktion ved hjælp af administration af mobilenheder](./mobile-app-configuration.md)
