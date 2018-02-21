---
title: Opret forbindelse til QuickBooks Online med Power BI
description: QuickBooks Online til Power BI
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
ms.openlocfilehash: 049e97ff0cc53eb8d8a2e3b976328693ec3fe065
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Opret forbindelse til QuickBooks Online med Power BI
Når du opretter forbindelse til dine QuickBooks Online-data fra Power BI, får du straks et Power BI-dashboard og Power BI-rapporter, der giver indsigt i antallet af din virksomheds likviditet, lønsomhed, kunder m.m. Brug dashboardet og rapporterne, som de er, eller tilpas dem for at fremhæve de oplysninger, som betyder mest for dig. Dataene opdateres automatisk én gang dagligt.

Opret forbindelse til [QuickBooks Online-indholdspakken](https://dxt.powerbi.com/getdata/services/quickbooks-online) til Power BI.

>[!NOTE]
>Hvis du vil importere dine QuickBooks Online-data i Power BI, skal du være administrator på din QuickBooks Online-konto og logge på med din administratorkonto.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getdata.png) 
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getservices.png) 
3. Vælg **QuickBooks Online**, og vælg derefter **Hent**.
   
   ![](media/service-connect-to-quickbooks-online/qbo.png)
4. Vælg **oAuth2** som Godkendelsesmetode, og vælg derefter **Log på**. 
5. Når du bliver spurgt, skal du angive dine legitimationsoplysninger til QuickBooks Online og følge QuickBooks Online-godkendelsesprocessen. Hvis du er allerede er logget på QuickBooks Online i din browser, bliver du muligvis ikke spurgt om legitimationsoplysninger.
   >[!NOTE]
   >Du skal bruge administratorlegitimationsoplysninger til din QuickBooks Online-konto.
6. Vælg det firma, du vil forbinde til Power BI, på det næste skærmbillede.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)
7. Vælg **Godkend** i det næste skærmbillede for at starte importprocessen. Det kan tage et par minutter, afhængigt af størrelsen på virksomhedens data. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
   Når Power BI har importeret dataene, vises der et nyt dashboard, en ny rapport og et nyt datasæt i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_leftnavnew.png)
8. Vælg QuickBooks Online-dashboardet. Dette er dashboardet, som Power BI oprettede automatisk for at vise dine importerede data. Du kan ændre dette dashboard, så det viser data på din foretrukne måde. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_dash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="troubleshooting"></a>Fejlfinding
**"Ups! Der er opstået en fejl"**

Hvis du får vist denne meddelelse, når du har valgt **Godkend**:

"Ups! Der opstod en fejl." Luk dette vindue, og prøv igen.

En anden bruger abonnerer allerede på dette program til denne virksomhed. Kontakt [administratormail] for at foretage ændringer på abonnementet."

![](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... dette betyder, at en anden administrator i din virksomhed allerede har forbindelse til dine firmadata med Power BI. Bed denne administrator om at dele dashboardet med dig. I øjeblikket kan kun én administrator oprette forbindelse et bestemt QuickBooks Online-firmadatasæt til Power BI. Når Power BI har oprettet dashboardet, kan administratoren dele det med flere kolleger på de samme Power BI-lejere.

**"Denne app er ikke konfigureret til at tillade forbindelser fra dit land"**

Power BI understøtter i øjeblikket kun amerikanske versioner af QuickBooks Online. 

![](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

