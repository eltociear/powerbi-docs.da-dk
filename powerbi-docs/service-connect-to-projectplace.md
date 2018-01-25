---
title: Opret forbindelse til Projectplace med Power BI
description: Projectplace til Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: aec56a34194d9ed6217384d8d05cbe2ce64080b2
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-projectplace-by-planview-with-power-bi"></a>Opret forbindelse til Projectplace fra Planview med Power BI
Med indholdspakken til Projectplace fra Planview kan du visualisere dine samarbejdsprojektdata på helt nye måder direkte i Power BI. Brug dine legitimationsoplysninger for logon til Projectplace til at få en interaktiv visning af de vigtigste projektstatistikker, find ud af, hvem der er dine mest aktive og produktive teammedlemmer, og identificer sårbare kort og aktiviteter på tværs af projekter på din Projectplace-konto. Du kan også udvide standarddashboardet og rapporter for at få den viden, der er vigtigst for dig.

[Opret forbindelse til indholdspakken til Projectplace i Power BI](https://app.powerbi.com/getdata/services/projectplace)

>[!NOTE]
>For at kunne importere dine Projectplace-data i Power BI skal du være Projectplace-bruger. Se flere krav nedenfor.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-projectplace/get.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
    ![](media/service-connect-to-projectplace/services.png)
3. Vælg **Projectplace fra Planview** på Power BI-siden, og vælg derefter **Hent**:  
   
    ![](media/service-connect-to-projectplace/projectplace.png)
4. Angiv URL-adressen til den Projectplace OData-feed, du vil bruge, i tekstfeltet URL-adresse til OData-feed, som du kan se på følgende billede:
   
    ![](media/service-connect-to-projectplace/params.png)
5. Vælg **OAuth** på listen Godkendelsesmetode, hvis ikke den allerede er valgt. Tryk på **Log på**, og gå igennem indlogningsforløbet.  
   
   ![](media/service-connect-to-projectplace/creds.png)
6. Vælg **Projectplace** i venstre rude på listen over dashboards. Power BI importerer Projectplace-data til dashboardet. Bemærk, at det kan tage et stykke tid at indlæse dataene.  
   
    Dashboardet indeholder felter, der viser data fra din Projectplace-database. Billedet nedenfor viser et eksempel på standarddashboardet til Projectplace i Power BI.
   
    ![](media/service-connect-to-projectplace/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
For at kunne importere dine Projectplace-data i Power BI skal du være Projectplace-bruger. Denne procedure forudsætter, at du allerede er logget på på Microsoft Power BI-hjemmesiden med en Power BI-konto. Hvis du ikke har en Power BI-konto, skal du oprette en ny gratis Power BI-konto på Power BI-hjemmesiden og derefter klikke på Hent data.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

