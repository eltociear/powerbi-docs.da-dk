---
title: Opret forbindelse til VMob med Power BI
description: VMob til Power BI
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
ms.openlocfilehash: 09bd84fc320b550ccdaa0771f747a19bc1003150
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-vmob-with-power-bi"></a>Opret forbindelse til VMob med Power BI
Det er nemt at spore og udforske dine VMob-data med Power BI og VMob-indholdspakken. Power BI henter følgende data: Brugerstatistik for al tid og de seneste 30 dage, nøgletal for handel for de seneste 30 dage og kampagneresultater for de seneste 30 dage.

Opret forbindelse til [VMob-indholdspakken](https://app.powerbi.com/getdata/services/vmob) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-vmob/services.png)
3. Vælg **VMob** \> **Hent**.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. Når du bliver spurgt, skal du angive din URL-adresse til VMob og klikke på knappen Næste. Denne URL-adresse leveres separat af VMob.
   
    ![](media/service-connect-to-vmob/params.png)
5. Vælg indstillingen **Grundlæggende** på rullelisten Godkendelsesmetode, angiv dit brugernavn og din adgangskode til VMob, og klik på knappen **Log på**.
   
    ![](media/service-connect-to-vmob/creds.png)
6. Importen starter automatisk, og Power BI henter dine VMob-data for at oprette et dashboard og en rapport til dig, som er klar til brug.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

