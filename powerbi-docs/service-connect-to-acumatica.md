---
title: Opret forbindelse til Acumatica med Power BI
description: Acumatica til Power BI
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
ms.openlocfilehash: 66d1544797008b4ed4c0ce2c7acd041aa60b967b
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-acumatica-with-power-bi"></a>Opret forbindelse til Acumatica med Power BI
Med Power BI Acumatica-indholdspakken kan du hurtigt få indsigt i dine data med salgsmuligheder. Power BI henter dine data, herunder salgsmuligheder og kunder og opretter derefter et standarddashboard og relaterede rapporter, der er baseret på disse data.

Opret forbindelse til [Acumatica-indholdspakken](https://app.powerbi.com/getdata/services/acumatica), eller læs mere om [Acumatica-integrationen](https://powerbi.microsoft.com/integrations/acumatica) med Power BI.

>[!NOTE]
>Denne indholdspakke kræver Acumatica v5.2 eller nyere.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-acumatica/getdata3.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-acumatica/getdata2.png)
3. Vælg **Acumatica** \> **Hent**.
   
   ![](media/service-connect-to-acumatica/acumatica.png)
4. Angiv dit Acumatica OData-slutpunkt. Et OData-slutpunkt gør det muligt for et eksternt system at anmode om data fra Acumatica. Acumatica OData-slutpunktet er formateret som følger og skal bruge HTTPS:
   
     https://[wedstedsdomæne]/OData/[firmanavn]
   
   Firmanavnet er kun påkrævet, hvis du har en installation med flere firmaer. Der findes flere oplysninger om at finde denne parameter i kontoen til Acumatica nedenfor.
   
   ![](media/service-connect-to-acumatica/parameters.png)
5. Som Godkendelsesmetode skal du vælge **Grundlæggende**. Angiv brugernavnet og adgangskoden fra din Acumatica-konto, og klik derefter på **Log på**.
   
    ![](media/service-connect-to-acumatica/creds2.png)
6. Når Power BI har importeret dataene, vises der et nyt dashboard, en rapport og et datasæt i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*, som forsvinder, når den er valgt. Når dashboardet vælges, vises et layout svarende til det nedenfor:
   
    ![](media/service-connect-to-acumatica/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Denne indholdspakke kræver Acumatica v5.2 eller nyere. Bekræft versionen med administratoren af Acumatica.

## <a name="finding-parameters"></a>Søg efter parametre
**Acumatica OData-slutpunkt**

Acumatica OData-slutpunktet er formateret som følger og skal bruge HTTPS:

    https://[sitedomain]/odata/[companyname]

Programwebstedets domæne kan findes i browserens adresselinje, når du er logget på Acumatica. I eksemplet nedenfor er webstedsdomænet "https://pbi.acumatica.com", så det OData-slutpunkt, der skal angives, vil være "https://pbi.acumatica.com/odata".

 ![](media/service-connect-to-acumatica/url.png)

Firmanavnet er kun påkrævet, hvis du har en installation med flere firmaer. Du kan finde disse oplysninger på logonsiden til Acumatica.

![](media/service-connect-to-acumatica/signin2.png)

## <a name="troubleshooting"></a>Fejlfinding
Hvis du ikke kan logge på, skal du bekræfte, at det angivne Acumatica OData-slutpunkt er formateret korrekt.

    https://<application site domain>/odata/<company name>

Hvis du har problemer med at oprette forbindelse, bedes du bekræfte din version af Acumatica med din administrator. Denne indholdspakke kræver version 5.2 eller nyere.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

