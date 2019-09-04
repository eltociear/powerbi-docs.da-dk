---
title: Udgiv fra Power BI Desktop
description: Udgiv fra Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 69e458d966e656847a4e2122df148e90c1834a58
ms.sourcegitcommit: c0f4d00d483121556a1646b413bab75b9f309ae9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/29/2019
ms.locfileid: "70160309"
---
# <a name="publish-from-power-bi-desktop"></a>Udgiv fra Power BI Desktop
Når du udgiver en **Power BI Desktop**-fil i **Power BI-tjenesten**, udgives dataene i modellen og de rapporter, du har oprettet i visningen **Rapport**, på dit Power BI-arbejdsområde. Du kan se et nyt datasæt med det samme navn og alle rapporter i navigatoren til dit arbejdsområde.

Hvis du udgiver fra **Power BI Desktop**, har det samme effekt, som hvis du bruger **Hent data** i Power BI til at oprette forbindelse til og overføre en **Power BI Desktop**-fil.

> [!NOTE]
> De ændringer, du foretager i Power BI-rapporten, f.eks. tilføjelse, sletning eller ændring af visualiseringer i rapporter, gemmes ikke i den oprindelige **Power BI Desktop**-fil.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Sådan udgiver du Power BI Desktop-datasæt og -rapporter
1. I Power BI Desktop skal du vælge **Fil** \> **Udgiv** \> **Publicer i Power BI** eller klikke på **Udgiv** på båndet.  

   ![Knappen Publicer](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. Log på Power BI.
3. Vælg en destination.

   ![Vælg en destination til publicering](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

Når det er fuldført, modtager du et link til rapporten. Klik på linket for at åbne rapporten på dit Power BI-websted.

![Dialogboks for fuldført publicering](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Udgiv igen eller erstat et datasæt, der er udgivet i Power BI Desktop
Når du udgiver en **Power BI Desktop**-fil, overføres datasættet og eventuelle rapporter, du har oprettet i **Power BI Desktop**, til Power BI-webstedet. Når du udgiver din **Power BI Desktop**-fil igen, erstattes datasættet på dit Power BI-websted med det opdaterede datasæt fra **Power BI Desktop**-filen.

Alt dette er ret ligetil, men der er et par ting, du skal vide:

* Hvis du allerede har to eller flere datasæt i Power BI med samme navn som **Power BI Desktop**-filen, lykkes udgivelsen måske ikke. Kontrollér, at du kun har ét datasæt i Power BI med det samme navn. Du kan også omdøbe filen og udgive den og dermed oprette et nyt datasæt med samme navn som filen.
* Hvis du omdøber eller sletter en kolonne eller måling, kan eventuelle visualiseringer, du allerede har i Power BI med dette felt, blive brudt. 
* Power BI ignorerer nogle formatændringer af eksisterende kolonner. Hvis du f.eks. ændrer formatet for en kolonne fra 0,25 til 25 %.
* Hvis du har en tidsplan for opdateringer, der er konfigureret for dit eksisterende datasæt i Power BI, og du føjer nye datakilder til din fil og derefter genudgiver dem, skal du logge på dem i *Administrer datakilder* før næste planlagte opdatering.
* Når du genudgiver et datasæt, der er udgivet fra **Power BI Desktop**, og har defineret en tidsplan for opdatering, startes en opdatering af datasættet, så snart du udgiver igen. 

