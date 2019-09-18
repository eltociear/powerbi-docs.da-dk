---
title: Udforsk rapporter i Power BI-mobilappsene
description: Se, hvordan du kan få vist og interagere med rapporter i Power BI-mobilappsene på din telefon eller tablet. Du kan oprette rapporter i Power BI-tjenesten eller Power BI Desktop og derefter interagere med dem i mobilappsene.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 08/09/2019
ms.author: mshenhav
ms.openlocfilehash: 166b7d88e6ab55481ec56b0cf4f91628cd141bef
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/16/2019
ms.locfileid: "69985736"
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Udforsk rapporter i Power BI-mobilappsene
Gælder for:

| ![iPhone](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android-telefon](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android-tablet](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10-enheder](./media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:---: |:---: |:---: |:---: |:---: |
| iPhone-telefoner |iPad-tablets |Android-telefoner |Android-tablets |Windows 10-enheder |

En Power BI-rapport er en interaktiv visning af dine data, hvor visualiseringer repræsenterer forskellige resultater og indsigter fra disse data. At få vist rapporter i Power BI-mobilapps er det sidste trin i en proces med tre trin:

1. [Opret rapporter i Power BI Desktop](../../desktop-report-view.md). Du kan endda [optimere en rapport til telefoner](mobile-apps-view-phone-report.md) i Power BI Desktop.
2. Publicer disse rapporter i Power BI-tjenesten [(https://powerbi.com)](https://powerbi.com) eller [Power BI-rapportserver](../../report-server/get-started.md).  
3. Derefter kan du interagere med rapporterne i Power BI-mobilappsene.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Åbn en Power BI-rapport i mobilappen
Power BI-rapporter er gemt på forskellige steder i mobilappen, afhængigt af hvor du har fået dem. De kan være placeret under Apps, Delt med mig, Arbejdsområder(herunder Mit arbejdsområde) eller på en rapportserver. Nogle gange skal du gennem et relateret dashboard for at komme til en rapport. Andre gange vises de på en liste.

På lister og i menuer kan du finde et ikon ud for et rapportnavn, som hjælper dig med at forstå, at dette element er en rapport:

![Rapporter i Mit arbejdsområde](./media/mobile-reports-in-the-mobile-apps/reports-my-workspace.png)

Der findes to ikoner til rapporter i Power BI-mobilappsene:

* ![Ikonet Rapport](./media/mobile-reports-in-the-mobile-apps/report-default-icon.png) angiver en rapport, der vises i liggende retning i appen. Den ser ud på samme måde som i en browser.

* ![Ikon for rapport, der er optimeret til telefoner](./media/mobile-reports-in-the-mobile-apps/report-phone-icon.png) angiver en rapport, der har mindst én rapportside, som er optimeret til telefoner, og som vises i stående format.

> [!NOTE]
> Når du holder din telefon i liggende retning, får du altid det liggende layout, selvom rapportsiden har et layout, der er optimeret til telefoner.

Hvis du vil hente en rapport fra et dashboard, skal du trykke på ellipsen (...) i øverste højre hjørne af et felt og derefter trykke på **Åbn rapport**:
  
  ![Åbn rapport](./media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Det er ikke alle felter, der kan åbnes som rapporter. De felter, der oprettes ved at stille spørgsmål i feltet Spørgsmål og svar, kan for eksempel ikke åbnes i en rapport, når du trykker på dem.
  
## <a name="interact-with-reports"></a>Interager med rapporter
Når du har åbnet en rapport i appen, kan du begynde at arbejde med den. Du kan gøre mange ting med rapporten og dens data. I rapportfoden kan du finde de handlinger, der kan udføres i rapporten. Når du trykker på og trykker længe på de data, der vises i rapporten, kan du også opdele dataene.

### <a name="using-tap-and-long-tap"></a>Brug af tryk og langt tryk
Et tryk er det samme som et klik med musen. Så hvis du vil fremhæve rapporten på baggrund af et datapunkt, skal du trykke på det pågældende datapunkt.
Når du trykker på en udsnitsværdi, vælges værdien, og resten af rapporten opdeles efter den pågældende værdi.
Når du trykker på et link, en knap eller et bogmærke, vises den handling, der er defineret af rapportens forfatter.

Du har sikkert bemærket, at der vises en kant, når du trykker på et visuelt element. I øverste højre hjørne af kanten vises en ellipse (...). Hvis du trykker på ellipsen, får du vist en menu med handlinger, du kan udføre med det visuelle element:

![Visuelt element og menu](./media/mobile-reports-in-the-mobile-apps/report-visual-menu.png)

### <a name="tooltip-and-drill-actions"></a>Værktøjstip og analysehandlinger

Når du trykker længe (trykker og holder nede) på et datapunkt, vises der et værktøjstip, der præsenterer de værdier, som dette datapunkt repræsenterer:

![Værktøjstip](./media/mobile-reports-in-the-mobile-apps/report-tooltip.png)

Hvis rapportforfatteren har konfigureret et værktøjstip til rapportsider, erstattes standardværktøjstippet med værktøjstippet fra rapporten:

![Værktøjstip til rapportsider](./media/mobile-reports-in-the-mobile-apps/report-page-tooltip.png)

> [!NOTE]
> Værktøjstip til rapporter understøttes for enheder på mindst 640 pixel og 320 pixel billeder. Hvis enheden er mindre, bruger appen standardværktøjstip.

Rapportforfattere kan definere hierarkier i dataene og relationer mellem rapportsider. Hierarkier gør det muligt at foretage detailudledning, få vist flere detaljer og få detaljeadgang til en anden rapportside fra et visuelt element og en værdi. Så når du trykker længe på en værdi, vises de relevante analyseindstillinger i sidefoden sammen med værktøjstippet:

![Analysehandlinger](./media/mobile-reports-in-the-mobile-apps/report-drill-actions.png)


Når du trykker på en bestemt del af en visualisering og derefter trykker på indstillingen *detaljeadgang*, tager Power BI dig til en anden side i rapporten, der er filtreret, så den værdi, du har klikket på, vises. En forfatter af en rapport kan angive en eller flere muligheder for detaljeadgang, som hver især fører dig til en anden side. Hvis det er tilfældet, kan du vælge, hvilken mulighed du vil foretage detaljeadgang for. Du kan bruge knappen Tilbage til at komme tilbage til den forrige side.


Du kan få flere oplysninger ved at læse om, hvordan du [tilføjer detaljeadgang i Power BI Desktop](../../desktop-drillthrough.md).
   
   > [!IMPORTANT]
   > I Power BI-mobilapps aktiveres detailudledning i matrix-og tabelvisualiseringer kun via celleværdier, ikke via kolonne-eller rækkeoverskrifter.
   
   
   
### <a name="using-the-actions-in-the-report-footer"></a>Brug af handlingerne i rapportfoden
Fra rapportfoden kan du udføre flere handlinger på den aktuelle rapportside eller hele rapporten. Sidefoden giver hurtig adgang til de mest almindeligt anvendte handlinger. Du kan få adgang til andre handlinger ved at trykke på ellipseknappen (...):

![Rapportfod](./media/mobile-reports-in-the-mobile-apps/report-footer.png)

De handlinger, du kan udføre fra sidefoden, er:
- Nulstille rapportfilteret og tværgående fremhævninger til den oprindelige tilstand.
- Åbne samtaleruden for at få vist eller tilføje kommentarer til denne rapport.
- Åbne filterruden for at få vist og ændre det filter, der aktuelt anvendes på rapporten.
- Gennemgå alle siderne i rapporten. Når du trykker på sidenavnet, indlæses og præsenteres den pågældende side.
Du kan flytte mellem rapportsider ved at stryge fra kanten af skærmen til midten.
- Se alle rapporthandlinger.

#### <a name="all-report-actions"></a>Alle rapporthandlinger
Når du trykker på ellipseknappen (...) i rapportfoden, kan du få vist alle de handlinger, du kan udføre i en rapport:


![Alle rapporthandlinger](./media/mobile-reports-in-the-mobile-apps/report-all-actions.png)

Nogle af handlingerne kan være deaktiveret, da de er afhængige af de specifikke rapportegenskaber.
Eksempel:

**Filtrering efter aktuel placering** er aktiveret, hvis forfatteren af rapporten kategoriserede rapporten med geografiske data. Du kan få flere oplysninger ved at læse om [identifikation af geografiske data i en rapport](https://docs.microsoft.com/power-bi/desktop-mobile-geofiltering).

**Scan for at filtrere rapporten efter stregkode** er kun aktiveret, hvis datasættet i din rapport er mærket som **stregkode**. Du kan finde flere oplysninger om at [tagge stregkoder i Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-mobile-barcodes).

**Inviter** er kun aktiveret, hvis du har tilladelse til at dele denne rapport med andre. Du har kun tilladelse, hvis du er ejer af rapporten, eller hvis du har fået tilladelse til at dele den igen af ejeren.

**Anmærk og del** kan være slået fra, hvis din organisation har en [Intune-beskyttelsespolitik](https://docs.microsoft.com/intune/app-protection-policies), som forbyder deling fra en Power BI-mobilapp.

## <a name="next-steps"></a>Næste trin
* [Få vist og interager med Power BI-rapporter, der er optimeret til din telefon](mobile-apps-view-phone-report.md)
* [Opret en version af en rapport, der er optimeret til telefoner](../../desktop-create-phone-report.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

