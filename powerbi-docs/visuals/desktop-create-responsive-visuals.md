---
title: Optimer en Power BI-visualisering til enhver størrelse
description: Få mere at vide om, hvordan du optimerer visuals i Power BI Desktop og Power BI-tjenesten til Power BI-telefonapps.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 4372f37cf6afc8fe51d6650ddd888bd41d3ea678
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61394874"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Optimer en Power BI-visualisering til enhver størrelse
Når du opretter en ny rapport, er de visuelle elementer *dynamiske* som standard: De ændres dynamisk, så den maksimale mængde data og indsigt vises uanset skærmstørrelse. Du kan angive, at visuals i ældre rapporter også skal ændre størrelse dynamisk.

Når visualiseringen ændrer størrelse, prioriterer Power BI datavisningen ved f.eks. at fjerne udfyldning og flytte forklaringen til øverst i visualiseringen automatisk, således at visualiseringen fortsat er informativ, selvom den bliver mindre. Dynamisk funktionalitet er især nyttigt i forbindelse med visualiseringer i Power BI-mobilappen på telefoner.

![Dynamisk tilpasning af en visualiserings størrelse](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Alle visuals med X- og Y-akser og udsnit kan ændre størrelse dynamisk.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Slå dynamisk funktionalitet til i Power BI Desktop
1. I en ældre rapport i Power BI Desktop skal du på fanen **Vis** sikre, at du har åbnet **Skrivebordslayout**.
   
    ![Ikonet Skrivebordslayout](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Vælg en visualisering, og i ruden **Visualiseringer** skal du vælge sektionen **Format**.
3. Udvid **Generelt** > skub **Dynamisk** til **Til**.
   
    ![Dynamisk Til](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Når du nu [opretter en rapport, der er optimeret til telefonen](../desktop-create-phone-report.md) og tilføjer denne visualisering, tilpasses den på fornem vis.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Slå dynamisk funktionalitet til i Power BI-tjenesten
Du kan slå dynamisk funktionalitet til for en visual i en rapport i Power BI-tjenesten. Du skal have mulighed for at redigere rapporten.

1. I en rapport i Power BI-tjenesten ([https://powerbi.com](https://powerbi.com)) skal du vælge **Rediger rapport**.
2. Vælg en visualisering, og i ruden **Visualiseringer** skal du vælge sektionen **Format**.
3. Udvid **Generelt** > skub **Dynamisk** til **Til**.
   
    ![Dynamisk Til](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Når du nu [opretter en telefonvisning af denne rapport](../desktop-create-phone-report.md) og tilføjer denne visual, tilpasses den på fornem vis.

## <a name="next-steps"></a>Næste trin
* [Opret rapporter, der er optimeret til Power BI-telefonapps](../desktop-create-phone-report.md)
* [Få vist Power BI-rapporter, der er optimeret til din telefon](../consumer/mobile/mobile-apps-view-phone-report.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

