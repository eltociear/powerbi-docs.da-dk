---
title: Opret forbindelse til GitHub med Power BI
description: GitHub til Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: b0f2bd53f1d8b82b70072446723c2ca3723eeacd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608422"
---
# <a name="connect-to-github-with-power-bi"></a>Opret forbindelse til GitHub med Power BI
Denne artikel fører dig gennem trække dine data fra din GitHub-konto med en app i Power BI-skabelon. Appen skabelon opretter et arbejdsområde med et dashboard, et sæt af rapporter og et datasæt, så du kan udforske dine GitHub-data. GitHub-app til Power BI giver dig indsigt i dine GitHub-lager, også kendt som lager med data om bidrag, problemer, pull-anmodninger og aktive brugere.

Når du har installeret appen skabelon, kan du ændre dashboardet og rapporten. Derefter kan du distribuere den som en app til kollegaer i din organisation.

Opret forbindelse til den [GitHub skabelonapp](https://app.powerbi.com/getdata/services/github) eller Læs mere om den [GitHub-integration](https://powerbi.microsoft.com/integrations/github) med Power BI.

Du kan også prøve de [GitHub selvstudium](service-tutorial-connect-to-github.md). Den installerer real GitHub-data om det offentlige lager til Power BI-dokumentationen.

>[!NOTE]
>Appen skabelon kræver GitHub-konto skal have adgang til lageret. Flere oplysninger om kravene nedenfor.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]
   
3. Vælg **GitHub** \> **Hent det nu**.
4. I **installere denne App i Power BI?** Vælg **installere**.
4. I den **Apps** skal du vælge den **GitHub** felt.

    ![GitHub-felt i Power BI](media/service-connect-to-github/power-bi-github-tile.png)

6. I **Kom i gang med din nye app**, skal du vælge **forbinde data**.

    ![Kom i gang med din nye app](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

5. Angiv lagernavnet og lagerejeren. Herunder kan du se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams).
   
    ![Navn på GitHub-lager i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Angiv dine GitHub-legitimationsoplysninger (dette trin kan springes over, hvis du allerede er logget på med din browser). 
6. Som **Godkendelsesmetode** skal du vælge **oAuth2** \> **Log på**. 
7. Følg skærmbillederne for GitHub-godkendelse. Giv GitHub til Power BI-skabelon apptilladelse til GitHub-dataene.
   
   ![Godkend til Power BI GitHub](media/service-connect-to-github/github_authorize.png)
   
    Powerbi opretter forbindelse til GitHub og dine data.  Dataene opdateres én gang om dagen. Når Power BI har importeret dataene, kan du se indholdet af det nye GitHub-arbejdsområde.

## <a name="modify-and-distribute-your-app"></a>Rediger og Distribuer din app

Du har installeret appen GitHub-skabelon. Det betyder, at du har også oprettet GitHub app-arbejdsområdet. Du kan ændre rapporten og dashboardet i arbejdsområdet, og derefter distribuere den som en *app* til kollegaer i din organisation. 

1. Vælg pilen ud for Arbejdsområdenavnet på i den venstre navigationslinje. Du kan se arbejdsområdet indeholder et dashboard og en rapport.

    ![App i navigationsruden til venstre](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

8. Vælg den nye [GitHub-dashboard](https://powerbi.microsoft.com/integrations/github).    
    ![GitHub-dashboard i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

3. For at få vist hele indholdet af det nye GitHub-arbejdsområde i venstre navigationslinje, skal du vælge **arbejdsområder** > **GitHub**.
 
   ![GitHub-arbejdsområde i venstre navigationsrude](media/service-connect-to-github/power-bi-github-left-nav.png)

    Denne visning er listen over indhold til arbejdsområdet. I det øverste højre hjørne skal du se **Opdater app**. Når du er klar til at distribuere din app til dine kollegaer, er, hvor du vil starte. 

    ![Listen over indhold på GitHub](media/service-connect-to-github/power-bi-github-content-list.png)

2. Vælg **rapporter** og **datasæt** at se de andre elementer i arbejdsområdet.

    Læs om [distribuere apps](service-create-distribute-apps.md) til dine kollegaer.

## <a name="whats-included-in-the-app"></a>Hvad er inkluderet i appen
Følgende data er tilgængelige fra GitHub i Power BI:     

| Tabelnavn | Beskrivelse |
| --- | --- |
| Bidrag |Tabellen bidrag giver de samlede tilføjelser, sletninger og bekræftelser, der er oprettet af bidragyderen, sammenlagt pr. uge. De 100 største bidragsydere er inkluderet. |
| Problemer |Angiver alle problemer i det valgte lager. Det indeholder beregninger som samlet og gennemsnitlig tid til at lukke et problem, samlet antal åbne problemer, samlet antal lukkede problemer. Denne tabel er tom, når der ikke er nogen problemer i lageret. |
| Pull-anmodninger |Denne tabel indeholder alle Pull-anmodningerne for lageret, og hvem der oprettede anmodningen. Den indeholder også beregninger om, hvor mange åbne, lukkede og samlede pull-anmodninger, hvor lang tid det tog at udføre pull-anmodningerne, og hvor lang tid den gennemsnitlige pull-anmodning tog. Denne tabel er tom, når der ikke er nogen problemer i lageret. |
| Brugere |Denne tabel indeholder en liste over GitHub-brugere eller -bidragsydere, der har bidraget, arkiveret problemer eller løst Pull-anmodninger for det valgte lager. |
| Milepæle |Den har alle milepæle for det valgte lager. |
| DateTable |Denne tabel indeholder datoer fra i dag og år tidligere, der gør det muligt at analysere dine GitHub-data efter dato. |
| ContributionPunchCard |Denne tabel kan bruges som et bidragshulkort for det valgte lager. Den viser anvendelser efter ugedag og klokkeslæt. Denne tabel er ikke forbundet til andre tabeller i modellen. |
| RepoDetails |Denne tabel indeholder oplysninger om det valgte lager. |

## <a name="system-requirements"></a>Systemkrav
* Den GitHub-konto, der har adgang til lageret.  
* Tilladelse givet til Power BI til GitHub-appen under det første logon. Se flere oplysninger herunder om tilbagekaldelse af adgang.  
* Tilstrækkelige API-kald til at hente og opdatere dataene.  

### <a name="de-authorize-power-bi"></a>Annuller godkendelsen af Power BI
Hvis du vil Annuller godkendelsen af Power BI fra at oprette forbindelse til dine GitHub-lager, kan du tilbagekalde adgangen i GitHub. Se dette [GitHub Hjælp](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth) emne for at få flere oplysninger.

<a name="FindingParams"></a>
## <a name="finding-parameters"></a>Søgning efter parametre
Du kan finde ejeren og lageret ved at kigge på lageret i selve GitHub:

![Navnet på lageret og ejeren](media/service-connect-to-github/github_ownerrepo.png)

Den første del, "Azure", er ejeren, og den anden del, "azure-sdk-for-php", er selve lageret.  Du kan se disse samme to elementer i lagerets URL-adresse:

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>Fejlfinding
Hvis det er nødvendigt, kan du kontrollere dine GitHub-legitimationsoplysninger.  

1. Gå til GitHub-webstedet i et andet browservindue, og log på GitHub. Du kan se, at du er logget på, i øverste højre hjørne af GitHub-webstedet.    
2. I GitHub skal du navigere til URL-adressen på det lager, du vil have adgang til i Power BI. Eksempel: https://github.com/dotnet/corefx.  
3. Når du er tilbage i Power BI, kan du prøve at oprette forbindelse til GitHub. Brug navnene på lageret og lagerejeren af det samme lager i dialogboksen Konfigurer GitHub.  

## <a name="next-steps"></a>Næste trin

* [Selvstudium: Opret forbindelse til en GitHub-lager med Power BI](service-tutorial-connect-to-github.md)
* [Opret nye arbejdsområder i Power BI](service-create-the-new-workspaces.md)
* [Installér og brug apps i Power BI](consumer/end-user-apps.md)
* [Opret forbindelse til Power BI-apps til eksterne tjenester](service-connect-to-services.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

