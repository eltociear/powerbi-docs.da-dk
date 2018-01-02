---
title: Optimer dine data til Power BI Quick Insights
description: "Optimer dine data til Power BI Quick Insights. Hvis Power BI ikke kan finde indsigter i dine data, kan du benytte følgende tiltag"
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
ms.date: 09/02/2017
ms.author: mihart
ms.openlocfilehash: 61901d0055c22540ec2f10bedbbb8cf641d606e9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>Optimer dine data til Power BI Quick Insights
Vil du forbedre Quick Insights-resultater?  Hvis du er ejer af datasæt, skal du prøve følgende:

* Skjul eller vis kolonner i dit datasæt. Power BI Quick Insights søger ikke i skjulte kolonner.  Derfor skal du skjule duplikerede eller unødvendige kolonner og vise interessante kolonner.
* Brug en blanding af datatyper som f.eks. navne, klokkeslæt, datoer og tal.
* Undgå (eller skjul) kolonner med duplikerede oplysninger.  Dette tager værdifuld tid fra søgning efter mønstre, der giver mere mening.  Eksempelvis en kolonne med delstatsnavne skrevet ud og en anden kolonne med forkortede delstatsnavne.
* Modtager du en fejlmeddelelse, der angiver, at dine data ikke er statistisk signifikante?  Dette kan ske med modeller, der er meget simple, eller som ikke indeholder mange data, eller som ikke har dato- eller numeriske kolonner. Hvis du vil generere indsigter, skal dit datasæt have mindst én dimension og én måling.

### <a name="next-steps"></a>Næste trin
[Power BI Quick Insights](service-insights.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

