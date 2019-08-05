---
title: URL-adresser til hvidliste for Power BI
description: I denne artikel beskrives de slutpunkter, der skal være tilgængelige for kunder, der bruger Power BI.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/22/2018
ms.custom: seodec18
ms.openlocfilehash: 5b8cce3c62811509b5a2fa80bdde683c6278c7b2
ms.sourcegitcommit: bc688fab9288ab68eaa9f54b9b59cacfdf47aa2e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/30/2019
ms.locfileid: "68624174"
---
# <a name="power-bi-urls-for-whitelisting"></a>URL-adresser til hvidliste for Power BI

**Power BI-onlinetjenesten**, som også kaldes Power BI SaaS (Software as a Service), kræver forbindelse til internettet. Slutpunkterne nedenfor skulle kunne nås af de kunder, der bruger Power BI-onlinetjenesten.

Hvis du vil bruge Power BI-onlinetjenesten, skal du have adgang til at oprette forbindelse til de slutpunkter, der er markeret med **Krævet** i tabellen nedenfor, og de slutpunkter, som er markeret med **Krævet** på de websteder, der linkes til. Hvis linket til et eksternt websted refererer til en bestemt sektion, skal du kun se slutpunkterne i den sektion.

De slutpunker, der er markeret med **Valgfrit**, kan også placeres på en **hvidliste** til bestemte funktioner.

Power BI-onlinetjenesten kræver kun, at TCP-port 443 er åben for de viste slutpunkter.

Stjernen (*) repræsenterer alle niveauer under roddomænet, og vi bruger I/T, når oplysningerne ikke er tilgængelige. I kolonnen **Destination(er)** vises en liste med FQDN/domæner og links til eksterne websteder, som indeholder yderligere oplysninger om slutpunkter.

>[!Important]
>Oplysningerne i tabellen nedenfor repræsenterer ikke **U.S. Government-clouden**, **Germany-clouden** og **China-clouden**.

## <a name="authentication"></a>Godkendelse

Power BI er afhængigt af de krævede slutpunkter til Office 365-autorisation og identitetssektioner. Hvis du vil bruge Power BI, skal du kunne oprette forbindelse til slutpunkterne på det websted, der linkes til nedenfor.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Påkrævet:** Godkendelse og identitet | Se dokumentationen til Office 365 for at få oplysninger om [Office Online og almindelige URL-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office)  | I/T |

## <a name="general-site-usage"></a>Websted til generel brug

Hvis du vil bruge Power BI, skal du kunne oprette forbindelse til slutpunkterne fra tabellen og de websteder, der linkes til nedenfor.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Påkrævet:** Back-end-API'er | *.analysis.windows.net | TCP 443 |
| 2 | **Påkrævet:** Office 365-integration | Se dokumentationen til Office 365 for at få oplysninger om [Office Online og almindelige URL-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office) | I/T |
| 3 | **Påkrævet:** Portal | app.powerbi.com | TCP 443 |
| 4 | **Påkrævet:** Tjenestetelemetri | dc.services.visualstudio.com | TCP 443 |
| 5 | **Valgfrit:** Meddelelser til orientering | dynmsg.modpim.com | TCP 443 |
| 6 | **Valgfrit:** NPS-undersøgelser | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Administration

Hvis du vil udføre administrative funktioner i Power BI, skal du kunne oprette forbindelse til slutpunkterne på de websteder, der linkes til nedenfor.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Påkrævet:** Til administration af brugere og visning af overvågningslogge | Se dokumentationen til Office 365 for at få oplysninger om [Office Online og almindelige URL-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office) | I/T |
| | | |

## <a name="getting-data"></a>Hent data

Hvis du vil hente data fra specifikke datakilder, f.eks. OneDrive, skal du kunne oprette forbindelse til slutpunkterne i tabellen nedenfor. Adgang til yderligere internetdomæner og URL-adresser er muligvis påkrævet til specifikke datakilder i din organisation.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Påkrævet:** AppSource (interne eller eksterne apps i Power BI) | appsource.microsoft.com <br> *.s-microsoft.com  | TCP 443 |
| 2 | **Valgfrit:** Log på, og hent data til indholdspakker | Afhænger af anvendte indholdspakker | Afhænger af anvendte indholdspakker |
| 3 | **Valgfrit:** Importér filer fra et personligt OneDrive | S [Krævede URL-adresser og porte til OneDrive-webstedet](https://docs.microsoft.com/onedrive/required-urls-and-ports) | I/T |
| 4 | **Valgfrit:** 60 sekunders video med selvstudie om Power BI | *.doubleclick.net <br> *.ggpht.com <br> *.google.com <br> *.googlevideo.com <br> *.youtube.com <br> *.ytimg.com <br> fonts.gstatic.com | TCP 443 |
| 5 | **Valgfrit:** PubNub-streamingdatakilder | Se [dokumentationen til PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | I/T |
| | | |

## <a name="dashboard-and-report-integration"></a>Dashboard- og rapportintegration

Power BI afhænger af, at bestemte slutpunkter kan understøtte dine dashboards og rapporter. Du skal kunne oprette forbindelse til slutpunkterne i tabellen og de websteder, der linkes til, nedenfor.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Påkrævet:** Excel-integration | Se dokumentationen til Office 365 for at få oplysninger om [Office Online og almindelige URL-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office) | I/T |
| | | |

## <a name="custom-visuals"></a>Brugerdefinerede visualiseringer

Power BI afhænger af, at bestemte slutpunkter kan se og få adgang til brugerdefinerede visualiseringer. Du skal kunne oprette forbindelse til slutpunkterne i tabellen og de websteder, der linkes til, nedenfor.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Påkrævet:** Importér en brugerdefineret visualisering fra Marketplace-brugergrænsefladen eller fra en fil | *.azureedge.net <br> *.blob.core.windows.net <br> store.office.com | TCP 443 |
| 2 | **Valgfrit:** Bing Maps | bing.com <br> platform.bing.com <br> *.virtualearth.net | TCP 443 |
| 3 | **Valgfrit:** PowerApps | Se [sektionen Krævede tjenester](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) fra webstedet med systemkrav til PowerApps | I/T |
| 4 | **Valgfrit:** Visio | Se dokumentationen til Office 365 for at få oplysninger om [Office Online og almindelige URL-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office) samt [SharePoint Online og OneDrive for Business](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) | I/T |
| | | |

## <a name="related-external-sites"></a>Relaterede eksterne websteder

Power BI-links til andre relaterede websteder. Disse websteder omfatter dokumentation, support, forslag til nye funktioner og meget mere. Disse websteder påvirker ikke funktionaliteten i Power BI og kan føjes til en hvidliste efter behov.

| Række | Formål | Destination(er) | Port(e) |
| --- | --- | --- | --- |
| 1 | **Valgfrit:** Communitywebsted | community.powerbi.com <br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **Valgfrit:** Dokumentationswebsted | docs.Microsoft.com <br> img-prod-cms-rt-microsoft-com.akamaized.net <br> statics-uhf-eas.akamaized.net <br> cdnssl.clicktale.net <br> ing-district.clicktale.net | TCP 443 |
| 3 | **Valgfrit:** Downloadwebsted (til Power BI Desktop osv.) | download.microsoft.com | TCP 443 |
| 4 | **Valgfrit:** Eksterne omdirigeringer | aka.ms <br> go.microsoft.com | TCP 443 |
| 5 | **Valgfrit:** Websted med idéer og feedback| ideas.powerbi.com <br> powerbi.uservoice.com | TCP 443 |
| 6 | **Valgfrit:** Power BI-webstedet – landingsside, links til yderligere oplysninger, supportwebsted, downloadlinks, partnerpræsentation osv. | powerbi.Microsoft.com | TCP 443 |
| 7 | **Valgfrit:** Power BI Developer Center | dev.powerbi.com | TCP 443 |
| 8 | **Valgfrit:** Supportwebsted | support.powerbi.com <br> s3.amazonaws.com <br> *.olark.com <br> logx.optimizely.com <br> mscom.demdex.net <br> tags.tiqcdn.com | TCP 443 |
| | | |