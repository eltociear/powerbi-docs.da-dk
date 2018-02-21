---
title: Opret forbindelse til SendGrid med Power BI
description: SendGrid til Power BI
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
ms.openlocfilehash: bbfd194cb4b65d91eedf417cc83959016bfff7e9
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2018
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

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Følgende målepunkter er tilgængelige i SendGrid-dashboardet:

* Overordnet mailstatistik – anmodninger, leveret, afvist, blokeret spam, spamrapport osv.
* Mailstatistik efter kategori
* Mailstatistik efter geografi
* Mailstatistik efter internetudbyder
* Mailstatistik efter enhed, klient, browser

## <a name="next-steps"></a>Næste trin
[Introduktion til Power BI](service-get-started.md)

[Hent data](service-get-data.md)

