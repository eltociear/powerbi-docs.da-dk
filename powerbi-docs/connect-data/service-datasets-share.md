---
title: Del et datasæt (prøveversion)
description: Som ejer af datasæt kan du oprette og dele dine datasæt, så andre kan bruge dem. Få mere at vide om, hvordan du deler dem.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: ba0e04ff4cd56566f7d33445fafa7c8cfcc6b7ad
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83284790"
---
# <a name="share-a-dataset-preview"></a>Del et datasæt (prøveversion)

Som forfatter af *datamodeller* i Power BI Desktop opretter du *datasæt*, som du kan distribuere i Power BI-tjenesten. Derefter kan andre rapportforfattere bruge dine datasæt som udgangspunkt for deres egne rapporter. I denne artikel får du mere at vide om, hvordan du deler dine datasæt. Hvis du vil vide mere om, hvordan du får og fjerner adgangen til dine delte datasæt, kan du læse om [tilladelsen Opret](service-datasets-build-permissions.md).

## <a name="steps-to-sharing-your-dataset"></a>Trin til at dele dit datasæt

1. Du starter ved at oprette en .pbix-fil med en datamodel i Power BI Desktop. Hvis du planlægger at tilbyde dette datasæt, så andre kan oprette rapporter, designer du muligvis slet ikke en rapport i .pbix-filen.

    Det er bedste praksis at gemme .pbix-filen i en Office 365-gruppe.

1. Publicer .pbix-filen i et [arbejdsområde med den nye oplevelse](../collaborate-share/service-create-the-new-workspaces.md) i Power BI-tjenesten.
    
    Andre medlemmer af dette arbejdsområde kan allerede oprette rapporter i andre arbejdsområder baseret på dette datasæt.

1. Du kan også [publicere en app](../collaborate-share/service-create-distribute-apps.md) fra dette arbejdsområde. Når du gør det, skal du på siden **Tilladelser** angive, hvem der har tilladelser, og hvad de kan gøre.

    > [!NOTE]
    > Hvis du vælger **Hele organisationen**, har ingen i organisationen tilladelsen Opret. Dette er et kendt problem. Angiv i stedet mailadresser under **Bestemte personer eller grupper**.  Hvis hele organisationen skal have tilladelsen Opret, skal du angive mailaliasser for hele organisationen.

    ![Angiv apptilladelser](media/service-datasets-build-permissions/power-bi-dataset-app-permission-new-look.png)

1. Vælg **Publicer app**, eller **Opdater app**, hvis den ikke allerede er publiceret.

## <a name="track-your-dataset-usage"></a>Spor forbruget af dit datasæt

Når du har et delt datasæt i dit arbejdsområde, vil du måske gerne vide, hvilke rapporter i andre arbejdsområder der er baseret på den.

1. Vælg **Få vist relaterede** i listevisningen Datasæt.

    ![ikonet Få vist relaterede](media/service-datasets-build-permissions/power-bi-dataset-view-related-to-dataset.png)

1. I dialogboksen **Relateret indhold** vises alle relaterede elementer. På denne liste kan du se relaterede elementer i dette arbejdsområde og **andre arbejdsområder**.
 
    ![Dialogboksen Relateret indhold](media/service-datasets-build-permissions/power-bi-dataset-related-workspaces.png)

## <a name="next-steps"></a>De næste trin

- [Brug datasæt på tværs af arbejdsområder (prøveversion)](service-datasets-across-workspaces.md)
- Har du nogen spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
