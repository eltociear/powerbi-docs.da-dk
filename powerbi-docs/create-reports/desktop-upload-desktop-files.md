---
title: Udgiv fra Power BI Desktop
description: Udgiv fra Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/20/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 4a363ce72002003981f1bcbe46e0f5367f89860f
ms.sourcegitcommit: c1f05254eaf5adb563f8d4f33c299119134c7d1f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/21/2020
ms.locfileid: "83733460"
---
# <a name="publish-datasets-and-reports-from-power-bi-desktop"></a>Udgiv datasæt og rapporter fra Power BI Desktop
Når du udgiver en Power BI Desktop-fil i Power BI-tjenesten, udgiver du dataene i modellen på dit Power BI-arbejdsområde. Det samme gælder for de rapporter, du har oprettet i visningen **Rapport**. Du kan se et nyt datasæt med det samme navn og alle rapporter i navigatoren til dit arbejdsområde.

Hvis du udgiver fra Power BI Desktop, har det samme effekt, som hvis du bruger **Hent data** i Power BI til at oprette forbindelse til og overføre en Power BI Desktop-fil.

> [!NOTE]
> De ændringer, du foretager i rapporten i Power BI, gemmes ikke i den oprindelige Power BI Desktop-fil igen. Dette omfatter, når du tilføjer, sletter eller ændrer visualiseringer i rapporter.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Sådan udgiver du Power BI Desktop-datasæt og -rapporter
1. I Power BI Desktop skal du vælge **Filer** \> **Udgiv** \> **Publicer i Power BI** eller vælge **Udgiv** på båndet.  

   ![Knappen Publicer](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. Log på Power BI.
3. Vælg en destination.

   ![Vælg en destination til publicering](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

Når udgivelsen er fuldført, modtager du et link til rapporten. Vælg linket for at åbne rapporten på dit Power BI-websted.

![Dialogboks for fuldført publicering](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="republish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Udgiv igen eller erstat et datasæt, der er udgivet i Power BI Desktop
Datasættet og eventuelle rapporter, du har oprettet i Power BI Desktop, uploades til Power BI-webstedet, når du udgiver en Power BI Desktop-fil. Når du udgiver din Power BI Desktop-fil igen, erstattes datasættet på dit Power BI-websted med det opdaterede datasæt fra Power BI Desktop-filen.

Denne proces er ret ligetil, men der er et par ting, du skal vide:

* To eller flere datasæt i Power BI med samme navn som Power BI Desktop-filen kan forårsage, at udgivelsen måske ikke lykkedes. Kontrollér, at du kun har ét datasæt i Power BI med det samme navn. Du kan også omdøbe filen og udgive den og dermed oprette et nyt datasæt med samme navn som filen.
* Hvis du omdøber eller sletter en kolonne eller måling, kan eventuelle visualiseringer, du allerede har i Power BI med dette felt, blive brudt. 
* Power BI ignorerer nogle formatændringer af eksisterende kolonner. Hvis du f.eks. ændrer formatet for en kolonne fra 0,25 % til 25 %.
* Lad os sige, at du har en tidsplan for opdatering, der er konfigureret til dit eksisterende datasæt i Power BI. Når du føjer nye datakilder til din fil og derefter udgiver igen, skal du logge på dem før næste planlagte opdatering.
* Når du genudgiver et datasæt, der er udgivet fra Power BI Desktop, og har defineret en tidsplan for opdatering, startes en opdatering af datasættet, så snart du udgiver igen.
* Når du foretager en ændring af et datasæt og derefter publicerer det igen, vises der en meddelelse om, hvor mange arbejdsområder, rapporter og dashboards der potentielt kan blive påvirket af ændringen, og du bliver bedt om at bekræfte, at du vil erstatte det aktuelt udgivne datasæt med det, du har ændret. Meddelelsen indeholder også et link til hele effektanalysen af datasættet i Power BI-tjenesten, hvor du kan se flere oplysninger og foretage en handling for at afhjælpe risikoen ved ændringen.

   ![Advarsel om genudgivelse af et datasæt](media/desktop-upload-desktop-files/pbid-dataset-impact-analysis-desktop-warning.png)

   [Få mere at vide om Effektanalyse af datasæt](../collaborate-share/service-dataset-impact-analysis.md).