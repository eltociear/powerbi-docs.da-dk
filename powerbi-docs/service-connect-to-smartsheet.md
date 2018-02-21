---
title: Opret forbindelse til Smartsheet med Power BI
description: Smartsheet til Power BI
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
ms.openlocfilehash: 49d0187336aec4a7cbdd4472355f933a16d5e60e
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Opret forbindelse til Smartsheet med Power BI
Smartsheet byder på en nem platform til samarbejde og fildeling. Smartsheet-indholdspakken til Power BI indeholder et dashboard, rapporter og datasæt, som viser en oversigt over din Smartsheet-konto. Du kan også bruge [Power BI Desktop](desktop-connect-to-data.md) til at oprette forbindelse direkte til individuelle ark i din konto. 

Opret forbindelse til [Smartsheet-indholdspakken](https://app.powerbi.com/groups/me/getdata/services/smartsheet) til Power BI.

>[!NOTE]
>Smartsheet-administratorkontoen er at foretrække til oprettelse af forbindelse og indlæsning af Power BI-indholdspakken, da den har ekstra adgang.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. Vælg **Smartsheet \> Hent**.
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. Til Godkendelsesmetode skal du vælge **oAuth2\> Log på**.
   
   Når du bliver spurgt, skal du angive dine legitimationsoplysninger til Smartsheet og følge godkendelsesprocessen.
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. Efter import af data i Power BI får du vist et nyt dashboard og datasæt samt en ny rapport i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*, vælg posten Smartsheet.
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Smartsheet-indholdspakken til Power BI indeholder et overblik over din Smartsheet-konto, f.eks det antal arbejdsområder, rapporter og ark, du har, når disse er blevet redigeret osv. Administratorer kan også se nogle oplysninger om brugerne i deres system, f.eks oprettere af øverste ark.  

Du kan også bruge Smartsheet-forbindelseskomponenten i [Power BI Desktop](desktop-connect-to-data.md) til at oprette direkte forbindelse til individuelle ark i din konto.  

## <a name="next-steps"></a>Næste trin:

[Kom i gang med Power BI](service-get-started.md)

[Hent data til Power BI](service-get-data.md)