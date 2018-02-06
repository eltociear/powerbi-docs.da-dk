---
title: "Grundlæggende oplysninger om webportalen Power BI-rapportserver"
description: "Læs om, hvordan du navigerer og arbejder i webportalen Power BI-rapportserver."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: 7d59531bfed80e854bc19b1df00aaf9cce7144d6
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="navigating-the-power-bi-report-server-web-portal"></a>Navigering i webportalen Power BI-rapportserver
Webportalen Power BI-rapportserver er en placering i det lokale miljø til visning, lagring og administration af dine Power BI-rapporter, dine mobile og sideinddelte rapporter og KPI'er.

![Webportalen Rapportserver](media/getting-around/report-server-web-portal.png)

Du kan se webportalen i alle moderne browsere. Rapporter og KPI'er er organiseret i mapper i webportalen, og du kan markere dem som favoritter. Du kan også gemme Excel-projektmapper der. Du kan starte de værktøjer, du skal bruge for at oprette rapporter, fra webportalen:

* **Power BI-rapporter** oprettet med Power BI Desktop: Se dem i webportalen og Power BI-mobilappsene.
* **Sideinddelte rapporter** oprettet i Report Builder: moderne udseende, dokumenter med fast layout, der er optimeret til udskrivning.
* **KPI'er** oprettet direkte i webportalen.

Du kan gennemse mapperne på rapportserveren eller søge efter specifikke rapporter i webportalen. Du kan få vist en rapport, dens generelle egenskaber og indsætte kopier af rapporten, der er registreret i rapporthistorikken. Afhængigt af dine rettigheder kan du muligvis også abonnere på rapporter og få dem leveret til din mailindbakke eller en delt mappe i filsystemet.

## <a name="web-portal-tasks"></a>Opgaver på webportalen
Du kan bruge webportalen til en række forskellige opgaver, herunder følgende:

* Få vist, søg i, udskriv og abonner på rapporter.
* Opret, sikr og vedligehold mappehierarkiet for at kunne organisere elementer på serveren.
* Konfigurer egenskaberne for rapportereksekvering, rapporthistorik og rapportparametre.
* Opret delte tidsplaner og delte datakilder for at gøre det lettere at håndtere tidsplaner og datakildeforbindelser.
* Opret datadrevne abonnementer for at kunne udrulle rapporter til en lang modtagerliste.
* Opret sammenkædede rapporter for at kunne genbruge og lave en eksisterende rapport om på forskellige måder.
* Download og åbn fælles værktøjer såsom Power BI Desktop (rapportserver), Report Builder og Mobile Report Publisher.
* [Opret KPI'er](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services).
* Send feedback eller forslag til nye funktioner.
* [Branding på webportalen](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal)
* [Arbejde med KPI'er](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)
* [Arbejde med delte datasæt](https://docs.microsoft.com/sql/reporting-services/work-with-shared-datasets-web-portal)

## <a name="web-portal-roles-and-permissions"></a>Roller og tilladelser til webportalen
Webportalen er et webprogram, der kører i en browser. Når du starter webportalen, afhænger de sider, links og indstillinger, som du kan se, af de tilladelser, du har på rapportserveren. Hvis du har en rolle med fuld tilladelse, har du adgang til samtlige programmenuer og -sider til administrering af en rapportserver. Hvis du har en rolle med tilladelse til at få vist og køre rapporter, kan du kun se de menuer og sider, der skal bruges til disse aktiviteter. Du kan have forskellige rolletildelinger til forskellige rapportservere eller endda til forskellige rapporter og mapper på en enkelt rapportserver.

## <a name="start-the-web-portal"></a>Start webportalen
1. Åbn din webbrowser.
   
    Se listen over [understøttede webbrowsere og versioner](browser-support.md).
2. Indtast webportalens URL-adresse i adresselinjen.
   
    URL-adressen er som standard *http://[ComputerName]/reports*.
   
    Rapportserveren er muligvis konfigureret til at bruge en bestemt port. For eksempel *http://[ComputerName]:80/reports* eller *http://[ComputerName]:8080/reports*.
   
    Du kan se, at webportalen deler elementer ind i disse kategorier:
   
   * KPI'er
   * Mobilrapporter
   * Sideinddelte rapporter
   * Power BI Desktop-rapporter
   * Excel-projektmapper
   * Datasæt
   * Datakilder
   * Ressourcer

## <a name="create-and-edit-power-bi-desktop-reports-pbix-files"></a>Opret og rediger Power BI Desktop-rapporter (.pbix-filer)
Du kan få vist, uploade, oprette, organisere og administrere tilladelser til Power BI Desktop-rapporter på webportalen.

### <a name="create-a-power-bi-desktop-report"></a>Opret en Power BI Desktop-rapport
1. Vælg **Ny** > **Power BI-rapport**.
   
    ![Opret ny Power BI-rapport.](media/getting-around/report-server-web-portal-new-powerbi-report.png)
   
    Power BI Desktop-appen åbnes.
   
    ![Power BI Desktop-app](media/getting-around/report-server-powerbi-desktop-start.png)
2. Opret din Power BI-rapport. Se [Hurtigstart: Power BI-rapporter](quickstart-create-powerbi-report.md), hvis du vil have flere oplysninger.
3. Upload din rapport til rapportserveren.

### <a name="edit-an-existing-power-bi-desktop-report"></a>Rediger en eksisterende Power BI Desktop-rapport
1. Klik på ellipsen (**...**) i øverste højre hjørne af rapportfeltet > **Rediger i Power BI Desktop**.
   
    ![Rediger i Power BI Desktop.](media/getting-around/report-server-web-portal-pbix-ellipsis.png)
   
    Power BI Desktop-appen åbnes.
2. Foretag dine ændringer, og gem... [hvordan?]

## <a name="create-and-edit-paginated-reports-rdl-files"></a>Opret og rediger sideinddelte rapporter (.rdl-filer)
Du kan få vist, uploade, oprette, organisere og administrere tilladelser til sideinddelte rapporter på webportalen.

### <a name="create-a-paginated-report"></a>Opret en sideinddelt rapport
1. Vælg **Ny** > **sideinddelt rapport**.
   
    Report Builder-appen åbnes.
   
    ![Ny Report Builder-rapport](media/getting-around/report-server-report-builder-new.png)
2. Opret din sideinddelte rapport. Se [Hurtigstart: Sideinddelte rapporter](quickstart-create-paginated-report.md), hvis du vil have flere oplysninger.
3. Upload din rapport til rapportserveren.

### <a name="edit-an-existing-paginated-report"></a>Rediger en eksisterende sideinddelt rapport
1. Klik på ellipsen (...) i øverste højre hjørne af rapportfeltet > **Rediger i Report Builder**.
   
    ![Rediger i Report Builder.](media/getting-around/report-server-web-portal-rdl-ellipsis.png)
   
    Report Builder-appen åbnes.
2. Foretag dine ændringer, og gem.

## <a name="upload-and-organize-excel-workbooks"></a>Upload og organisering af Excel-projektmapper
Du kan uploade, organisere og administrere tilladelser til Power BI Desktop-rapporter og Excel-projektmapper. De vil blive samlet i en gruppe i webportalen.

Projektmapperne gemmes på Power BI-rapportserveren, nogenlunde ligesom andre ressourcefiler. Når du vælger en af projektmapperne, bliver den downloadet lokalt på skrivebordet. Du kan gemme de ændringer, du har foretaget, ved at uploade den til rapportserveren igen.

## <a name="manage-items-in-the-web-portal"></a>Administrer elementer i webportalen
Power BI-rapportserver tilbyder detaljeret kontrol over de elementer, som du gemmer på webportalen. For eksempel kan du konfigurere abonnementer, cachelagring, øjebliksbilleder og sikkerhed for hver enkelte sideinddelte rapport.

1. Vælg ellipsen (...) i øverste højre hjørne, og vælg derefter **Administrer**.
   
    ![Vælg Administrer.](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Vælg den egenskab eller anden funktion, som du vil konfigurere.
   
    ![Vælg en egenskab.](media/getting-around/report-server-web-portal-manage-properties.png)
3. Vælg **Anvend**.

Læs mere om [arbejde med abonnementer i webportalen](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal).

## <a name="tag-your-favorite-reports-and-kpis"></a>Mærk dine favoritrapporter og -KPI'er
Du kan mærke rapporter og KPI'er, som skal være favoritter. De er lettere at finde, fordi de alle sammen er samlet i en enkelt Favoritter-mappe, både i webportalen og i Power BI-mobilappsene. 

1. Vælg ellipsen (**...**) i øverste højre hjørne af den KPI eller rapport, der skal være en favorit, og vælg **Føj til Favoritter**.
   
    ![Føj til Favoritter](media/getting-around/report-server-web-portal-favorite-ellipsis.png)
2. Vælg **Favoritter** på båndet på webportalen for at se den sammen med andre favoritter på siden Favoritter på webportalen.
   
    ![Vis Favoritter.](media/getting-around/report-server-web-portal-favorites.png)
   
    I Power BI-mobilappsene kan du nu få vist disse favoritter sammen med dine foretrukne dashboards fra Power BI-tjenesten.
   
    ![Visning af Favoritter i mobilappen.](media/getting-around/power-bi-iphone-faves-report-server.png)

## <a name="hide-or-view-items-in-the-web-portal"></a>Skjul eller vis elementer på webportalen
Du kan skjule elementer på webportalen, og du kan vælge at få vist skjulte elementer.

### <a name="hide-an-item"></a>Skjul et element
1. Vælg ellipsen (...) i øverste højre hjørne, og vælg derefter **Administrer**.
   
    ![Vælg Administrer](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Vælg **Skjul dette element**.
   
    ![Vælg Skjul](media/getting-around/report-server-web-portal-hide-property.png)
3. Vælg **Anvend**.

### <a name="view-hidden-items"></a>Vis skjulte elementer
1. Vælg **Felter** (eller **Liste**) i øverste højre hjørne > **Vis skjulte elementer**.
   
    Nu vises elementerne. De er gråtonede, men du kan stadig åbne og redigere dem.
   
    ![Vis skjulte elementer.](media/getting-around/report-server-web-portal-show-hidden-grayed.png)

## <a name="search-for-items"></a>Søg efter elementer
Du kan indtaste et søgeord, så får du vist alt, hvad du har adgang til. Resultaterne er inddelt i KPI'er, rapporter, datasæt og andre elementer. Du kan derefter interagere med resultaterne og føje dem til dine favoritter.  

![Søg efter elementer](media/getting-around/report-server-web-portal-search.png)

## <a name="move-or-delete-items-in-list-view"></a>Flyt eller slet elementer i Liste-visningen
Som standard vises indholdet på webportalen i Felt-visning.

Du kan skifte til Liste-visning, hvor det er nemt at flytte eller slette flere elementer ad gangen. 

1. Vælg **Felter** > **Liste**.
   
    ![Skift visninger.](media/getting-around/report-server-web-portal-list-view.png)
2. Vælg elementerne, og vælg derefter **Flyt** eller **Slet**.

## <a name="next-steps"></a>Næste trin
[Brugerhåndbog](user-handbook-overview.md)  
[Hurtigstart: Sideinddelte rapporter](quickstart-create-paginated-report.md)  
[Hurtigstart: Power BI-rapporter](quickstart-create-powerbi-report.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

