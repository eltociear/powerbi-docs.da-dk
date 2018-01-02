---
title: "Sådan kan du bruge Power BI Spørgsmål og svar"
description: "Sådan kan du bruge Power BI Spørgsmål og svar"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Sådan kan du bruge Power BI Spørgsmål og svar
## <a name="ask-questions-of-your-data-using-natural-language"></a>Stil spørgsmål om dine data med et naturligt sprog
Start på et dashboard. I feltet Spørgsmål og svar kan du skrive dit spørgsmål ved hjælp af et naturligt sprog. Spørgsmål og svar kan genkende de ord, du skriver, og kan regne ud, hvor (i hvilket datasæt) svaret findes. Spørgsmål og svar hjælper dig også med udforme dit spørgsmål med automatisk fuldførelse, anden formulering og andre tekst- og visuelle hjælpemidler.

![](media/service-how-to-q-and-a/powerbi-qna.png)

Svaret på dit spørgsmål vises som en interaktiv visualisering og opdateres, når du ændrer spørgsmålet.

Spørgsmål og svar er interaktiv og endda sjov, og oftere medfører ét spørgsmål mange andre, efterhånden som visualiseringerne viser interessante veje at forfølge. Se Amanda demonstrere brugen af Spørgsmål og svar til at oprette visualiseringer, grave ned i disse visualiseringer og fastgøre dem til dashboards.

> [!NOTE]
> Spørgsmål og svar er også tilgængelig i [Microsoft Power BI-appen til iOS på iPads, iPhones og iPod Touch-enheder](mobile-apps-ios-qna.md).
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>Brug et naturligt sprog til at stille spørgsmål om dine data
1. Placer markøren i spørgsmålsfeltet. Selv inden du begynder at skrive, viser Spørgsmål og svar en ny skærm med forslag som hjælp til at udforme dit spørgsmål.
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   Listen indeholder:  
   a.  de spørgsmål, der bruges til at oprette [felter](service-dashboard-tiles.md), som allerede er fastgjort til dashboardet, og  
   b.  navnet på tabeller i de [underliggende datasæt](service-get-data.md).  
   
   Du kan altid vælge et af disse spørgsmål som udgangspunkt og fortsætte med at forbedre spørgsmålet for at finde det specifikke svar, du søger efter. Eller brug et tabelnavn til at hjælpe dig med at formulere et nyt spørgsmål.
2. Vælg på rullelisten, eller begynd at skrive dit eget spørgsmål.  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. Mens du skriver et spørgsmål, vælger Power BI Spørgsmål og svar den bedste [visualisering](power-bi-visualization-types-for-reports-and-q-and-a.md) til at vise dit svar, og visualiseringen ændres automatisk, når du ændrer spørgsmålet. Spørgsmål og svar hjælper dig også med at formulere dit spørgsmål med automatisk fuldførelse ved at omformulere spørgsmålet og med andre tekst- og visuelle hjælpemidler.  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. Når du skriver en forespørgsel, leder Power BI efter svaret i datasæt, der har et felt i dette dashboard.  Hvis alle felterne kommer fra *datasæt A*, så kommer dit svar fra *datasæt A*.  Hvis der er felter fra *datasæt A* og *datasæt B*, søger Spørgsmål og svar efter det bedste svar fra disse 2 datasæt.
   
   > [!TIP]
   > Så vær forsigtig, for hvis du kun har ét felt fra *datasæt A*, og du fjerner det fra dashboardet, vil Spørgsmål og svar ikke længere have adgang til *datasæt A*.
   > 
   > 
5. Når du er tilfreds med resultatet, [kan du fastgøre visualiseringen til et dashboard](service-dashboard-pin-tile-from-q-and-a.md) ved at vælge fastgørelsesikonet i øverste højre hjørne. Hvis dashboardet er blevet delt med dig, eller det er en del af en app, kan det ikke fastgøres.
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>Fortæl Spørgsmål og svar, hvilken visualisering der skal bruges.
Med Spørgsmål og svar kan du ikke blot bede dine data tale for sig selv, du kan fortælle dem, hvordan de skal vises. Føj blot "som et <visualization type>" til slutningen af dit spørgsmål.  F.eks. "vis lagermængde efter fabrik som et kort" og "vis samlet lagerbeholdning som et kort".  Prøv selv.

## <a name="how-does-qa-know-how-to-answer-questions"></a>Hvordan ved Spørgsmål og svar, hvordan der skal svares på spørgsmål?
### <a name="which-datasets-does-qa-use"></a>Hvilke datasæt bruger Spørgsmål og svar?
Hvordan ved Spørgsmål og svar, hvordan der skal svares på dataspecifikke spørgsmål? Funktionen er afhængig af navnene på tabellerne, kolonnerne og de beregnede felter i det underliggende datasæt. Så hvad du (eller datasættets ejer) kalder ting er vigtigt! 

Antag for eksempel, at du havde en Excel-tabel med navnet "Salg", med kolonner med titlerne "Produkt", "Måned", "Solgte enheder", "Bruttosalg" og "Fortjeneste". Du kan stille spørgsmål om enhver af disse enheder.  Du kan spørge "vis *salg*, "samlet *fortjeneste* efter *måned*", "sortér *produkter* efter *solgte enheder*" og meget mere.

Spørgsmål og svar kan besvare spørgsmål, der er baseret på, hvordan dit datasæt er organiseret. Hvordan vil dette fungerer for dataene i Salesforce? Når du opretter forbindelse til din konto på salesforce.com, opretter Power BI automatisk et dashboard.  Før du begynder at stille spørgsmål med Spørgsmål og svar, skal du se på de data, der vises i dashboardets visualiseringer, og også de data, der vises på rullelisten Spørgsmål og svar.

* Hvis visualiseringernes akseetiketter og værdier omfatter "salg", "kunde", "måned" og "salgsmuligheder", kan du med sikkerhed stille spørgsmål som: "Hvilken *kunde* har den højeste *salgsmulighed* eller vis *salg* pr. måned som et søjlediagram".
* Hvis rullelisten indeholder "sælger", "delstat" og "år", kan du med sikkerhed stille spørgsmål som: "hvilken *sælger* havde det laveste *salg* i *Florida* i *2013*".

Hvis du har data om et websteds ydeevne i Google Analytics, kan du bede Spørgsmål og svar om den tid, der blev brugt på en webside, antallet af entydige sidebesøg og brugerengagement. Eller hvis du forespørger på demografiske data, kan du stille spørgsmål om alder og indkomst i husholdningen efter placering.

### <a name="which-visualization-does-qa-use"></a>Hvilken visualisering bruger Spørgsmål og svar?
Spørgsmål og svar vælger den bedste visualisering baseret på de data, der bliver vist. Nogle gange er data i det eller de underliggende datasæt defineret som en bestemt type eller kategori, og det hjælper Spørgsmål og svar med at vide, hvordan de skal vises. Hvis data f.eks. er defineret som en datotype, er det mere sandsynligt, at de vises som et kurvediagram. For data, der er kategoriseret som en by, er det mere sandsynligt, at de vises som et kort.

Du kan også fortælle Spørgsmål og svar, hvilken visualisering der skal bruges, ved at føje den til dit spørgsmål. Men husk, at det ikke altid er muligt for Spørgsmål og svar at vise dataene i den ønskede visualiseringstype.

Du kan finde oplysninger om nøgleord, som Spørgsmål og svar genkender, i [Tip til at stille spørgsmål](service-q-and-a-tips.md).

## <a name="next-steps"></a>Næste trin
Tilbage til [Spørgsmål og svar i Power BI](service-q-and-a.md)  
[Selvstudium: Brug Spørgsmål og svar med eksemplet på detailhandelssalg](power-bi-visualization-introduction-to-q-and-a.md)  
[Tip til at stille spørgsmål med Spørgsmål og svar](service-q-and-a-tips.md)  
[Klargør en projektmappe til Spørgsmål og svar](service-prepare-data-for-q-and-a.md)  
[Fastgør et felt til dashboardet fra Spørgsmål og svar](service-dashboard-pin-tile-from-q-and-a.md)  

