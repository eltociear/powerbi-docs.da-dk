---
title: Filtrer en rapport og dele den med kollegaer – Power BI
description: Få mere at vide om, hvordan du filtrerer Power BI-rapporter og deler dem med kolleger i din organisation.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770692"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>Filtrer en rapport i Power BI og dele den med kolleger
*Deling* er velegnet til at give nogle få personer adgang til dine dashboards og rapporter. Hvad nu hvis du vil dele en filtreret version af en rapport? Måske en rapport, der kun viser data for en bestemt by eller sælger eller et bestemt år. Prøv at filtrere en rapport og deler den, eller oprette en brugerdefineret URL-adresse. Rapporten filtreres, når modtagerne åbner den. De kan fjerne filteret ved at ændre URL-adressen. 

Med Power BI får du [adskillige andre måder at samarbejde om og distribuere dine rapporter på](service-how-to-collaborate-distribute-dashboards-reports.md). Til deling skal du og dine modtagere bruge en [Power BI Pro-licens](service-features-license-type.md), eller indholdet skal være i en [Premium-kapacitet](service-premium-what-is.md). 

## <a name="two-ways-to-filter-a-report"></a>To måder at filtrere en rapport

### <a name="set-a-filter"></a>Angiv et filter

Åbn rapporten i [Redigeringsvisning](consumer/end-user-reading-view.md), anvend filteret, og gem rapporten.
   
I dette eksempel filtrerer vi [Eksempel på detailanalyse](sample-tutorial-connect-to-the-samples.md) for kun at vise værdier, hvor **Territory** (Område) er lig med **NC**.
   
![Ruden Rapportfilter](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>Opret et filter i URL-adressen

Tilføj følgende i slutningen af rapportsidens URL-adresse:
   
?filter=*tabelnavn*/*feltnavn* eq *værdi*
   
Feltet skal være af typen number, datetime eller streng. Værdierne *tablename* eller *fieldname* må ikke indeholde mellemrum.
   
I vores eksempel er navnet på tabellen **Store** (Butik), navnet på feltet er **Territory** (Område), og den værdi, vi vil filtrere på, er **NC**:
   
?filter=Store/Territory eq 'NC'
   
![URL-adresse til filtreret rapport](media/service-share-reports/power-bi-filter-url3.png)
   
Din browser tilføjer specialtegn for at repræsentere skråstreger, mellemrum og apostrofer, så du ender med:
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

Se artiklen [filtrere en rapport med forespørgselsstrengparametre i URL-adressen](service-url-filters.md) for meget flere detaljer.

## <a name="share-the-filtered-report"></a>Del den filtreret rapport

1. Når du [dele rapporten](service-share-dashboards.md)skal du fjerne markeringen af **Send meddelelse via mail til modtagere** afkrydsningsfelt.

    ![Dialogboksen Deling af rapport](media/service-share-reports/power-bi-share-report-dialog.png)

4. Send linket med det filter, du oprettede tidligere.

## <a name="next-steps"></a>Næste trin
* Har du feedback? Kom med dine forslag på [webstedet for Power BI-community'et](https://community.powerbi.com/).
* [Hvordan kan jeg samarbejde på og dele dashboards og rapporter?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Del et dashboard](service-share-dashboards.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).

