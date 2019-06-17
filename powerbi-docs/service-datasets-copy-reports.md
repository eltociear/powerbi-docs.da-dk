---
title: Kopiér rapporter fra andre arbejdsområder (prøveversion) – Power BI
description: Få mere at vide om, hvordan du deler et datasæt med brugere på tværs af organisationen. De kan derefter oprette rapporter baseret på dit datasæt i deres egne arbejdsområder.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 507af4de9d57d2d54fe3e28bca8b1aff7da5cf30
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461459"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>Kopiér rapporter fra andre arbejdsområder (prøveversion)

Få mere at vide, hvordan du kopierer en rapport fra ét arbejdsområde og gemmer den i et andet arbejdsområde. Du kan derefter ændre rapporten og tilføje eller slette visualiseringer og andre elementer.

Når du finder en rapport, du vil bruge, i et arbejdsområde eller en app, kan du lave en kopi af den og derefter redigere den, så den passer til dine behov. Du behøver ikke at oprette datamodellen. Den er allerede oprettet for dig. Og det er meget nemmere at ændre en eksisterende rapport, end det er at starte forfra.

## <a name="save-a-copy-of-a-report"></a>Gem en kopi af en rapport

1. Gå til listevisningen Rapporter i en app eller et arbejdsområde.

1. Under **Handlinger** skal du vælge **Gem en kopi**.

    ![Gem en kopi af en rapport](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    Du kan kun se ikonet **Gem en kopi**, hvis rapporten er i et arbejdsområde med den nye oplevelse, og du har [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets). Selvom du har adgang til arbejdsområdet, skal du have tilladelsen Opret for datasættet.

3. Navngiv rapporten, og vælg destinationsarbejdsområdet under **Gem en kopi af denne rapport**.

    ![Dialogboksen Gem en kopi](media/service-datasets-copy-reports/power-bi-dataset-save-report.png)

    Du kan gemme rapporten i det aktuelle arbejdsområde eller et andet i Power BI-tjenesten. Du kan kun se arbejdsområder, som er arbejdsområder med den nye oplevelse, hvor du er medlem.
  
4. Vælg **Gem**.

    Når du gemmer en kopi af rapporten, opretter du en direkte forbindelse til datasættet, og du kan åbne oplevelsen for oprettelse af rapporten, hvor hele datasættet er tilgængeligt. Du har ikke lavet en kopi af datasættet. Datasættet befinder sig stadig på den oprindelige placering. Du kan bruge alle tabeller og målinger i datasættet i din egen rapport. Begrænsninger for sikkerhed på rækkeniveau på datasættet er i kraft, så du kan kun se data, du har tilladelse til at se, på baggrund af din rolle for sikkerhed på rækkeniveau.

    Power BI opretter automatisk en post på listen over datasæt, hvis rapporten er baseret på et datasæt uden for arbejdsområdet. Ikonet for dette datasæt er forskellig fra ikonet for datasæt i arbejdsområdet: ![Ikon for delt datasæt](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)


    På denne måde kan medlemmer af arbejdsområdet se, hvilke rapporter og dashboards der bruger datasæt, som er uden for arbejdsområdet. Posten viser oplysninger om datasættet og nogle få udvalgte handlinger.

    ![Handlinger for datasæt](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

## <a name="view-related-datasets"></a>Få vist relaterede datasæt

Når du har en rapport i dit arbejdsområde, har du måske brug for at vide, hvilket datasæt den er baseret på.

1. Vælg **Få vist relaterede** i listevisningen Rapporter.

    ![ikonet Få vist relaterede](media/service-datasets-copy-reports/power-bi-dataset-view-related.png)

1. I dialogboksen **Relateret indhold** vises alle relaterede elementer. På denne liste ligner datasættet ethvert andet. Du kan ikke se, at den befinder sig i et andet arbejdsområde. Dette er et kendt problem.
 
    ![Dialogboksen Relateret indhold](media/service-datasets-copy-reports/power-bi-dataset-related.png)


## <a name="next-steps"></a>Næste trin

- [Brug datasæt på tværs af arbejdsområder (prøveversion)](service-datasets-across-workspaces.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
