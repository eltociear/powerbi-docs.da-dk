---
title: "Få vist relateret indhold i Power BI-tjenesten"
description: "Nemmere navigation, se relateret indhold i dashboards, rapporter og datasæt"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 43dffab862173779068f1180f83bc6c92bf98013
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/02/2018
---
# <a name="view-related-content-in-power-bi-service"></a>Få vist relateret indhold i Power BI-tjenesten
Ruden **Relateret indhold** viser, hvordan din Power BI-tjenestes indhold – dashboards, rapporter og datasæt – er forbundet.  Og det bliver bedre: Fra denne rude kan du udføre almindelige opgaver som opdatering, omdøbning, generering af indsigter og meget mere. Vælg en relateret rapport eller dashboard, så åbnes den i dit Power BI-arbejdsområde.   

Som du har muligvis allerede er har opdaget, er rapporter baseret på datasæt, rapportens visualiseringer er derefter fastgjort til dashboards, og dashboardets visualiseringer har en kæde tilbage til rapporter. Men hvordan ved du, hvilke dashboards der er vært for visualiseringer fra din Marketing-rapport? Og hvordan kan du finde disse dashboards? Bruger dashboardet Indkøb visualiseringer fra mere end ét datasæt? Hvis det er tilfældet, hvad hedder de så, og hvordan kan du åbne og redigere dem? Bruges dit HR-datasæt i nogen rapporter eller dashboards, eller kan det flyttes, uden at det medfører brudte kæder? Denne slags spørgsmål kan du få svar i ruden **Relateret indhold**.  Ruden viser ikke kun relateret indholdet, det gør det også muligt for dig at handle på indholdet og let navigere mellem relateret indhold.

![relateret indhold](media/service-related-content/power-bi-view-related-dashboard-new.png)

> [!NOTE]
> Funktionen Relateret indhold virker ikke med streamingdatasæt.
> 
> 

## <a name="view-related-content-for-a-dashboard"></a>Få vist relateret indhold for et dashboard
Se Will få vist relateret indhold for et dashboard. Følg derefter de trinvise instruktioner under videoen for selv at afprøve det med datasættet Eksempel på indkøbsanalyse.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M#t=3m05s" frameborder="0" allowfullscreen></iframe>


Du skal som minimum bruge *visningstilladelser* til et dashboard for at åbne ruden **Relateret indhold**. I dette eksempel vi bruger [Eksempel på indkøbsanalyse](sample-procurement.md).

**Metode 1**

I et arbejdsområde skal du vælge fanen **Dashboards** og derefter vælge ikonet **Få vist relaterede** ![Få vist relaterede-ikon](media/service-related-content/power-bi-view-related-icon-new.png).

![Fanen Dashboard](media/service-related-content/power-bi-view-related-dash-newer.png)

<br>

**Metode 2**

Mens du har et dashboard åbent, skal du vælge   ![ikonet Få vist relaterede](media/service-related-content/power-bi-view-related-new.png) øverst i menulinjen.

Ruden **Relateret indhold** åbnes. Den viser alle de rapporter, der har visualiseringer, der er fastgjort til dashboardet, og deres tilknyttede datasæt. Til dette dashboard er der visuelle effekter, der er fastgjort fra tre forskellige rapporter, og de rapporter er baseret på tre forskellige datasæt.

![Ruden Relateret indhold](media/service-related-content/power-bi-view-related-dashboard-new.png)

Her kan du handle direkte på det relaterede indhold.  Vælg f.eks. et rapportnavn for at åbne det.  For en angivet rapport skal du vælge et ikon for at [analysere i Excel](service-analyze-in-excel.md), [omdøbe](service-rename.md) eller [få indsigt](service-insights.md). For et datasæt skal du vælge et ikon for at [oprette en ny rapport](service-report-create-new.md), [opdatere](refresh-data.md), omdøbe, [analysere i Excel](service-analyze-in-excel.md), [få indsigt](service-insights.md) eller åbne vinduet **Indstillinger** for datasættet.  

## <a name="view-related-content-for-a-report"></a>Få vist relateret indhold for en rapport
Du skal som minimum bruge *visningstilladelser* til en rapport for at åbne ruden **Relateret indhold**. I dette eksempel vi bruger [Eksempel på indkøbsanalyse](sample-procurement.md).

**Metode 1**

I et arbejdsområde skal du vælge fanen **Rapporter** og derefter vælge ikonet **Få vist relaterede** ![Få vist relaterede-ikon](media/service-related-content/power-bi-view-related-icon-new.png).

![Fanen Rapporter](media/service-related-content/power-bi-view-related-report-newer.png)

<br>

**Metode 2**

Åbn rapporten i [Læsevisning](service-reading-view-and-editing-view.md), og vælg ![Få vist relaterede-ikonet](media/service-related-content/power-bi-view-related-new.png) i den øverste menulinje.

Ruden **Relateret indhold** åbnes. Den viser det tilknyttede datasæt og alle dashboards, der har mindst ét felt, der er fastgjort fra rapporten. Til denne rapport er der visualiseringer, der er fastgjort til to forskellige dashboards.

![Ruden Relateret indhold](media/service-related-content/power-bi-view-related-report.png)

Her kan du handle direkte på det relaterede indhold.  Vælg f.eks. et dashboardnavn for at åbne det.  For alle dashboards på listen skal du vælge et ikon for at [dele dashboardet med andre](service-share-dashboards.md) eller for at åbne vinduet **Indstillinger** for dashboardet. For datasættet skal du vælge et ikon for at [oprette en ny rapport](service-report-create-new.md), [opdatere](refresh-data.md), omdøbe, [analysere i Excel](service-analyze-in-excel.md), [få indsigt](service-insights.md) eller åbne vinduet **Indstillinger** for datasættet.  

## <a name="view-related-content-for-a-dataset"></a>Få vist relateret indhold for et datasæt
Du skal som minimum bruge *visningstilladelser* til et datasæt for at åbne ruden **Relateret indhold**. I dette eksempel vi bruger [Eksempel på indkøbsanalyse](sample-procurement.md).

I et arbejdsområde skal du vælge fanen **Datasæt** og finde ikonet **Få vist relaterede**![Få vist relaterede-ikon](media/service-related-content/power-bi-view-related-icon-new.png).

![Fanen Datasæt](media/service-related-content/power-bi-view-related-dataset-newer.png)

Vælg ikonet for at åbne ruden **Relateret indhold**.

![](media/service-related-content/power-bi-datasets.png)

Her kan du handle direkte på det relaterede indhold.  Vælg f.eks. et dashboard- eller rapportnavn for at åbne det.  For alle dashboards på listen skal du vælge et ikon for at [dele dashboardet med andre](service-share-dashboards.md) eller for at åbne vinduet **Indstillinger** for dashboardet. For en rapport skal du vælge ikonet for at [analysere i Excel](service-analyze-in-excel.md), [omdøbe](service-rename.md) eller [få indsigt](service-insights.md).  

## <a name="limitations-and-troubleshooting"></a>Begrænsninger og fejlfinding
* Hvis din browser ikke har tilstrækkelig plads, kan du ikke se en indstilling for **Få vist relaterede**, men du får stadig vist ikonet Få vist relaterede ![Få vist relaterede-ikon](media/service-related-content/power-bi-view-related-icon-new.png). Vælg ikonet for at åbne ruden **Relateret indhold**.
* Hvis du vil åbne Relateret indhold for en rapport, skal du være i [Læsevisning](service-reading-view-and-editing-view.md).
* Relateret indhold er ikke tilgængeligt i Power BI Desktop.
* Funktionen Relateret indhold fungerer ikke for streamingdatasæt.

## <a name="next-steps"></a>Næste trin
* [Introduktion til Power BI-tjenesten](service-get-started.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

