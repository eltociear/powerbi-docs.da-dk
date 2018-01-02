---
title: Opret et felt med et stort tal fra en rapport i Power BI
description: Opret et felt med et stort tal fra en rapport i Power BI
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 9f748ed1d3a34c6c6aceb14337bbb780598a15f9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-a-power-bi-report"></a>Opret et felt med et stort tal fra en rapport i Power BI
Nogle gange er et enkelt tal det vigtigste, du vil finde frem til på dit Power BI-dashboard, som f.eks. salg i alt, markedsandel år efter år eller samlede salgsmuligheder. Du kan oprette et felt med et stort tal ved at [stille et spørgsmål i feltet til spørgsmål og svar](power-bi-visualization-big-number.md) eller i en Power BI-rapport. Denne artikel forklarer, hvordan du opretter et i en rapport.

1. Opret et [dashboard](service-dashboards.md), og [hent data](service-get-data.md).
   
   Hvis du vil have data at øve dig på, [kan du downloade eksemplet på detailhandelsanalyse](sample-retail-analysis.md). 
2. Åbn rapporten i [Redigeringsvisning](service-reading-view-and-editing-view.md).
3. Find en side i rapporten med et tomt område, eller [tilføj en ny side i rapporten](power-bi-report-add-page.md).
4. Vælg talfeltet, som du vil vise, i listen Felter.
   
   I dette eksempel skal du **åbne Store count** i tabellen **Store**. Power BI opretter et søjlediagram med det ene tal.
   
   ![](media/power-bi-visualization-big-number-report/pbi_rptnumbertilechart.png)
5. Vælg kortikonet i ruden Visuelle effekter.
   
   ![](media/power-bi-visualization-big-number-report/pbi_changechartcard.png)
6. Hold markøren over kortet, og vælg tandhjulsikonet ![](media/power-bi-visualization-big-number-report/pbi_pintile.png) for at føje feltet til dashboardet. 
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-icon.png)
7. Fastgør feltet til et eksisterende dashboard eller til et nyt dashboard. 
   
   * Eksisterende dashboard: Vælg navnet på dashboardet på rullelisten.
   * Nyt dashboard: Skriv navnet på det nye dashboard.
8. Vælg **Fastgør**.
   
   En meddelelse om fuldførelse (næsten helt oppe i højre hjørne) giver dig besked om, at det visuelle element er blevet føjet til dit dashboard som et felt.
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-success-message.png)
9. Vælg **Gå til dashboard**. Der kan du [redigere og flytte](service-dashboard-edit-tile.md) den fastgjorte visualisering.

## <a name="next-steps"></a>Næste trin
[Dashboard-felter i Power BI](service-dashboard-tiles.md)

[Dashboards i Power BI](service-dashboards.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

