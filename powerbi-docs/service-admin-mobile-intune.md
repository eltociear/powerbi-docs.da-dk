---
title: Konfiguration af mobilapps med Microsoft Intune
description: Sådan konfigurerer du Power BI-mobilapps med Microsoft Intune. Dette omfatter, hvordan du tilføjer og installerer programmet. Og hvordan du opretter politikken for mobilapps til at styre sikkerheden.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: d28a27d69d6e8799f08ddaa05e734ded62150c8f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710925"
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Konfiguration af mobilapps med Microsoft Intune

Microsoft Intune giver organisationer mulighed for at administrere enheder og programmer. Power BI-mobilprogrammerne til iOS og Android kan integreres med Intune. Denne integration gør det muligt for dig at administrere programmet på dine enheder og styre sikkerheden. Ved hjælp af konfigurationspolitikker kan du kontrollere elementer som at anmode om pinkode for at give adgang, hvordan data håndteres af programmet og tilmed kryptere programdata, når appen ikke er i brug.

## <a name="general-mobile-device-management-configuration"></a>Konfiguration af generel administration af mobilenheder

Denne artikel forudsætter, at Intune er konfigureret korrekt, og at du har enheder tilmeldt i Intune. Artiklen er ikke tænkt som en komplet konfigurationsvejledning til Microsoft Intune. Du kan finde flere oplysninger om Intune under [Hvad er Intune?](/intune/introduction-intune/)

Microsoft Intune kan fungere sammen med administration af mobilenheder (MDM) i Office 365. Hvis du bruger MDM, vises "tilmeldt MDM" på enheden, men den kan administreres i Intune.

> [!NOTE]
> Når du konfigurerer Intune, er dataopdatering i baggrunden slået fra for Power BI-mobilappen på din iOS- eller Android-enhed. Power BI opdaterer dataene via Power BI-tjenesten på internettet, når du åbner appen.

## <a name="step-1-get-the-url-for-the-application"></a>Trin 1: Hent URL-adressen til programmet

Før vi opretter programmet i Intune, skal vi have hentet URL-adresserne for appsene. Til iOS får vi den fra iTunes. Til Android kan du hente den fra Power BI-mobilsiden.

Gem URL-adressen, da du skal bruge den, når vi opretter programmet.

### <a name="get-ios-url"></a>Hent URL-adressen til iOS

For at få URL-adressen for appen til iOS skal vi hente den fra iTunes.

1. Åbn iTunes.

1. Søg efter *Power BI*.

1. Du bør se **Microsoft Power BI** angivet under **iPhone-apps** og **iPad-apps**. Du kan bruge begge dele, da du får den samme URL-adresse.

1. Vælg rullemenuen **Hent**, og vælg **Kopiér link**.

    ![URL-adresse til iTunes](media/service-admin-mobile-intune/itunes-url.png)

Det bør ligne følgende: *https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8* .

### <a name="get-android-url"></a>Hent URL-adressen til Android

Du kan hente URL-adressen til Google Play via [Power BI-mobilsiden](https://powerbi.microsoft.com/mobile/). Vælg **Download fra Google Play** for at komme til appsiden. Du kan kopiere URL-adressen fra browserens adresselinje. Det bør ligne følgende: *https://play.google.com/store/apps/details?id=com.microsoft.powerbim* .

## <a name="step-2-create-a-mobile-application-management-policy"></a>Trin 2: Opret en politik for administration af mobilapps

Politikken for administration af mobilapps giver dig mulighed for at gennemtvinge ting som f.eks. pinkode til adgang. Du kan oprette en på Intune-portalen.

Du kan oprette programmet eller politikken først. Det har ingen betydning, i hvilken rækkefølge de tilføjes. Så længe de begge findes på installationstrinnet.

1. Vælg **Politik** > **Konfigurationspolitikker** på Intune-portalen.

    ![Intune-portalen](media/service-admin-mobile-intune/intune-policy.png)

1. Vælg **Tilføj...** .

1. Under **Software** kan du vælge administration af mobilapps til enten Android eller iOS. For at komme hurtigt i gang kan du vælge **Opret en politik med de anbefalede indstillinger**, eller du kan oprette en brugerdefineret politik.

1. Rediger politikken for at konfigurere de ønskede begrænsninger på programmet.

## <a name="step-3-create-the-application"></a>Trin 3: Opret programmet

Programmet er en reference, eller en pakke, som gemmes i Intune til installation. Vi skal oprette et program og henvise til den URL-adresse for appen, vi fik fra enten Google Play eller iTunes.

Du kan oprette programmet eller politikken først. Det har ingen betydning, i hvilken rækkefølge de tilføjes. Så længe de begge findes på installationstrinnet.

1. Gå til Intune-portalen, og vælg **Apps** fra menuen til venstre.

1. Vælg **Tilføj app**. Dette starter programmet **Tilføj software**.

### <a name="create-for-ios"></a>Opret til iOS

1. Vælg **Styret iOS-app fra App Store** på rullelisten.

1. Angiv URL-adressen for appen, som vi hentede under [Trin 1](#step-1-get-the-url-for-the-application), og vælg **Næste**.

    ![Softwareinstallation: iOS](media/service-admin-mobile-intune/intune-add-software-ios1.png)

1. Angiv en **Udgiver**, et **Navn** og en **Beskrivelse**. Du kan vælge at angive et **Ikon**. **Kategori** er til appen Firmaportal. Når du er færdig, skal du vælge **Næste**.

1. Du kan vælge, om du vil publicere apps til **Alle** (standard), **iPad** eller **iPhone**. Som standard vises **Alle**, og det fungerer for begge enhedstyper. Power BI-appen har den samme URL-adresse til både iPhone og iPad. Vælg **Næste**.

1. Vælg **Upload**.

1. Hvis du ikke kan se appen på listen, kan du opdatere siden: Gå til **Oversigt** og derefter tilbage til **Apps**.

    ![Fanen Apps](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="create-for-android"></a>Opret til Android

1. Vælg **Eksternt link** på rullelisten.

1. Angiv URL-adressen for appen, som vi hentede under [Trin 1](#step-1-get-the-url-for-the-application), og vælg **Næste**.

    ![Programinstallation: Android](media/service-admin-mobile-intune/intune-add-software-android1.png)

1. Angiv en **Udgiver**, et **Navn** og en **Beskrivelse**. Du kan vælge at angive et **Ikon**. **Kategori** er til appen Firmaportal. Når du er færdig, skal du vælge **Næste**.

1. Vælg **Upload**.

1. Hvis du ikke kan se appen på listen, kan du opdatere siden: Gå til **Oversigt** og derefter tilbage til **Apps**.

    ![Fanen Apps](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>Trin 4: Installér programmet

Når du har tilføjet programmet, skal du installere det, så det bliver tilgængeligt for dine slutbrugere. Dette er trinnet, hvor du binder den politik, du har oprettet, til appen.

### <a name="deploy-for-ios"></a>Udrul på iOS

1. Vælg den app, du har oprettet, på skærmbilledet med apps. Vælg derefter linket **Administrer installation...** .

    ![Administrer udrulning](media/service-admin-mobile-intune/intune-deploy-ios1.png)

1. I skærmbilledet **Vælg grupper** kan du vælge, hvilke grupper du vil installere denne app til. Vælg **Næste**.

1. I skærmbilledet **Installationshandling** kan du vælge, hvordan du vil installere denne app. Hvis du vælger **Tilgængelig installation** eller **Påkrævet installation**, bliver appen tilgængelig på Firmaportal, så brugerne kan installere den efter behov. Når du har foretaget dit valg, skal du vælge **Næste**.

    ![Udrulningshandling](media/service-admin-mobile-intune/intune-deploy-ios2.png)

1. I skærmbilledet **Styring af mobilapp** kan du vælge den politik for administration af mobilapps, du oprettede på [Trin 2](#step-2-create-a-mobile-application-management-policy). Den indstilles som standard til den politik, du har oprettet, hvis det er den eneste iOS-politik, der er tilgængelig. Vælg **Næste**.

    ![Administration af mobilapp](media/service-admin-mobile-intune/intune-deploy-ios3.png)

1. I skærmbilledet **VPN-profil** kan du vælge en politik, hvis du har en for din organisation. Standardindstillingen er **Ingen**. Vælg **Næste**.

1. I skærmbilledet **Konfiguration af mobilapps** kan du vælge en **Politik om appkonfiguration**, hvis du har oprettet en. Standardindstillingen er **Ingen**. Dette er ikke påkrævet. Vælg **Udfør**.

Når du har installeret appen, skal der stå **Ja** ud for installeret på siden med apps.

### <a name="deploy-for-android"></a>Udrul på Android

1. Vælg den app, du har oprettet, på skærmbilledet med apps. Vælg derefter linket **Administrer installation...** .

    ![Administrer udrulning](media/service-admin-mobile-intune/intune-deploy-android1.png)
1. I skærmbilledet **Vælg grupper** kan du vælge, hvilke grupper du vil installere denne app til. Vælg **Næste**.

1. I skærmbilledet **Installationshandling** kan du vælge, hvordan du vil installere denne app. Hvis du vælger **Tilgængelig installation** eller **Påkrævet installation**, bliver appen tilgængelig på Firmaportal, så brugerne kan installere den efter behov. Når du har foretaget dit valg, skal du vælge **Næste**.

    ![Udrulningshandling](media/service-admin-mobile-intune/intune-deploy-android2.png)

1. I skærmbilledet **Styring af mobilapp** kan du vælge den politik for administration af mobilapps, du oprettede på [Trin 2](#step-2-create-a-mobile-application-management-policy). Den indstilles som standard til den politik, du har oprettet, hvis det er den eneste Android-politik, der er tilgængelig. Vælg **Udfør**.

    ![Administration af mobilapp](media/service-admin-mobile-intune/intune-deploy-android3.png)

Når du har installeret appen, skal der stå **Ja** ud for installeret på siden med apps.

## <a name="step-5-install-the-application-on-a-device"></a>Trin 5: Installér programmet på en enhed

Du installerer programmet via appen *Firmaportal*. Hvis du ikke har installeret appen Firmaportal, kan du hente den via App Store på iOS- eller Android-platformen. Du skal logge på Firmaportal med dit organisationslogon.

1. Åbn appen Firmaportal.

1. Hvis du ikke ser Power BI-appen angivet som en udvalgt app, skal du vælge **Firmaapps**.

    ![Virksomhedsapps](media/service-admin-mobile-intune/intune-companyportal1.png)

1. Vælg den Power BI-app, du har installeret.

    ![Power BI-app](media/service-admin-mobile-intune/intune-companyportal2.png)

1. Vælg **Installér**.

    ![Installér app](media/service-admin-mobile-intune/intune-companyportal3.png)

1. Hvis du er på iOS, får du en pushmeddelelse om installation af appen. Vælg **Installér** i pushdialogboksen.

    ![Appinstallation](media/service-admin-mobile-intune/intune-companyportal5.png)

1. Når appen er installeret, kan du se, at den er **Administreret af dit firma**. Hvis du har aktiveret adgang ved hjælp af pinkode i politikken, får du vist følgende.

    ![Angiv pinkode](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Næste trin

[Konfigurer og udrul politikker for administration af mobilapps i Microsoft Intune-konsollen](/intune/app-protection-policies/)  

[Power BI-apps til mobilenheder](consumer/mobile/mobile-apps-for-mobile-devices.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)  
