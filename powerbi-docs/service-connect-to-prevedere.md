---
title: Opret forbindelse til Prevedere med Power BI
description: Prevedere til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8abf93b30b976aea1d0164238d173abe1be260e8
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185353"
---
# <a name="connect-to-prevedere-with-power-bi"></a>Opret forbindelse til Prevedere med Power BI
Få adgang til eksklusive og vigtige økonomiske oplysninger, der sikkert og proaktivt kan drive din virksomhed fremad.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Opret forbindelse til [Prevedere-indholdspakken](https://app.powerbi.com/getdata/services/prevedere) til Power BI.

>[!NOTE]
>Hvis du ikke er eksisterende Prevedere-bruger, skal du bruge [prøvenøglen](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html) for at prøve det.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-prevedere/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-prevedere/services.png)
3. Vælg **Prevedere** og derefter **Hent**.
   
   ![](media/service-connect-to-prevedere/connect.png)
4. Vælg **Nøgle** som **Godkendelsesmetode**, og angiv din Prevedere API-nøgle.
   
    ![](media/service-connect-to-prevedere/creds.png)
5. Vælg **Log på** for at starte importprocessen. Når processen er færdig, vises et nyt dashboard samt rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
     ![](media/service-connect-to-prevedere/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Indholdspakken skaffer indsigt i dine salgsprognoser, prognosemodeller, overordnede indikatorer og meget mere.

## <a name="system-requirements"></a>Systemkrav
Denne indholdspakke kræver adgang til en Prevedere API-nøgle eller prøvenøglen (se nedenfor).

## <a name="finding-parameters"></a>Sådan finder du parametre
<a name="FindingParams"></a>

Eksisterende kunder har adgang til deres data ved hjælp af deres API-nøgle. Hvis du endnu ikke er kunde, kan du se et udsnit af dataene og analyserne ved hjælp af [prøvenøglen](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html).

## <a name="troubleshooting"></a>Fejlfinding
Det kan tage et stykke tid at indlæse dataene afhængigt af størrelsen på din forekomst.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

