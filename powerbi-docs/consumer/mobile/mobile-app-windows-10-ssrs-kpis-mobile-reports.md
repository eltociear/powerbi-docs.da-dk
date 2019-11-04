---
title: Få vist SSRS-mobilrapporter og KPI'er i Windows 10-mobilappen – Power BI
description: Power BI-mobilappen til Windows 10 tilbyder live, touchaktiveret mobiladgang til dine vigtige firmaoplysningerne i det lokale miljø.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: mshenhav
ms.openlocfilehash: 114cf65e8abb072ab3f0254cbd4041a43a31d1dc
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/30/2019
ms.locfileid: "73059638"
---
# <a name="view-reporting-services-ssrs-mobile-reports-and-kpis-in-the-windows-10-power-bi-mobile-app"></a>Få vist SSRS-mobilrapporter (SQL Server Reporting Services) og KPI'er i Windows 10 Power BI-mobilappen
Power BI-mobilappen til Windows 10 tilbyder live, touchaktiveret mobiladgang til dine vigtige firmaoplysningerne i det lokale miljø via SQL Server 2016 Reporting Services. 

![Reporting Services-mobilrapporter](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>Det vigtigste først
[Opret Reporting Services-mobilrapporter](https://msdn.microsoft.com/library/mt652547.aspx) med SQL Server 2016 Enterprise Edition Mobile Report Publisher, og publicer dem på [Reporting Services-webportalen](https://msdn.microsoft.com/library/mt637133.aspx). Opret KPI'er direkte på webportalen. Organiser dem i mapper, og markér dine favoritter, så du nemt kan finde dem. 

Få derefter vist mobilrapporter og KPI'er organiseret i mapper eller samlet som favoritter i Power BI-mobilappen til Windows 10. 

> [!NOTE]
> Din enhed skal køre Windows 10. Appen fungerer bedst på enheder med mindst 1 GB RAM og 8 GB internt lager.
> 
> 

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Udforsk eksempler uden en SQL Server 2016 Reporting Services-server
Selvom du ikke har adgang til en Reporting Services-webportal, kan du stadig udforske funktionerne i Reporting Services-mobilrapporter.

1. Åbn Power BI-appen på din Windows 10-enhed.
2. Tryk på knappen til global navigation ![Knappen til global navigation](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) i øverste venstre hjørne.
3. Tryk på ikonet **Indstillinger** ![ikonet Indstillinger](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png), højreklik eller tryk på **Opret forbindelse til serveren**, og tryk derefter på **Få vist eksempler**.
   
   ![Få vist SSRS-eksempler](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. Åbn mappen Retail Reports eller Sales Reports for at se deres KPI'er og mobilrapporter.
   
   ![Eksempel-KPI'er og -mobilrapporter](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

Gennemse eksemplerne for at interagere med KPI'er og mobilrapporter.

## <a name="connect-to-a-reporting-services-report-server"></a>Opret forbindelse til en Reporting Services-rapportserver
1. Nederst på navigationslinjen til venstre skal du trykke på **Indstillinger** ![ikonet Indstillinger](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png)
2. Tryk på **Opret forbindelse til serveren**.
3. Udfyld serveradressen og dit brugernavn og din adgangskode. Brug dette format til serveradressen:
   
     `http://<servername>/reports` ELLER   `https://<servername>/reports`
   
   > [!NOTE]
   > Inkluder **http** eller **https** i begyndelsen af forbindelsesstrengen.
   > 
   > 
   
    Tryk på **Avanceret indstilling** for evt. at give serveren et navn.
4. Tryk på markeringen for at oprette forbindelse. 
   
   Nu kan du se serveren på navigationslinjen til venstre.
   
   ![Server på navigationslinjen til venstre](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >Tryk på knappen til globale navigation ![knappen til global navigation](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) når som helst for at skifte mellem dine Reporting Services-mobilrapporter og dine dashboards i Power BI-tjenesten. 
   > 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>Visning af Reporting Services-KPI'er og mobilrapporter i Power BI-appen
Reporting Services-KPI'er og mobilrapporter vises i de samme mapper, som de er placeret i på Reporting Services-webportalen.

![Rapportmapper](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* Tryk på en KPI for at få den vist i fokuseringstilstand.
  
    ![KPI i fokuseringstilstand](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* Tryk på en mobilrapport for at åbne og interagere med den i Power BI-appen.
  
    ![Reporting Services-mobilrapport](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Få vist dine foretrukne KPI'er og rapporter
Du kan markere KPI'er og mobilrapporter som favoritter på din Reporting Services-webportal og derefter se dem i en praktisk mappe på din Windows 10-mobilenhed sammen med dine foretrukne Power BI-dashboards og -rapporter.

* Tryk på **Favoritter**.
  
   ![Ikonet Favoritter](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   Dine favoritter fra webportalen findes alle på denne side.
  
   ![Siden Favoritter](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

Læs mere om [Favoritter i Power BI-mobilappsene](mobile-apps-favorites.md).

## <a name="remove-a-connection-to-a-report-server"></a>Fjern en forbindelse til en rapportserver
Du kan kun oprette forbindelse til én rapportserver ad gangen fra din Power BI-mobilapp. Hvis du vil oprette forbindelse til en anden server, skal du afbryde forbindelsen til den aktuelle.

1. Nederst på navigationslinjen til venstre skal du trykke på **Indstillinger** ![ikonet Indstillinger](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png).
2. Tryk på og hold det servernavn nede, som du ikke vil have forbindelse til.
3. Tryk på **Fjern server**.
   
    ![Fjern server](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Opret Reporting Services-mobilrapporter og -KPI'er
Du opretter ikke Reporting Services-KPI'er og -mobilrapporter i Power BI-mobilappen. Du opretter dem i SQL Server Mobile Report Publisher og på en SQL Server 2016 Reporting Services-webportal.

* [Opret dine egne Reporting Services-mobilrapporter](https://msdn.microsoft.com/library/mt652547.aspx), og publicer dem på en Reporting Services-webportal.
* Opret [KPI'er på en Reporting Services-webportal](https://msdn.microsoft.com/library/mt683632.aspx)

## <a name="next-steps"></a>Næste trin
* [Kom i gang med Power BI-mobilappen til Windows 10](mobile-windows-10-phone-app-get-started.md)  
* [Hvad er Power BI?](../../fundamentals/power-bi-overview.md)  
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

