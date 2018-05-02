---
title: Brug detaljeadgang i Power BI Desktop
description: Lær, hvordan du kan analysere data på en ny rapportside i Power BI Desktop
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
ms.date: 4/10/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: b5da2bf43f2d38e0828571e2b9d404feb615ac69
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/16/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Brug detaljeadgang i Power BI Desktop
Med **detaljeadgang** i **Power BI Desktop** kan du oprette en side i rapporten, som fokuserer på et bestemt objekt – f.eks. en leverandør, en kunde eller en producent. Når denne rapportside er i fokus, kan brugere højreklikke på et datapunkt på andre rapportsider og få detaljeadgang til siden med fokus for at få oplysninger, der er filtreret i forhold til denne kontekst.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Brug detaljeadgang
1. Hvis du vil bruge **detaljeadgang**, skal du oprette en rapportside, der indeholder de visuals, du gerne vil have vist for den type enhed, som du vil have detaljeadgang til. 

    Hvis du f.eks. vil angive detaljeadgang for producenter, kan du oprette en side med detaljeadgang med visuelle elementer, der viser det samlede salg, enheder leveret i alt, salg efter kategori, salg efter område osv. Det betyder, at når du får detaljeadgang til denne side, er de pågældende visuals specifikke for den valgte producent.

2. På siden med detaljeadgang kan du derefter gå til sektionen **Felter** i ruden **Visualiseringer** og trække det felt, du vil have detaljeadgang til, til området **Detaljeadgangsfiltre**.

    ![](media/desktop-drillthrough/drillthrough_02.png)

    Når du føjer et felt til området **Detaljeadgangsfiltre**, opretter **Power BI Desktop** automatisk et visuelt element for knappen *Tilbage*. Dette visuelle element bliver en knap i udgivne rapporter, så brugere, der anvender din rapport i **Power BI-tjenesten**, nemt kan komme tilbage til den rapportside, de kom fra (den side, de valgte at få detaljeadgang fra).

    ![](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Brug dit eget billede på en Tilbage-knap    
 Eftersom knappen Tilbage er et billede, kan du erstatte billedet af dette visual med et hvilket som helst billede, og det fungerer stadig som en Tilbage-knap, der sender brugere af rapporten tilbage til den oprindelige side.

1. Du bruger dit eget billede på en Tilbage-knap ved at placere et billede på siden Detaljeadgang.
2. Vælg det visual, du vil bruge, og angiv skyderen for **Tilbage-knappen** til Til. Billedet fungerer nu som en Tilbage-knap.

    ![](media/desktop-drillthrough/drillthrough_05.png)

    Når din side med **detaljeadgang** er fuldført, og brugere højreklikker på et datapunkt i din rapport, der benytter det felt, du har anbragt i området **Detaljeadgangsfiltre**, vises en genvejsmenu, der understøtter detaljeadgang til denne side.

    ![](media/desktop-drillthrough/drillthrough_04.png)

    Når brugerne vælger at få detaljeadgang, filtreres siden, så den viser oplysninger om det datapunkt, de har højreklikket på. Hvis de f.eks. har højreklikket på et datapunkt om Contoso (en producent) og har valgt at få detaljeadgang, filtreres den side med detaljeadgang, de sendes videre til, til Contoso.

    > [!NOTE]
    > Det er kun det felt, der er i **Detaljeadgangsfiltre**, der sendes videre til rapportsiden med detaljeadgang. Der sendes ingen andre kontekstafhængige oplysninger.
    > 
    > 

Så nemt er det at bruge **detaljeadgang** i dine rapporter. Det kan give dig en udvidet visning af de enhedsoplysninger, du vælger til dit detaljeadgangsfilter.

