---
title: 'Project Online: Opret forbindelse til data via Power BI Desktop'
description: 'Project Online: Opret forbindelse til data via Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6cae9bdfbb89e8c3a11e8ee3fec45327296319b3
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34288906"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: Opret forbindelse til data via Power BI Desktop
Du kan oprette forbindelse til data i Project Online via Power BI Desktop.

### <a name="step-1-download-power-bi-desktop"></a>Trin 1: Download Power BI Desktop
1. [Download Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662), og kør derefter installationsprogrammet for at få **Power BI Desktop** på din computer.

### <a name="step-2-connect-to-project-online-with-odata"></a>Trin 2: Opret forbindelse til Project Online med OData
1. Åbn **Power BI Desktop**.
2. På *velkomstskærmen* skal du vælge **Hent data**.
3. Vælg **OData-feed**, og vælg **Opret forbindelse**.
4. Angiv adressen til dit OData-feed i feltet til URL-adressen, og klik derefter på OK.
   
   Hvis adressen til dit Project Web App-websted ligner adressen https://\<tenantname\>.sharepoint.com/sites/pwa, skal den adresse, du indtaster til dit OData-feed, være https://\<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata.
   
   I dette eksempel bruger vi https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop beder dig om at blive godkendt med din Office 365-konto. Vælg Organisationskonto, og angiv derefter dine legitimationsoplysninger.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Bemærk, at der som minimum skal være adgang til Oversigtsfremviser på Project Web App-webstedet via den konto, du bruger til at oprette forbindelse til OData-feedet. 

Herfra kan du vælge, hvilke tabeller du vil oprette forbindelse til, og lave en forespørgsel.  Vil du gerne vide, hvordan du kommer i gang?  I følgende blogindlæg vises, hvordan du opretter et diagram for en statusrapport ud fra dine Project Online-data.  I blogindlægget henvises der til, hvordan du kan bruge Power Query til at oprette forbindelse til Project Online, men det gælder også for Power BI Desktop.

[Opret diagrammer for statusrapporter til Project ved hjælp af Power Pivot og Power-forespørgsel](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

