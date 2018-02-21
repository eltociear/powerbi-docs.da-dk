---
title: Opret forbindelse til Stripe med Power BI
description: Stripe til Power BI
services: powerbi
documentationcenter: 
author: SarinaJoan
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
ms.author: sarinas
ms.openlocfilehash: 02ff2a878f8ae016d824d9039c79279519428136
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-stripe-with-power-bi"></a>Opret forbindelse til Stripe med Power BI
Visualiser og udforsk dine Stripe-data i Power BI med Power BI-indholdspakken. Power BI Stripe-indholdspakken trækker data ind om dine kunder, gebyrer, begivenheder og fakturaer. Dataene indeholder de seneste titusinde hændelser og 5.000 gebyrer over de seneste 30 dage. Indholdet opdateres automatisk en gang om dagen med en tidsplan, du styrer. 

Opret forbindelse til [Stripe-indholdspakken til Power BI](https://app.powerbi.com/getdata/services/stripe).

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg Hent data nederst i venstre navigationsrude.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. Vælg **Stripe** &gt; **Hent**.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Angiv din Stripe [API-nøgle](https://dashboard.stripe.com/account/apikeys) for at oprette forbindelse.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. Importprocessen starter automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden og er markeret med en stjerne. Vælg dashboardet for at få vist de importerede data.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data til Power BI](service-get-data.md)

