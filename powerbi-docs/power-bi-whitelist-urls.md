---
title: URL-adresser i Power BI
description: Slutpunkter skal kunne nås af de kunder, der bruger Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/13/2018
ms.openlocfilehash: 8e29fa0c9471bb865619102247f38776208c3d87
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/14/2018
ms.locfileid: "40101121"
---
# <a name="power-bi-urls"></a>URL-adresser i Power BI

**Power BI-onlinetjenesten**, som også kaldes Power BI SaaS (Software as a Service), kræver forbindelse til internettet. Slutpunkterne nedenfor skulle kunne nås af de kunder, der bruger Power BI-onlinetjenesten.

Hvis du vil bruge Power BI-onlinetjenesten, skal du have adgang til at oprette forbindelse til de slutpunkter, der er markeret med **Krævet** i tabellen nedenfor, og de slutpunkter, som er markeret med **Krævet** på de websteder, der linkes til. Hvis linket til et eksternt websted refererer til en bestemt sektion, skal du kun se slutpunkterne i den sektion.

De slutpunker, der er markeret med **Valgfrit**, kan også placeres på en **hvidliste** til bestemte funktioner.

Power BI-onlinetjenesten kræver kun, at TCP-port 443 er åben for de viste slutpunkter.

Stjernen (*) repræsenterer alle niveauer under roddomænet, og vi bruger I/T, når oplysningerne ikke er tilgængelige. I kolonnen **Destination(er)** vises en liste med FQDN/domæner og links til eksterne websteder, som indeholder yderligere oplysninger om slutpunkter.

>[!Important]
>Oplysningerne i tabellen nedenfor repræsenterer ikke **U. S. Government-clouden**, **Germany-clouden** og **China-clouden**.

## <a name="authentication"></a>Godkendelse

Power BI er afhængigt af de krævede slutpunkter til Office 365-autorisation og identitetssektioner. Hvis du vil bruge Power BI, skal du kunne oprette forbindelse til slutpunkterne på det websted, der linkes til nedenfor.

| Række | Formål | Destination(er) | Port(e) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Påkrævet:** Autentifikation og identitet | Se [sektionen Office 365-autentifikation og identitet](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_identity) fra webstedet med hvidlistning til Office 365 | I/T |

## <a name="general-site-usage"></a>Websted til generel brug

Hvis du vil bruge Power BI, skal du kunne oprette forbindelse til slutpunkterne fra tabellen og de websteder, der linkes til nedenfor.

| Række | Formål | Destination(er) | Port(e) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Krævet:** Backend-API'er | *.analysis.windows.net | TCP 443 |
| 2 | **Krævet:** Office 365-integration | Se [sektionen Office 365-portal og delt](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) fra Office 365-webstedet med hvidlistning | I/T |
| 3 | **Krævet:** Portal | app.powerbi.com | TCP 443 |
| 4 | **Krævet:** Tjenestetelemetri | dc.services.visualstudio.com | TCP 443 |
| 5 | **Valgfrit:** Meddelelser til orientering | dynmsg.modpim.com | TCP 443 |
| 6 | **Valgfrit:** NPS-undersøgelser | nps.onyx.azure.net | TCP 443 |

## <a name="administration"></a>Administration

Hvis du vil udføre administrative funktioner i Power BI, skal du kunne oprette forbindelse til slutpunkterne på de websteder, der linkes til nedenfor.

| Række | Formål | Destination(er) | Port(e) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Krævet:** Til administration af brugere og visning af overvågningslogge | Se [sektionen Office 365-portal og delt](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) fra Office 365-webstedet med hvidlistning | I/T |

## <a name="get-data"></a>Hent data

Hvis du vil kunne hente data fra specifikke datakilder, f.eks. OneDrive, skal du kunne oprette forbindelse til slutpunkterne i tabellen nedenfor.

| Række | Formål | Destination(er) | Port(e) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Krævet:** AppSource (interne eller eksterne apps i Power BI) | appsource.microsoft.com | TCP 443 |
| 2 | **Valgfrit:** Importér filer fra en personlig OneDrive | S [Krævede URL-adresser og porte til OneDrive-webstedet](https://support.office.com/en-ie/article/required-urls-and-ports-for-onedrive-ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a) | I/T |
| 3 | **Valgfrit:** 60 sekunders video med selvstudie i Power BI | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 4 | **Valgfrit:** PubNub-streamingdatakilder | Se [dokumentationen til PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | I/T |

## <a name="dashboard-and-report-integration"></a>Dashboard- og rapportintegration 

Power BI afhænger af, at bestemte slutpunkter kan understøtte dine dashboards og rapporter. Du skal kunne oprette forbindelse til slutpunkterne i tabellen og de websteder, der linkes til, nedenfor.

| Række | Formål | Destination(er) | Port(e) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Krævet:** Excel-integration | Se [sektionen Office Online](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) fra webstedet til hvidlistning til Office 365 | I/T |

## <a name="custom-visuals"></a>Brugerdefinerede visuelle elementer

Power BI afhænger af, at bestemte slutpunkter kan se og få adgang til brugerdefinerede visualiseringer. Du skal kunne oprette forbindelse til slutpunkterne i tabellen og de websteder, der linkes til, nedenfor.

| Række | Formål | Destination(er) | Port(e) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Krævet:** Importér en brugerdefineret visualisering fra Marketplace-brugergrænsefladen og en fil | *.microsoft.com </br> *.bing.com </br> *.msecnd.net </br> *.osi.office.net </br> *.azureedge.net </br> ajax.aspnetcdn.com </br> nexus.ensighten.com </br> store.office.com | TCP 443 |
| 2 | **Valgfrit:** Bing Maps | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **Valgfrit:** PowerApps | Se [sektionen Krævede tjenester](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) fra webstedet med systemkrav til PowerApps | I/T |
| 4 | **Valgfrit:** Visio | Se [sektionen Office Online](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) fra webstedet til hvidlistning til Office 365 | I/T |