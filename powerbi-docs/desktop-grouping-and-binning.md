---
title: Brug gruppering og gruppering i beholder i Power BI Desktop
description: Få mere at vide om, hvordan du grupperer og placerer elementer i beholdere i Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9e8cfc89ba1556f2c6c28c4ddafc7a1bfad3029f
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2018
---
# <a name="use-grouping-and-binning-in-power-bi-desktop"></a>Brug gruppering og gruppering i beholder i Power BI Desktop
Når der oprettes visuals i **Power BI Desktop**, samles dine data i dele (eller grupper) baseret på de værdier, der bliver fundet i de underliggende data. Det er ofte fint, men der kan være tilfælde, hvor du gerne vil justere, hvordan disse dele vises. Eksempel: Du vil måske placere tre produktkategorier i én større kategori (én *gruppe*). Det kan også være, at du vil se salgstal, der er placeret i beholderstørrelser på USD 1.000.000 i stedet for jævnt fordelt på USD 923.983.

I Power BI Desktop kan du **gruppere** datapunkter, så du kan få vist, analysere og udforske data og tendenser i dine visuals på en mere klar måde. Du kan også definere **beholderstørrelsen**, som ofte kaldes *gruppering i beholder*, for at sortere værdierne i lige store grupper, så du bedre kan visualisere data på en meningsfuld måde.

### <a name="using-grouping"></a>Brug af gruppering
Hvis du vil bruge gruppering, skal du vælge to eller flere elementer på en visual ved at bruge Ctrl + klik for at vælge flere elementer. Højreklik derefter på et af elementerne, og vælg **Gruppér** i den menu, der vises.

![](media/desktop-grouping-and-binning/grouping-binning_1.png)

Når du har oprettet gruppen, føjes den til området **Forklaring** for den pågældende visual og vises også på listen **Felter**.

![](media/desktop-grouping-and-binning/grouping-binning_2.png)

Når du har en gruppe, kan du nemt redigere medlemmerne i denne gruppe ved at højreklikke på feltet i området **Forklaring** eller på listen **Felter** og vælge **Rediger grupper**.

![](media/desktop-grouping-and-binning/grouping-binning_3.png)

I vinduet **Grupper**, der vises, kan du oprette nye grupper eller redigere eksisterende grupper. Du kan også *omdøbe* en gruppe ved at dobbeltklikke på titlen **Grupper og medlemmer** og skrive et nyt navn.

Der er forskellige ting, du kan gøre med grupper. Du kan føje elementer fra listen **Ikke-grupperede værdier** til en ny gruppe eller til en af de eksisterende grupper. Hvis du vil oprette en ny gruppe, skal du vælge to eller flere elementer (ved hjælp af Ctrl + klik) fra feltet **Ikke-grupperede værdier** og derefter klikke på knappen **Gruppér** under dette felt.

Du kan føje en ikkegrupperet værdi til en eksisterende gruppe: Du skal blot vælge den værdi, der ikke er grupperet, og derefter vælge den eksisterende gruppe, som du vil føje den til, og til sidst klikke på knappen **Gruppér**. Hvis du vil fjerne et element fra en gruppe, skal du vælge det i feltet **Grupper og medlemmer** og derefter klikke på **Opdel gruppe**. Du kan også vælge, om ikkegrupperede kategorier skal placeres i gruppen **Andre** eller skal forblive ikkegrupperede.

![](media/desktop-grouping-and-binning/grouping-binning_4.png)

> [!NOTE]
> Du kan oprette grupper for et hvilket som helst felt i brønden **Felter** uden at skulle vælge flere i en eksisterende visualisering. Du skal blot højreklikke på feltet og vælge **Ny gruppe** i den menu, der vises.
> 
> 

### <a name="using-binning"></a>Brug af gruppering i beholder
Du kan angive beholderstørrelsen for numeriske felter og klokkeslætsfelter i **Power BI Desktop.** Du kan bruge gruppering i beholder til at tilpasse de data, der vises i **Power BI Desktop**, til den korrekte størrelse.

Du anvender en beholderstørrelse ved at højreklikke på et **Felt** og vælge **Ny gruppe**.

![](media/desktop-grouping-and-binning/grouping-binning_5.png)

I vinduet **Grupper** skal du angive den **Grupperingsstørrelse**, du vil have for beholderen.

![](media/desktop-grouping-and-binning/grouping-binning_6.png)

Når du vælger **OK**, kan du se, at der vises et nyt felt i ruden **Felter**, hvor *(grupperinger)* er tilføjet. Du kan derefter trække dette felt til canvasset, så du kan bruge beholderstørrelsen i en visualisering.

![](media/desktop-grouping-and-binning/grouping-binning_7.png)

Du kan se, hvordan **gruppering i beholdere** fungerer i denne [video](https://www.youtube.com/watch?v=BRvdZSfO0DY).

Så nemt er det at bruge **gruppering** og **gruppering i beholder** til at sikre, at dine data vises lige præcis på den måde, du gerne vil, i dine visualiseringer.

