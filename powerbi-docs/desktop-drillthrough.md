---
title: Brug detaljeadgang i Power BI Desktop
description: Lær, hvordan du bruger detaljeadgang til at analysere data på en ny rapportside i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: a7b00b0cb611dd3e0921885ddaca6547fdb43fd3
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/04/2020
ms.locfileid: "74310981"
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Brug detaljeadgang i Power BI Desktop
Med *detaljeadgang* i Power BI Desktop kan du oprette en side i rapporten, som fokuserer på et bestemt objekt, f.eks. en leverandør, en kunde eller en producent. Hvis du vil bruge detaljeadgang, skal du vælge funktionen ved at højreklikke på et datapunkt på andre rapportsider og derefter gå videre ned til siden med fokus for at få de oplysninger, der er filtreret i forhold til konteksten.

![Brug detaljeadgang](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Brug detaljeadgang
1. Hvis du vil bruge detaljeadgang, skal du oprette en rapportside med de visualiseringer, du vil have til den type enhed, som du vil have detaljeadgang til. 

    Lad os f.eks. sige, at du vil angive detaljeadgang til producenter. Så kan du oprette en side med detaljeadgang med visuelle elementer, der viser det samlede salg, enheder leveret i alt, salg efter kategori, salg efter område osv. Det betyder, at når du får detaljeadgang til denne side, er de pågældende visuals specifikke for den valgte producent.

2. På siden med detaljeadgang kan du derefter gå til sektionen **Felter** i ruden **Visualiseringer** og trække det felt, du vil aktivere detaljeadgang til, til området **Detaljeadgangsfiltre**.

    ![Detaljeadgang til område](media/desktop-drillthrough/drillthrough_02.png)

    Når du føjer et felt til området **Detaljeadgangsfiltre**, opretter Power BI Desktop automatisk et visuelt element for knappen *Tilbage*. Denne visual bliver en knap i publicerede rapporter. De brugere, der benytter din rapport i Power BI-tjenesten, bruger denne knap til at komme tilbage til den rapportside, de kom fra.

    ![Detaljeadgang til billede](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Brug dit eget billede på en Tilbage-knap    
 Da knappen Tilbage er et billede, kan du erstatte billedet af denne visual med et hvilken som helst billede, du ønsker. Det fungerer stadig som en tilbage-knap, så brugerne af rapporter kan vende tilbage til den oprindelige side. 

Hvis du vil bruge dit eget billede til en tilbage-knap, skal du gøre følgende:

1. På fanen **Hjem** vælger du **Image**. Find derefter dit billede, og placer det på siden med detaljeadgang.

2. Vælg det nye billede på siden med detaljeadgang. I ruden **Formatér billede** skal du indstille skyderen **Handling** til **Til** og derefter indstille **Type** til **Tilbage**. Billedet fungerer nu som en Tilbage-knap.

    ![Indlæs billedet, og angiv typen som Tilbage](media/desktop-drillthrough/drillthrough_05.png)

    
     Nu kan brugerne højreklikke på et datapunkt i din rapport og få en genvejsmenu, der understøtter detaljeadgang til denne side. 

    ![Detaljeadgangsmenu](media/desktop-drillthrough/drillthrough_04.png)

    Når brugerne vælger at få detaljeadgang, filtreres siden, så den viser oplysninger om det datapunkt, de har højreklikket på. Lad os f.eks. sige, at de har højreklikket på et datapunkt om producenten Contoso og valgt at få detaljeadgang. Den side med detaljeadgang, som de skal du gå til, filtreres til Contoso.

## <a name="pass-all-filters-in-drillthrough"></a>Overfør alle filtre i detaljeadgang

Fra og med versionen af Power BI Desktop fra maj 2018 kan du overføre alle anvendte filtre til detaljeadgangsvinduet. Du kan f.eks. kun vælge en bestemt kategori af produkter og de visuals, der filtreres til denne kategori, og derefter vælge detaljeadgang. Du er måske interesseret i at se, hvordan denne detaljeadgang ville se ud med alle de anvendte filtre.

Hvis du vil beholde alle anvendte filtre, skal du gå til sektionen **Detaljeadgang** i ruden **Visualiseringer** og slå indstillingen **Overfør alle filtre** **til**. 

![Behold alle filtre](media/desktop-drillthrough/drillthrough_06.png)

I de versioner af Power BI Desktop, der er udgivet før maj 2018, svarer funktionsmåden til at slå denne indstilling **fra**.

Når du derefter udfører detaljeadgang på et visuelt element, kan du se, hvilke filtre der er anvendt som resultat af det visuelle kildeelement, hvor der er anvendt midlertidige filtre. I sektionen **Detaljeadgang** i ruden **Visualisering**, vises disse midlertidige filtre med kursiv. 

![Midlertidige filtre med kursiv](media/desktop-drillthrough/drillthrough_07.png)

Selvom du kan gøre dette med sider med værktøjstip, ville det give en forkert oplevelse, fordi værktøjstippet ikke ser ud til at fungere korrekt. Derfor anbefales det ikke at gøre dette med værktøjstip.

## <a name="add-a-measure-to-drillthrough"></a>Føj et mål til detaljeadgang

Ud over at overføre alle filtre til vinduet med detaljeadgang kan du også tilføje et mål (eller en numerisk kolonne med en opsummering) i detaljeområdet. Træk detaljeadgangsfeltet til kortet **Detaljeadgang** for at anvende det. 

![Føj et mål til detaljeadgang](media/desktop-drillthrough/drillthrough_08.png)

Når du tilføjer et mål eller en numerisk kolonne med en opsummering, kan du få adgang til siden, når feltet bruges i området *Værdi* for en visual.

Så nemt er det at bruge detaljeadgang i dine rapporter. Det kan give dig en udvidet visning af de enhedsoplysninger, som du valgte til dit detaljeadgangsfilter.

## <a name="next-steps"></a>De næste trin

Du vil måske også være interesseret i følgende artikler:

* [Brug tværgående detaljeadgang i rapport i Power BI Desktop](desktop-cross-report-drill-through.md)
* [Brug af udsnitsværktøjer i Power BI Desktop](visuals/power-bi-visualization-slicers.md)

