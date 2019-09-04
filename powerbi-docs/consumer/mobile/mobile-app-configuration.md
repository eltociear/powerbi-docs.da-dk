---
title: Konfigurationsindstillinger i Power BI-appen til iOS
description: Sådan tilpasser du funktionsmåden for Power BI til iOS, ved hjælp af MDM-værktøjet
author: paulinbar
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: bc9c6dd8cd892ab0304cc5a99a3bb780486f32f0
ms.sourcegitcommit: c0f4d00d483121556a1646b413bab75b9f309ae9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/29/2019
ms.locfileid: "70160167"
---
# <a name="remotely-configure-power-bi-ios-app-using-mobile-device-management-mdm-tool"></a>Du kan fjernkonfigurere Power BI-appen til iOS ved hjælp af MDM-værktøjet (Mobile Device Management)

Power BI - Mobil-appen til iOS understøtter appindstillinger, der gør det muligt for administratorer af Office 365 og MDM (Mobile Device Management), f.eks. Intune, at tilpasse appens funktionsmåde.

Power BI - Mobil-appen til iOS understøtter følgende konfigurationsscenarier:

- Konfiguration af rapportserveren
- Indstillinger for databeskyttelse

## <a name="report-server-configuration"></a>Konfiguration af rapportserveren

Power BI-appen til iOS gør det muligt for administratorer at fjern-"pushe" konfigurationen af rapportserveren med tilmeldte enheder.

| Nøgle | Type | Beskrivelse |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL-adresse | Streng | URL-adresse til rapportserver.<br><br>Skal starte med http/https.|
| com.microsoft.powerbi.mobile.ServerBrugernavn | Streng | [valgfri]<br><br>Det brugernavn, der skal bruges til at oprette forbindelse til serveren.<br><br>Hvis der ikke findes et brugernavn, vil appen bede brugeren skrive brugernavnet til forbindelsen.|
| com.microsoft.powerbi.mobile.ServerVist navn | Streng | [valgfri]<br><br>Standardværdien er "Rapportserver"<br><br>Et navn, der bruges i appen til at repræsentere serveren. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolesk | [valgfri]<br><br>Standardværdien er True. Når værdien er angivet til True, tilsidesætter den alle eksisterende rapportserverdefinitioner på mobilenheden. Eksisterende servere, der allerede er konfigureret, slettes. Dette forhindrer også, at brugeren kan fjerne konfigurationen.<br><br>Hvis indstillingen er angivet til "False", tilføjes de overførte værdier, og eksisterende indstillinger ændres ikke. Hvis den samme URL-adresse allerede er konfigureret i mobilappen, forbliver konfigurationen, som den er. Appen beder ikke brugeren om at godkende igen for den samme server. |

## <a name="data-protection-setting"></a>Indstilling for databeskyttelse

Power BI-appen til iOS giver administratorer mulighed for at tilpasse standardkonfigurationen for sikkerhed og indstillinger for beskyttelse af personlige oplysninger. Du kan gennemtvinge, at brugerne skal angive deres Face ID, Touch ID eller en adgangskode, når du åbner Power BI-appen.

| Nøgle | Type | Beskrivelse |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boolesk | Standardværdien er False. <br><br>Biometriske data, f.eks TouchID eller FaceID, kan være påkrævet, for at brugerne kan få adgang til appen på deres enhed. Når det er påkrævet, bruges biometriske data ud over godkendelse.<br><br>Hvis du bruger politikker for appbeskyttelse, anbefaler Microsoft, at du deaktiverer denne indstilling for at forhindre dobbelte adgangsprompter. |

## <a name="deploying-app-configuration-settings"></a>Udrulning af konfigurationsindstillinger for apps

Følgende trin gør det muligt for dig at oprette en appkonfigurationspolitik. Når konfigurationspolitikken er oprettet, kan du tildele indstillingerne til grupper af brugere.

1. Opret forbindelse til dit MDM-værktøj.

2. Opret og navngiv en ny appkonfigurationspolitik.

3. Vælg, hvilke brugere appkonfigurationspolitikken skal distribueres til.

4. Opret nøgleværdipar for den indstilling, du vil pushe til dine brugere.

Intune-portalen gør det muligt for administratorer nemt at installere disse indstillinger til Power BI-appen til iOS via konfigurationspolitikker for apps.
Dog understøttes en eventuel MDM-udbyder. Hvis du ikke bruger Intune, skal du se din MDM-dokumentation for at få oplysninger om, hvordan du installerer disse indstillinger.

## <a name="next-steps"></a>Næste trin

* Download [Power BI-mobilappen til iPhone](http://go.microsoft.com/fwlink/?LinkId=522062)
* Følg [@MSPowerBI på Twitter](https://twitter.com/MSPowerBI)
* Deltag i samtalen i [Power BI-community'et](http://community.powerbi.com/)
