---
title: Konfigurationsindstillinger i Power BI-appen
description: Sådan tilpasser du funktionsmåden for Power BI ved hjælp af MDM-værktøjet
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 11/07/2019
ms.author: painbar
ms.openlocfilehash: a517ee4edce6e18eadcbe2b1b6765684f8121b21
ms.sourcegitcommit: 768e1e4b19fe8c7627010127c2420d63021cb542
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199430"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>Du kan fjernkonfigurere Power BI-appen ved hjælp af MDM-værktøjet (Mobile Device Management)

Appen Power BI – Mobil til iOS og Android understøtter appindstillinger, der gør det muligt for administratorer af Office 365 og MDM-tjenester (Mobile Device Management), f.eks. Intune, at tilpasse appens funktionsmåde.

Appen Power BI – Mobil understøtter følgende konfigurationsscenarier:

- Konfiguration af rapportserveren (iOS og Android)
- Indstillinger for databeskyttelse (iOS)

## <a name="report-server-configuration-ios-and-android"></a>Konfiguration af rapportserveren (iOS og Android)

Power BI-appen til iOS og Android gør det muligt for administratorer at fjern-"pushe" konfigurationen af rapportserveren til tilmeldte enheder.

| Nøgle | Type | Beskrivelse |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL-adresse | Streng | URL-adresse til rapportserver.<br><br>Skal starte med http/https.|
| com.microsoft.powerbi.mobile.ServerBrugernavn | Streng | [valgfri]<br><br>Det brugernavn, der skal bruges til at oprette forbindelse til serveren.<br><br>Hvis der ikke findes et brugernavn, vil appen bede brugeren skrive brugernavnet til forbindelsen.|
| com.microsoft.powerbi.mobile.ServerVist navn | Streng | [valgfri]<br><br>Standardværdien er "Rapportserver"<br><br>Et navn, der bruges i appen til at repræsentere serveren. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolesk | [valgfri]<br><br>Standardværdien er True. Når værdien er angivet til True, tilsidesætter den alle eksisterende rapportserverdefinitioner på mobilenheden. Eksisterende servere, der allerede er konfigureret, slettes. Dette forhindrer også, at brugeren kan fjerne konfigurationen.<br><br>Hvis indstillingen er angivet til "False", tilføjes de overførte værdier, og eksisterende indstillinger ændres ikke. Hvis den samme URL-adresse allerede er konfigureret i mobilappen, forbliver konfigurationen, som den er. Appen beder ikke brugeren om at godkende igen for den samme server. |

## <a name="data-protection-settings-ios"></a>Indstillinger for databeskyttelse (iOS)

Power BI-appen til iOS giver administratorer mulighed for at tilpasse standardkonfigurationen for sikkerhed og indstillinger for beskyttelse af personlige oplysninger. Du kan gennemtvinge, at brugerne skal angive deres Face ID, Touch ID eller en adgangskode, når du åbner Power BI-appen.

| Nøgle | Type | Beskrivelse |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boolesk | Standardværdien er False. <br><br>Biometriske data, f.eks TouchID eller FaceID, kan være påkrævet, for at brugerne kan få adgang til appen på deres enhed. Når det er påkrævet, bruges biometriske data ud over godkendelse.<br><br>Hvis du bruger politikker for appbeskyttelse, anbefaler Microsoft, at du deaktiverer denne indstilling for at forhindre dobbelte adgangsprompter. |

## <a name="deploying-app-configuration-settings"></a>Udrulning af konfigurationsindstillinger for apps

Følgende er de trin, du skal følge for at oprette en appkonfigurationspolitik. Når du har oprettet konfigurationspolitikken, kan du tildele dens indstillinger til grupper af brugere.

1. Opret forbindelse til dit MDM-værktøj.
2. Opret og navngiv en ny appkonfigurationspolitik.
3. Vælg, hvilke brugere appkonfigurationspolitikken skal distribueres til.
4. Opret nøgleværdipar for den indstilling, du vil pushe til dine brugere.

Intune-portalen gør det muligt for administratorer nemt at installere disse indstillinger til Power BI-appen via konfigurationspolitikker for apps. Dog understøttes en eventuel MDM-udbyder. Hvis du ikke bruger Intune, skal du se din MDM-dokumentation for at få oplysninger om, hvordan du installerer disse indstillinger.

## <a name="next-steps"></a>Næste trin

* Hent Power BI-mobilappen i [App Store](https://apps.apple.com/app/microsoft-power-bi/id929738808) og [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.powerbim&amp;amp;clcid=0x409)
* Følg [@MSPowerBI på Twitter](https://twitter.com/MSPowerBI)
* Deltag i samtalen i [Power BI-community'et](https://community.powerbi.com/)
