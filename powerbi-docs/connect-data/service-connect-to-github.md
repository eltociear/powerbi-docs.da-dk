---
title: Opret forbindelse til GitHub med Power BI
description: GitHub til Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/25/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 1be2d3db9dbf341def86c087344ef7a32cd006a0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83337713"
---
# <a name="connect-to-github-with-power-bi"></a>Opret forbindelse til GitHub med Power BI
I denne artikel gennemgår vi, hvordan du trækker data fra din GitHub-konto med en skabelonapp i Power BI. Med skabelonappen oprettes et arbejdsområde med et dashboard, et sæt rapporter og et datasæt, der giver dig mulighed for at udforske dine GitHub-data. Med GitHub-appen til Power BI kan du få indsigt i dit GitHub-lager med data om bidrag, problemer, pullanmodninger og aktive brugere.

Når du har installeret skabelonappen, kan du ændre dashboardet og rapporten. Du kan derefter distribuere den som en app til kolleger i organisationen.

Opret forbindelse til [GitHub-skabelonappen](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.pbiapps-github), eller læs mere om [GitHub-integrationen](https://powerbi.microsoft.com/integrations/github) med Power BI.

Du kan også prøve [GitHub-selvstudiet](service-tutorial-connect-to-github.md). Her installeres rigtige GitHub-data om det offentlige lager til Power BI-dokumentationen.

>[!NOTE]
>Denne skabelonap kræver, at GitHub-kontoen har adgang til lageret. Flere oplysninger om kravene nedenfor.
>
>Denne skabelonapp understøtter ikke GitHub Enterprise. 

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]
   
3. Vælg **GitHub** \> **Hent nu**.
4. Vælg **Installér** under **Installér denne Power BI-app?** .
4. Vælg feltet **GitHub** i ruden **App**.

    ![GitHub-felt i Power BI](media/service-connect-to-github/power-bi-github-tile.png)

6. Under **Kom i gang med din nye app** skal du vælge **Opret forbindelse**.

    ![Kom i gang med din nye app](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

5. Angiv lagernavnet og lagerejeren. Herunder kan du se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams).
   
    ![Navn på GitHub-lager i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Angiv dine GitHub-legitimationsoplysninger (dette trin kan springes over, hvis du allerede er logget på med din browser). 
6. Som **godkendelsesmetode** skal du vælge **oAuth2** \> **Log på**. 
7. Følg skærmbillederne for GitHub-godkendelse. Giv GitHub-skabelonappen til Power BI tilladelse til GitHub-dataene.
   
   ![GitHub-godkendelse i Power BI](media/service-connect-to-github/github_authorize.png)
   
    Power BI opretter forbindelse til GitHub og dine data.  Dataene opdateres én gang om dagen. Når Power BI importerer dataene, får du vist indholdet af dit nye GitHub-arbejdsområde.

## <a name="modify-and-distribute-your-app"></a>Rediger og distribuer din app

Du har installeret GitHub-skabelonappen. Det betyder, at du også har oprettet GitHub-arbejdsområdet. I arbejdsområdet kan du ændre rapporten og dashboardet og derefter distribuere den som en *app* til kolleger i din organisation. 

1. Vælg pilen ud for navnet på arbejdsområdet i navigationsruden. Du kan se, at arbejdsområdet indeholder et dashboard og en rapport.

    ![App i navigationsruden](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

8. Vælg det nye [GitHub-dashboard](https://powerbi.microsoft.com/integrations/github).    
    ![GitHub-dashboard i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

3. Hvis du vil have vist alt indholdet i dit nye GitHub-arbejdsområde, skal du vælge **Arbejdsområder** > **GitHub**.
 
   ![GitHub-arbejdsområde i navigationsruden](media/service-connect-to-github/power-bi-github-left-nav.png)

    Denne visning er indholdslisten for arbejdsområdet. I øverste højre hjørne kan du se **Opdater app.** Når du er klar til at distribuere din app til dine kolleger, er det her, du starter. 

    ![GitHub-indholdsliste](media/service-connect-to-github/power-bi-github-content-list.png)

2. Vælg **rapporter** og **Datasæt** for at få vist andre elementer i arbejdsområdet.

    Læs, hvordan du [distribuerer apps](../collaborate-share/service-create-distribute-apps.md) til dine kolleger.

## <a name="whats-included-in-the-app"></a>Dette er inkluderet i prøveversionen
Følgende data er tilgængelige fra GitHub i Power BI:     

| Tabelnavn | Beskrivelse |
| --- | --- |
| Bidrag |Tabellen Bidrag indeholder de samlede tilføjelser, sletninger og bekræftelser, der er oprettet af bidragyderen, sammenlagt pr. uge. De 100 største bidragsydere er inkluderet. |
| Problemer |Angiver alle problemer i det valgte lager. Det indeholder beregninger som samlet og gennemsnitlig tid til at lukke et problem, samlet antal åbne problemer, samlet antal lukkede problemer. Denne tabel er tom, når der ikke er nogen problemer i lageret. |
| Pull-anmodninger |Denne tabel indeholder alle Pull-anmodningerne for lageret, og hvem der oprettede anmodningen. Den indeholder også beregninger om, hvor mange åbne, lukkede og samlede pullanmodninger der er, hvor lang tid det tog at udføre pullanmodningerne, og hvor lang tid den gennemsnitlige pullanmodning tog. Denne tabel er tom, når der ikke er nogen problemer i lageret. |
| Brugere |Denne tabel indeholder en liste over GitHub-brugere eller -bidragsydere, der har bidraget, arkiveret problemer eller løst pullanmodninger for det valgte lager. |
| Milepæle |Den har alle milepæle for det valgte lager. |
| DateTable |Denne tabel indeholder datoer fra i dag og fra tidligere år, der gør det muligt for dig at analysere dine GitHub-data efter dato. |
| ContributionPunchCard |Denne tabel kan bruges som et bidragshulkort for det valgte lager. Den viser anvendelser efter ugedag og klokkeslæt. Denne tabel er ikke forbundet til andre tabeller i modellen. |
| RepoDetails |Denne tabel indeholder oplysninger om det valgte lager. |

## <a name="system-requirements"></a>Systemkrav
* Den GitHub-konto, der har adgang til lageret.  
* Tilladelse givet til Power BI til GitHub-appen under det første logon. Se flere oplysninger herunder om tilbagekaldelse af adgang.  
* Tilstrækkelige API-kald til at hente og opdatere dataene.
>[!NOTE]
>Denne skabelonapp understøtter ikke GitHub Enterprise.

### <a name="de-authorize-power-bi"></a>Annuller godkendelsen af Power BI
Hvis du vil annullere godkendelsen af forbindelsen mellem Power BI og dit GitHub-lager, kan du tilbagekalde adgangen i GitHub. Du kan finde flere oplysninger under dette emne i [GitHub Hjælp](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth).

<a name="FindingParams"></a>
## <a name="finding-parameters"></a>Søgning efter parametre
Du kan finde ejeren og lageret ved at kigge på lageret i selve GitHub:

![Lagernavn og -ejer](media/service-connect-to-github/github_ownerrepo.png)

Den første del, "Azure", er ejeren, og den anden del, "azure-sdk-for-php", er selve lageret.  Du kan se disse samme to elementer i lagerets URL-adresse:

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>Fejlfinding
Hvis det er nødvendigt, kan du kontrollere dine GitHub-legitimationsoplysninger.  

1. Gå til GitHub-webstedet i et andet browservindue, og log på GitHub. Du kan se, at du er logget på, i øverste højre hjørne af GitHub-webstedet.    
2. I GitHub skal du navigere til URL-adressen på det lager, du vil have adgang til i Power BI. For eksempel: https://github.com/dotnet/corefx.  
3. Når du er tilbage i Power BI, kan du prøve at oprette forbindelse til GitHub. Brug navnene på lageret og lagerejeren af det samme lager i dialogboksen Konfigurer GitHub.  

## <a name="next-steps"></a>Næste trin

* [Selvstudium: Opret forbindelse til et GitHub-lager med Power BI](service-tutorial-connect-to-github.md)
* [Opret nye arbejdsområder i Power BI](../collaborate-share/service-create-the-new-workspaces.md)
* [Installér og brug apps i Power BI](../consumer/end-user-apps.md)
* [Opret forbindelse til Power BI-apps til eksterne tjenester](service-connect-to-services.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
