---
title: KPI-visualiseringer (selvstudium)
description: opret KPI i power bi
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: xmja6EpqaO0
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/09/2017
ms.author: mihart
ms.openlocfilehash: 23b322c9fbc4c203a5b20aa45bb41c2cb6cb7f0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="kpi-visuals-tutorial"></a>KPI-visualiseringer (selvstudium)
Et nøgletal (KPI) er en visuel ledetråd, der viser fremgangen mod et målbart mål. Du kan finde flere oplysninger om KPI'er ved at se [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050).

## <a name="when-to-use-a-kpi"></a>Hvornår bruger man et KPI
KPI'er er et godt valg:

* til at måle fremgang (hvad er jeg foran eller bagefter med?)
* til at måle afstanden til et mål (hvor langt foran eller bagefter er jeg?)   

## <a name="kpi-visual-requirements"></a>Krav til KPI-visualiseringer
Et nøgletal (KPI) er baseret på et bestemt mål og er designet til at hjælpe dig med at evaluere den aktuelle værdi og status for en metrik i henhold til et angivet mål. KPI-visualiseringer kræver derfor en *basismåling*, som evalueres til en værdi, og en *mål*-måling eller -værdi, og en tærskel eller et mål.

> [!NOTE]
> I øjeblikket skal et KPI-datasæt indeholde målværdier for et KPI. Hvis dit datasæt ikke indeholder et mål, kan du oprette dem ved at føje et Excel-ark med mål til din datamodel eller PBIX-fil.
> 
> 

## <a name="how-to-create-a-kpi"></a>Sådan opretter du et KPI
Log på Power BI for at følge med, og vælg **Hent Data > Eksempler > Retail Analysis Sample**. Vi opretter et KPI, der måler vores fremgang mod et salgsmål.

Eller se Sådan opretter du enkelte metrikvisualiseringer: mål, kort og nøgletal.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Vælg **Sales > Total Units This Year**.  Dette er indikatoren.
2. Tilføj **Time > Month**.  Dette repræsenterer tendensen.
3. VIGTIGT: Sorter diagrammet efter **Month**. Når du konverterer visualiseringen til et KPI, er der ikke muligt at sortere.
4. Konverter visualiseringen til et KPI ved at vælge ikonet KPI i visualiseringsruden.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-icon.png)
5. Tilføj et mål. Tilføj sidste års salg som målet. Træk **Total Units Last Year** til feltet **Target goals**.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi.png)
6. Du kan eventuelt formatere KPI'et ved at vælge malerrulleikonet for at åbne ruden Formatering.
   
   * **Indicator** – -styrer indikatorens visningsenheder og decimalpladser.
   * **Trend axis** – når den er slået **Til**, vises tendensaksen som baggrund i KPI-visualiseringen.  
   * **Goals** – når det er slået **Til**, viser visualiseringen målet og afstanden til målet som en procentdel.
   * **Status** – nogle KPI'er anses som *bedre* for højere værdier, og nogle anses som *bedre* for lavere værdier. For eksempel indtægter vs. ventetid. En højere værdi for indtjening er typisk bedre i forhold til en højere værdi for ventetiden – det anses normalt som værre. Denne indstilling muliggør valget af en KPI-funktionsmåde. Statusvalget er som standard, **høj er bedre**.
7. Når du har KPI'et, som du vil have det, skal du [fastgøre det til et dashboard](service-dashboard-pin-tile-from-report.md).

KPI'er er også tilgængelige på dine mobilenheder – så du altid har fingeren på virksomhedens puls.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Hvis KPI'et ikke ligner det ovenfor, kan det skyldes, at du skal sortere efter måned. Da KPI'er ikke har en sorteringsindstilling, skal du sorterer efter måned, *før* du konverterer din visualisering til et KPI.

## <a name="next-steps"></a>Næste trin
[Rapporter i Power BI](service-reports.md)

[Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

