---
title: Opret forbindelse til SendGrid med Power BI
description: SendGrid til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2e9da4bc46a741af42a214d4e70fd46bfaa4a541
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61151954"
---
# <a name="connect-to-sendgrid-with-power-bi"></a>Opret forbindelse til SendGrid med Power BI
Med Power BI-indholdspakken til SendGrid kan du udtrække indsigt og statistikker fra din SendGrid-konto. Ved hjælp af SendGrid-indholdspakken kan du visualisere SendGrid-statistikkerne i et dashboard.

Opret forbindelse til [SendGrid-indholdspakken](https://app.powerbi.com/getdata/services/sendgrid) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-sendgrid/pbi_getdata.png) 
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-sendgrid/pbi_getservices.png) 
3. Vælg **SendGrid**-indholdspakken, og klik på **Hent**.
   
   ![](media/service-connect-to-sendgrid/sendgrid.png) 
4. Når du bliver spurgt, skal du angive SendGrid-brugernavn og -adgangskode. Vælg **Log på**.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgridsignin.png)
5. Når Power BI har importeret dataene, får du vist et nyt dashboard, en ny rapport og et nyt datasæt i venstre navigationsrude, der er udfyldt med mailstatistikken for de seneste 90 dage. Nye elementer er markeret med en gul stjerne \*.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgriddash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Følgende målepunkter er tilgængelige i SendGrid-dashboardet:

* Overordnet mailstatistik – anmodninger, leveret, afvist, blokeret spam, spamrapport osv.
* Mailstatistik efter kategori
* Mailstatistik efter geografi
* Mailstatistik efter internetudbyder
* Mailstatistik efter enhed, klient, browser

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](power-bi-overview.md)

[Hent data](service-get-data.md)

