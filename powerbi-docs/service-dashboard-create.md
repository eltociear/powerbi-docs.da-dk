---
title: Opret et Power BI-dashboard fra en rapport
description: Opret et Power BI-dashboard fra en rapport
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/09/2017
ms.author: mihart
ms.openlocfilehash: dac5628756898a20fe139447bc2d165ba804320c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Opret et Power BI-dashboard fra en rapport
Du har læst [Dashboards i Power BI](service-dashboards.md), og nu vil du oprette dit eget. Der er mange forskellige måder at oprette et dashboard på – fra en rapport, fra bunden, fra et datasæt, ved at kopiere et eksisterende dashboard og meget mere.  Dette emne og denne video viser dig, hvordan du opretter et nyt dashboard ved at fastgøre visualiseringer fra en eksisterende rapport.

> **BEMÆRK!** Dashboards er en funktion i Power BI-tjenesten ikke Power BI Desktop. Der kan ikke oprettes dashboards på Power BI-mobilenheder, men du kan [få dem vist og dele dem](mobile-apps-view-dashboard.md).
> 
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Opret et dashboard ved at fastgøre visualiseringer og billeder fra en rapport
Se Amanda oprette et nyt dashboard ved at fastgøre visualiseringer fra en rapport. Prøv det derefter selv ved hjælp af eksemplet på indkøbsanalyse ved at følge trinnene under videoen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Importér et datasæt med en rapport
Vi importerer et af eksempeldatasættene i Power BI og bruger det til at oprette vores nye dashboard. Det eksempel, vi bruger, er en Excel-projektmappe med to PowerView-ark. Når du importerer projektmappen til Power BI, føjes der et datasæt og en rapport til dit arbejdsområde.  Rapporten oprettes automatisk ud fra PowerView-arkene.

1. [Vælg dette link](http://go.microsoft.com/fwlink/?LinkId=529784) for at downloade og gemme Excel-filen med eksempel på indkøbsanalyse. Det anbefales, at du gemme den i din OneDrive for Business.
2. Åbn Power BI-tjenesten i din browser (app.powerbi.com).
3. Vælg et eksisterende arbejdsområde, eller opret et nyt apparbejdsområde.
4. Vælg **Hent data** i navigationen til venstre.
   
    ![](media/service-dashboard-create/power-bi-get-data3.png)
5. Vælg **Filer**.
   
   ![](media/service-dashboard-create/power-bi-select-files.png)
6. Naviger til den placering, hvor du har gemt Excel-filen med eksempel på indkøbsanalyse. Markér den, og vælg **Opret forbindelse**.
   
   ![](media/service-dashboard-create/power-bi-connectnew.png)
7. Til denne øvelse skal du vælge **Importér**.
   
    ![](media/service-dashboard-create/power-bi-import.png)
8. Når du får vist meddelelsen om, at processen lykkedes, skal du klikke på **x** for at lukke den.
   
   ![](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>Åbn rapporten, og fastgør nogle felter på et dashboard
1. Bliv i samme arbejdsområde, og vælge fanen **Rapporter**. Den nyligt importerede rapport vises med en gul stjerne. Markér navnet på rapporten for at åbne den.
   
    ![](media/service-dashboard-create/power-bi-reports.png)
2. Rapporten åbnes i [læsevisning](service-interact-with-a-report-in-reading-view.md). Bemærk, at den har to faner nederst: Discount Analysis (Rabatanalyse) og Spend Overview (Udgiftsoversigt). Hver fane repræsenterer en side i rapporten.
   
    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. Peg på en visualisering for at få vist de tilgængelige indstillinger. Hvis du vil føje en visualisering til et dashboard, skal du vælge ikonet til fastgørelse ![](media/service-dashboard-create/power-bi-pin-icon.png).
   
    ![](media/service-dashboard-create/power-bi-hover.png)
4. Da vi opretter et nyt dashboard, skal du markere indstillingen for **nyt dashboard** og give den et navn. 
   
   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. Når du vælger **Fastgør**, opretter Power BI det nye dashboard i det aktuelle arbejdsområde. Når meddelelsen **Fastgjort til dashboard** vises, skal du vælge **Gå til dashboard**. Hvis du bliver bedt om at gemme rapporten, skal du vælge **Gem**.
   
     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI åbner det nye dashboard, og der er ét felt – den visualisering, vi lige har fastgjort. 
   
   ![](media/service-dashboard-create/power-bi-pinned.png)
7. Markér feltet for at vende tilbage til rapporten. Fastgør nogle flere felter til det nye dashboard. Når vinduet **Fastgør til dashboard** vises, skal du denne gang vælge **Eksisterende dashboard**.  
   
   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

Tillykke med oprettelsen af dit første dashboard! Nu, hvor du har et dashboard, er der så utroligt meget, du kan bruge det til.  Prøv en af de foreslåede **Næste trin** nedenfor, eller begynd at afspille og udforske på egen hånd.   

## <a name="next-steps"></a>Næste trin
* [Tilpas størrelsen af felter, og flyt dem](service-dashboard-edit-tile.md)
* [Alt om dashboardfelter](service-dashboard-tiles.md)
* [Del dit dashboard ved at oprette en app](service-create-distribute-apps.md)
* [Power BI – Grundlæggende begreber](service-basic-concepts.md)
* [Dashboards i Power BI](service-dashboards.md)
* [Tip til udformning af et fantastisk dashboard](service-dashboards-design-tips.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

