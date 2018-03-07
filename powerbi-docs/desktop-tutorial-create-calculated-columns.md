---
title: 'Selvstudium: Opret beregnede kolonner i Power BI Desktop'
description: 'Selvstudium: Opret beregnede kolonner i Power BI Desktop'
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
LocalizationGroup: Learn more
ms.openlocfilehash: acdaa95908cd03006170eb06ddfc780c836c64ac
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>Selvstudium: Opret beregnede kolonner i Power BI Desktop
Nogle gange indeholder de data, du analyserer, ikke et bestemt felt, du skal bruge for at få de resultater, du er ude efter. Det er her, beregnede kolonner kommer ind i billedet. Beregnede kolonner gør brug af DAX-formler (Data Analysis Expressions) til at definere en kolonnes værdi. Disse værdier kan være næsten alt, f.eks. sammensætning af tekstværdier fra nogle andre kolonner andre steder i modellen eller beregning af en numerisk værdi fra andre værdier. Lad os f.eks. sige, at dine data har kolonnen By og Stat (som felter på listen Felter), men du vil gerne have et enkelt felt af typen Placering, der indeholder begge som en enkelt værdi, f.eks. Miami, FL. Det er præcis det, beregnede kolonner er beregnede til.

Beregnede kolonner er lig med målinger, da begge er baseret på en DAX-formel, men adskiller sig fra hinanden på den måde, de bruges på. Målinger bruges mest i området Værdier af en visualisering, til at beregne resultater, der er baseret på andre felter, som du har i en række i en tabel eller på en akse, i en forklaring eller i et gruppeområde i en visualisering. Beregnede kolonner bruges derimod, når du gerne vil have kolonnens resultater på den pågældende række i tabellen eller på akse-, forklarings- eller gruppeområdet.

I dette selvstudium lærer du, hvordan du kan oprette nogle af dine egne beregnede kolonner i Power BI Desktop. Selvstudiet er til de Power BI-brugere, som allerede har erfaring med Power BI Desktop, og som er klar til at arbejde med mere avancerede modeller. Du bør allerede have kendskab til at bruge forespørgsler til at importere data, arbejde med flere relaterede tabeller og tilføje felter på dit rapportcanvas. Hvis du ikke har erfaring med Power BI Desktop, skal du se [Introduktion til Power BI Desktop](desktop-getting-started.md).

Hvis du vil følge trinnene i dette selvstudium, skal du downloade filen [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip). Dette er den samme eksempelfil, der bruges til selvstudiet [Opret dine egne målinger i Power BI Desktop](desktop-tutorial-create-measures.md). Den indeholder data om salget for det fiktive firma Contoso, Inc. Da dataene i filen er importeret fra en database, kan du ikke oprette forbindelse til datakilden eller se den i Forespørgselseditor. Når du har hentet filen til din computer, kan du åbne den i Power BI Desktop.

## <a name="lets-create-a-calculated-column"></a>Lad os oprette en beregnet kolonne
Lad os sige, at vi gerne vil have vist produktkategorier sammen med produktunderkategorier i en enkelt værdi for rækker, som mobiltelefoner – tilbehør, mobiltelefoner – Smart telefoner og PDA'er osv. I rapportvisning eller datavisning (vi bruger rapportvisning her), hvis vi ser på vores produkttabeller på listen over felter, kan vi se, at der ikke er nogen felter, der indeholder det, vi gerne vil have. Vi har dog feltet ProductCategory og feltet ProductSubcategory i hver deres tabel.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

Vi opretter en ny beregnet kolonne, der skal kombinere værdier fra disse to kolonner til nye værdier for vores nye kolonne. Vi skal altså kombinere data fra to forskellige tabeller i én enkelt kolonne. Eftersom vi vil benytte DAX til at oprette vores nye kolonne, kan vi udnytte alle fordelene for den model, vi allerede har, herunder relationerne mellem forskellige tabeller, der allerede findes.

### <a name="to-create-a-productfullcategory-column"></a>Sådan oprettes en kolonne af typen ProductFullCategory
1.  Højreklik på eller klik på pil ned på tabellen **ProductSubCategory** på feltlisten, og klik derefter på **New Column** (Ny kolonne). På den måde sikres det, at vores nye kolonne føjes til tabellen ProductSubCategory.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    Formellinjen vises langs toppen af dit rapportcanvas eller datagitter. Her kan du omdøbe kolonnen og angive en DAX-formel.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    En ny beregnet kolonne hedder som standard blot Column (Kolonne). Hvis du ikke omdøber den, og du opretter efterfølgende kolonner, navngives de Column2, Column3 osv. Vi vil gerne have, at kolonnerne kan identificeres, så vi giver vores nye kolonne et nyt navn.
    
2.  Eftersom navnet **Column** (Kolonne) allerede er fremhævet på formellinjen, skal du blot skrive **ProductFullCategory**.
    
    Nu kan du begynde at skrive en formel. Værdierne i den nye kolonne skal starte med navnet ProductCategory fra tabellen ProductCategory. Eftersom denne kolonne er i en anden, men relateret tabel, skal vi bruge funktionen [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) til at hjælpe os med at hente kolonnen.
    
3.  Skriv et **R** efter lighedstegnet. Herefter får du vist en rulleliste med forslag til alle de DAX-funktioner, der begynder med R. Jo mere du skriver, desto tættere kommer listen på den funktion, vi har brug for. Du får vist en beskrivelse af funktionen ud for funktionen. Vælg **RELATED** ved at rulle ned, og tryk derefter på Enter.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    Der vises en startparentes sammen med en anden forslagsliste over alle de kolonner, du kan bruge som argument i RELATED-funktionen. Der vises også en beskrivelse og oplysninger om de parametre, der forventes.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    Et udtryk vises altid mellem en start- og slutparentes. I dette tilfælde indeholder udtrykket et enkelt argument, der overføres til funktionen RELATED: den relaterede kolonne, værdierne skal returneres fra. Listen over kolonner indsnævres automatisk til kun at vise de kolonner, der er relateret. I dette tilfælde vil vi have kolonnen ProductCategory i tabellen ProductCategory.
    
    Vælg **ProductCategory [ProductCategory]**, og skriv derefter en slutparentes.
    
    > [!TIP]
    > Syntaksfejl skyldes ofte, at der mangler en slutparentes, eller at den er placeret forkert. Men ofte tilføjes den automatisk i Power BI Desktop, hvis du glemmer den.
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. Vi tilføjer en bindestreg for at adskille hver værdi, så efter slutparentesen i det første udtryk skal du lave et mellemrum, et &-tegn (&), anførselstegn, mellemrum, bindestreg (-), endnu et mellemrum, et anførselstegn og derefter endnu et &-tegn. Din formel skal se sådan ud:
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > Klik på den nedadvendte pil i højre side af formellinjen for at udvide formeleditoren. Klik på Alt & Enter for at gå en linje ned og tabulator for at flytte ting.
    > 
    > 
    
5.  Til sidst skal du indtaste endnu en åbningsparentes og derefter markere kolonnen **[ProductSubcategory]** for at afslutte formlen. Din formel skal se sådan ud:
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    Du kan se, at vi ikke har brugt endnu en RELATED-funktion i det andet udtryk, der kalder ProductSubcategory-kolonnen. Dette skyldes, at denne kolonne allerede er i den samme tabel, som vi opretter den nye kolonne i. Vi kan indtaste [ProductCategory] med tabelnavnet (fuldt kvalificeret) eller uden (ikke-kvalificeret).
    
6.  Afslut formlen ved at trykke på Enter eller ved at klikke på fluebenet i formellinjen. Formlen valideres og tilføjes på feltlisten i tabellen **ProductSubcategory**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    Læg mærke til, at beregnede kolonner får et særligt ikon på feltlisten. Det viser, at de indeholder en formel. De ser kun sådan ud i Power BI Desktop. I Power BI-tjenesten (Power BI-webstedet) er det ikke muligt at ændre en formel, hvorfor et beregnet kolonnefelt ikke har et ikon.
    
## <a name="lets-add-our-new-column-to-a-report"></a>Lad os føje den nye kolonne til en rapport
Vi kan nu føje vores nye ProductFullCategory-kolonne til rapportcanvasset. Lad os se på SalesAmount efter ProductFullCategory.

Træk kolonnen **ProductFullCategory** fra tabellen **ProductSubcategory** til rapportcanvasset, og træk derefter feltet **SalesAmount** fra tabellen **Sales** ind i diagrammet.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>Lad os oprette en anden beregnet kolonne
Nu ved du, hvordan du kan oprette en beregnet kolonne, så lad os oprette en mere.

Contoso Sales-salgseksemplet i Power BI Desktop-modellen indeholder salgsdata for både aktive og inaktive butikker. Vi vil gerne gøre det tydeligt, at de data, der vises for inaktive butikker, fremstår som inaktive. Vi vil gerne have et felt med navnet Active StoreName. Vi er derfor nødt til at oprette endnu en kolonne. I dette tilfælde vil vi gerne have vist butikkens navn som "Inaktiv", når en butik er inaktiv, men have vist butikkens rigtige navn, når der er tale om en aktiv butik.

Heldigvis er der en kolonne med navnet Status i tabellen Stores (Butikker) med værdien On (Aktiveret) for aktive butikker og Off (Deaktiveret) for inaktive butikker. Vi kan kontrollere værdierne for hver række i kolonnen Status for at oprette nye værdier i vores nye kolonne.

### <a name="to-create-an-active-storename-column"></a>Sådan oprettes en kolonne af typen Active StoreName
1.  Opret en ny beregnet kolonne med navnet **Active StoreName** i tabellen **Stores**.
    
    I denne kolonne kontrollerer DAX-formlen den enkelte butiks status. Hvis en butiks status er On (Aktiveret), returneres butikkens navn. Hvis den er Off (Deaktiveret), får den navnet "Inactive" (Inaktiv). Vi bruger den logiske funktion [IF](https://msdn.microsoft.com/library/ee634824.aspx) til at kontrollere butikkens status og returnere en bestemt værdi, hvis resultatet er true eller false.
    
2.  Begynd med at skrive **IF**. Forslagslisten viser, hvad du kan tilføje. Vælg **IF**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    Det første argument for IF er en logisk test. Vi vil gerne afprøve, om en butik har status "On" (Aktiveret).
    
3.  Indtast en startparentes **[** , som gør det muligt for os at vælge kolonner fra tabellen Stores. Vælg **[Status]**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  Lige efter **[Status]** skal du skrive **= "On"** og derefter et komma (**,**) for at angive det andet argument. Værktøjstippet angiver, at vi skal tilføje den værdi, der skal bruges, når resultatet er true.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  Hvis butikken er On (Aktiveret), vil vi have vist butikkens navn. Skriv en startparentes **[**, og vælg kolonnen **[StoreName]**, og skriv derefter et andet komma, så vi kan indtaste vores tredje argument.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  Vi skal tilføje den værdi, der skal angives, når resultatet er false. I dette tilfælde **"Inactive"**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Afslut formlen ved at trykke på Enter eller ved at klikke på fluebenet i formellinjen. Formlen valideres og tilføjes på feltlisten i tabellen Stores.
    
    Vi kan nu bruge vores nye Active StoreName-kolonne i visualiseringer på samme måde som et hvilket som helst andet felt. I dette diagram vises butikker med statussen On (Aktiveret) enkeltvist efter navn, men butikker med statussen Off (Deaktiveret) grupperes og vises som inaktive. 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>Det har du lært
Beregnede kolonner kan forbedre vores data og give bedre indsigt. Du har lært, hvordan du opretter beregnede kolonner ved at bruge formellinjen, hvordan du bruger forslagslisten, og hvordan du bedst navngiver nye kolonner.

## <a name="next-steps"></a>Næste trin
Hvis du vil vide mere om DAX-formler og oprette beregnede kolonner med mere avancerede DAX-formler, skal du se [Grundlæggende DAX i Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Denne artikel har fokus på de grundlæggende koncepter i DAX, for eksempel syntaks, funktioner og en dybere forståelse af kontekst.

Husk at føje [DAX-reference (Data Analysis Expressions)](https://msdn.microsoft.com/library/gg413422.aspx) til dine favoritter. Det er her, du finder detaljerede oplysninger om DAX-syntaks, operatorer og de mere end 200 DAX-funktioner.

