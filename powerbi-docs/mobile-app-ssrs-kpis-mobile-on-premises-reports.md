---
title: Vis rapporter og KPI'er i det lokale miljø i Power BI-mobilapps
description: Power BI-mobilappsene tilbyder live, touchaktiveret mobiladgang til dine virksomhedsoplysninger i det lokale miljø via SQL Server Reporting Services og Power BI-rapportserver.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: maggies
ms.openlocfilehash: 999fdf0376973d6550a5c4e214b4315db01e74e0
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34482239"
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Vis rapporter og KPI'er fra rapportserveren i det lokale miljø i Power BI-mobilapps

Power BI-mobilapps leverer live, touchaktiveret mobiladgang til dine firmaoplysninger i det lokale miljø via Power BI-rapportserver og SQL Server 2016 Reporting Services (SSRS).

Gælder for:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-telefon](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tablet](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhones |iPad-tablets |Android-telefoner |Android-tablets |


![Startside for rapportserver i mobilappsene](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Det vigtigste først
**Mobilappsene er der, hvor du ser Power BI-indhold, ikke hvor du opretter det.**

* Du og andre personer, der opretter rapporter i din organisation, [opretter Power BI-rapporter med Power BI Desktop, og publicerer dem derefter på webportalen Power BI-rapportserver](report-server/quickstart-create-powerbi-report.md). 
* Du opretter [KPI'er direkte i webportalen](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services), organiserer dem i mapper og markerer dine favoritter, så du nemt kan finde dem. 
* Du [opretter Reporting Services-mobilrapporter](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) med SQL Server 2016 Enterprise Edition Mobile Report Publisher, og publicerer dem på [Reporting Services-webportalen](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Derefter opretter du forbindelse til op til fem rapportservere i Power BI-mobilappsene for at se Power BI-rapporter og -KPI'er, organiseret i mapper eller samlet som favoritter. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Se nærmere på eksemplerne i mobilappsene uden serverforbindelse
Selvom du ikke har adgang til en Reporting Services-webportal, kan du stadig udforske funktionerne i Reporting Services-mobilrapporter og -KPI'er. 

1. Tryk på knappen til global navigation ![Knappen til global navigation](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) i øverste venstre hjørne, og tryk derefter på tandhjulsikonet øverst til højre ![Tandhjulsikon](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. Tryk på **Reporting Services-eksempler**, og gennemse for at interagere med eksemplerne på KPI'er og mobilrapporter.
   
   ![Reporting Services-eksempler](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-report-server"></a>Opret forbindelse til en rapportserver i det lokale miljø
Du kan se Power BI-rapporter, Reporting Services-mobilrapporter og KPI'er i Power BI-mobilapps. 

1. Åbn Power BI-appen på din mobilenhed.
2. Hvis du ikke er logget på Power BI endnu, skal du trykke på **Rapportserver**.
   
   ![Log på en rapportserver](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Hvis du allerede er logget på Power BI-appen, skal du trykke på knappen til global navigation ![Knappen til global navigation](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png)og derefter trykke på tandhjulsikonet ![Tandhjulsikon](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) øverst til højre.
3. Tryk på **Opret forbindelse til server**.
   
    ![Opret forbindelse til server](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)

     Mobilappen skal have adgang til serveren på en eller anden måde. Der er et par måder at gøre det på:

    - Den nemmeste måde er at være på samme netværk/anvende en VPN-forbindelse.
    - Det er muligt at bruge en Web Application Proxy til at oprette forbindelse, hvis du er uden for organisationen. Du kan få flere oplysninger under [Brug af OAuth til at oprette forbindelse til Reporting Services](mobile-oauth-ssrs.md). 
    - Åbn en forbindelse (port) i firewallen.

1. Udfyld serveradressen og dit brugernavn og din adgangskode. Brug dette format til serveradressen:
   
     `http://<servername>/reports`
   
     ELLER
   
     `https://<servername>/reports`
   
   Inkluder **http** eller **https** foran forbindelsesstrengen.
   
    ![Dialogboksen Opret forbindelse til server](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (Valgfrit) Under **Avancerede indstillinger** kan du give serveren et brugervenligt, hvis du vil.
6. Nu kan du se serveren på den venstre navigationsbjælke – i dette eksempel hedder den "power bi-rapportserver".
   
   ![Rapportserver i venstre navigationsrude](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="connect-to-an-on-premises-report-server-in-ios"></a>Opret forbindelse til en rapportserver i det lokale miljø i iOS

Hvis du får vist Power BI i iOS-mobilappen, kan din it-administrator have angivet en appkonfigurationspolitik. Hvis det er tilfældet, skal du ikke angive lige så mange oplysninger, når du skal oprette forbindelse til en rapportserver. 

1. Du får vist en meddelelse om, at din mobilapp er konfigureret med en rapportserver. Tryk på **Log på**.

    ![Log på rapportserveren](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-sign-in.png)

2.  Oplysningerne for rapportserveren er allerede udfyldt på siden **Opret forbindelse til server**. Tryk på **Opret forbindelse**.

    ![Rapportserveroplysningerne er udfyldt](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-remote-configure-connect-server.png)

3. Skriv en adgangskode, og tryk derefter på **Log på**. 

    ![Rapportserveroplysningerne er udfyldt](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-address.png)

Nu kan du få vist og interagere med KPI'er og Power BI-rapporter på rapportserveren.

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Se Power BI-rapporter og -KPI'er i Power BI-appen
Power BI-rapporter, Reporting Services-mobilrapporter og KPI'er vises i de samme mapper, som de er placeret i på Reporting Services-webportalen. 

* Tryk på en Power BI-rapport ![Ikon for Power BI-rapport](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Den åbnes i vandret tilstand, og du kan interagere med den i Power BI-appen.
  
    ![Power BI-rapport](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* I Power BI Desktop kan ejere [optimere en rapport](desktop-create-phone-report.md) til Power BI-mobilapps. På din mobiltelefon har optimerede rapporter et særligt ikon, ![ikonet for Optimeret Power BI-rapport](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png), og layout.
  
    ![Power BI-rapport optimeret til mobil visning](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Tryk på en KPI for at få den vist i fokuseret tilstand.
  
    ![KPI i fokuseret tilstand](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Se dine foretrukne KPI'er og rapporter
Du kan markere KPI'er og rapporter som favoritter på webportalen og derefter se dem i en enkelt praktisk mappe på din mobilenhed sammen med din foretrukne Power BI-dashboards.

* Tryk på **Favoritter**.
  
   ![Favoritter i venstre navigationsrude](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server-update.png)
  
   Dine foretrukne KPI'er og rapporter fra webportalen findes alle på denne side sammen med Power BI-dashboards i Power BI-tjenesten:
  
   ![Power BI-rapporter og -dashboards på siden Favoritter](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Fjern en forbindelse til en rapportserver
1. Nederst på navigationslinjen til venstre skal du trykke på **Indstillinger**.
2. Tryk på det servernavn, som du ikke vil have forbindelse til.
3. Tryk på **Fjern server**.

## <a name="next-steps"></a>Næste trin
* [Introduktion til Power BI](service-get-started.md)  
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

