---
title: Del Power BI-rapporter med kollegaer
description: Se, hvordan du deler Power BI-rapporter og filtrerede rapporter med kollegaer i din organisation.
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/14/2017
ms.author: maggies
ms.openlocfilehash: 022f085d12d7dc872052ca9205deca264b1c0418
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="share-power-bi-reports-with-your-coworkers"></a>Del Power BI-rapporter med dine kollegaer
*Deling* er velegnet til at give nogle få personer adgang til dine dashboards og rapporter. Power BI giver dig [adskillige måder at samarbejde og distribuere dine rapporter på](service-how-to-collaborate-distribute-dashboards-reports.md), og deling er bare én af dem.

Til deling skal du og dine modtagere bruge en [Power BI Pro-licens](service-free-vs-pro.md), eller indholdet skal være i en [Premium-kapacitet](service-premium.md). Forslag? Power BI-teamet er altid interesseret i din feedback, så gå til [webstedet for Power BI-community'et](https://community.powerbi.com/).

Du kan dele en rapport med kollegaer i samme maildomæne som dig selv fra dit eget Mit arbejdsområde eller fra et apparbejdsområde. Når du deler en rapport, kan de personer, du deler den med, få den vist og interagere med den, men ikke redigere den. De kan se de samme data, som du kan se i rapporterne, medmindre der er anvendt [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md). 

## <a name="share-a-power-bi-report"></a>Del en Power BI-rapport
1. I Power BI-tjenesten skal du [oprette et dashboard](service-dashboard-create.md) med mindst ét felt, der er sammenkædet med den rapport, du vil dele. 
   
    Selvom du kun vil dele rapporten, skal du først oprette et dashboard, der er sammenkædet med rapporten, og dele den. 

1. I øverste højre hjørne af dashboardet skal du vælge **Del**.

     ![Vælg Del](media/service-share-reports/power-bi-share-upper-right.png)
  
2. Angiv adresserne på dine modtagere. Hvis du ikke vil sende dem en mail om dashboardet, skal du fjerne markeringen i afkrydsningsfeltet **Send meddelelse via mail til modtagere**.

     ![Fjern markeringen i afkrydsningsfeltet Send meddelelse via mail](media/service-share-reports/power-bi-share-dont-send-mail.png)

4. Vælg **Del**.

      De personer, du deler dashboardet med, har nu tilladelse til at se den underliggende rapport. 

1. Åbn rapporten i Power BI-tjenesten, kopiér URL-adressen til rapportsiden, og send den til dine kollegaer. 
   
    Når de vælger linket, åbner Power BI en skrivebeskyttet version af rapporten.

## <a name="share-a-filtered-version-of-a-report"></a>Del en filtreret version af en rapport
Hvad nu hvis du vil dele en filtreret version af en rapport? Måske en rapport, der kun viser data for en bestemt by eller sælger eller et bestemt år. Du kan gøre dette ved at oprette en brugerdefineret URL-adresse.

1. Åbn rapporten i [Redigeringsvisning](service-reading-view-and-editing-view.md), anvend filteret, og gem rapporten.
   
   I dette eksempel filtrerer vi [Eksempel på detailanalyse](sample-tutorial-connect-to-the-samples.md) for kun at vise værdier, hvor **Territory** (Område) er lig med **NC**.
   
   ![Ruden Rapportfilter](media/service-share-reports/power-bi-filter-report2.png)
2. Tilføj følgende i slutningen af rapportsidens URL-adresse:
   
   ?filter=*tabelnavn*/*feltnavn* eq *værdi*
   
    Feltet skal være af typen **streng**, og hverken *tabelnavn* eller *feltnavn* må indeholde mellemrum.
   
   I vores eksempel er navnet på tabellen **Store** (Butik), navnet på feltet er **Territory** (Område), og den værdi, vi vil filtrere på, er **NC**:
   
    ?filter=Store/Territory eq NC
   
   ![URL-adresse til filtreret rapport](media/service-share-reports/power-bi-filter-url3.png)
   
   Din browser tilføjer specialtegn for at repræsentere skråstreger og mellemrum, så du ender med:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20NC
3. Send denne URL-adresse til dine kollegaer. 
   
   Når de vælger linket, åbner Power BI en skrivebeskyttet version af den filtrerede rapport.

## <a name="next-steps"></a>Næste trin
* Har du feedback? Kom med dine forslag på [webstedet for Power BI-community'et](https://community.powerbi.com/).
* [Hvordan kan jeg samarbejde på og dele dashboards og rapporter?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Del et dashboard](service-share-dashboards.md)
* Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/).

