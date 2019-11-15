---
title: 'Sådan fastgør du en hel rapportside til et Power BI-dashboard '
description: Dokumentationen om, hvordan du fastgør en hel dynamisk rapportside til et Power BI-dashboard fra en rapport.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: d620c1def289cea39a90092876ce275eea8ee699
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73853069"
---
# <a name="pin-an-entire-report-page-as-a-live-tile-to-a-power-bi-dashboard"></a>Fastgør en hel rapportside, som et dynamisk felt, til et Power BI-dashboard
En anden måde at tilføje et nyt [dashboardfelt](consumer/end-user-tiles.md) på er ved at fastgøre en hel rapportside. Dette er en nem metode til at fastgøre mere end én visualisering ad gangen.  Når du fastgør en hel side, er felterne også *dynamiske*, og du kan interagere med dem direkte på dashboardet. Og de ændringer, du foretager af visualiseringerne i rapporteditoren, f.eks. ved at tilføje et filter eller ændre de felter, der bruges i diagrammet, afspejles også i dashboardfeltet.  

Det er kun muligt at fastgøre dynamiske felter fra rapporter på dashboards i Power BI-tjenesten (app.powerbi.com).

> [!NOTE]
> Du kan ikke fastgøre felter fra rapporter, der deles med dig.
> 
> 

## <a name="pin-a-report-page"></a>Fastgør en rapportside
Se Amanda fastgøre en dynamisk rapportside til et dashboard, og følg derefter den trinvise vejledning under videoen for selv at prøve det.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EzhfBpPboPA" frameborder="0" allowfullscreen></iframe>


1. Åbn en rapport i [redigeringstilstand](service-interact-with-a-report-in-editing-view.md).
2. Vælg **Fastgør dynamisk side** på menulinjen, uden at der er valgt visualiseringer.
   
   ![Ikon til fastgørelse af dynamisk side](media/service-dashboard-pin-live-tile-from-report/pbi-pin-live-page.png) 
3. Fastgør feltet til et eksisterende dashboard eller et nyt dashboard. Læg mærke til den fremhævede tekst: *Ved at fastgøre en dynamisk side vises ændringer i rapporter på dashboardfeltet, når siden opdateres.*
   
   * Eksisterende dashboard: Vælg navnet på dashboardet på rullelisten. Dashboards, der er blevet delt med dig, vises ikke på rullelisten.
   * Nyt dashboard: Skriv navnet på det nye dashboard.
     
     ![Dialogboksen Fastgør til dashboard](media/service-dashboard-pin-live-tile-from-report/pbi-pin-live-page-dialog.png)
4. Vælg **Fastgør dynamisk**. En meddelelse om fuldførelse (næsten helt oppe i højre hjørne) giver dig besked om, at siden er blevet føjet til dit dashboard som et felt.

## <a name="open-the-dashboard-to-see-the-pinned-live-tile"></a>Åbn dashboardet for at se det fastgjorte felt
1. Vælg dashboardet med det nye dynamiske felt i navigationsruden. Her kan du f.eks. [omdøbe, ændre størrelse på, sammenkæde og flytte](service-dashboard-edit-tile.md) den fastgjorte rapportside.  
2. Interager med det dynamiske felt.  På skærmbilledet herunder har valg af en søjle i søjlediagrammet filtreret og fremhævet de andre visualiseringer i feltet i tværgående retning.
   
    ![dashboards med et dynamisk felt](media/service-dashboard-pin-live-tile-from-report/pbi-live-tile.png)

## <a name="next-steps"></a>Næste trin
[Dashboards i Power BI](consumer/end-user-dashboards.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

