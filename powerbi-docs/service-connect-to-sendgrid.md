---
title: Opret forbindelse til SendGrid med Power BI
description: SendGrid til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a08d9d10725a5c135ef6732b8397a57833463f4c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247820"
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

