---
title: Opret forbindelse til Mandrill med Power BI
description: Mandrill til Power BI
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
ms.openlocfilehash: 976ca32f0c43f6d8412f9468dc9f61ab9768fa4c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-mandrill-with-power-bi"></a>Opret forbindelse til Mandrill med Power BI
Power BI-indholdspakken trækker data fra din Mandrill-konto og opretter et dashboard, et sæt rapporter og et datasæt, så du kan udforske dine data. Brug Mandrills analyser til hurtigt for at få overblik over dine nyhedsbreve eller din markedsføringskampagne. Dataene er indstillet til daglig opdatering for at sikre, at de data, du overvåger, er opdaterede.

Opret forbindelse til [Mandrill-indholdspakken til Power BI.](http://app.powerbi.com/getdata/services/mandrill)

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-mandrill/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
    ![](media/service-connect-to-mandrill/services.png)
3. Vælg **Mandrill** > **Hent**.
   
    ![](media/service-connect-to-mandrill/mandrill.png)
4. Vælg **Nøgle** som **Godkendelsesmetode**, og angiv din API-nøgle. Du kan finde nøglen under fanen **Indstillinger** i Mandrill-dashboardet. Vælg **Log på** for at starte importprocessen, som kan tage et par minutter, afhængigt af mængden af data på din konto.
   
    ![](media/service-connect-to-mandrill/auth.png)
5. Når Power BI har importeret dataene, vises der et nyt dashboard, rapport og datasæt i venstre navigationsrude. Dette er standarddashboardet, som Power BI oprettede for at vise dine data.
   
    ![](media/service-connect-to-mandrill/mandrill-dashboard1.jpg)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="next-steps"></a>Næste trin
[Introduktion til Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

