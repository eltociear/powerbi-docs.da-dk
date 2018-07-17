---
title: Opret forbindelse til Planview Enterprise med Power BI
description: Planview Enterprise til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1f3bdb66d9737102c63ecace5359ba1b96265f6a
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37137393"
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>Opret forbindelse til Planview Enterprise med Power BI
Med indholdspakken til Planview Enterprise kan du visualisere dine data til administration af ressourcer og arbejde på helt nye måder direkte i Power BI. Brug dine legitimationsoplysninger til at logge på Planview Enterprise for at se dine porteføljeinvesteringer, få et overblik over, hvor du er over og under budgettet samt for at se, hvor godt dine projekter følger virksomhedens strategiske prioriteringer. Du kan også udvide det alternative dashboard og de alternative rapporter for at få indblik i det, der er vigtigst for dig.

Opret forbindelse til [indholdspakken til Planview Enterprise i Power BI](https://app.powerbi.com/getdata/services/planview-enterprise)

>[!NOTE]
>Hvis du vil importere dine Planview Enterprise-data i Power BI, skal du være Planview Enterprise-bruger og have funktionen Rapporteringsportalfremviser aktiveret som en del af din rolle. Se flere krav nedenfor.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-planview/get.png)
2. I feltet **Tjenester** skal du vælge **Hent**.
   
    ![](media/service-connect-to-planview/services.png)
3. Vælg **Planview Enterprise** på Power BI-siden, og vælg derefter **Hent**:  
    ![](media/service-connect-to-planview/planview.png)
4. I tekstfeltet til URL-adressen for Planview Enterprise skal du angive URL-adressen for den Planview Enterprise-server, du vil bruge. Angiv navnet på Planview Enterprise-databasen i tekstfeltet til Planview Enterprise-databasen, og klik derefter på Næste.  
    ![](media/service-connect-to-planview/params.png)
5. Vælg **Basic** på listen Godkendelsesmetode, hvis ikke den allerede er valgt. Angiv **Brugernavn** og **Adgangskode** for din konto, og vælg **Log på**.  
   ![](media/service-connect-to-planview/creds.png)
6. I ruden til venstre skal du vælge Planview Enterprise på listen over dashboards.  
     I Power BI importeres Planview Enterprise-data til dashboardet. Bemærk, at det kan tage et stykke tid at indlæse dataene.  
    ![](media/service-connect-to-planview/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Hvis du vil importere dine Planview Enterprise-data i Power BI, skal du være Planview Enterprise-bruger og have funktionen Rapporteringsportalfremviser aktiveret som en del af din rolle. Se flere krav nedenfor.

Denne procedure forudsætter, at du allerede er logget på Microsoft Power BI-hjemmesiden med en Power BI-konto. Hvis du ikke har en Power BI-konto, kan du gå til [powerbi.com](https://powerbi.microsoft.com/get-started/). Under **Power BI – Cloudsamarbejde og -deling** skal du vælge **Prøv gratis**. Klik derefter på **Hent Data**.

## <a name="next-steps"></a>Næste trin:

[Hvad er Power BI?](power-bi-overview.md)

[Hent data til Power BI](service-get-data.md)