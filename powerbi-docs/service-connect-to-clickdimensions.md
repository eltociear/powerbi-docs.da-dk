---
title: Opret forbindelse til ClickDimensions med Power BI
description: ClickDimensions til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9506ab48e48fe04e07de8dcb08ad5234d31045cf
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242949"
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

