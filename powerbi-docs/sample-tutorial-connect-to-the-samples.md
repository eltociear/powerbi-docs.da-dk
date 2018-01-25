---
title: Brug af Power BI-eksempler, et selvstudium.
description: 'Selvstudium: Brug af Power BI-eksempler'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 03/08/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: d92edce9ae1332c4a0c73be5db93201c9b87dc86
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="the-power-bi-samples-a-tutorial"></a>Power BI-eksemplerne, et selvstudium
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

Vi anbefaler at starte med artiklen [Eksempeldatasæt til Power BI](sample-datasets.md). I den artikel lærer du alt om eksemplerne. Hvordan du får dem, hvor du gemmer dem, hvordan du bruger dem og nogle af historierne, som hvert eksempel fortæller. Når du har fået styr på det grundlæggende, så vend tilbage til dette selvstudium.   

## <a name="about-this-tutorial"></a>Om dette selvstudium
I selvstudium lærer du, hvordan du importerer indholdspakkerne med eksempler, føjer dem til Power BI-tjenesten og åbner indholdet. En *indholdspakke* er en eksempeltype, hvor datasættet er pakket sammen med et dashboard og en rapport. Indholdspakkerne med eksempler er tilgængelige i Power BI ved brug af **Hent data**.

> [!NOTE]
> Dette selvstudium gælder for Power BI-tjenesten, og ikke Power BI Desktop.
> 
> 

Indholdspakke med eksemplet *Retail Analysis*, der bruges i dette selvstudium, består af et dashboard, en rapport og et datasæt.
Lær denne indholdspakke og dens scenarie at kende ved at [tage en rundvisning af Retail Analysis-eksemplet](sample-retail-analysis.md), før du starter.

## <a name="get-data-in-this-case-get-a-sample-content-pack"></a>Hent data (i dette tilfælde, hent en indholdspakke med eksempel)
1. Åbn Power BI-tjenesten (app.powerbi.com), og log på.
2. Vælg et arbejdsområde, og opret et nyt dashboard.  
   
    ![](media/sample-tutorial-connect-to-the-samples/power-bi-create-dashboard2.png)
3. Navngiv det **Retail Analysis Sample**.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-name-dashboard.png)
4. Vælg **Hent data** nederst i venstre navigationsrude. Hvis du ikke kan se **Hent data**, så udvid ruden ved at vælge ![](media/sample-tutorial-connect-to-the-samples/expand-nav.png).
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_getdata.png)
5. Vælg **Eksempler**.  
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_samplesdownload.png)
6. Vælg *Retail Analysis Sample*, og vælg **Opret forbindelse**.   
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_retailanalysissampleconnect.png)

## <a name="what-exactly-was-imported"></a>Hvad blev der helt præcist importeret?
Med indholdspakkerne med eksempel henter Power BI en kopi af indholdet og gemmer det for dig i clouden, når du vælger **Opret forbindelse**. Da den person, der oprettede indholdspakken inkluderede et datasæt, en rapport og et dashboard, er det, det du får, når du klikker på **Opret forbindelse**.

1. Power BI opretter det nye dashboard og viser det på fanen **Dashboards**. Den gule stjerne viser dig, at det er nyt.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-dashboard.png)
2. Åbn fanen **Rapporter**.  Her kan du se en ny rapport med navnet *Retail Analysis Sample*.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-report.png)
   
   Og se fanen **Datasæt**.  Der er også et nyt datasæt.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-dataset.png)

## <a name="explore-your-new-content"></a>Udforsk dit nye indhold
Udforsk nu dashboardet, datasættet og rapporten på egen hånd. Der er mange forskellige måder til at navigere til dine dashboards, rapporter og datasæt, og kun en af dem er beskrevet herunder.  

> [!TIP]
> Vil du holdes lidt i hånden først?  Prøv [Tour of the Retail Analysis sample](sample-retail-analysis.md), hvor du får en trinvis gennemgang af dette eksempel.
> 
> 

1. Naviger tilbage til fanen **Dashboards**, og vælg dashboardet *Retail Analysis Sample* for at åbne det.    
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards.png)
2. Dashboardet åbnes.  Det har forskellige visualiseringsfelter.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards2new.png)
3. Vælg et af felterne for at åbne den underliggende rapport.  I dette eksempel vælger vi områdediagrammet (vist med lyserødt på det forrige billede). Rapporten åbnes på siden, der indeholder områdediagrammet.
   
    ![](media/sample-tutorial-connect-to-the-samples/power-bi-report.png)
   
   > [!NOTE]
   > Hvis feltet var blevet oprettet ved brug af [Power BI Q&A](power-bi-q-and-a.md), ville Q&A-siden være blevet åbent i stedet for.
   > 
   > 
4. Tilbage på fanen **Datasæt** har du flere muligheder for at udforske dit datasæt.  Du kan ikke åbne det for at se alle rækkerne og kolonnerne (ligesom du kan i Power BI Desktop eller Excel).  Når en person deler en indholdspakke med kollegaer, ønsker de typisk at dele indsigt og ikke give deres kollegaer direkte adgang til dataene. Men det betyder ikke, at du ikke kan udforske datasættet.  
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon2.png)
   
   * En af måderne til at udforske datasættet er ved at oprette dine egne visualiseringer og rapporter fra bunden.  Vælg diagramikonet ![](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon4.png) for at åbne datasættet i rapportredigeringstilstand.
     
       ![](media/sample-tutorial-connect-to-the-samples/power-bi-report-editing.png)
   * En anden måde til at udforske datasættet er ved at køre [Hurtig indsigt](service-insights.md). Vælg ellipsen (...), og vælg **Få indsigt**. Vælg **Vis indsigt**, når indsigten er klar.
     
       ![](media/sample-tutorial-connect-to-the-samples/power-bi-insights.png)

## <a name="next-steps"></a>Næste trin
[Grundlæggende begreber i Power BI](service-basic-concepts.md)

[Eksempler til Power BI-tjenesten](sample-datasets.md)

[Datakilder til Power BI](service-get-data.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

