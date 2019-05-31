---
title: 'Selvstudium: Opret forbindelse til en GitHub-lager med Power BI'
description: I dette selvstudium opretter du forbindelse til virkelige data i GitHub-tjenesten med Power BI, og Power BI opretter automatisk dashboards og rapporter.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 04/19/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 3aeb1fc16ae200399125a2366a8993d45aad34c4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578609"
---
# <a name="tutorial-connect-to-a-github-repo-with-power-bi"></a>Selvstudium: Opret forbindelse til en GitHub-lager med Power BI
I dette selvstudium opretter du forbindelse til virkelige data i GitHub-tjenesten med Power BI, og Power BI opretter automatisk dashboards og rapporter. Du opretter forbindelse til Power BI content offentlige lager (også kendt som en *lager*), og se svar på spørgsmål som: Hvor mange bidrager til det offentlige Power BI-indhold? Hvem der bidrager mest? På hvilken ugedag er der flest bidrag? Og andre spørgsmål. 

![GitHub-rapporten i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

I dette selvstudium kan du udføre følgende trin:

> [!div class="checklist"]
> * Opret en GitHub-konto, hvis du ikke allerede har en 
> * Log på din Power BI-konto, eller opret én, hvis du ikke allerede har en
> * Åbn Power BI-tjenesten
> * Find GitHub-appen
> * Angiv oplysningerne for det offentlige GitHub-lager i Power BI
> * Få vist dashboardet og rapporten med GitHub-data
> * Ryd op i ressourcer ved at slette appen

Hvis du ikke er tilmeldt Power BI, kan du [tilmelde dig en gratis prøveversion](https://app.powerbi.com/signupredirect?pbi_source=web), før du begynder.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil gennemføre dette selvstudium, skal du oprette en GitHub-konto, hvis du ikke allerede har en. 

- Tilmelde dig en [GitHub-konto](https://docs.microsoft.com/contribute/get-started-setup-github).


## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Log på Power BI-tjenesten (https://app.powerbi.com). 
2. Vælg **Apps** og derefter **Hent apps** i navigationsruden til venstre.
   
   ![Hent apps i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. Vælg **Apps**, type **GitHub** i søgefeltet > **Hent det nu**.
   
   ![Hent GitHub i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-app-source.png) 

4. I **installere denne App i Power BI?** Vælg **installere**.
5. I **din nye app er klar**, skal du vælge **gå til app**.
6. I **Kom i gang med din nye app**, skal du vælge **forbinde data**.

    ![Kom i gang med din nye app](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

7. Angiv lagernavnet og lagerejeren. URL-adressen til dette lager er https://github.com/MicrosoftDocs/powerbi-docs, så **Lagerejer** er **MicrosoftDocs**, og **Lager** er **powerbi-docs**. 
   
    ![Navn på GitHub-lager i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Angiv de GitHub-legitimationsoplysninger, du har oprettet. Power BI springer måske dette trin over, hvis du allerede er logget på GitHub i din browser. 

6. For **godkendelsesmetode**, hold **oAuth2** valgte \> **Log på**.

7. Følg skærmbillederne for GitHub-godkendelse. Giv Power BI-tilladelse til GitHub-dataene.
   
   Nu kan Power BI oprette forbindelse til GitHub og oprette forbindelse til dataene.  Dataene opdateres én gang om dagen.

8. Når Power BI har importeret dataene, kan du se indholdet af det nye GitHub-arbejdsområde. 
9. Vælg pilen ud for Arbejdsområdenavnet på i den venstre navigationslinje. Du kan se arbejdsområdet indeholder et dashboard og en rapport. 

    ![App i navigationsruden til venstre](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

10. Vælg ellipsen (...) ud for navnet på dashboardet > **Omdøb** > type **GitHub-dashboard**.
 
    ![GitHub-felt i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav.png) 

8. Vælg det globale navigationsikon for at minimere venstre navigationsrude, så du har mere plads.

    ![Ikonet til global navigation](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. Vælg din GitHub-dashboardet.
    
    GitHub-dashboardet indeholder dynamiske data, så du kan se værdierne kan være anderledes.

    ![GitHub-dashboard i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

    

## <a name="ask-a-question"></a>Stil et spørgsmål

1. Placer markøren i **stil et spørgsmål om dine data**. Power BI tilbyder **spørgsmål for at komme i gang**. 

1. Vælg **hvor mange brugere er der**.
 
    ![Hvor mange brugere er der](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-users.png)

13. Derimellem **hvor mange** og **brugere er der**, type **pull-anmodninger pr.** . 

     Powerbi opretter et søjlediagram med antallet af pull-anmodninger pr. person.

    ![Hvor mange pull-anmodninger pr. bruger, er der](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-prs.png)


13. Vælg pinkoden for at fastgøre den til dit dashboard, derefter **Afslut spørgsmål og svar**.

## <a name="view-the-github-report"></a>Få vist GitHub-rapporten 

1. Vælg søjlediagrammet i GitHub-dashboardet, **Pull-anmodninger pr. måned** at åbne den tilknyttede rapport.

    ![Pull-anmodninger pr. måned søjlediagram](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-column-chart.png)

2. Vælg et brugernavn i den **samlede pull-anmodninger pr. bruger** diagram. I dette eksempel skal se vi mest muligt ud af deres timer var i februar.

    ![Fremhævelse af GitHub-rapport i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-cross-filter-total-prs.png)

3. Vælg fanen **Hulkort** for at få vist den næste side i rapporten. 
 
    ![Hulkort for GitHub-rapport i Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Tilsyneladende tirsdag kl. 3 er det mest almindelige tidspunkt og dag i ugen for *bekræftelser*, når personer Kontrollér i deres arbejde.

## <a name="clean-up-resources"></a>Fjern ressourcer

Nu, hvor du har gennemført selvstudiet, kan du slette GitHub-appen. 

1. Vælg **Apps** på navigationslinjen til venstre.
2. Peg på GitHub-feltet, og vælg **Slet** ud for skraldespanden.

    ![Slet GitHub-appen](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Næste trin

I dette selvstudie har du oprettet forbindelse til et offentligt GitHub-lager og hentet data, som Power BI har formateret på et dashboard og i en rapport. Du har besvaret nogle spørgsmål om dataene ved at udforske dashboardet og rapporten. Nu kan du få mere at vide om at oprette forbindelse til andre tjenester, f.eks. Salesforce, Microsoft Dynamics og Google Analytics. 
 
> [!div class="nextstepaction"]
> [Opret forbindelse til de onlinetjenester, du bruger](service-connect-to-services.md)


