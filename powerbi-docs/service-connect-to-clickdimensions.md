---
title: Opret forbindelse til ClickDimensions med Power BI
description: ClickDimensions til Power BI
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
LocalizationGroup: Connect to services
ms.openlocfilehash: 35b6fd4c2594a29745fe307d804b3f0147d94e43
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-clickdimensions-with-power-bi"></a>Opret forbindelse til ClickDimensions med Power BI
Indholdspakken ClickDimensions til Power BI giver brugerne mulighed at anvende ClickDimensions-marketingdata i Power BI, så ledelsesteams får yderligere indsigt i succesen af deres salgs- og marketinginitiativer. Visualisér og analysér mailinteraktioner, webbesøg og formularindsendelser i Power BI-dashboards og -rapporter.

Opret forbindelse til [ClickDimensions-indholdspakken](https://app.powerbi.com/getdata/services/click-dimensions) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-clickdimensions/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-clickdimensions/services.png)
3. Vælg **ClickDimensions** \>  **Hent**.
   
   ![](media/service-connect-to-clickdimensions/clickdimensions.png)
4. Angiv placeringen af dit datacenter (USA, Europa eller Australien), og vælg **Næste**.
   
   ![](media/service-connect-to-clickdimensions/params.png)
5. Som **Godkendelsesmetode** skal du vælge **Grundlæggende** \> **Log på**. Når du bliver spurgt, skal du angive dine ClickDimensions-legitimationsoplysninger. Se detaljer om at [finde de pågældende parametre](#FindingParams) nedenfor
   
    ![](media/service-connect-to-clickdimensions/creds.png)
6. Efter godkendelsen starter importprocessen automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
     ![](media/service-connect-to-clickdimensions/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
For at oprette forbindelse til Power BI-indholdspakken skal du angive det datacenter, der svarer til din konto, og logge på med din ClickDimensions-konto. Hvis du ikke er sikker på, hvilket datacenter du skal angive, skal du spørge din administrator.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Find parametre
Kontonøglen findes i CRM-indstillinger \> ClickDimensions-indstillinger. Kopiér Kontonøgle fra ClickDimensions-indstillinger, og sæt den ind i feltet Brugernavn.  

![](media/service-connect-to-clickdimensions/crm.png)  

Kopiér Power BI-token fra ClickDimensions-indstillinger, og sæt det ind i feltet Adgangskode. Power BI-token findes i CRM-indstillinger \> ClickDimensions-indstillinger.  

![](media/service-connect-to-clickdimensions/crm2.png)  

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

