---
title: Opret forbindelse til AT Internet Bridge med Power BI
description: AT Internet Bridge til Power BI
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
ms.openlocfilehash: 67ed59961ca5bc4b382adf105bbc5c97ff470118
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Opret forbindelse til AT Internet Bridge med Power BI
Med AT Internet kan du hurtigt udtrække værdifulde oplysninger fra dine data, takket være den ensartede platform til digitale analyser, Analytics Suite. AT Internet Bridge-indholdspakken til Power BI indeholder data vedrørende besøg, datakilder, lokalisering og enheder til dit websted.

Opret forbindelse til [AT Internet Bridge-indholdspakken](https://app.powerbi.com/getdata/services/at-internet-bridge) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-at-internet/pbi_getdata.png) 
2. Markér **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-at-internet/pbi_getservices.png) 
3. Vælg **AT Internet Bridge** \> **Hent**.
   
   ![](media/service-connect-to-at-internet/atinternet.png)
4. Angiv det AT Internet Website-nummer, du ønsker at oprette forbindelse til.
   
   ![](media/service-connect-to-at-internet/params.png)
5. Vælg **Basic** som godkendelsesmetoden, angiv dit brugernavn og din adgangskode til AT Internet, og klik på **Log på**.
   
   ![](media/service-connect-to-at-internet/creds.png)
6. Klik på **Tilslut** for at starte importprocessen. Når processen er færdig, vises et nyt dashboard samt rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
    ![](media/service-connect-to-at-internet/atinternet.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Denne indholdspakke indeholder data fra de seneste 45 dage i følgende tabeller:  

    - Konvertering  
    - Enheder  
    - Lokalisering  
    - Datakilder  
    - Globale besøg  

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)
