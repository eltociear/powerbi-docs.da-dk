---
title: Filtrer og del Power BI-rapporter med kolleger
description: Få mere at vide om, hvordan du deler Power BI-rapporter og filtrerede rapporter med kolleger i din organisation.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 8f025c11a5269befdb7819684e10e8511ae6bc98
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545629"
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Del en filtreret Power BI-rapport med dine kolleger
*Deling* er velegnet til at give nogle få personer adgang til dine dashboards og rapporter. Med Power BI får du [adskillige andre måder at samarbejde om og distribuere dine rapporter på](service-how-to-collaborate-distribute-dashboards-reports.md).

Til deling skal du og dine modtagere bruge en [Power BI Pro-licens](service-free-vs-pro.md), eller indholdet skal være i en [Premium-kapacitet](service-premium.md). Forslag? Power BI-teamet tager meget gerne mod din feedback, så gå til [webstedet for Power BI-community'et](https://community.powerbi.com/).

Du kan dele en rapport med kolleger inden for det samme maildomæne som dig fra de fleste steder i Power BI-tjenesten: Favoritter, Seneste, Delt med mig (hvis ejeren tillader det), Mit arbejdsområde eller andre arbejdsområder. Når du deler en rapport, kan de personer, du deler den med, få den vist og interagere med den, men ikke redigere den. De kan se de samme data, som du kan se i rapporterne, medmindre der er anvendt [sikkerhed på rækkeniveau (RLS)](service-admin-rls.md). 

## <a name="filter-and-share-a-report"></a>Filtrer og del en rapport
Hvad nu hvis du vil dele en filtreret version af en rapport? Måske en rapport, der kun viser data for en bestemt by eller sælger eller et bestemt år. Du kan gøre dette ved at oprette en brugerdefineret URL-adresse.

1. Åbn rapporten i [Redigeringsvisning](consumer/end-user-reading-view.md), anvend filteret, og gem rapporten.
   
   I dette eksempel filtrerer vi [Eksempel på detailanalyse](sample-tutorial-connect-to-the-samples.md) for kun at vise værdier, hvor **Territory** (Område) er lig med **NC**.
   
   ![Ruden Rapportfilter](media/service-share-reports/power-bi-filter-report2.png)
2. Tilføj følgende i slutningen af rapportsidens URL-adresse:
   
   ?filter=*tabelnavn*/*feltnavn* eq *værdi*
   
    Feltet skal være af typen **streng**, og hverken *tabelnavn* eller *feltnavn* må indeholde mellemrum.
   
   I vores eksempel er navnet på tabellen **Store** (Butik), navnet på feltet er **Territory** (Område), og den værdi, vi vil filtrere på, er **NC**:
   
    ?filter=Store/Territory eq 'NC'
   
   ![URL-adresse til filtreret rapport](media/service-share-reports/power-bi-filter-url3.png)
   
   Din browser tilføjer specialtegn for at repræsentere skråstreger, mellemrum og apostrofer, så du ender med:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Del rapporten](service-share-dashboards.md), men fjern markeringen i afkrydsningsfeltet **Send mail til modtagere**. 

    ![Dialogboksen Deling af rapport](media/service-share-reports/power-bi-share-report-dialog.png)

4. Send linket med det filter, du oprettede tidligere.

## <a name="next-steps"></a>Næste trin
* Har du feedback? Kom med dine forslag på [webstedet for Power BI-community'et](https://community.powerbi.com/).
* [Hvordan kan jeg samarbejde på og dele dashboards og rapporter?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Del et dashboard](service-share-dashboards.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).

