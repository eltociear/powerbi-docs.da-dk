---
title: Opret forbindelse til Lithium med Power BI
description: Lithium til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1d41ce3ff0c73675793e872170914b96a1d73d14
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-lithium-with-power-bi"></a>Opret forbindelse til Lithium med Power BI
Lithium skaber tillidsforhold mellem verdens bedste varemærker og deres kunder, så alle kan få svar og dele deres oplevelser. Ved at forbinde Lithium-indholdspakken med Power BI kan du foretage vigtige målinger i dit onlinecommunity, som kan hjælpe med at fremme salget, reducere serviceomkostningerne og forbedre loyaliteten. 

Opret forbindelse til [Lithium-indholdspakken](https://app.powerbi.com/getdata/services/lithium) til Power BI.

>[!NOTE]
>Power BI-indholdspakken bruger Lithium-API'EN. For mange opkald til API'en kan resultere i yderligere gebyrer fra Lithium. Bekræft dette med din Lithium-administrator.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Vælg **Lithium** \> **Hent**.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Angiv URL-adressen til dit Lithium-community. Den vil være i formatet *https://community.yoursite.com*.
   
   ![](media/service-connect-to-lithium/params.png)
5. Angiv dine legitimationsoplysninger til Lithium, når du bliver bedt om dem. Vælg **oAuth 2** som godkendelsesmetoden, og klik på **Log på** , og følg derefter logonflowet for Lithium.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Når logonflowet er fuldført, starter importprocessen. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Lithium-indholdspakken kræver et Lithium-community v15.9 eller højere. Kontakt Lithium-administratoren for at bekræfte dette.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

