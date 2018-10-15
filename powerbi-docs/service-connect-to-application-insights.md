---
title: Opret forbindelse til Application Insights Opret forbindelse til Power BI
description: Application Insights til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 00a42a3ffcc92ca7bc48459635359acb9da8da82
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548344"
---
# <a name="connect-to-application-insights-with-power-bi"></a>Opret forbindelse til Application Insights med Power BI
Brug Power BI til at oprette effektive brugerdefinerede dashboards fra telemetrien [Application Insights](https://azure.microsoft.com/documentation/articles/app-insights-overview/). Få oplysninger om din apptelemetri på nye måder. Kombiner målepunkter fra flere apps eller komponenttjenester på ét dashboard. Denne første version af Power BI-indholdspakken til Application Insights indeholder widgets til målinger, der er relateret til almindeligt forbrug, f.eks. aktive brugere, sidevisning, sessioner, browser- og operativsystemversion samt geografisk fordeling af brugere på et kort.

Opret forbindelse til [Application Insights-indholdspakken til Power BI](https://app.powerbi.com/getdata/services/application-insights).

>[!NOTE]
>Denne integrationsmetode er nu **frarådet**. Hvis du vil vide mere om den foretrukne metode til at forbinde Application Insights til Power BI, skal du bruge [funktionen til eksport af analyseforespørgsler](https://docs.microsoft.com/azure/application-insights/app-insights-export-power-bi#export-analytics-queries).

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![Knappen Hent data](media/service-connect-to-application-insights/pbi_getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
    ![Knappen Hent tjenester](media/service-connect-to-application-insights/pbi_getservices.png)
3. Vælg **Application Insights** > **Hent**.
   
    ![Application Insights-indholdspakke](media/service-connect-to-application-insights/appinsights.png)
4. Angiv oplysningerne om den app, du vil oprette forbindelse til, herunder **ressourcenavn til Application Insights**, **ressourcegruppe** og **abonnements-id**. Se [Find dine Application Insights-parametre](#FindingAppInsightsParams) nedenfor for at få flere oplysninger.
   
    ![Dialogboks til at oprette forbindelse til Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. Vælg **Log på**, og følg på anvisningerne på skærmen for at oprette forbindelse.
   
    ![Logon til at oprette forbindelse til Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. Importprocessen starter automatisk. Når du er færdig, vises der en meddelelse, og der vises et nyt dashboard, en rapport og et datasæt i navigationsruden markeret med en stjerne.  Vælg dashboardet for at få vist de importerede data.
   
    ![Application Insights-dashboard](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Application Insights-indholdspakken indeholder følgende tabeller og målepunkter:  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
Ressourcenavnet, ressourcegruppen og abonnements-id'et findes alt sammen på Azure-portalen. Når navnet vælges, åbnes en detaljeret visning, og du kan bruge Essentials-rullelisten til at finde alle de værdier, du har brug for.

![Application Insights-parametre](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Kopiér og indsæt disse i felterne i Power BI:

![Application Insights-parametre](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

