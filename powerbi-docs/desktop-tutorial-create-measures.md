---
title: 'Selvstudium: Opret dine egne målinger i Power BI Desktop'
description: 'Selvstudium: Opret dine egne målinger i Power BI Desktop'
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: f3a58d8acc7d8eb24954e9db0c0db91eacad2f9a
ms.sourcegitcommit: 65426de556cd7207cbc4f478198664e25c33a769
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/30/2018
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Selvstudium: Opret dine egne målinger i Power BI Desktop
Du kan oprette nogle af de mest effektive løsninger til dataanalyse i Power BI Desktop ved hjælp af målinger. Målinger hjælper dig med at udføre beregninger på dine data, når du arbejder med dine rapporter. I dette selvstudium lærer du, hvordan du skal forstå målinger, og hvordan du opretter dine egne grundlæggende målinger i Power BI Desktop.

### <a name="prerequisites"></a>Forudsætninger
- Denne artikel er beregnet til Power BI-brugere, som allerede har erfaring med Power BI Desktop, så de kan oprette mere avancerede modeller. Du bør allerede have kendskab til at bruge Hent data og Forespørgselseditor til at importere data, arbejde med flere relaterede tabeller og tilføje felter på dit rapportcanvas. Hvis du ikke har erfaring med Power BI Desktop, skal du se [Introduktion til Power BI Desktop](desktop-getting-started.md).
  
- Download filen [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip), som indeholder data om onlinesalget for det fiktive firma Contoso, Inc. Dataene blev importeret fra en database, så du kan ikke oprette forbindelse til datakilden eller få dem vist i Forespørgselseditor. Udpak filen på din computer, og åbn den derefter i Power BI Desktop.

## <a name="understand-measures"></a>Forstå målinger

Målinger oprettes oftest automatisk for dig. I filen Contoso Sales Sample skal du markere afkrydsningsfeltet ved siden af feltet **SalesAmount** i tabellen **Sales** i brønden Felter. Du kan også trække **SalesAmount** til rapportcanvasset. Der vises en ny visualisering med et søjlediagram, hvor du kan se den samlede sum af alle værdier i kolonnen SalesAmount i tabellen Sales.

![Diagrammet SalesAmount](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

Alle felter, der vises i brønden Felter med et sigmaikon, ![sigmaikon](media/desktop-tutorial-create-measures/meastut_sigma.png) er numeriske, og værdierne kan sammenlægges. I stedet for at vise en tabel med alle to millioner rækker af værdierne for SalesAmount, har Power BI Desktop registreret en numerisk datatype og automatisk oprettet og beregnet en måling for at sammenlægge dataene. Sum er standardsammenlægningen for en numerisk datatype, men du kan nemt anvende forskellige sammenlægninger, f.eks. gennemsnit eller antal. Det er vigtigt at forstå sammenlægninger for at forstå målinger, da alle målinger vil udføre en form for sammenlægning. 

Hvis du vil ændre diagramsammenlægningen til gennemsnit, skal du i området **Værdi** i ruden Visualiseringer klikke på pilen i rullemenuen ved siden af **SalesAmount** og vælge **Gennemsnit**. Visualiseringen ændres til et gennemsnit af alle salgsværdierne i feltet SalesAmount.

![Diagram for SalesAmount med gennemsnit](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Du kan ændre typen af sammenlægningen, afhængigt af det resultat du vil have vist, men det er ikke alle typer af sammenlægninger, der kan anvendes for alle numeriske datatyper. For feltet SalesAmount vil sammenlægningen Sum og Gennemsnit for eksempel give mening. Det kan også give mening at bruge Minimum og Maksimum. Værdierne i feltet SalesAmount er valuta, så selvom de er numeriske, vil Antal ikke give så meget mening for dette felt.

De værdier, der beregnes ud fra målinger, ændres på baggrund af dine interaktioner i rapporten. Hvis du for eksempel trækker feltet **RegionCountryName** fra tabellen **Geography** til diagrammet, vises det gennemsnitlige salgsbeløb for hvert land.

![Salgsbeløb efter land](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Når resultatet af en måling ændres på grund af en interaktion med rapporten, påvirkes målingens *kontekst*. Hver gang du arbejder med visualiseringer i rapporten, ændrer du konteksten for, hvordan en måling beregner og viser resultater.

## <a name="create-and-use-your-own-measures"></a>Opret og brug dine egne målinger

I de fleste tilfælde beregner og returnerer Power BI automatisk værdier i henhold til de typer af felter og sammenlægninger, du vælger, men i nogle tilfælde vil du måske oprette dine egne målinger for at udføre mere komplekse og unikke beregninger. I Power BI Desktop kan du oprette dine egne målinger ved at bruge DAX-formelsproget (Data Analysis Expressions). 

I DAX-formler bruges der mange af de samme funktioner og operatorer samt den samme syntaks som i Excel-formler. DAX-funktionerne er dog designet til at arbejde med relationelle data og udføre mere dynamiske beregninger, når du interagerer med dine rapporter. Der er mere end 200 DAX-funktioner, som kan udføre alt lige fra enkle sammenlægninger, som Sum og Gennemsnit, til mere komplekse statistik- og filtreringsfunktioner. Der findes mange ressourcer, hvor du kan få mere at vide om DAX. Når du er færdig med dette selvstudium, kan vi anbefale [Grundlæggende DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Når du har oprettet din egen måling, føjes den til listen Felter i den tabel, du vælger, og kaldes for *modelmåling*. Nogle af fordelene ved modelmålinger er, at du kan navngive dem, ligesom du vil, hvilket gør det nemmere at identificere dem. Du kan også bruge dem som argumenter i andre DAX-udtryk, og du kan få dem til at udføre komplekse beregninger meget hurtigt.

>[!TIP]
>Fra og med udgivelsen af Power BI Desktop i februar 2018 er mange almindelige beregninger tilgængelige som **hurtigmålinger**, som skriver DAX-formler for dig på baggrund af dine input i dialogboksen. Disse hurtige, effektive beregninger er også gode til at lære om DAX og forsyne dine egne tilpassede målinger. Hvis du vil oprette eller udforske hurtigmålinger, skal du vælge **Ny hurtigmåling** på listen **Flere indstillinger** i en tabel eller under **Beregninger** under fanen Hjem på båndet. Du kan finde flere oplysninger om oprettelse og brug af hurtigmålinger under [Brug hurtigmålinger](desktop-quick-measures.md).

### <a name="create-a-measure"></a>Opret en måling

Du vil analysere din nettoomsætning ved at trække rabatter og returneringer fra det samlede salgsbeløb. Uanset hvilken kontekst du har i din visualisering, har du brug for en måling, der trækker summen af DiscountAmount og ReturnAmount fra summen af SalesAmount. Der er ikke noget felt for nettoomsætning på listen Felter, men du har byggeklodserne til at oprette din egen måling, der kan beregne nettoomsætningen. 

1.  Højreklik på tabellen **Sales** i brønden Felter, eller hold over tabellen, og vælg ellipsen **Flere indstillinger** (...). Vælg derefter **Ny måling**. På den måde gemmes din nye måling i tabellen Sales, hvor den er nemmere at finde igen.
    
    ![Ny måling](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    Du kan også oprette en ny måling ved at vælge **Ny måling** i gruppen Beregninger under fanen Hjem på Power BI Desktop-båndet.
    
    ![Ny måling via båndet](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    
    >[!TIP]
    >Når du opretter en måling via båndet, kan den blive oprettet i en hvilken som helst tabel, så den vil være nemmere at finde, hvis du opretter den der, hvor du har planlagt at bruge den. Du skal derfor først markere tabellen Sales for at aktivere den og derefter vælge **Ny måling**. 
    
    Formellinjen vises langs toppen af rapportcanvasset, hvor du kan omdøbe målingen og angive en DAX-formel.
    
    ![Formellinje](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
2.  En ny måling kaldes som standard blot for Måling. Hvis du ikke omdøber den, vil yderligere målinger blive kaldt for Måling 2, Måling 3 osv. Det er bedst, hvis dine målinger er nemme at identificere, så fremhæv **Måling** på formellinjen, og skriv derefter **Net Sales**.
    
3.  Nu kan du begynde at skrive en formel. Begynd at skrive **Sum** efter lighedstegnet. I takt med at du skriver, vises en rullemenu med forslag, hvor alle DAX-funktioner, der starter med det bogstav, du skriver, vises. Rul ned, hvis det er nødvendigt, for at vælge **SUM** på listen, og tryk derefter på Enter.
    
    ![Vælg SUM](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Der vises en startparentes sammen med en anden rullemenu med en forslagsliste over alle tilgængelige kolonner, du kan bruge som argument i SUM-funktionen.
    
    ![Vælg kolonne](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    Udtryk vises altid mellem en start- og slutparentes. Dit udtryk indeholder et enkelt argument, som skal bruges i SUM-funktionen: kolonnen SalesAmount. Begynd at skrive "SalesAmount", indtil der kun er én værdi tilbage på listen: Sales(SalesAmount). Navnet på kolonnen, som kommer før navnet på tabellen, kaldes for kolonnens *fulde navn*. Med fulde navne på kolonner er det nemmere at læse dine formler. 
    
    ![Vælg SalesAmount](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
4. Vælg **Sales[SalesAmount]**, og skriv derefter en slutparentes.
    
    > [!TIP]
    > Syntaksfejl skyldes ofte, at der mangler en slutparentes, eller at den er placeret forkert.
    
    
    
5.  Sådan trækker du de to andre kolonner fra:
    1. Skriv et mellemrum, et minustegn (**-**) og endnu et mellemrum efter slutparentesen for det første udtryk. 
    2. Angiv en anden SUM-funktion, og begynd at skrive "DiscountAmount", indtil du kan vælge kolonnen **Sales[DiscountAmount]** som argument. Tilføj en slutparentes. 
    3. Angiv et mellemrum, endnu et minustegn, et mellemrum, en anden SUM-funktion med **Sales[ReturnAmount]** som argument og en slutparentes.
    
    ![Fuldstændig formel](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
6.  Tryk på Enter, eller klik på fluebenet på formellinjen for at afslutte og validere formlen. Den validerede måling er nu klar til brug på listen Felter for tabellen Sales. 
    
    ![Måling på listen Felter](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
Hvis du løber tør for plads til at angive en formel eller vil angive den over flere linjer, skal du vælge pilen til højre for formellinjen for at åbne for mere plads.

![Pil i formel](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)

Du kan adskille dele af formlen over flere linjer ved at trykke på **Alt + Enter** eller ved at flytte ting over ved hjælp af **tabulatortasten**.

![Udvidet formel](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)

### <a name="use-your-measure-in-the-report"></a>Brug målingen i rapporten
Du kan nu føje målingen Net Sales til rapportcanvasset og beregne nettoomsætningen for alle andre felter, du føjer til rapporten. Sådan ser du nettoomsætning efter land:

1. Markér målingen **Net Sales** i tabellen **Sales**, eller træk den ind i rapportcanvasset.
    
2. Markér feltet **RegionCountryName** i tabellen **Geography**, eller træk det til diagrammet.
    
    ![Nettoomsætning efter land](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
Hvis du vil se forskellen mellem nettoomsætning og samlet salg efter land, skal du vælge feltet **SalesAmount** eller trække det til diagrammet. 

![Salgsbeløb og nettoomsætning efter land](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)

Der bruges nu to målinger i diagrammet: SalesAmount, som blev beregnet automatisk, og Net Sales, som du oprettede. Hver måling blev beregnet i henhold til konteksten i et andet felt, RegionCountryName.
    
### <a name="use-your-measure-with-a-slicer"></a>Brug målingen sammen med et udsnitsværktøj

Du kan nu tilføje et udsnitsværktøj, så du kan filtrere nettoomsætningen og salgsbeløbet yderligere efter kalenderår.
    
1.  Klik på et tomt område ved siden af diagrammet, og vælg derefter visualiseringen **Tabel** under **Visualiseringer**. Dette opretter en tom tabelvisualisering på dit rapportcanvas.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
2.  Træk feltet **Year** fra tabellen **Calendar** til den nye tomme tabelvisualisering. Da Year er et numerisk felt, beregner Power BI Desktop værdierne, men det giver ikke meget mening som en sammenlægning. 
    
    ![Sammenlægningen Year](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
3.  Under **Værdier** i ruden Visualiseringer skal du vælge rullemenuen ved siden **Year** og derefter vælge **Opsummer ikke**. De enkelte år vises nu i tabellen.
    
    ![Opsummer ikke](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
4.  Vælg ikonet **Udsnitsværktøj** i ruden Visualiseringer for at konvertere den nye tabel til et udsnit.

    ![Skift til udsnitsværktøj](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
5.  Vælg en vilkårlig værdi i udsnittet **Year** for at filtrere diagrammet **Net Sales and Sales Amount by Country** følgeligt. Målingerne Net Sales og SalesAmount genberegner og viser resultater i henhold til konteksten af det valgte felt for Year. 
    
    ![Diagram med udsnit efter Year](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

### <a name="use-your-measure-in-another-measure"></a>Brug din måling i en anden måling

Du ønsker at finde ud af, hvilke produkter der har den højeste nettoomsætning pr. solgt enhed, så du har brug for en måling, der opdeler nettoomsætning efter mængden af solgte enheder. Du kan oprette en ny måling, der opdeler resultatet af målingen Net Sales efter summen af Sales[SalesQuantity].

1.  Opret en ny måling med navnet **Net Sales per unit** i tabellen Sales.
    
2.  Begynd at skrive **Net Sales** i formellinjen. På forslagslisten kan du se, hvad du kan tilføje. Vælg **[Net Sales]**.
    
    ![Formel med Net Sales](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    Du kan også referere til en måling ved blot at begynde at skrive en startparentes (**[**). På forslagslisten kan du kun se målinger, du kan føje til formlen.
    
    ![Parenteser viser kun målinger](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  Angiv et mellemrum, en divisionsoperator (**/**), endnu et mellemrum, en SUM-funktion, og skriv derefter **Quantity**. På forslagslisten kan du se alle de kolonner, hvor Quantity indgår i navnet. Vælg **Sales[SalesQuantity]**, skriv slutparentesen, og tryk på Enter, eller markér afkrydsningsfeltet for at validere formlen. Formlen skal se sådan ud:
    
    `Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])`
    
4. Markér målingen **Net Sales per Unit** i tabellen Sales, eller træk den ind i et tomt område på rapportcanvasset. I diagrammet kan du se nettoomsætningen pr. enhed for alle solgte produkter, hvilket ikke er meget informativt. 
    
    ![Samlet nettoomsætning pr. enhed](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
5. Ret diagrammets visualiseringstype til **Træstruktur** for at få et andet layout.
    
    ![Skift til træstruktur](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. Markér feltet **Product Category**, eller træk det ind i træstrukturen eller i feltet Gruppe i ruden Visualiseringer. Nu har du nogle gode oplysninger!
    
    ![Træstruktur efter Product Category](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
7. Prøv at fjerne feltet **ProductCategory** og i stedet trække feltet **ProductName** ind i diagrammet. 
    
    ![Træstruktur efter Product Name](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
Nu leger vi bare lidt med tingene, men du må indrømme, at det er ret smart. Eksperimentér med andre måder at filtrere og formatere visualiseringen på.

## <a name="what-youve-learned"></a>Det har du lært
Målinger er effektive til at få indsigt i data. Du har lært, hvordan du opretter målinger ved hjælp af formellinjen, navngiver dem, så de giver mest mening, og finder og vælger de korrekte formelelementer ved hjælp af DAX-forslagslisten. Du har også fået en introduktion til kontekst, hvor resultatet af beregninger i målinger ændres i henhold til andre felter eller andre udtryk i formlerne.

## <a name="next-steps"></a>Næste trin
- Hvis du vil vide mere om hurtigmålinger i Power BI Desktop, der udfører mange almindelige beregninger for dig, skal du se [Brug hurtigmålinger til nemt at udføre almindelige og effektive beregninger](desktop-quick-measures.md).
  
- Hvis du vil vide mere om DAX-formler og oprette mere avancerede målinger, skal du se [Grundlæggende DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Denne artikel har fokus på de grundlæggende koncepter i DAX, for eksempel syntaks, funktioner og en dybere forståelse af kontekst.
  
- Husk at føje [DAX-reference (Data Analysis Expressions)](https://msdn.microsoft.com/library/gg413422.aspx) til dine favoritter. Det er her, du finder detaljerede oplysninger om DAX-syntaks, operatorer og de mere end 200 DAX-funktioner.

