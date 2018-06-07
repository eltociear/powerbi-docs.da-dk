---
title: Administrer indhold på webportalen til Power BI-rapportserveren
description: Læs om, hvordan du administrerer indhold på webportalen til Power BI-rapportserveren.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/24/2018
ms.author: maggies
ms.openlocfilehash: 9b896c9db6c1368c5e435df21c28cd99b8dda15f
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721702"
---
# <a name="manage-content-in-the-web-portal"></a>Administrer indhold på webportalen 
Webportalen Power BI-rapportserver er en placering i det lokale miljø til visning, lagring og administration af dine Power BI-rapporter, dine mobile og sideinddelte rapporter og KPI'er.

![Webportalen Rapportserver](media/getting-around/report-server-web-portal.png)

Du kan se webportalen i alle moderne browsere. Rapporter og KPI'er er organiseret i mapper i webportalen, og du kan markere dem som favoritter. Du kan også gemme Excel-projektmapper der. Du kan starte de værktøjer, du skal bruge for at oprette rapporter, fra webportalen:

* **Power BI-rapporter** oprettet med Power BI Desktop: Se dem i webportalen og Power BI-mobilappsene.
* **Sideinddelte rapporter** oprettet i Report Builder: moderne udseende, dokumenter med fast layout, der er optimeret til udskrivning.
* **KPI'er** oprettet direkte i webportalen.

Du kan gennemse mapperne på rapportserveren eller søge efter specifikke rapporter i webportalen. Du kan få vist en rapport, dens generelle egenskaber og indsætte kopier af rapporten, der er registreret i rapporthistorikken. Afhængigt af dine rettigheder kan du muligvis også abonnere på rapporter og få dem leveret til din mailindbakke eller en delt mappe i filsystemet.

## <a name="web-portal-roles-and-permissions"></a>Roller og tilladelser til webportalen
Programmet til webportalen kører i en browser. Når du starter webportalen, afhænger de sider, links og indstillinger, som du kan se, af de tilladelser, du har på rapportserveren. Hvis du har en rolle med fuld tilladelse, har du adgang til samtlige programmenuer og -sider til administrering af en rapportserver. Hvis du har en rolle med tilladelse til at få vist og køre rapporter, kan du kun se de menuer og sider, der skal bruges til disse aktiviteter. Du kan have forskellige rolletildelinger til forskellige rapportservere eller endda til forskellige rapporter og mapper på en enkelt rapportserver.

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

## <a name="manage-items-in-the-web-portal"></a>Administrer elementer i webportalen
Power BI-rapportserver tilbyder detaljeret kontrol over de elementer, som du gemmer på webportalen. For eksempel kan du konfigurere abonnementer, cachelagring, øjebliksbilleder og sikkerhed for hver enkelte sideinddelte rapport.

1. Vælg ellipsen (...) i øverste højre hjørne, og vælg derefter **Administrer**.
   
    ![Vælg Administrer.](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Vælg den egenskab eller anden funktion, som du vil konfigurere.
   
    ![Vælg en egenskab.](media/getting-around/report-server-web-portal-manage-properties.png)
3. Vælg **Anvend**.

Læs mere om [arbejde med abonnementer i webportalen](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal).

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI-rapportserveren?](get-started.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

