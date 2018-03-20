---
title: Integrer med rapportwebdelen i SharePoint Online
description: "Med Power BI’s nye rapportwebdel til SharePoint Online kan du nemt kan integrere interaktive Power BI-rapporter på SharePoint Online-sider."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/19/2017
ms.author: maghan
LocalizationGroup: Share your work
ms.openlocfilehash: 11b1d2c1c5205fd1346e9350b0a814b7d76d4135
ms.sourcegitcommit: 85d18d9f11a4ce4d4ed65e4544d13da6c2d9b1d4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/08/2018
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Integrer med rapportwebdelen i SharePoint Online

Med Power BI’s nye rapportwebdel til SharePoint Online kan du nemt kan integrere interaktive Power BI-rapporter på SharePoint Online-sider.

Når du bruger den nye indstilling **Integrer i SharePoint Online**, er de integrerede rapporter helt sikre, så du kan nemt oprette sikre interne webportaler.

## <a name="requirements"></a>Krav

Der er et par krav for, at **Integrer i SharePoint Online**-rapporter kan fungere.

* Power BI-webdelen til SharePoint Online kræver [moderne sider](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Integrer din rapport

Hvis du vil integrere din rapport i SharePoint Online, skal du først hente URL-adressen til rapporten og derefter bruge denne URL-adresse med den nye Power BI-webdel i SharePoint Online.

### <a name="get-a-url-to-your-report"></a>Hent en URL-adresse til rapporten

1. Få vist rapporten i Power BI-tjenesten.

2. Vælg menuen **Filer**.

3. Vælg **Integrer i SharePoint Online**.
   
    ![](media/service-embed-report-spo/powerbi-file-menu.png)

4. Kopiér URL-adressen fra dialogboksen.

    ![](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

   > [!NOTE]
   > Du kan også bruge den URL-adresse, der vises i din webbrowsers adresselinje, når du får vist en rapport. Den URL-adresse indeholder den rapportside, du ser i øjeblikket. Du skal fjerne rapportsektionen fra URL-adressen, hvis du vil bruge en anden side.

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Føj Power BI-rapporten til en SharePoint Online-side

1. Åbn den ønskede side i SharePoint Online, og vælg **Rediger**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Eller opret en ny moderne webside ved at vælge **+ Ny** i SharePoint Online.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Vælg **+**, og vælg webdelen **Power BI**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Vælg **Tilføj rapport**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)

4. Indsæt rapportens URL-adresse i ruden med egenskaber. Dette er den URL-adresse, du har kopieret fra trinnene ovenfor. Rapporten indlæses automatisk.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Vælg **Publicer** for at gøre ændringerne synlige for dine SharePoint Online-brugere.

    ![](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="granting-access-to-reports"></a>Giv adgang til rapporter

Integrering af en rapport i SharePoint Online giver ikke automatisk brugere tilladelse til at få vist rapporten. Tilladelserne til at få vist rapporten angives i Power BI-tjenesten.

> [!IMPORTANT]
> Sørg for at gennemse, hvem der kan få vist rapporten, i Power BI-tjenesten, og giv adgang til dem, der er ikke angivet.

Du kan give adgang til rapporten i Power BI-tjenesten på to måder. Hvis du bruger en Office 365-gruppe til at oprette SharePoint Online-teamwebstedet, kan du angive brugeren som medlem af apparbejdsområdet i Power BI-tjenesten. Dette sikrer, at brugerne kan få vist indholdet af den pågældende gruppe. Du kan finde flere oplysninger under [Opret og distribuer en app i Power BI](service-create-distribute-apps.md).

Ellers kan du også give brugerne adgang til din rapport ved at gøre følgende.

1. Føj et felt fra rapporten til et dashboard.

2. Del dashboardet med de brugere, der skal have adgang til rapporten. Du kan finde flere oplysninger i [Del et dashboard med kolleger og andre](service-share-dashboards.md).

## <a name="web-part-settings"></a>Indstillinger for webdele

Nedenfor findes en beskrivelse af de indstillinger, der kan tilpasses til Power BI-webdelen til SharePoint Online.

![](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Egenskab | Beskrivelse |
| --- | --- |
| Sidenavn |Angiver den standardside, der vises af webdelen. Vælg en værdi på rullelisten. Hvis der ikke vises nogen sider, har rapporten enten kun én side, eller den URL-adresse, du har indsat, indeholder et sidenavn. Fjern rapportsektion fra URL-adressen for at vælge en bestemt side. |
| Vis |Indstillingen til at justere, hvordan rapporten er tilpasset SharePoint Online-siden. |
| Vis navigationsruden |Viser eller skjuler ruden Sidenavigation. |
| Vis filterruden |Viser eller skjuler filterruden. |

## <a name="multi-factor-authentication"></a>Multifaktorgodkendelse

Hvis du bliver bedt om at logge på ved hjælp af multifaktorgodkendelse i dit Power BI-miljø, bliver du muligvis bedt om at logge på med en sikkerhedsenhed for at bekræfte din identitet. Dette kan ske, hvis du ikke loggede på SharePoint Online ved hjælp af multifaktorgodkendelse, men dit Power BI-miljø kræver en konto, der er godkendt af en sikkerhedsenhed.

> [!NOTE]
> Multifaktorgodkendelse understøttes endnu ikke med Azure Active Directory 2.0. Brugerne modtager en meddelelse med ordet *fejl*. Hvis brugeren logger på SharePoint Online igen ved hjælp af sin sikkerhedsenhed, kan vedkommende muligvis få vist rapporten.

## <a name="reports-that-do-not-load"></a>Rapporter, der ikke indlæses

Rapporten indlæses muligvis ikke i Power BI-webdelen, og du kan få vist følgende meddelelse.

*Dette indhold er ikke tilgængeligt.*

![](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Der er to almindelige årsager til denne meddelelse.

1. Du har ikke adgang til rapporten.
2. Rapporten blev slettet.

Du skal kontakte ejeren af SharePoint Online-siden for at få hjælp til at udbedre problemet.

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

* **Fejl: "Der opstod en fejl, prøv at logge af og på igen og derefter besøge denne side igen. Korrelations-id: udefineret, HTTP-svarstatus: 400, serverens fejlkode 10001, meddelelse: manglende opdateringstoken"**
  
  Hvis du får vist denne fejl, kan du prøve en af følgende fremgangsmåder.
  
  1. Log af SharePoint, og log på igen. Sørg for at lukke alle browservinduer, før du logger på igen.

  2. Hvis din brugerkonto kræver multifaktorgodkendelse, skal du sikre, at du logger på SharePoint ved hjælp af din multifaktorgodkendelsesenhed (telefonapp, chipkort osv.)

* Power BI understøtter ikke de samme oversatte sprog som SharePoint Online. Derfor ser du muligvis ikke den korrekte oversættelse i den integrerede rapport.

* Der kan opstå tekniske problemer, hvis du bruger Internet Explorer 10. Du kan se de [browsere, der understøttes af Power BI](service-browser-support.md) og [Office 365](https://products.office.com/office-system-requirements#Browsers-section).

* Power BI webdelen er ikke tilgængelig i [nationale cloudmiljøer](https://powerbi.microsoft.com/en-us/clouds/). 

## <a name="next-steps"></a>Næste trin

[Tillad eller forbyd, at slutbrugere opretter moderne webstedssider](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
[Opret og distribuer en app i Power BI](service-create-distribute-apps.md)  
[Del et dashboard med kolleger og andre](service-share-dashboards.md)  
[Power BI Premium – hvad er det?](service-premium.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/) 

