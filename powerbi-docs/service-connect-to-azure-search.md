---
title: Opret forbindelse til Azure Search med Power BI
description: Azure Search til Power BI
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
ms.openlocfilehash: eb106547efa67accacd3c955d53bc9ac4d114d8e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-search-with-power-bi"></a>Opret forbindelse til Azure Search med Power BI
Med Azure Search Traffic Analytics kan du overvåge og forstå trafikken til Azure Search-tjenesten. Azure Search-indholdspakken til Power BI giver detaljeret indsigt i dine Search-data, herunder søgning, indeksering, tjenestestatistik og ventetid fra de seneste 30 dage. Flere oplysninger finder du i [Azure-blogindlæg](https://azure.microsoft.com/en-us/blog/analyzing-your-azure-search-traffic/).

Opret forbindelse til [Azure Search-indholdspakken](https://app.powerbi.com/getdata/services/azure-search) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-azure-search/pbi_getdata.png) 
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-azure-search/pbi_getservices.png) 
3. Vælg **Azure Search** \> **Hent**.
   
   ![](media/service-connect-to-azure-search/azuresearch.png)
4. Angiv navnet på den tabellagerkonto, hvor din Azure Search-analyse er gemt.
   
   ![](media/service-connect-to-azure-search/params.png)
5. Vælg **Nøgle** som godkendelsesmetode, og angiv din nøgle til lagerkontoen. Klik på **Log på** for at starte indlæsningsprocessen.
   
   ![](media/service-connect-to-azure-search/creds.png)
6. Når indlæsningen er fuldført, vises der et nyt dashboard, en rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
    ![](media/service-connect-to-azure-search/dashboard2.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Azure Search-indholdspakken kræver, at Azure Search Traffic Analytics er aktiveret på kontoen.

## <a name="troubleshooting"></a>Fejlfinding
Kontrollér, at navnet på lagerkontoen er angivet korrekt sammen med den fulde adgangsnøgle. Navnet på lagerkontoen skal svare til den konto, der er konfigureret med Azure Search Traffic Analytics.

## <a name="next-steps"></a>Næste trin
[Introduktion til Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

