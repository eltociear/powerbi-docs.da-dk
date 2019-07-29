---
title: Udforsk rapporter i Power BI-mobilappsene
description: Se, hvordan du kan få vist og interagere med rapporter i Power BI-mobilappsene på din telefon eller tablet. Du kan oprette rapporter i Power BI-tjenesten eller Power BI Desktop og derefter interagere med dem i mobilappsene.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/21/2019
ms.author: mshenhav
ms.openlocfilehash: 49ee06d544e409cadc6728d286cb841f5f4adec4
ms.sourcegitcommit: acd9f8212c9b0c6d3d8c4d56bba3c285246f3122
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/16/2019
ms.locfileid: "68230283"
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Udforsk rapporter i Power BI-mobilappsene
Gælder for:

| ![iPhone](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android-telefon](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android-tablet](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10-enheder](./media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone-telefoner |iPad-tablets |Android-telefoner |Android-tablets |Windows 10-enheder |

En Power BI-rapport er en interaktiv visning af dine data, hvor visualiseringer repræsenterer forskellige resultater og indsigter fra disse data. At få vist rapporter i Power BI-mobilapps er det sidste trin i en proces med tre trin.

1. [Opret rapporter i Power BI Desktop](../../desktop-report-view.md). Du kan endda [optimere en rapport til telefoner](mobile-apps-view-phone-report.md) i Power BI Desktop. 
2. Publicer disse rapporter i Power BI-tjenesten [(https://powerbi.com)](https://powerbi.com) eller [Power BI-rapportserver](../../report-server/get-started.md).  
3. Derefter kan du interagere med rapporterne i Power BI-mobilappsene.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Åbn en Power BI-rapport i mobilappen
Power BI-rapporter er gemt på forskellige steder i mobilappen, afhængigt af hvor du har fået dem. De kan være placeret under Apps, Delt med mig, Arbejdsområder(herunder Mit arbejdsområde) eller på en rapportserver. Nogle gange skal du gennem et relateret dashboard for at komme til en rapport. Andre gange vises de på en liste.

På lister og i menuer kan du finde et ikon ud for et rapportnavn, som hjælper dig med at forstå, at dette element er en rapport. 

![rapporter i Mit arbejdsområde](./media/mobile-reports-in-the-mobile-apps/reports-my-workspace.png) 

Der findes to ikoner til rapporter i Power BI - Mobil-apps:

* ![Ikonet Rapport](./media/mobile-reports-in-the-mobile-apps/report-default-icon.png) angiver en rapport, som vises i liggende retning i appen og har det samme udseende som i browseren.

* ![ikon for rapport, der er optimeret til telefoner](./media/mobile-reports-in-the-mobile-apps/report-phone-icon.png) angiver en rapport, der har mindst én rapportside, som er optimeret til telefoner og vises i stående format. 

Bemærk! Når du holder din telefon i liggende retning, får du altid det liggende layout, selv om rapportsiden har et layout, der er optimeret til telefoner. 

Hvis du vil hente en rapport fra et dashboard, skal du trykke på de tre prikker (...) i øverste højre hjørne af et felt > **Åbn rapport**.
  
  ![Åbn rapport](./media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Det er ikke alle felter, der kan åbnes i en rapport. De felter, der er oprettet ved at stille spørgsmål i feltet Spørgsmål og svar, kan for eksempel ikke åbnes i en rapport, når du trykker på dem. 
  
## <a name="interacting-with-reports"></a>Arbejde med rapporter
Når du har åbnet en rapport i appen, kan du begynde at arbejde med den. Du kan gøre mange ting med rapporten og dens data. I rapportfoden kan du finde handlinger, som du kan udføre på rapporten, og ved at trykke på og trykke længe på de data, der vises i rapporten, kan du opdele dataene.

### <a name="using-tap-and-long-tap"></a>Brug af tryk og langt tryk
Et tryk svarer til et klik med musen. Så hvis du vil fremhæve rapporten på baggrund af et datapunkt, skal du trykke på det pågældende datapunkt.
Hvis du trykker på værdien af et udsnit, vælges denne værdi, som bruges til opdeling af resten af rapporten. Hvis du trykker på et link, en knap eller et bogmærke, aktiveres den ud fra hvilken handling, der er defineret af forfatteren.

Du har sikkert bemærket, at der vises en kant, når du trykker på en visual. I øverste højre hjørne af kanten vises der tre prikker (...). Når du trykker på dem, vises en menu med handlinger, du kan udføre på denne visual.

![rapportvisual og menu](./media/mobile-reports-in-the-mobile-apps/report-visual-menu.png)

### <a name="tooltip-and-drill-actions"></a>Værktøjstip og analysehandlinger

Når du trykker længe (trykker og holder nede) på et datapunkt, vises der et værktøjstip, der præsenterer de værdier, som dette datapunkt repræsenterer. 

![værktøjstip til rapporter](./media/mobile-reports-in-the-mobile-apps/report-tooltip.png)

Hvis rapportforfatterens har konfigureret et værktøjstip til rapportsider, erstattes standardværktøjstippet med værktøjstippet fra rapporten.

![værktøjstip til rapportside](./media/mobile-reports-in-the-mobile-apps/report-page-tooltip.png)

> [!NOTE]
> Værktøjstip til rapporter understøttes for enheder, der har en størrelse på mere end 640 pixels og et billede på 320. Hvis enheden er mindre, bruger appen standardværktøjstips.

Rapportforfattere kan definere hierarkier i dataene og relationer mellem rapportsider. Et hierarki gør det muligt at foretage detailudledning, få vist flere detaljer og få detaljeadgang til en anden rapportside fra en visual og en værdi. Så når du trykker længe på en værdi, vises de relevante analyseindstillinger i bundteksten sammen med værktøjstippet. 

![rapportanalysehandlinger](./media/mobile-reports-in-the-mobile-apps/report-drill-actions.png)

Når der er mulighed for *detaljeadgang*, og du trykker på en bestemt del af en visualisering, føres du til en anden side i rapporten, der er filtreret, så den værdi, du har klikket på, vises.  En forfatter af en rapport kan angive en eller flere muligheder for detaljeadgang, som hver især fører dig til en anden side. Hvis det er tilfældet, kan du vælge, hvilken mulighed du vil. Du kan bruge knappen Tilbage til at komme tilbage til den forrige rapportside.

Læs om, hvordan du [tilføjer detaljeadgang i Power BI Desktop](../../desktop-drillthrough.md).
   
   > [!IMPORTANT]
   > I Power BI - Mobil-appen aktiveres detailudledning i matrix- og tabelvisuals kun via en celleværdi og ikke af kolonnerne og rækkeoverskrifterne.
   
   
   
### <a name="using-the-actions-in-the-report-footer"></a>Brug af handlingerne i rapportfoden
Rapportfoden indeholder handlinger, som du kan udføre på den aktuelle rapportside eller hele rapporten. Sidefoden har hurtig adgang til de mest nyttige handlinger, og der er adgang til alle handlinger fra de tre prikker (...).

![rapportfod](./media/mobile-reports-in-the-mobile-apps/report-footer.png)

De handlinger, du kan udføre fra sidefoden, er:
1) Nulstille rapportfilteret og tværgående fremhævninger til den oprindelige tilstand.
2) Åbne samtaleruden for at få vist eller tilføje kommentarer til denne rapport.
3) Åbne filterruden for at få vist og ændre det filter, der aktuelt anvendes på rapporten.
4) Få vist alle siderne i denne rapport. Når du trykker på sidenavnet, indlæses og præsenteres den pågældende side.
Det er muligt at flytte mellem rapportsider ved at stryge fra kanten af skærmen til midten.
5) Se alle rapporthandlinger.

#### <a name="all-report-actions"></a>Alle rapporthandlinger
Hvis du trykker på muligheden ... i rapportfoden, vises alle de handlinger, du kan udføre i en rapport. 

![rapport, alle handlinger](./media/mobile-reports-in-the-mobile-apps/report-all-actions.png)

Nogle af handlingerne kan være deaktiveret, da de er afhængige af de specifikke rapportegenskaber.
Eksempel:
1) **Filtrering efter aktuel placering** er aktiveret, hvis dataene i din rapport er kategoriseret af forfatteren med geografiske data. [Se, hvordan du identificerer geografiske data i din rapport](https://docs.microsoft.com/power-bi/desktop-mobile-geofiltering).
2) **Scan for at filtrere rapporten efter stregkode** er kun aktiveret, hvis datasættet i din rapport er mærket som stregkode. [Sådan mærkes stregkoder i Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-mobile-barcodes). 
3) **Inviter** er kun aktiveret, hvis du har tilladelse til at dele denne rapport med andre. Du har kun tilladelse, hvis du er ejer af rapporten, eller hvis du har fået tilladelse til at dele den igen af ejeren.
4) **Anmærk og del** kan være deaktiveret, hvis din organisation har er en [Intune-beskyttelsespolitik](https://docs.microsoft.com/intune/app-protection-policies), som forbyder deling fra Power BI - Mobil-appen. 

## <a name="next-steps"></a>Næste trin
* [Få vist og interager med Power BI-rapporter, der er optimeret til din telefon](mobile-apps-view-phone-report.md)
* [Opret en version af en rapport, der er optimeret til telefoner](../../desktop-create-phone-report.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

