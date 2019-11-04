---
title: Opret forbindelse til Lithium med Power BI
description: Lithium til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: tebercov
LocalizationGroup: Connect to services
ms.openlocfilehash: 9a02c642d0b5d766b22b3b8c3853da2d4d773cbd
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060568"
---
# <a name="connect-to-lithium-with-power-bi"></a>Opret forbindelse til Lithium med Power BI

Lithium skaber tillidsforhold mellem verdens bedste varemærker og deres kunder, så alle kan få svar og dele deres oplevelser. Ved at forbinde Lithium-indholdspakken med Power BI kan du foretage vigtige målinger i dit onlinecommunity, som kan hjælpe med at fremme salget, reducere serviceomkostningerne og forbedre loyaliteten. 

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

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
4. Angiv URL-adressen til dit Lithium-community. Den vil være i formatet *https://community.yoursite.com* .
   
   ![](media/service-connect-to-lithium/params.png)
5. Angiv dine legitimationsoplysninger til Lithium, når du bliver bedt om dem. Vælg **oAuth 2** som godkendelsesmetoden, og klik på **Log på** , og følg derefter logonflowet for Lithium.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Når logonflowet er fuldført, starter importprocessen. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Lithium-indholdspakken kræver et Lithium-community v15.9 eller højere. Kontakt Lithium-administratoren for at bekræfte dette.

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](fundamentals/power-bi-overview.md)

[Grundlæggende begreber for designere i Power BI-tjenesten](service-basic-concepts.md)

