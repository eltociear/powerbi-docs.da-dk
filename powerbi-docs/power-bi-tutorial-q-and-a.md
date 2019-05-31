---
title: Brug Power BI spørgsmål og svar til at udforske og oprette visuelle elementer
description: Sådan bruges Power BI spørgsmål og svar til at oprette nye visualiseringer på dashboards og i rapporter.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: c6fd8967a49515af4d0614653b3d7550c335052f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625372"
---
# <a name="use-power-bi-qa-to-explore-your-data-and-create-visuals"></a>Brug Power BI spørgsmål og svar til at udforske dine data og oprette visuelle elementer

Den hurtigste måde at få svar ud af dine data på er nogle gange at stille et spørgsmål på et naturligt sprog. Funktionen spørgsmål og svar i Power BI kan du udforske dine data med dine egne ord.  Den første del af denne artikel viser, hvordan du bruger spørgsmål og svar i dashboards i Power BI-tjenesten. Den anden del viser, hvad du kan gøre med spørgsmål og svar, når du opretter rapporter i Power BI-tjenesten eller Power BI Desktop. Se flere baggrund, for den [spørgsmål og svar til forbrugere](consumer/end-user-q-and-a.md) artikel. 

[Spørgsmål og svar i Power BI-mobilappsene](consumer/mobile/mobile-apps-ios-qna.md) og [spørgsmål og svar med Power BI Embedded](developer/qanda.md) behandles i særskilte artikler. 

Spørgsmål og svar er interaktiv, endda sjov. Ofte, fører et spørgsmål til andre, efterhånden som visualiseringerne viser interessante veje at forfølge. Se Amanda demonstrere brugen af Spørgsmål og svar til at oprette visualiseringer, grave ned i disse visuals og fastgøre dem til dashboards.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-the-power-bi-service"></a>Del 1: Brug spørgsmål og svar på et dashboard i Power BI-tjenesten

I Power BI-tjenesten (app.powerbi.com) indeholder et dashboard felter, der er fastgjort fra et eller flere datasæt, så du kan stille spørgsmål om nogle af de data, der er indeholdt i en af disse datasæt. Hvis du vil se, hvilke rapporter og datasæt blev brugt til at oprette dashboardet, skal du vælge **få vist relaterede** i menulinjen.

![Få vist relaterede rapporter og datasæt](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Spørgsmålsfeltet spørgsmål og svar er placeret i det øverste venstre hjørne af dit dashboard, hvor du skriver dit spørgsmål ved hjælp af naturligt sprog. Ikke se spørgsmål og svar? Se [overvejelser og fejlfinding](consumer/end-user-q-and-a.md#considerations-and-troubleshooting) i den **spørgsmål og svar til forbrugere** artikel.  Spørgsmål og svar kan genkende de ord, du skriver og regne ud, hvor (i hvilket datasæt) for at finde svaret. Spørgsmål og svar hjælper dig også med udforme dit spørgsmål med automatisk fuldførelse, anden formulering og andre tekst- og visuelle hjælpemidler.

![Spørgsmål og svar](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

Svaret på dit spørgsmål vises som en interaktiv visualisering og opdateres, når du ændrer spørgsmålet.

1. Åbn et dashboard, og placer markøren i spørgsmålsfeltet. I øverste højre hjørne, skal du vælge **nye spørgsmål og svar-oplevelsen**.

    ![Ny Power BI-spørgsmål og svar-oplevelsen](media/power-bi-tutorial-q-and-a/power-bi-qna-new-experience.png)

1. Selv inden du begynder at skrive, viser Spørgsmål og svar en ny skærm med forslag som hjælp til at udforme dit spørgsmål. Du kan se udtryk og fuldførte spørgsmål, der indeholder navnene på tabellerne i de underliggende datasæt og kan muligvis se fuldførte spørgsmål på listen, hvis datasættets ejer har oprettet [udvalgte spørgsmål](service-q-and-a-create-featured-questions.md),

   ![Spørgsmål og svar forslag til spørgsmål](media/power-bi-tutorial-q-and-a/power-bi-qna-suggested-questions.png)

   Du kan vælge et af disse spørgsmål som udgangspunkt og fortsætte med at forbedre spørgsmålet for at finde en bestemt svar. Eller brug et tabelnavn til at hjælpe dig med at formulere et nyt spørgsmål.

2. Vælg på listen over spørgsmål, eller Begynd at skrive dine egne spørgsmål, og vælg blandt forslagene på rullelisten.

   ![Vælg et spørgsmål på listen](media/power-bi-tutorial-q-and-a/power-bi-qna-select-a-question-how-many-stores.png)

3. Mens du skriver et spørgsmål, vælger spørgsmål og svar den bedste visualisering til at vise dit svar.

   ![Spørgsmål og svar hvor mange gemmer efter delstat](media/power-bi-tutorial-q-and-a/power-bi-qna-how-many-stores-by-state.png)

4. Visualiseringen ændres dynamisk, mens du ændrer spørgsmålet.

   ![Spørgsmål og svar hvor mange gemmer efter delstat som søjlediagram](media/power-bi-tutorial-q-and-a/power-bi-qna-stores-by-state-bar-chart.png)

1. Når du skriver et spørgsmål, leder Power BI efter det bedste svar ved hjælp af et vilkårligt datasæt, der har et felt i det pågældende dashboard.  Hvis alle felterne kommer fra *datasæt A*, så kommer dit svar fra *datasæt A*.  Hvis der er felter fra *datasæt a* og *datasæt b*, derefter spørgsmål og svar søger efter det bedste svar fra disse 2 datasæt.

   > [!TIP]
   > Så vær forsigtig, for hvis du kun har ét felt fra *datasæt A*, og du fjerner det fra dashboardet, vil Spørgsmål og svar ikke længere have adgang til *datasæt A*.
   >

5. Når du er tilfreds med resultatet, Fastgør Visualiseringen til et dashboard ved at vælge fastgørelsesikonet i øverste højre hjørne. Hvis dashboardet er blevet delt med dig, eller det er en del af en app, kan det ikke fastgøres.

   ![Spørgsmål og svar kan du fastgøre det visuelle element](media/power-bi-tutorial-q-and-a/power-bi-qna-pin-visual.png)

## <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>Del 2: Brug Spørgsmål og svar i en rapport i Power BI-tjenesten eller Power BI Desktop

Brug Spørgsmål og svar til at udforske dine datasæt og føje visualiseringer til rapporten og til dashboards. En rapport er baseret på et enkelt datasæt og kan være helt tom eller indeholde sider, der er fulde af visualiseringer. Men bare fordi en rapport er tom, så betyder det ikke, at der ikke er nogen data, du kan udforske – datasættet er knyttet til rapporten og afventer, at du udforsker og opretter visualiseringer.  Du kan få vist, hvilket datasæt der bruges til at oprette en rapport, ved at åbne rapporten i Power BI-tjenestens Læsevisning og vælge **Få vist relaterede** på menulinjen.

![Få vist relaterede datasæt](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Hvis du vil bruge spørgsmål og svar i rapporter, skal du have redigeringsrettigheder til rapporten og underliggende datasæt. I den [spørgsmål og svar til forbrugere](consumer/end-user-q-and-a.md) artikel bruger vi referere til dette som en *creator* scenarie. Hvis du er i stedet *forbruger* en rapport, der er blevet delt med dig, spørgsmål og svar er ikke tilgængelig.

1. Åbn en rapport i redigeringsvisning (Power BI-tjenesten) eller rapportvisning (Power BI Desktop), og vælg **stil et spørgsmål** i menulinjen.

    **Power BI Desktop**    
    ![Vælg stil et spørgsmål i Power BI Desktop](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Tjeneste**    
    ![Vælg stil et spørgsmål i Power BI-tjenesten](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Et Spørgsmål og svar-felt vises på rapportcanvasset. I eksemplet nedenfor vises spørgsmålsfeltet oven på en anden visualisering. Det er fint nok, men det kan være en fordel at føje en tom side til rapporten, før du stiller et spørgsmål.

    ![Spørgsmål og svar](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. Placer markøren i spørgsmålsfeltet. Mens du skriver, viser Spørgsmål og svar forslag, som kan hjælpe dig med at definere dit spørgsmål.

   ![Skriv i feltet spørgsmål og svar](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. Imens du skriver et spørgsmål, vælger Spørgsmål og svar den bedste [visualisering ](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md)til at vise dit svar, og visualiseringen ændres automatisk, når du ændrer spørgsmålet.

   ![Opretter en visualisering, spørgsmål og svar](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. Når du har den ønskede visualisering, skal du vælge ENTER. Hvis du vil gemme visualiseringen med rapporten, skal du vælge **Filer > Gem**.

6. Interager med den nye visualisering. Det er lige meget, hvordan du har oprettet visualiseringen – du har adgang til samme interaktivitet, formatering og funktioner.

   ![Interager med Visualiseringen](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

   Hvis du har oprettet visualiseringen i Power BI-tjenesten, kan du endda [fastgøre den til et dashboard](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Fortæl Spørgsmål og svar, hvilken visualisering der skal bruges
Du kan bruge Spørgsmål og svar til ikke kun at bede dine data om at tale for sig selv, du kan også bestemme, hvordan Power BI skal vise svaret. Føj blot "som et <visualization type>" til slutningen af dit spørgsmål.  F.eks. "vis lagermængde efter fabrik som et kort" og "vis samlet lagerbeholdning som et kort".  Prøv selv.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- Hvis du har forbindelse til et datasæt ved hjælp af en direkte forbindelse eller gateway, så skal Spørgsmål og svar være [aktiveret for det pågældende datasæt](service-q-and-a-direct-query.md).

- Du har åbnet en rapport, men kan ikke se indstillingen Spørgsmål og svar. Hvis du bruger Power BI-tjenesten, skal du sørge for, at rapporten er åben i Redigeringsvisning. Hvis du ikke kan åbne redigeringsvisning, betyder det, at du ikke har redigeringstilladelser til rapporten, og du kan bruge spørgsmål og svar med den relevante rapport.

## <a name="next-steps"></a>Næste trin

- [Spørgsmål og svar til forbrugere](consumer/end-user-q-and-a.md)   
- [Tip til at stille spørgsmål med Spørgsmål og svar](consumer/end-user-q-and-a-tips.md)   
- [Klargør en projektmappe til Spørgsmål og svar](service-prepare-data-for-q-and-a.md)  
- [Forbered et datasæt for i det lokale miljø til spørgsmål og svar](service-q-and-a-direct-query.md)   
- [Fastgør et felt til dashboardet fra Spørgsmål og svar](service-dashboard-pin-tile-from-q-and-a.md)
