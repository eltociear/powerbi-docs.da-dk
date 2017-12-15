---
title: "Selvstudium: Opret dine egne målinger i Power BI Desktop"
description: "Selvstudium: Opret dine egne målinger i Power BI Desktop"
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
ms.openlocfilehash: f51d7d07bd36784978e43c516424b6f08fc4e211
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Selvstudium: Opret dine egne målinger i Power BI Desktop
Nogle af de stærkeste løsninger til dataanalyse i Power BI Desktop kan oprettes ved hjælp af målinger. Målinger hjælper os med at udføre beregninger på vores data, når vi arbejder med rapporterne. I dette selvstudium lærer du, hvordan du kan oprette nogle af dine egne grundlæggende målinger i Power BI Desktop.

Denne artikel er for de Power BI-brugere, som allerede har erfaring med Power BI Desktop, og som er klar til at arbejde med mere avancerede modeller. Du bør allerede have kendskab til at bruge Hent data og Forespørgselseditor til at importere data, arbejde med flere relaterede tabeller og tilføje felter på dit rapportcanvas. Hvis du ikke har erfaring med Power BI Desktop, skal du se [Introduktion til Power BI Desktop](desktop-getting-started.md).

Hvis du vil følge trinnene i dette selvstudium, skal du downloade filen [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip). Den indeholder data om onlinesalget for det fiktive firma Contoso, Inc. Da dataene i filen er importeret fra en database, kan du ikke oprette forbindelse til datakilden eller se den i Forespørgselseditor. Når du har hentet filen til din computer, kan du åbne den i Power BI Desktop.

## <a name="what-are-these-measures-all-about"></a>Hvad handler disse målinger om?
Målinger oprettes ofte automatisk, for eksempel hvis du markerer afkrydsningsfeltet id for **SalesAmount** i tabellen **Sales** på feltlisten, eller hvis du trækker **SalesAmount** til dit rapportcanvas.

![](media/desktop-tutorial-create-measures/measurestut_salesamountinfieldlist.png)

Der vises en ny diagramvisualisering som denne:

![](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

Der oprettes et søjlediagram med det samlede salg fra feltet SalesAmount.  Feltet SalesAmount er blot en kolonne med navnet SalesAmount i tabellen Sales, som allerede er blevet importeret.

Kolonnen SalesAmount indeholder mere end to millioner rækker med salgsværdier. Du undrer dig måske over, hvorfor du ikke får vist en tabel med rækkerne med alle disse værdier. Det skyldes, at Power BI Desktop ved, at alle værdierne i SalesAmount er en numerisk datatype og at du sandsynligvis vil arbejde videre med dem ved at lægge dem sammen, finde gennemsnittet, tælle dem osv.

Når et felt på listen Felter vises med sigmaikonet ![](media/desktop-tutorial-create-measures/meastut_sigma.png), betyder det, at feltet er numerisk, og at du kan bruge værdierne til beregninger. Da du i dette tilfælde valgte SalesAmount, oprettede Power BI Desktop sin egen måling, og summen af alle salgsbeløb beregnes og vises i diagrammet.

Sum er standardfunktionen, når du vælger et felt med en numerisk datatype, men det er nemt at vælge en anden type aggregering.

Hvis du klikker på den nedadvendte pil ud for **SalesAmount** i området **Værdier**, kan du vælge **Gennemsnit**.

![](media/desktop-tutorial-create-measures/meastut_salesamountaverage.png)

Visualiseringen ændres til et gennemsnit af alle salgsværdierne i feltet SalesAmount.

![](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Du kan ændre typen af aggregering til den type resultat, du vil have vist, men det er ikke alle typer aggregering, der kan bruges med alle numeriske datatyper. For feltet SalesAmount vil aggregeringerne Sum og Gennemsnit for eksempel give mening. Det kan også give mening at bruge Minimum og Maksimum. Men Antal vil ikke give så meget mening, da værdierne er valutaværdier, selvom feltet er angivet som numerisk.

Det er vigtigt at forstå aggregeringer for at forstå målinger, da alle målinger vil udføre en type aggregering. Senere kommer der nogle flere eksempler med Sum, når du opretter dine egne målinger.

De værdier, der beregnes ud fra målinger, ændres altid baseret på interaktionerne i rapporten. Hvis du for eksempel trækker feltet **RegionCountryName** fra tabellen **Geography** til diagrammet, vises det gennemsnitlige salgsbeløb for hvert land.

![](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Når resultatet af en måling ændres på grund af en interaktion med rapporten, påvirkes målingens *kontekst*. Hver gang du arbejder med rapporten, ændrer du konteksten for, hvordan en måling beregnes og viser resultatet.

I de fleste tilfælde vil Power BI beregne og returnere værdier ifølge de tilføjede felter og de valgte typer aggregering. Men i andre tilfælde skal du muligvis oprette dine egne målinger for at kunne udføre mere komplekse beregninger.

I Power BI Desktop kan du oprette dine egne målinger ved at bruge DAX-formelsproget (Data Analysis Expressions). DAX-formler ligner Excel-formler en hel del. DAX bruger mange af de samme funktioner, operatorer og samme syntaks som Excel-formler. Funktionerne i DAX er dog designet til at arbejde med relationelle data og udføre mere dynamiske beregninger, når der interageres med rapporter.

Der er mere end 200 DAX-funktioner, som kan udføre alt lige fra enkle aggregeringer som Sum og Gennemsnit til mere komplekse statistik- og filterfunktioner. Jeg vil ikke gå alt for meget i detaljer med DAX-sproget her, men der er mange ressourcer, du kan bruge for at lære mere. Når du er færdig med dette selvstudium, kan vi anbefale [Grundlæggende DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Når du opretter dine egne målinger, tilføjes de på listen Felter for den ønskede tabel. Dette kaldes en *modelmåling*, og den gemmes i tabellen som et felt. En af de store fordele ved modelmålinger er, at du kan kalde dem det, du vil, så de er nemmere at identificere. De kan også bruges som argument i andre DAX-udtryk, og du kan oprette målinger, der udfører komplekse beregninger hurtigt.

## <a name="lets-create-our-own-measure"></a>Lad os oprette en måling
Det kan for eksempel være for at analysere nettoomsætningen. Som du kan se på listen over felter i tabellen Sales, er der ikke et felt med navnet NetSales. Men der findes de ting, der skal bruges til at beregne nettoomsætningen.

Du skal bruge en måling, der kan fratrække rabatter og returvarer fra salgsbeløbene. Da målingen skal beregne et resultat for enhver kontekst i visualiseringen, skal summen af DiscountAmount og ReturnAmount trækkes fra summen af SalesAmount. Det kan måske virke lidt forvirrende, men det bliver logisk lige om lidt.

### <a name="net-sales"></a>Nettoomsætning
1.  Højreklik på eller klik på de tre prikker til højre for tabellen **Sales** på feltlisten, og klik derefter på **Ny måling**. Dette sikrer, at den nye måling gemmes i tabellen Sales, hvor den er nem at finde igen.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    > [!TIP]
    > Du kan også oprette en ny måling ved at klikke på knappen Ny måling under fanen Hjem på båndet i Power BI Desktop.
    > 
    > ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    > 
    > Når du opretter en måling fra båndet, kan målingen blive oprettet i enhver af tabellerne. Selvom en måling ikke behøver at tilhøre en bestemt tabel, vil det være nemmere at finde den, hvis du opretter den i den tabel, der giver mest mening for dig. Hvis du vil placere den i en bestemt tabel, skal du først klikke på tabellen for at markere den. Klik derefter på Ny måling. I dette eksempel opretter vi den første måling i tabellen Sales.
    > 
    > 
    
    Formellinjen vises langs toppen af dit rapportcanvas. Her kan du omdøbe målingen og angive en DAX-formel.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
    Lad os give den nye måling et navn. Som standard kaldes en ny måling blot for Mål. Hvis du ikke omdøber den, og du opretter efterfølgende målinger, navngives de Mål 2, Mål 3 osv. Det skal være nemt at finde målingen igen, så jeg foreslår navnet Net Sales.
    
2. Fremhæv **Mål** på formellinjen, og skriv derefter **Net Sales**.
    
    Nu kan du begynde at skrive en formel.
    
3.  Skriv et **S** efter lighedstegnet. Der vises en rulleliste med forslag, hvor du kan se alle de DAX-funktioner, som starter med bogstavet S. Når du skriver flere bogstaver, justeres listen til de relevante funktioner. Vælg **SUM** ved at rulle ned, og tryk derefter på Enter.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Når du har trykket på Enter, vises der en startparentes sammen med en anden forslagsliste over alle de kolonner, du kan bruge som argument i SUM-funktionen.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    Et udtryk vises altid mellem en start- og slutparentes. I dette tilfælde vil udtrykket indeholde et enkelt argument, der overføres til funktionen SUM: den kolonne, hvor værdierne skal lægges sammen. Du kan indsnævre listen over kolonner ved at skrive det første bogstav i kolonnenavnet. I dette eksempel er det kolonnen SalesAmount, så hvis du skriver salesam, indsnævres listen til kun to elementer. Og de er faktisk den samme kolonne. Den ene viser kun [SalesAmount], fordi vi opretter vores måling i samme tabel som kolonnen SalesAmount findes i. For den anden vises tabelnavnet foran kolonnenavnet.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
    Det er generelt en god idé altid at angive det fuldt kvalificerede kolonnenavn. Det vil gøre det nemmere at læse formlerne.
    
4. Vælg **Sales[SalesAmount]**, og skriv derefter en slutparentes.
    
    > [!TIP]
    > Syntaksfejl skyldes ofte, at der mangler en slutparentes, eller at den er placeret forkert.
    > 
    > 
    
    Nu skal de to andre kolonner trækkes fra.
    
5.  Skriv et mellemrum efter slutparentesen for det første udtryk, og indtast derefter et minustegn (**-**) efterfulgt af et mellemrum. Angiv derefter en ny SUM-funktion med kolonnen **Sales[DiscountAmount]** som argument.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
    Der begynder at mangle plads til formlen. Men det er ikke noget problem.
    
6.  Klik på den nedadvendte pil i højre side af formellinjen.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)
    
    Nu er der mere plads. Nu kan du skrive nye dele af formlen på en ny linje ved at trykke på Alt+Enter. Du kan også flytte ting ved at trykke på tabulatortasten.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)
    
    Nu kan du tilføje den sidste del af formlen.
    
7.  Tilføj et ekstra minustegn efterfulgt af en anden SUM-funktion med kolonnen **Sales[ReturnAmount]** som argument.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
    Nu ser formlen færdig ud.

8.  Tryk på Enter, eller klik på fluebenet på formellinjen for at afslutte formlen. Formlen valideres og tilføjes på feltlisten i tabellen Sales.

### <a name="lets-add-our-new-measure-to-a-report"></a>Nu kan du tilføje den nye måling i en rapport
Nu kan du tilføje målingen Net Sales på dit rapportcanvas, og så beregnes nettoomsætningen for de øvrige felter, der føjes til rapporten. Lad os se på nettoomsætningen efter salg.

1.  Træk målingen **Net Sales** fra tabellen **Sales** til dit rapportcanvas.
    
2. Træk nu feltet **RegionCountryName** fra tabellen **Geography** til diagrammet.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
    Nu kan du tilføje flere data.
    
3.  Træk feltet **SalesAmount** til diagrammet for at se forskellen mellem nettoomsætningen og salgsbeløbet.
    
    Nu indeholder diagrammet to målinger. SalesAmount, der blev opsummeret automatisk, samt målingen Net Sales, som du lige har oprettet. I begge tilfælde blev resultaterne beregnet i konteksten for et andet felt i diagrammet, som er landene i RegionCountryName.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)
    
    Nu kan du tilføje et udsnit, så du yderligere kan opdele nettoomsætningen og salgsbeløbet efter kalenderår.
    
4.  Klik på et tomt område ud for diagrammet, og klik derefter på visualiseringen Tabel under **Visualiseringer**.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktablevisbutton.png)
    
    Dette opretter en tom tabelvisualisering på dit rapportcanvas.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
5.  Træk feltet **Year** fra tabellen **Calendar** til den nye tomme tabel.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
    Da Year er et numerisk felt, vil Power BI Desktop lægge værdierne sammen og vise et diagram. Men det er ikke så praktisk til et udsnit.
    
6. Under **Værdier** skal du klikke på pilen ud for **Year** og derefter klikke på **Opsummer ikke**.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
    Nu kan du ændre feltet Year i tabelvisualiseringen til et udsnit.

    7.  Klik på visualiseringen **Udsnit** under **Visualiseringer**.

    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
    Nu vises Year som et udsnit. Nu kan du vælge enkelte eller flere år, hvorefter visualiseringerne i rapporten tilpasses efter de valgte indstillinger i udsnittet.
    
8. Prøv at klikke på **2013**. Du kan se, at diagrammet ændres. Målingerne Net Sales og SalesAmount genberegnes og viser resultaterne for 2013. Igen er konteksten for beregningen af målingerne og visningen af resultaterne blevet ændret.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

## <a name="lets-create-another-measure"></a>Lad os oprette en anden måling
Nu ved du, hvordan du kan oprette dine egne målinger, så lad os oprette en mere.

### <a name="net-sales-per-unit"></a>Net sales per unit
Hvad nu, hvis jeg gerne vil se, hvilket produkt der er solgt flest af i antal?

Til det formål kan du oprette en ny måling. Til denne beregning skal du dividere nettoomsætningen med antal solgte enheder. Det vil sige, at målingen Net Sales skal divideres med summen af Sales[SalesQuantity].

1.  Opret en ny måling med navnet **Net Sales per Unit** i tabellen Sales eller Products.
    
    Til denne måling skal du bruge målingen Net Sales, som du oprettede tidligere. Med DAX kan du lave en reference til andre målinger i formlen.
    
2.  Start med at skrive **Net Sales**. Forslagslisten viser, hvad du kan tilføje. Vælg **[Net Sales]**.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    Du kan også referere til en anden måling ved blot at starte med at skrive en kantet venstreparentes (**[**). Forslagslisten viser nu kun de målinger, du kan tilføje i formlen.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  Angiv et mellemrum lige efter **[Net Sales]**, derefter et divisionstegn (**/**), angiv funktionen SUM, og skriv derefter **Quantity** for antal. Forslagslisten viser alle de kolonner, som har Quantity i navnet. Vælg **Sales[SalesQuantity]**. Formlen skulle nu se sådan ud:
    
    > **Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])**
    > 
    > 
    
    Ret smart, ikke? Det er forholdsvis nemt at skrive DAX-formler ved hjælp af søgefunktionen og forslagslisten. Nu kan du se, hvad du kan få vist med den nye måling Net Sales per Unit.
    
4. Træk målingen **Net Sales per Unit** til et tomt område på dit rapportcanvas.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
    Det ser ikke videre interessant ud. Men bare rolig.
    
5.  Ret diagrammets visualiseringstype til **Træstruktur**.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. Træk nu feltet **ProductCategory** fra tabellen **ProductCategory** til området **Gruppe**.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
    Det er brugbare oplysninger, men hvad nu, hvis du vil se nettoomsætningen pr. produkt?
    
7. Fjern feltet **ProductCategory**, og træk i stedet feltet **ProductName** fra tabellen **Product** til området **Gruppe**. 
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
    Nu leger vi bare lidt med tingene, men du må indrømme, at det er ret smart. Vi kan naturligvis filtrere træstrukturen på en lang række måder, som jeg ikke lige vil komme nærmere ind på i dette selvstudium.

## <a name="what-weve-learned"></a>Det har du lært
Med målinger har du mulighed for effektivt at få en større indsigt i dine data. Hvordan du opretter målinger ved hjælp af formellinjen. Du kan navngive målinger, som du vil, og med forslagslisten er det nemt at finde og vælge de rette elementer, du vil tilføje i formler. Du har fået en introduktion til kontekst, hvor resultatet af beregningen af målinger ændres i forhold til andre felter eller andre udtryk i dine formler i målinger.

## <a name="next-steps"></a>Næste trin
Hvis du vil vide mere om DAX-formler og oprette mere avancerede målinger, skal du se [Grundlæggende DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Denne artikel har fokus på de grundlæggende koncepter i DAX, for eksempel syntaks, funktioner og en dybere forståelse af kontekst.

Husk at føje [DAX-reference (Data Analysis Expressions)](https://msdn.microsoft.com/library/gg413422.aspx) til dine favoritter. Det er her, du finder detaljerede oplysninger om DAX-syntaks, operatorer og de mere end 200 DAX-funktioner.

