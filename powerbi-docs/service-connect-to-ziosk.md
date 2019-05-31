---
title: Opret forbindelse til Ziosk Survey Analytics med Power BI
description: Ziosk til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d22f67f52d0abe0621e244874def845c7d25c15b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61138184"
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

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
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
[Hvad er Power BI?](power-bi-overview.md)

[Power BI – Grundlæggende begreber](consumer/end-user-basic-concepts.md)

