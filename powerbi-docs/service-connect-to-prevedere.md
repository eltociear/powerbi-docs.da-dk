---
title: Opret forbindelse til Prevedere med Power BI
description: Prevedere til Power BI
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
ms.openlocfilehash: fd9426a8fce0ed1d707184b421a93f989852a33d
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-prevedere-with-power-bi"></a>Opret forbindelse til Prevedere med Power BI
Få adgang til eksklusive og vigtige økonomiske oplysninger, der sikkert og proaktivt kan drive din virksomhed fremad.

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

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
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

