---
title: Opret et link til en bestemt placering i Power BI-mobilappsene
description: Se, hvordan du kan oprette et dybt link til et bestemt dashboard, felt eller en rapport i Power BI-mobilappen ved hjælp af en URI (Uniform Resource Identifier).
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3be6882219e23a2d22ee03e6805ce3a1e8e08b8f
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34297716"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Opret et link til en bestemt placering i Power BI-mobilappsene
Du kan oprette og bruge en URI til at linke til en bestemt placering (et *dybt link*) i Power BI-mobilappsene på alle mobilplatformene: iOS, Android og Windows 10.

URI-links kan pege direkte på dashboards, felter og rapporter.

Destinationen for det dybe link bestemmer URI'ens format. Følg disse trin for at oprette dybe links til forskellige placeringer. 

## <a name="open-the-power-bi-mobile-app"></a>Åbn Power BI-mobilappen
Brug denne URI til at åbne Power BI-mobilappen på en hvilken som helst enhed:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Åbn på et bestemt dashboard
Denne URI åbner Power BI-mobilappen på et bestemt dashboard:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

Du kan finde det 36 tegn lange objekt-id for dashboardet ved at gå til det pågældende dashboard i Power BI-tjenesten (https://powerbi.com). Se eksempelvis den fremhævede del af denne URL-adresse:

https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**

Hvis dashboardet er i en anden gruppe end Mit arbejdsområde, skal du tilføje `&GroupObjectId=<36-character-group-id>` enten før eller efter dashboard-id'et. Eksempel: 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Bemærk &-tegnet mellem de to.

## <a name="open-to-a-specific-tile-in-focus"></a>Åbn med et bestemt felt i fokus
Denne URI åbner Power BI-mobilappen med et bestemt felt i fokus:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

Du kan finde de 36 tegn lange id'er til dashboards og felter ved at gå til dashboardet for Power BI-tjenesten (https://powerbi.com). og åbne feltet i fokustilstand. Se eksempelvis de fremhævede dele af denne URL-adresse:

https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

For dette felt ville URI'en være:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

Bemærk &-tegnet mellem de to.

Hvis dashboardet er i en anden gruppe end Mit arbejdsområde, skal du tilføje `&GroupObjectId=<36-character-group-id>`

## <a name="open-to-a-specific-report"></a>Åbn på en bestemt rapport
Denne URI åbner en bestemt rapport i Power BI-mobilappen:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

Du kan finde det 36 tegn lange objekt-id for rapporten ved at gå til den pågældende rapport i Power BI-tjenesten (https://powerbi.com). Se eksempelvis den fremhævede del af denne URL-adresse:

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>Åbn på en bestemt rapportside
Denne URI åbner en bestemt rapportside i Power BI-mobilappen:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

Rapportsiden hedder "ReportSection" efterfulgt af et tal. Igen skal du åbne rapporten i Power BI-tjenesten (https://powerbi.com)) og navigere til den pågældende rapportside. 

Se eksempelvis den fremhævede del af denne URL-adresse:

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>Åbn i fuldskærmsvisning
Tilføj parameteren med fed skrift for at åbne på en bestemt rapport i fuldskærmsvisning:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Eksempel: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Tilføj kontekst (valgfrit)
Du kan også tilføje kontekst i strengen. Hvis du får brug for at kontakte os, kan vi bruge denne kontekst til at filtrere vores data til din app. Tilføj `&context=<app-name>` i linket

Se eksempelvis den fremhævede del af denne URL-adresse: 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>Næste trin
Din feedback hjælper os med at afgøre, hvad der skal implementeres fremover, så husk at stemme på andre funktioner, du gerne vil se i Power BI-mobilapps. 

* [Power BI-apps til mobilenheder](mobile-apps-for-mobile-devices.md)
* Følg @MSPowerBI på Twitter
* Deltag i samtalen i [Power BI-communityet](http://community.powerbi.com/)
* [Introduktion til Power BI](service-get-started.md)

