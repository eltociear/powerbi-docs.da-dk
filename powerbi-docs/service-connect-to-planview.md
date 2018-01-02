---
title: Opret forbindelse til Planview Enterprise med Power BI
description: Planview Enterprise til Power BI
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
ms.openlocfilehash: 12346c0a9a580b2c3dd36c61a00d27097e1b3937
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
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

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Hvis du vil importere dine Planview Enterprise-data i Power BI, skal du være Planview Enterprise-bruger og have funktionen Rapporteringsportalfremviser aktiveret som en del af din rolle. Se flere krav nedenfor.

Denne procedure forudsætter, at du allerede er logget på Microsoft Power BI-hjemmesiden med en Power BI-konto. Hvis du ikke har en Power BI-konto, skal du oprette en ny gratis Power BI-konto på Power BI-hjemmesiden og derefter klikke på Hent data.

## <a name="next-steps"></a>Næste trin:

[Introduktion til Power BI](service-get-started.md)

[Hent data til Power BI](service-get-data.md)