---
title: "Skift størrelsen på en rapportside (selvstudium)"
description: 'Selvstudium: Skift visningsindstillingerne for en side i en Power BI-rapport'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: a5cc05e26012f88e889612788d4479a370063d4f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="change-the-size-of-a-report-page-tutorial"></a>Skift størrelsen på en rapportside (selvstudium)
I den [tidligere artikel og video](power-bi-report-display-settings.md) lærte du to forskellige måder at styre sidevisning i Power BI-rapporter: **Vis** og **Sidestørrelse**. Nu skal du prøve selv.

## <a name="first-lets-change-the-page-view-setting"></a>Først skal vi ændre sidens Visningsindstilling
1. Åbn en rapport i Læsevisning eller Redigeringsvisning. Dette eksempel bruger siden "New Stores" fra [Eksempel med detailhandelsanalyse](sample-retail-analysis.md).  Siden vises vha. indstillingen **Tilpas til siden**.  I dette tilfælde viser Tilpas til siden rapportsiden uden rullepaneler, men nogle af oplysningerne og titlerne er for små til at læse.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. Sørg for, at der ikke er valgt nogen visuelle effekter på lærredet. Vælg **Vis** og gennemse visningsindstillingerne.

* I Læsetilstand ser du dette.
  
     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
* I Redigeringstilstand ser du dette.
  
    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. Lad os se, hvordan siden ser ud til, vha. indstillingen **Faktisk størrelse**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)
   
   Ikke fantastisk. Dashboardet har nu dobbelte rullepaneler.
2. Skift til **Tilpas til bredde**.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)
   
   Det ser bedre ud. Nu har vi rullepaneler, men det er nemmere at læse oplysningerne.

## <a name="change-the-default-view-for-a-report-page"></a>Skift standardvisningen for en rapportside
Alle Power BI-rapporter har som standard visningen **Tilpas til siden**. Men hvad nu, hvis du vil have, at denne rapportside altid åbner i visningen **Faktisk størrelse**?

1. På siden **New stores** i rapporten, kan du skifte tilbage til visningen **Faktisk størrelse**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)
2. Gem rapporten med et andet navn ved at vælge **Filer > Gem som**. Du har nu 2 kopier af rapporten. I den oprindelige rapport åbnes **New stores** stadig i standardvisningen, men i den nye rapport åbnes den i visningen **Faktisk størrelse**. Lad os se.
   
   ![](media/power-bi-change-report-display-settings/power-bi-save-as.png)
3. Vælg navnet på arbejdsområdet i den øverste navigationslinje for at vende tilbage til det arbejdsområde.  
   
   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. Vælg fanen **Rapporter**, og vælg den nye rapport, du lige har oprettet (den har en gul stjerne).
   
    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. Rapporten åbner i visningen **Faktisk størrelse**!
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

## <a name="now-lets-explore-the-page-size-setting"></a>Nu skal vi kigge nærmere på indstillingen *Sidestørrelse*
Indstillingerne for størrelse er kun tilgængelige i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md). Du skal have ejerrettigheder til rapporten for at åbne den i Redigeringsvisning. Hvis du har oprettet forbindelse til nogle af vores [eksempler](sample-datasets.md), har du ejerrettigheder til disse rapporter.

1. Åbn siden "District monthly sales" for [Eksempel på analyse af detailhandel](sample-retail-analysis.md) i Redigeringsvisning.
2. Sørg for, at der ikke er valgt nogen visuelle effekter på lærredet.  Vælg malerrulleikonet i ruden **Visuelle effekter**![](media/power-bi-change-report-display-settings/power-bi-paintroller.png).
3. Vælg **Sidestørrelse** &gt; **Type** for at få vist indstillinger for sidestørrelse.
   
   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. Vælg **Letter**.  På lærredet forbliver kun indholdet, der passer til 816 x 1056 pixel (Letter) på den hvide del af lærredet.
   
   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. Hvis vi ændrer **Vis** til "Tilpas til bredde," viser vores lærred nu kun sideindhold, der passer til bogstavstørrelsen.
   
   ![](media/power-bi-change-report-display-settings/power-bi-fit-to-width-new.png)
6. Vælg **Sidestørrelse** **16:9**-højde-bredde-forhold.
   
   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)
   
   Siden i rapporten vises med et højde-bredde-forhold på 16 bred og 9 høj. Se den faktiske pixelstørrelse, der bruges, ved at se på de gråtonede Bredde- og Højde-felter (1280 x 720). Der er meget tom plads rundt om rapportlærredet. Dette skyldes, at vi tidligere angav **Vis** til "Tilpas til bredde".
7. Fortsæt med at udforske indstillingerne **Sidestørrelse**.

## <a name="using-page-view-and-page-size-together"></a>Brug siden Visning og Sidestørrelse sammen
Brug siden Visning og Sidestørrelse sammen for at oprette en rapport, der ser bedst ud, når den er integreret i et andet program.

I denne opgave skal du oprette en rapportside, der vises i et program, som har plads til 500 pixel i bredden og 750 pixel i højden.

Husk, at vi i det forrige trin så, at vores rapportside i øjeblikket vises med 1280 pixel i bredden og 720 pixel i højden. Så vi ved, at vi skal udføre meget tilpasning af størrelse og omarrangering, hvis alle vores visuelle effekter skal passe.

1. Tilpas og flyt de visuelle effekter, så de passer på mindre end halvdelen af det aktuelle lærredsområde.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. Vælg **Sidestørrelse** &gt; **Brugerdefineret**.
3. Angiv Bredde til 500, og angiv Højde til 750.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. Skift rapportsiden, så den ser bedst ud. Skift mellem **Vis > Faktisk størrelse** og **Vis > Tilpas til siden** for at foretage ændringer.
   
    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>Næste trin
[Opret rapporter for Cortana](service-cortana-answer-cards.md)

Tilbage til [Indstillinger for sidevisning i en Power BI-rapport](power-bi-report-display-settings.md)

Læs mere om [rapporter i Power BI](service-reports.md)

Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)

