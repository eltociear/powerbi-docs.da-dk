---
title: Del et datasæt (prøveversion)
description: Som ejer af datasæt kan du oprette og dele dine datasæt, så andre kan bruge dem. Få mere at vide om, hvordan du bevarer styringen over, hvem der har adgang til dataene, ved hjælp af tilladelsen Opret.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/14/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 17c3322ed5f24d106412bafb9c4235ee15a626aa
ms.sourcegitcommit: 4d5166944fcc6fe4666cab055ae75e7a0a77866d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2019
ms.locfileid: "69530525"
---
# <a name="share-a-dataset-preview"></a>Del et datasæt (prøveversion)

Som forfatter af *datamodeller* i Power BI Desktop kan du dele dem som *datasæt* i Power BI-tjenesten. Derefter kan forfattere af rapporter nemt finde og genbruge de datasæt, du har delt. Få mere at vide om, hvordan du deler dem, og hvordan du styrer, hvem der har adgang til dataene, ved hjælp af tilladelsen Opret.

## <a name="steps-to-sharing-your-dataset"></a>Trin til at dele dit datasæt

1. Du starter ved at oprette en .pbix-fil med en datamodel i Power BI Desktop. Hvis du planlægger at tilbyde dette datasæt, så andre kan oprette rapporter, designer du muligvis slet ikke en rapport i .pbix-filen.

    Det er bedste praksis at gemme .pbix-filen i en Office 365-gruppe.

1. Publicer .pbix-filen i et [arbejdsområde med den nye oplevelse](service-create-the-new-workspaces.md) i Power BI-tjenesten.
    
    Andre medlemmer af dette arbejdsområde kan allerede oprette rapporter i andre arbejdsområder baseret på dette datasæt.

1. Du kan også [publicere en app](service-create-distribute-apps.md) fra dette arbejdsområde. Når du gør det, skal du på siden **Tilladelser** angive, hvem der har tilladelser, og hvad de kan gøre.

    > [!NOTE]
    > Hvis du vælger **Hele organisationen**, har ingen i organisationen tilladelsen Opret. Dette er et kendt problem. Angiv i stedet mailadresser under **Bestemte personer eller grupper**.  Hvis hele organisationen skal have tilladelsen Opret, skal du angive mailaliasser for hele organisationen.

    ![Angiv apptilladelser](media/service-datasets-build-permissions/power-bi-dataset-app-permissions.png)

1. Vælg **Publicer app**, eller **Opdater app**, hvis den ikke allerede er publiceret.

## <a name="build-permissions-for-shared-datasets"></a>Tilladelsen Opret for delte datasæt

Tilladelsestypen Opret er kun relevant for datasæt. Med den kan brugere oprette nyt indhold i et datasæt, f.eks. dashboards, rapporter, fastgjorte felter fra Spørgsmål og svar samt søgning efter indsigt. De kan også oprette nyt indhold i datasæt uden for Power BI, f.eks. Excel-ark via Analysér i Excel, XMLA og Eksportér.

Brugerne får tilladelsen Opret på forskellige måder:

- Hvis du er medlem af et arbejdsområde med mindst en bidragyderrolle, har du automatisk tilladelsen Opret for et datasæt og tilladelse til at kopiere en rapport.
 
- Et medlem af arbejdsområdet, hvor datasættet er placeret, kan tildele tilladelsen til specifikke brugere eller sikkerhedsgrupper i centret for tilladelser. Vælg ellipsen (...) ud for et datasæt > **Administrer tilladelser**.

    ![Vælg ellipsen](media/service-datasets-build-permissions/power-bi-dataset-manage-permissions.png)

    Derved åbnes centret for tilladelser for det pågældende datasæt, hvor du kan angive og ændre tilladelser.

    ![Center for tilladelse](media/service-datasets-build-permissions/power-bi-dataset-permissions.png)

- En administrator eller et medlem af arbejdsområdet, hvor datasættet er placeret, kan beslutte under publicering af appen, at brugere med tilladelse til appen også får tilladelsen Opret for de underliggende datasæt. Du kan finde yderligere oplysninger under [Trin til at dele dit datasæt](#steps-to-sharing-your-dataset) i denne artikel.

- Lad os antage, at du har tilladelserne Del igen og Opret for et datasæt. Når du deler en rapport eller et dashboard, der er baseret på et datasæt, kan du angive, at modtagerne også får tilladelsen Opret for det underliggende datasæt.

    ![Tilladelsen Opret](media/service-datasets-build-permissions/power-bi-share-report-allow-users.png)

Du kan fjerne tilladelsen Opret for et datasæt fra en person. Hvis du gør det, kan de stadig få vist rapporten, som er baseret på det delte datasæt, men de kan ikke længere redigere den.

## <a name="more-granular-permissions"></a>Flere detaljerede tilladelser

Power BI introducerede tilladelsen Opret i juni 2019 som et supplement til de eksisterende tilladelser Læs og Del igen. Alle brugere, der allerede havde tilladelsen Læs for datasæt via apptilladelser, deling eller adgang til et arbejdsområde på dette tidspunkt, fik også tilladelsen Opret for de samme datasæt. De fik tilladelsen Opret automatisk, fordi de med tilladelsen Læs allerede havde ret til at oprette nyt indhold baseret på datasættet ved hjælp af Analysér i Excel eller Eksportér.

Med den mere detaljerede tilladelse Opret kan du vælge, hvem der kun kan se indholdet i den eksisterende rapport eller på det eksisterende dashboard, og hvem der kan oprette indhold, som er forbundet til de underliggende datasæt.

Hvis dit datasæt bruges af en rapport uden for datasættets arbejdsområde, kan du ikke slette dette datasæt. I stedet får du vist en fejlmeddelelse.

Du kan fjerne tilladelsen Opret. Hvis du gør det, kan de personer, hvis tilladelser du har tilbagekaldt, stadig få vist rapporten, men de kan ikke længere redigere den.

## <a name="track-your-dataset-usage"></a>Spor forbruget af dit datasæt

Når du har et delt datasæt i dit arbejdsområde, vil du måske gerne vide, hvilke rapporter i andre arbejdsområder der er baseret på den.

1. Vælg **Få vist relaterede** i listevisningen Datasæt.

    ![ikonet Få vist relaterede](media/service-datasets-build-permissions/power-bi-dataset-view-related-to-dataset.png)

1. I dialogboksen **Relateret indhold** vises alle relaterede elementer. På denne liste kan du se relaterede elementer i dette arbejdsområde og **andre arbejdsområder**.
 
    ![Dialogboksen Relateret indhold](media/service-datasets-build-permissions/power-bi-dataset-related-workspaces.png)

## <a name="next-steps"></a>Næste trin

- [Brug datasæt på tværs af arbejdsområder (prøveversion)](service-datasets-across-workspaces.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
