---
title: "Optimer en Power BI-visualisering til enhver størrelse"
description: "Få mere at vide om, hvordan du optimerer visualiseringer i Power BI Desktop og Power BI-tjenesten til Power BI-telefonapps."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: a059c01d6e9e08851434f71a1f36ac096054e291
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Optimer en Power BI-visualisering til enhver størrelse
Du kan indstille visualiseringerne på dit dashboard eller i din rapport til at være *dynamiske*, så de ændres dynamisk for at vise den maksimale mængde data og indsigt, uanset skærmstørrelse.

Når visualiseringen ændrer størrelse, prioriterer Power BI datavisningen ved f.eks. at fjerne udfyldning og flytte forklaringen til øverst i visualiseringen automatisk, således at visualiseringen fortsat er informativ, selvom den bliver mindre. Dynamisk funktionalitet er især nyttigt i forbindelse med visualiseringer i Power BI-mobilappen på telefoner.

![Dynamisk tilpasning af en visualiserings størrelse](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Du kan slå dynamisk funktionalitet til for alle visualiseringer med X- og Y-akser og udsnit.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Slå dynamisk funktionalitet til i Power BI Desktop
1. I Power BI Desktop på fanen **Vis** skal du sikre, at du har åbnet **Skrivebordslayout**.
   
    ![Ikonet Skrivebordslayout](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Vælg en visualisering, og i ruden **Visualiseringer** skal du vælge sektionen **Format**.
3. Udvid **Generelt** > skub **Dynamisk** til **Til**.
   
    ![Dynamisk Til](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Når du nu [opretter en rapport, der er optimeret til telefonen](desktop-create-phone-report.md) og tilføjer denne visualisering, tilpasses den på fornem vis.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Slå dynamisk funktionalitet til i Power BI-tjenesten
Du kan slå dynamisk funktionalitet til for en visualisering i en rapport i Power BI-tjenesten. Du skal have mulighed for at redigere rapporten.

1. I en rapport i Power BI-tjenesten ([https://powerbi.com](https://powerbi.com)) skal du vælge **Rediger rapport**.
2. Vælg en visualisering, og i ruden **Visualiseringer** skal du vælge sektionen **Format**.
3. Udvid **Generelt** > skub **Dynamisk** til **Til**.
   
    ![Dynamisk Til](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Når du nu [opretter en telefonvisning af et dashboard](service-create-dashboard-mobile-phone-view.md) og tilføjer denne visualisering, tilpasses den på fornem vis.

## <a name="next-steps"></a>Næste trin
* [Opret rapporter, der er optimeret til Power BI-telefonapps](desktop-create-phone-report.md)
* [Opret en telefonvisning af et dashboard i Power BI](service-create-dashboard-mobile-phone-view.md)
* [Få vist Power BI-rapporter, der er optimeret til din telefon](mobile-apps-view-phone-report.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

