---
title: Selvstudium – brug af Spørgsmål og svar på et dashboard eller i en rapport
description: Selvstudium i, hvordan du kan bruge Spørgsmål og svar i Power BI til at oprette nye visualiseringer på dashboards og i rapporter.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/17/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 69e1bfffab1dd30685036b3c5265f81040a5f7c3
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187139"
---
# <a name="tutorial-how-to-use-qa-to-create-visualizations-and-build-reports"></a>Selvstudium: Sådan bruger du Spørgsmål og svar til at oprette visualiseringer og rapporter
I [Oversigt over Spørgsmål og svar](consumer/end-user-q-and-a.md) blev du introduceret til Spørgsmål og svar i Power BI og fik defineret forskellen mellem *forbrugere* (får dashboards og rapporter delt med sig) og *forfattere* (ejer de underliggende rapporter og datasæt). Den første del af dette selvstudium er primært beregnet til forbrugere af dashboards ved hjælp af Power BI-tjenesten. Desuden er den anden del beregnet til forfattere af rapporter ved hjælp af enten Power BI-tjenesten eller Power BI Desktop. [Spørgsmål og svar og Power BI-mobil](consumer/mobile/mobile-apps-ios-qna.md) og [Spørgsmål og svar med Power BI Embedded](developer/qanda.md) behandles i særskilte artikler.

Spørgsmål og svar er interaktiv og endda sjov, og oftere medfører ét spørgsmål mange andre, efterhånden som visualiseringerne viser interessante veje at forfølge. Se Amanda demonstrere brugen af Spørgsmål og svar til at oprette visualiseringer, grave ned i disse visuals og fastgøre dem til dashboards.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-power-bi-service-apppowerbicom"></a>Del 1: Brug Spørgsmål og svar på et dashboard i Power BI-tjenesten (app.powerbi.com)
Et dashboard indeholder felter, der er fastgjort fra et eller flere datasæt, så du kan stille spørgsmål om alle dataene, der er indeholdt i alle disse datasæt. Hvis du vil se, hvilke rapporter og datasæt, der blev brugt til at oprette dashboardet, skal du vælge **Få vist relaterede** på menulinjen.

![](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Spørgsmålsfeltet Spørgsmål og svar er placeret i det øverste venstre hjørne af dashboardet, og her skal du indtaste dit spørgsmål i et naturligt sprog. Spørgsmål og svar kan genkende de ord, du skriver, og kan regne ud, hvor (i hvilket datasæt) svaret findes. Spørgsmål og svar hjælper dig også med udforme dit spørgsmål med automatisk fuldførelse, anden formulering og andre tekst- og visuelle hjælpemidler.

![](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

Svaret på dit spørgsmål vises som en interaktiv visualisering og opdateres, når du ændrer spørgsmålet.

1. Åbn et dashboard, og placer markøren i spørgsmålsfeltet. Selv inden du begynder at skrive, viser Spørgsmål og svar en ny skærm med forslag som hjælp til at udforme dit spørgsmål. Du får vist navnene på tabellerne i de [underliggende datasæt](service-get-data.md) og kan muligvis se fuldførte spørgsmål på listen, hvis datasættets ejer har oprettet [udvalgte spørgsmål](service-q-and-a-create-featured-questions.md),

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-cursor.png)

   Du kan altid vælge et af disse spørgsmål som udgangspunkt og fortsætte med at forbedre spørgsmålet for at finde det specifikke svar, du søger efter. Eller brug et tabelnavn til at hjælpe dig med at formulere et nyt spørgsmål.

2. Vælg blandt datasætindstillinger, eller begynd at skrive dit eget spørgsmål, og vælg blandt forslagene på rullelisten.

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-list.png)

3. Imens du skriver et spørgsmål, vælger Spørgsmål og svar den bedste [visualisering ](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md)til at vise dit svar, og visualiseringen ændres automatisk, når du ændrer spørgsmålet.

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-viz.png)

4. Når du skriver et spørgsmål, leder Power BI efter det bedste svar ved hjælp af et vilkårligt datasæt, der har et felt i det pågældende dashboard.  Hvis alle felterne kommer fra *datasæt A*, så kommer dit svar fra *datasæt A*.  Hvis der er felter fra *datasæt A* og *datasæt B*, søger Spørgsmål og svar efter det bedste svar fra disse 2 datasæt.

   > [!TIP]
   > Så vær forsigtig, for hvis du kun har ét felt fra *datasæt A*, og du fjerner det fra dashboardet, vil Spørgsmål og svar ikke længere have adgang til *datasæt A*.
   >
   >
5. Når du er tilfreds med resultatet, [kan du fastgøre visualiseringen til et dashboard](service-dashboard-pin-tile-from-q-and-a.md) ved at vælge fastgørelsesikonet i øverste højre hjørne. Hvis dashboardet er blevet delt med dig, eller det er en del af en app, kan det ikke fastgøres.

   ![](media/power-bi-tutorial-q-and-a/pbi_qna_finish-typing-question.jpg)

##    <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>Del 2: Brug Spørgsmål og svar i en rapport i Power BI-tjenesten eller Power BI Desktop

Brug Spørgsmål og svar til at udforske dine datasæt og føje visualiseringer til rapporten og til dashboards. En rapport er baseret på et enkelt datasæt og kan være helt tom eller indeholde sider, der er fulde af visualiseringer. Men bare fordi en rapport er tom, så betyder det ikke, at der ikke er nogen data, du kan udforske – datasættet er knyttet til rapporten og afventer, at du udforsker og opretter visualiseringer.  Du kan få vist, hvilket datasæt der bruges til at oprette en rapport, ved at åbne rapporten i Power BI-tjenestens Læsevisning og vælge **Få vist relaterede** på menulinjen.

![](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Hvis du vil bruge Spørgsmål og svar i rapporter, skal du have redigeringsrettigheder til rapporten og underliggende datasæt. I [Oversigtsemnet for Spørgsmål og svar](consumer/end-user-q-and-a.md) henviste vi til dette som et *forfatter*scenarie. Så hvis du i stedet *forbruger* en rapport, der er blevet delt med dig, så er Spørgsmål og svar ikke tilgængelig.

1. Åbn en rapport i Redigeringsvisning (Power BI-tjenesten) eller Rapportvisning (Power BI Desktop), og vælg **Stil et spørgsmål** på menulinjen.

    **Desktop**    
    ![](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Tjeneste**    
    ![](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Et Spørgsmål og svar-felt vises på rapportcanvasset. I eksemplet nedenfor vises spørgsmålsfeltet oven på en anden visualisering. Det er fint nok, men det kan være en fordel at [føje en tom side til rapporten](power-bi-report-add-page.md), før du stiller et spørgsmål.

    ![](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. Placer markøren i spørgsmålsfeltet. Mens du skriver, viser Spørgsmål og svar forslag, som kan hjælpe dig med at definere dit spørgsmål.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. Imens du skriver et spørgsmål, vælger Spørgsmål og svar den bedste [visualisering ](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md)til at vise dit svar, og visualiseringen ændres automatisk, når du ændrer spørgsmålet.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. Når du har den ønskede visualisering, skal du vælge ENTER. Hvis du vil gemme visualiseringen med rapporten, skal du vælge **Filer > Gem**.

6. Interager med den nye visualisering. Det er lige meget, hvordan du har oprettet visualiseringen – du har adgang til samme interaktivitet, formatering og funktioner.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

   Hvis du har oprettet visualiseringen i Power BI-tjenesten, kan du endda [fastgøre den til et dashboard](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Fortæl Spørgsmål og svar, hvilken visualisering der skal bruges.
Du kan bruge Spørgsmål og svar til ikke kun at bede dine data om at tale for sig selv, du kan også bestemme, hvordan Power BI skal vise svaret. Føj blot "som et <visualization type>" til slutningen af dit spørgsmål.  F.eks. "vis lagermængde efter fabrik som et kort" og "vis samlet lagerbeholdning som et kort".  Prøv selv.

##  <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- Hvis du har forbindelse til et datasæt ved hjælp af en direkte forbindelse eller gateway, så skal Spørgsmål og svar være [aktiveret for det pågældende datasæt](consumer/end-user-q-and-a-direct-query.md).

- Du har åbnet en rapport, men kan ikke se indstillingen Spørgsmål og svar. Hvis du bruger Power BI-tjenesten, skal du sørge for, at rapporten er åben i Redigeringsvisning. Hvis du ikke kan åbne Redigeringsvisning, så har du ikke redigeringstilladelser for den pågældende rapport og har ikke adgang til at bruge Spørgsmål og svar med den relevante rapport.

## <a name="next-steps"></a>Næste trin
Tilbage til [Spørgsmål og svar i Power BI](consumer/end-user-q-and-a.md)   
[Selvstudium: Brug Spørgsmål og svar med eksemplet på detailhandelssalg](power-bi-visualization-introduction-to-q-and-a.md)   
[Tip til at stille spørgsmål med Spørgsmål og svar](consumer/end-user-q-and-a-tips.md)   
[Klargør en projektmappe til Spørgsmål og svar](service-prepare-data-for-q-and-a.md)  
[Forbered et datasæt i det lokale miljø til Spørgsmål og svar](consumer/end-user-q-and-a-direct-query.md)
[Fastgør et felt til dashboardet fra Spørgsmål og svar](service-dashboard-pin-tile-from-q-and-a.md)
