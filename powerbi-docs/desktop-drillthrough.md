---
title: Brug detaljeadgang i Power BI Desktop
description: "Lær, hvordan du kan analysere data på en ny rapportside i Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f4cf7b0b850445b794c092f01b7e9a837ca3f215
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Brug detaljeadgang i Power BI Desktop
Med **detaljeadgang** i **Power BI Desktop** kan du oprette en side i rapporten, som fokuserer på et bestemt objekt – f.eks. en leverandør, en kunde eller en producent. Når denne rapportside er i fokus, kan brugere højreklikke på et datapunkt på andre rapportsider og få detaljeadgang til siden med fokus for at få oplysninger, der er filtreret i forhold til denne kontekst.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Brug detaljeadgang
Hvis du vil bruge **detaljeadgang**, skal du oprette en rapportside, der indeholder visuelle elementer, du ønsker at se for typen af enhed, som du have detaljeadgang til. Hvis du f.eks. vil angive detaljeadgang for producenter, kan du oprette en side med detaljeadgang med visuelle elementer, der viser det samlede salg, enheder leveret i alt, salg efter kategori, salg efter område osv. Det betyder, at når du får detaljeadgang til denne side, er de visuelle elementer specifikke for den producent, du har klikket på og valgt at få detaljeadgang til.

På den pågældende side med detaljeadgang kan du derefter gå til sektionen **Felter** i ruden **Visualiseringer** og trække det felt, du vil have detaljeadgang til, til området **Detaljeadgangsfiltre**.

![](media/desktop-drillthrough/drillthrough_02.png)

Når du føjer et felt til området **Detaljeadgangsfiltre**, opretter **Power BI Desktop** automatisk et visuelt element for knappen *Tilbage*. Dette visuelle element bliver en knap i udgivne rapporter, så brugere, der anvender din rapport i **Power BI-tjenesten**, nemt kan komme tilbage til den rapportside, de kom fra (den side, de valgte at få detaljeadgang fra).

![](media/desktop-drillthrough/drillthrough_03.png)

Da knappen *Tilbage* er et billede, kan du erstatte billedet af dette visuelle element med et hvilket som helst billede, og det fungerer stadig korrekt som den knap, der sender brugere af rapporten tilbage til den oprindelige side. Hvis du vil bruge dit eget billede til knappen Tilbage, skal du bare anbringe et visuelt billede på siden med detaljeadgang, vælge det visuelle element og derefter slå skyderen for *knappen Tilbage* til. Derefter fungerer dit billede som knappen *Tilbage*.

![](media/desktop-drillthrough/drillthrough_05.png)

Når din side med **detaljeadgang** er fuldført, og brugere højreklikker på et datapunkt i din rapport, der benytter det felt, du har anbragt i området **Detaljeadgangsfiltre** på siden med detaljeadgang, vises der en genvejsmenu, hvor brugerne kan få detaljeadgang til denne side.

![](media/desktop-drillthrough/drillthrough_04.png)

Når de vælger at få detaljeadgang, filtreres siden, så den viser oplysninger om det datapunkt, de har højreklikket fra. Hvis de f.eks. har højreklikket på et datapunkt om Contoso (en producent) og har valgt at få detaljeadgang, filtreres den side med detaljeadgang, de sendes videre til, til Contoso.

> [!NOTE]
> Det er kun det felt, der er i området **Detaljeadgangsfiltre**, der sendes videre til siden med detaljeadgangsrapporten. Der sendes ingen andre kontekstafhængige oplysninger.
> 
> 

Så nemt er det at bruge **detaljeadgang** i dine rapporter. Det kan give dig en udvidet visning af de enhedsoplysninger, du vælger til dit detaljeadgangsfilter.

