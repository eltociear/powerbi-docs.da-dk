---
title: Installér Power BI Desktop optimeret til Power BI-rapportserver
description: Se, hvordan du kan installere Power BI Desktop optimeret til Power BI-rapportserver
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/03/2019
ms.openlocfilehash: a97c8125af46eae193f6c592d0b3c1153ae9b50c
ms.sourcegitcommit: 9bf3cdcf5d8b8dd12aa1339b8910fcbc40f4cbe4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/05/2019
ms.locfileid: "71968632"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Installér Power BI Desktop optimeret til Power BI-rapportserver

Hvis du vil oprette Power BI-rapporter for Power BI-rapportserver, skal du downloade og installere den Power BI Desktop-version, der er optimeret til Power BI-rapportserver. Dette er en anden udgivelse end Power BI Desktop, der bruges med Power BI-tjenesten. Versionen af Power BI Desktop til Power BI-tjenesten indeholder f.eks. prøveversionsfunktioner, som ikke findes i versionen Power BI-rapportserver, før de er generelt tilgængelige. Når du bruger denne udgivelse, sikrer du, at rapportserveren kan interagere med en kendt version af rapporterne og modellen. 

Den gode nyhed er, at du kan installere Power BI Desktop og Power BI Desktop optimeret til Power BI-rapportserver side om side på den samme computer.

## <a name="download-and-install-power-bi-desktop"></a>Download og installér Power BI Desktop

Den nemmeste måde til at sikre, at du har den nyeste version af Power BI Desktop optimeret til Power BI-rapportserver, er ved at starte fra webportalen på rapportserveren.

1. På webportalen Rapportserver skal du vælge pilen **Download** > **Power BI Desktop**.

    ![Download Power BI Desktop fra webportalen](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Eller gå til hjemmesiden for [Power BI-rapportserver](https://powerbi.microsoft.com/report-server/), og vælg **Avancerede indstillinger for download**.

2. På siden Download Center skal du vælge et sprog og derefter vælge **Download**.

3. Afhængigt af din computer skal du vælge: 

    - **PBIDesktopRS.msi** (32-bit-version) eller
    - **PBIDesktopRS_x64.msi** (64-bit-version).

1. Når du har downloadet installationsprogrammet, skal du køre installationsguiden til Power BI Desktop (september 2019).

2. Til sidst i installationsprocessen skal du vælge **Start Power BI Desktop**.

    Programmet starter automatisk, og du er klar til at gå i gang.

## <a name="verify-youre-using-the-correct-version"></a>Kontrollér, at du bruger den korrekte version
Det er nemt at kontrollere, at du bruger den korrekte version af Power BI Desktop: Se på startskærmen eller titellinjen i Power BI Desktop. Du kan se, at du har den rigtige version, fordi der står **Power BI Desktop (september 2019)** på titellinjen. Farverne i Power BI-logoet er også omvendt: gul på sort i stedet for sort på gul.

![Power BI Desktop – september 2019](media/install-powerbi-desktop/power-bi-report-server-desktop-sept-2019.png)

I versionen af Power BI Desktop til Power BI-tjenesten vises måned og årstal ikke på titellinjen.

## <a name="file-extension-association"></a>Tilknytning af filtypenavne
Hvis du installerer både Power BI Desktop og Power BI Desktop optimeret til Power BI-rapportserver på den samme computer, er den seneste installation af Power BI Desktop tilknyttet filtypenavnet .pbix. Det betyder, at den version af Power BI Desktop, du senest har installeret, startes, når du dobbeltklikker på en .pbix-fil.

Hvis du har installeret Power BI Desktop og derefter installerer Power BI Desktop optimeret til Power BI-rapportserver, åbnes alle .pbix-filer i Power BI Desktop optimeret til Power BI-rapportserver som standard. Hvis du foretrækker, at Power BI Desktop åbnes som standard, når du dobbeltklikker på en .pbix-fil, kan du geninstallere [Power BI Desktop fra Microsoft Store](http://aka.ms/pbidesktopstore).

Du kan til enhver tid starte med at åbne den version af Power BI Desktop, du vil bruge. Og derefter kan du åbne filen fra Power BI Desktop.

Hvis du redigerer en Power BI-rapport i Power BI-rapportserver eller opretter en ny Power BI-rapport fra webportalen, er det altid den korrekte version Power BI Desktop, der åbnes.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Power BI-rapporter i Power BI-rapportserver, i Power BI-tjenesten (http://app.powerbi.com) og i Power BI-mobilapps fungerer stort set ens, men nogle enkelte funktioner er forskellige.

### <a name="selecting-a-language"></a>Vælg et sprog

I forbindelse med Power BI Desktop, der er optimeret til Power BI-rapportserver, skal du vælge sproget, når du installerer appen. Du kan ikke ændre det bagefter, men du kan installere en version på et andet sprog.

### <a name="report-visuals-in-a-browser"></a>Rapportvisualiseringer i en browser

Rapporter i Power BI-rapportserver understøtter alle visualiseringer, herunder brugerdefinerede visualiseringer. Rapporter i Power BI-rapportserver understøtter ikke:

* R-visuals
* ArcGIS-kort
* Brødkrummer
* Prøveversionsfunktioner i Power Bi Desktop

### <a name="reports-in-the-power-bi-mobile-apps"></a>Rapporter i Power BI-mobilapps

Rapporter i Power BI-rapportserver understøtter al den grundlæggende funktionalitet i [Power BI-mobilappsene](../consumer/mobile/mobile-apps-for-mobile-devices.md), herunder:

* [Rapport med telefonlayout](../desktop-create-phone-report.md): Du kan optimere en rapport til Power BI-mobilapps. På din mobiltelefon har optimerede rapporter et særligt ikon ![ikon for layout af rapport på telefon](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png) og layout.
  
    ![Rapport optimeret til telefoner](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

Rapporter i Power BI-rapportserver understøtter ikke disse funktioner i Power BI-mobilappsene:

* R-visuals
* ArcGIS-kort
* Brugerdefinerede visuals
* Brødkrummer
* Geofiltrering eller stregkoder

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop til tidligere versioner af Power BI-rapportserver

Hvis du har en tidligere version af rapportserveren, skal du have den tilsvarende version af Power BI Desktop. Her er linket til at downloade en tidligere version.

- Microsoft Power BI Desktop ([Optimeret til Power BI-rapportserver – januar 2019](https://go.microsoft.com/fwlink/?linkid=2055039))

## <a name="next-steps"></a>Næste trin

Nu, hvor du har installeret Power BI Desktop, kan du begynde at oprette Power BI-rapporter.

[Opret en Power BI-rapport til Power BI-rapportserveren](quickstart-create-powerbi-report.md)  
[Hvad er Power BI-rapportserveren?](get-started.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
