---
title: Integrer med rapportwebdelen i SharePoint Online
description: Med Power BI’s nye rapportwebdel til SharePoint Online kan du nemt kan integrere interaktive Power BI-rapporter på SharePoint Online-sider.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 05/16/2019
ms.openlocfilehash: c8789d47ed1b67f9fd6808865514120457a29dfe
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051278"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Integrer med rapportwebdelen i SharePoint Online

Med Power BI’s nye rapportwebdel til SharePoint Online kan du nemt kan integrere interaktive Power BI-rapporter på SharePoint Online-sider.

Når du bruger den nye **Integrer i SharePoint Online** indstilling, de integrerede rapporter er helt sikre, så du kan nemt oprette sikre interne webportaler.

## <a name="requirements"></a>Krav

For **Integrer i SharePoint Online** rapporter kan fungere, kræves følgende:

* En Power BI Pro-licens eller en [Power BI Premium-kapacitet (EM eller P SKU)](service-premium-what-is.md) med en licens til Power BI.
* Power BI-webdelen til SharePoint Online kræver [moderne sider](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Integrer din rapport
Hvis du vil integrere din rapport i SharePoint Online, skal du få rapportens URL-adresse og bruge den sammen med SharePoint Online nye Power BI-webdelen.

### <a name="get-a-report-url"></a>Hent en URL-adresse til rapporten

1. Få vist rapporten i Power BI.

2. Vælg den **fil** rullemenuen, vælg derefter **Integrer i SharePoint Online**.

    ![Filmenu](media/service-embed-report-spo/powerbi-file-menu.png)

3. Kopiér rapport URL-adressen fra dialogboksen.

    ![Integrer link](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Føj Power BI-rapporten til en SharePoint Online-side

1. Åbn siden target i SharePoint Online, og vælg **Rediger**.

    ![Side med SP-redigeringer](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    I Sharepoint Online, skal du vælge **+ ny** til at oprette en ny moderne webside.

    ![Ny SP-side](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Vælg den **+** rullelisten og derefter vælge den **Power BI**.

    ![Ny SP-webdel](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Vælg **Tilføj rapport**.

    ![Ny SP-rapport](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)  

4. Indsæt den tidligere kopieret rapportens URL-adresse til den **Power BI-rapportlinket** rude. Rapporten indlæses automatisk.

    ![Egenskaber for ny SP-webdel](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Vælg **Publicer** for at gøre ændringerne synlige for dine SharePoint Online-brugere.

    ![Indlæst SP-rapport](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="grant-access-to-reports"></a>Giv adgang til rapporter

Integration af en rapport i SharePoint Online ikke automatisk give brugerne tilladelse til at få vist rapporten – du skal angive visningstilladelser i Power BI.

> [!IMPORTANT]
> Sørg for at gennemse, hvem der kan få vist rapporten, i Power BI-tjenesten, og giv adgang til dem, der er ikke angivet.

Der er to måder til at give adgang til rapporten i Power BI. Den første måde, hvis du bruger en Office 365-gruppe til at oprette SharePoint Online-teamwebstedet, er at angive brugeren som medlem af den **apparbejdsområdet i Power BI-tjenesten** og **SharePoint-side**. Du kan finde flere oplysninger under [Administrer dit apparbejdsområde](service-manage-app-workspace-in-power-bi-and-office-365.md).

Den anden måde er at integrere en rapport i en app og dele den direkte med brugere:  

1. Forfatteren (skal være en Pro-bruger) opretter en rapport i et apparbejdsområde. Til at dele med **gratis Power BI-brugere**, app-arbejdsområdet skal angives som en **Premium-arbejdsområde**.

2. Forfatteren udgiver appen og installerer den. Forfatteren har brug at sikre, at du installerer appen for at få adgang til den URL-adresse til rapporten, der bruges til at integrere i SharePoint Online.

3. Nu skal alle slutbrugere også installere appen. Du kan også bruge den **installere appen automatisk** -funktionen, som du kan aktivere på den [Power BI-administrationsportalen](service-admin-portal.md)skal have den app, der er installeret på forhånd for slutbrugere.

   ![Installér appen automatisk](media/service-embed-report-spo/install-app-automatically.png)

4. Opretteren åbner appen og går til rapporten.

5. Forfatteren kopierer den integrerede rapport URL-adresse fra rapporten, hvor appen er installeret. **Brug ikke den oprindelige rapport URL-adresse fra app-arbejdsområdet.**

6. Opret et nyt teamwebsted i SharePoint Online.

7. Føj tidligere kopieret rapport URL-adressen til Power BI-webdelen.

8. Tilføj alle slutbrugere og/eller grupper, som skal bruge dataene på siden SharePoint Online og i den Power BI-app, du har oprettet.

    > [!NOTE]
    > **Brugerne eller grupperne skal have adgang både til siden SharePoint Online og rapporten i Power BI-appen for at få vist rapporten på SharePoint-siden.**

Nu kan slutbrugeren gå til teamwebstedet i SharePoint Online og få vist rapporterne på siden.

## <a name="multi-factor-authentication"></a>Multifaktorgodkendelse

Hvis du bliver bedt om at logge på ved hjælp af multifaktorgodkendelse i dit Power BI-miljø, bliver du muligvis bedt om at logge på med en sikkerhedsenhed for at bekræfte din identitet. Dette sker, hvis du ikke har logget SharePoint Online ved hjælp af multifaktorgodkendelse, men dit Power BI-miljø kræver en sikkerhedsenhed for at validere en konto.

> [!NOTE]
> Azure Active Directory 2.0 understøtter ikke Multi-Factor Authentication til Azure - brugere får vist en fejlmeddelelse. Hvis brugeren logger på SharePoint Online igen ved hjælp af sin sikkerhedsenhed, kan vedkommende muligvis få vist rapporten.

## <a name="web-part-settings"></a>Indstillinger for webdele

Nedenfor er de indstillinger, kan du justere til Power BI-webdelen til SharePoint Online.

![Egenskaber for SP-webdel](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Egenskab | Beskrivelse |
| --- | --- |
| Sidenavn |Angiver den webdelen standardside. Vælg en værdi på rullelisten. Hvis der ikke vises nogen sider, har rapporten enten kun én side, eller den URL-adresse, du har indsat, indeholder et sidenavn. Fjern rapportsektion fra URL-adressen for at vælge en bestemt side. |
| Vis |Justerer, hvordan rapporten passer ind i SharePoint Online-siden. |
| Vis navigationsruden |Viser eller skjuler ruden Sidenavigation. |
| Vis filterruden |Viser eller skjuler filterruden. |

## <a name="reports-that-do-not-load"></a>Rapporter, der ikke indlæses

Hvis rapporten ikke indlæses i Power BI-webdelen, kan du se følgende meddelelse:

![Dette indhold er ikke tilgængelig meddelelse](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Der er to almindelige årsager til denne meddelelse.

1. Du har ikke adgang til rapporten.
2. Rapporten blev slettet.

Kontakt ejeren af SharePoint Online-side for at hjælpe med at løse problemet.

## <a name="licensing"></a>Licensering

Brugere, der ser en rapport i SharePoint, skal enten have en **Power BI Pro-licens**, eller indholdet skal være i et arbejdsområde, der er i en **[Power BI Premium-kapacitet (EM- eller P-SKU)](service-admin-premium-purchase.md)** .

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

* Fejl: "Der opstod en fejl. Prøv at logge af og på igen, og besøg derefter denne side igen. Korrelations-ID: udefineret. HTTP-svarstatus: 400, serverfejlkode 10001. Meddelelse: Manglende opdateringstoken"
  
  Hvis du modtager denne fejl, kan du prøve at udføre et af fejlfindingstrinnene nedenfor.
  
  1. Log af SharePoint, og log på igen. Sørg for at lukke alle browservinduer, før du logger på igen.

  2. Hvis din brugerkonto kræver multifaktorgodkendelse (MFA), derefter logge på SharePoint ved hjælp af enheden MFA (telefonapp, chipkort osv.).
  
  3. Azure B2B-gæstebrugerkonti understøttes ikke. Brugerne kan se det Power BI-logo, der viser, at delen indlæses, men den viser ikke rapporten.

* Power BI understøtter ikke de samme oversatte sprog som SharePoint Online. Derfor ser du muligvis ikke den korrekte oversættelse i den integrerede rapport.

* Der kan opstå tekniske problemer, hvis du bruger Internet Explorer 10. Du kan se de [browsere, der understøttes af Power BI](consumer/end-user-browsers.md) og [Office 365](https://products.office.com/office-system-requirements#Browsers-section).

* Power BI-webdelen er ikke tilgængelig til [nationale cloudmiljøer](https://powerbi.microsoft.com/clouds/).

* Den klassiske SharePoint-server understøttes ikke med denne webdel.

* [URL-filtre](service-url-filters.md) understøttes ikke med SPO-webdelen.

## <a name="next-steps"></a>Næste trin

* [Tillad eller forbyd, at slutbrugere opretter moderne webstedssider](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
* [Opret og distribuer en app i Power BI](service-create-distribute-apps.md)  
* [Del et dashboard med kolleger og andre](service-share-dashboards.md)  
* [Hvad er Power BI Premium?](service-premium-what-is.md)
* [Integrer en rapport på en sikker portal eller et websted](service-embed-secure.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)