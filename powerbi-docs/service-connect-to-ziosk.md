---
title: Opret forbindelse til Ziosk Survey Analytics med Power BI
description: Ziosk til Power BI
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
ms.openlocfilehash: 0f4cd7166334338e4b19586c189fd363c5b7c934
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-ziosk-survey-analytics-with-power-bi"></a>Opret forbindelse til Ziosk Survey Analytics med Power BI
Ziosk Survey Analytics-indholdspakken til Power BI giver restauranter med Ziosk-tablets uforlignelig adgang til indsigt, der leveres af Ziosk-undersøgelsesdata, herunder segmentering efter dag, placering, medarbejder og meget mere.

Opret forbindelse til [Ziosk Survey Analytics-indholdspakken](https://app.powerbi.com/getdata/services/ziosk-survey-analytics) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.  
   
    ![](media/service-connect-to-ziosk/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.  
   
    ![](media/service-connect-to-ziosk/services.png)
3. Vælg **Ziosk Survey Analytics**, og vælg derefter **Hent**.  
   
    ![](media/service-connect-to-ziosk/ziosk.png)
4. Vælg **OAuth 2** og derefter **Log på**. Når du bliver spurgt, skal du angive dine legitimationsoplysninger til Ziosk.
   
    ![](media/service-connect-to-ziosk/creds.png)
   
    ![](media/service-connect-to-ziosk/creds2.png)
5. Når der er oprettet forbindelse, indlæses der automatisk et dashboard, en rapport og et datasæt. Når det er fuldført, opdateres felterne med data fra din Ziosk-konto.
   
    ![](media/service-connect-to-ziosk/dashboard.png)

**Hvad nu?**

* Prøv at [stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Indholdspakken indeholder data fra følgende tabeller:  

    - Alcohol Category (alkoholkategori)  
    - Appetizer Category (forretkategori)  
    - CommentKeywords (KommentarNøgleord)  
    - Date (dato)  
    - Daypart (dagtimer)  
    - Dessert Category (dessertkategori)  
    - FreeForm (kombination)  
    - Kids Category (børnekategori)  
    - Messages (meddelelser)  
    - Premium Content Category (premiumindholdskategori)  
    - Question (spørgsmål)  
    - Store (butik)  
    - Surveys (undersøgelser)  
    - Weekday (ugedag)  


## <a name="system-requirements"></a>Systemkrav
Der kræves en Ziosk-konto med rettigheder til at overstående tabeller for at kunne instantiere denne indholdspakke.

## <a name="next-steps"></a>Næste trin
[Introduktion til Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

