---
title: 'Selvstudium: Kombiner data fra Excel og et OData-feed i Power BI Desktop'
description: 'Selvstudium: Kombiner data fra Excel og et OData-feed'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/21/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: 94e40681d065591db008f8a9062d851e0bd83f61
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285754"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>Selvstudium: Kombiner salgsdata fra Excel og et OData-feed

Det er almindeligt at have data, der er spredt på forskellige datakilder, for eksempel produktoplysninger i én database og salgsoplysninger i en anden. Med **Power BI Desktop** kan du kombinere data fra forskellige kilder og oprette interessante, overbevisende dataanalyser og visualiseringer. 

I dette selvstudium lærer du, hvordan du kombinerer data fra to datakilder: en Excel-projektmappe, der indeholder produktoplysninger, og et OData-feed, der indeholder ordredata. Når du har importeret de enkelte datasæt og har udført transformerings- og sammenlægningstrin, kan du bruge data fra begge kilder til at fremstille en salgsanalyserapport med interaktive visualiseringer. Disse metoder kan også anvendes på SQL Server-forespørgsler, CSV-filer og andre datakilder i Power BI Desktop.

>[!NOTE]
>I Power BI Desktop kan du som regel udføre den samme opgave på flere måder. Du kan f.eks. også få adgang til mange af indstillingerne på båndet ved at højreklikke eller vælge menuen **Flere indstillinger** på en kolonne eller celle. Flere alternative metoder beskrives i nedenstående trin. 

## <a name="import-the-product-data-from-excel"></a>Importér produktdata fra Excel

Først skal du importere produktdataene fra Excel-projektmappen Products.xlsx til i Power BI Desktop.

1. [Hent Excel-projektmappen Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx), og gem den som **Products.xlsx**.
   
2. Vælg rullepilen ud for **Hent data** under fanen **Hjem** på båndet i Power BI Desktop, og vælg derefter **Excel** på rullelisten **Mest almindelige**. 
   
   ![Hent data](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >Du kan også vælge selve menupunktet **Hent data** eller vælge **Hent data** fra Power BI-dialogboksen **Introduktion**, vælge **Excel** eller **Filer** > **Excel** i dialogboksen **Hent data** og derefter vælge **Opret forbindelse**.
   
3. I dialogboksen **Åbn** skal du gå til og vælge filen **Products.xlsx** og derefter vælge **Åbn**.
   
4. I ruden **Navigator** skal du vælge tabellen **Products** og derefter vælge **Rediger**.
   
   ![Ruden Navigator til Excel](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
Der åbnes et eksempel på tabellen i **Power-forespørgselseditor**, hvor du kan anvende transformationer for at rydde op i dataene. 
   
![Power-forespørgselseditor](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>Du kan også åbne **Power-forespørgselseditor** ved at vælge **Rediger forespørgsler** > **Rediger forespørgsler** på båndet **Hjem** i Power BI Desktop eller ved at højreklikke eller vælge **Flere indstillinger** ud for en hvilket som helst forespørgsel i **rapportvisning** og vælge **Rediger forespørgsel**.

## <a name="clean-up-the-products-columns"></a>Ryd op i produktkolonnerne

Din kombinerede rapport skal kun bruge kolonnerne **ProductID**, **ProductName**, **QuantityPerUnit** og **UnitsInStock** fra Excel-projektmappen, så du kan fjerne de andre kolonner. 

1. Markér kolonnerne **ProductID**, **ProductName**, **QuantityPerUnit** og **UnitsInStock** i **Power-forespørgselseditor** (brug **Ctrl**+**klik** for at markere mere end én kolonne, eller brug **Skift**+**klik** for at markere kolonner, der er ved siden af hinanden).
   
2. Højreklik på en af de valgte overskrifter, og vælg **Fjern andre kolonner** på rullelisten for at fjerne alle undtagen de markerede kolonner fra tabellen. 
   Du kan også vælge **Fjern kolonner** > **Fjern andre kolonner** i gruppen **Administrer kolonner** under fanen **Hjem** på båndet. 
   
   ![Fjern andre kolonner](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>Importér ordredataene fra et OData-feed

Importér derefter ordredataene fra OData-feedet for eksempelsalgssystemet Northwind. 

1. I **Power-forespørgselseditor** skal du vælge **Ny kilde** og derefter vælge **OData-feed** på rullelisten **Mest almindelige**. 
   
   ![Hent OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. Indsæt URL-adressen til OData-feedet for Northwind, `http://services.odata.org/V3/Northwind/Northwind.svc/`, i dialogboksen **OData-feed**, og vælg **OK**.
   
   ![Dialogboksen OData-feed](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. I ruden **Navigator** skal du vælge tabellen **Orders** og derefter vælge **OK** for at indlæse data i **Power-forespørgselseditor**.
   
   ![Ruden Navigator til OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >I **Navigator** kan du vælge et tabelnavn uden at markere afkrydsningsfeltet, hvis du vil have vist et eksempel.

## <a name="expand-the-order-data"></a>Udvid ordredataene

Når du opretter forbindelse til datakilder, der har flere tabeller, f.eks. relationsdatabaser eller Northwind OData-feedet, kan du bruge referencer mellem tabeller til at oprette dine forespørgsler. Tabellen **Orders** indeholder referencer til flere relaterede tabeller. Du kan tilføje kolonnerne **ProductID**, **UnitPrice** og **Quantity** fra den relaterede tabel **Order_Details** i emnetabellen (**Orders**) ved hjælp af handlingen **Udvid**. 

1. Rul til højre i tabellen **Orders**, indtil du kan se kolonnen **Order_Details**. Bemærk, at den indeholder referencer til en anden tabel i stedet for data.
   
   ![Kolonnen Order_Details](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. Vælg ikonet **Udvid** (![ikonet Udvid](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) i kolonneoverskriften **Order_Details**. 
   
3. På rullemenuen **Udvid**:
   
   1. Vælg **(Markér alle kolonner)** for at rydde alle kolonner.
      
   2. Vælg **ProductID**, **UnitPrice** og **Quantity**, og vælg derefter **OK**.
      
      ![Dialogboksen Udvid](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

Når du har udvidet tabellen **Order_Details**, erstattes kolonnen **Order_Details** af de tre nye kolonner fra den indlejrede tabel, og der er nye rækker i tabellen til de data, der er tilføjet fra de enkelte ordrer. 

![Udvidede kolonner](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>Opret en brugerdefineret beregnet kolonne

I Power-forespørgselseditor kan du oprette beregninger og brugerdefinerede felter for at forbedre dine data. Du opretter en brugerdefineret kolonne, der beregner den samlede pris for hver linjevare, ved at gange enhedsprisen med antallet af varer.

1. Vælg **Brugerdefineret kolonne** under fanen **Tilføj kolonne** på båndet i Power-forespørgselseditor.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. I dialogboksen **Brugerdefineret kolonne** skal du skrive **LineTotal** i feltet **Nyt kolonnenavn**.

3. I feltet **Formel for brugerdefineret kolonne:** Efter **=** skal du angive **[Order_Details.UnitPrice]** \* **[Order_ Details.Quantity]**. Du kan også vælge feltnavnene fra rulleboksen **Tilgængelige kolonner** og vælge **<< Indsæt** i stedet at skrive dem. 
3. Vælg **OK**.
   
   ![Dialogboksen Brugerdefineret kolonne](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

Det nye felt **LineTotal** vises som den sidste kolonne i tabellen **Orders**.

## <a name="set-the-data-type-for-the-new-field"></a>Angiv datatypen for det nye felt

Når Power-forespørgselseditor opretter forbindelse til data, bestemmes den bedste datatype for de enkelte felter, og dataene vises i overensstemmelse hermed. Du kan se de datatyper, der er tildelt til felter, via ikonerne i overskrifterne eller under **Datatype** i gruppen **Transformér** under fanen **Hjem** på båndet. 

Din nye kolonne **LineTotal** har datatypen **Enhver**, men dens værdier er valuta. Hvis du vil tildele en datatype, skal du højreklikke på kolonneoverskriften **LineTotal**, vælge **Skift datatype** på rullelisten og derefter vælge **Fast decimaltal**. 

![Skift datatype](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>Du kan også vælge kolonnen **LineTotal**, vælge rullepilen ud for **Datatype** i området **Transformér** under fanen **Hjem** på båndet og derefter vælge **Fast decimaltal**.

## <a name="clean-up-the-orders-columns"></a>Ryd op i ordrekolonner

Du kan gøre det nemmere at arbejde med modellen ved at slette, omdøbe og omarrangere nogle af kolonnerne.

Rapporten bruger kun kolonnerne **OrderDate**, **ShipCity**, **ShipCountry**, **Order_Details.ProductID**, **Order_Details.UnitPrice** og **Order_Details.Quantity**. Du kan markere disse kolonner og bruge **Fjern andre kolonner**, som du gjorde med Excel-dataene, eller du kan markere alle kolonner undtagen de viste, højreklikke på en af de markerede kolonner og vælge **Fjern kolonner** for at fjerne dem alle. 

Du kan gøre det lettere at identificere kolonnerne **Order_Details.ProductID**, **Order_Details.UnitPrice** og **Order_Details.Quantity** ved at fjerne præfikset *Order_Details.* fra kolonnenavnene. Sådan omdøber du kolonnerne til henholdsvist **ProductID**, **UnitPrice** og **Quantity**:

1. Dobbeltklik eller tryk og hold nede på de enkelte kolonneoverskrifter, eller højreklik på kolonneoverskriften, og vælg **Omdøb** på rullelisten. 
2. Slet præfikset *Order_Details.* fra alle navne, og tryk derefter på **Enter**.

Endelig kan du nemmere få adgang til kolonnen **LineTotal** ved at trække og slippe den til venstre umiddelbart til højre for kolonnen **ShipCountry**.

![Tabel, der er ryddet op](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>Gennemse forespørgselstrinnene

Efterhånden som du udformede og transformerede data i Power-forespørgselseditor, blev de enkelte trin registreret i området **Anvendte trin** i ruden **Forespørgselsindstillinger** i højre side af Power-forespørgselseditor. Du kan gå tilbage igennem de Anvendte trin for at gennemse de ændringer, du har lavet, og redigere, slette eller omarrangere dem, hvis det er nødvendigt. Dette kan dog være risikabelt, da ændring af foregående trin kan bryde senere trin. 

Vælg alle dine forespørgsler på listen **Forespørgsler** i venstre side af Power-forespørgselseditor, og gennemse de **Anvendte trin** i **Forespørgselsindstillinger**. Når du har anvendt de tidligere datatransformeringer, vil de Anvendte trin for dine to forespørgsler se sådan ud:

![Anvendte trin for produktforespørgsel](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![Anvendte trin for ordreforespørgsel](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>De underliggende data for Anvendte trin er formler, som er skrevet på **Power-forespørgselssproget**, der også er kendt som **M**-sproget. Hvis du vil se og redigere formlerne, skal du vælge **Avanceret editor** i gruppen **Forespørgsel** under fanen Hjem på båndet. 

## <a name="import-the-transformed-queries"></a>Importér de transformerede forespørgsler

Når du er tilfreds med dine transformerede data, skal du vælge **Luk og anvend** > **Luk og anvend** i gruppen **Luk** under fanen **Hjem** på båndet for at importere dataene til rapportvisning i Power BI Desktop. 

![Luk og anvend](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Når dataene er indlæst, vises forespørgslerne på listen **Felter** i rapportvisning i Power BI Desktop.

![Forespørgsler på listen Felter](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Administrer relationen mellem datasæt

I Power BI Desktop er det ikke et krav, at du kombinerer forespørgsler for at oprette rapporter ud fra dem. Men du kan bruge relationerne mellem datasæt, afhængigt af hvilke felter de har til fælles, til at udvide og forbedre dine rapporter. Power BI Desktop kan registrere relationer automatisk, eller du kan oprette dem i Power BI Desktop-dialogboksen **Administrer relationer**. Du kan finde flere oplysninger om relationer i Power BI Desktop under [Opret og administrer relationer](desktop-create-and-manage-relationships.md).

Datasættene i Orders og Products i dette selvstudium deler feltet *ProductID*, så der er en relation mellem dem, der er baseret på denne kolonne. 

1. I rapportvisning i Power BI Desktop skal du vælge **Administrer relationer** i området **Relationer** under fanen **Hjem** på båndet.
   
   ![Båndet Administrer relationer](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. I dialogboksen **Administrer relationer** kan du se, at Power BI Desktop allerede har registreret og angivet en aktiv relation mellem tabellerne Products og Orders. Vælg **Rediger** for at få vist relationen. 
   
   ![Dialogboksen Administrer relationer](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   Dialogboksen **Rediger relationer** åbnes og viser oplysninger om relationen.  
   
   ![Dialogboksen Rediger relation](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop har automatisk registreret relationen korrekt, så du kan vælge **Annuller** og derefter **Luk** for at lukke dialogboksene for relationen.

Du kan også få vist og administrere relationerne mellem dine forespørgsler ved at vælge visningen **Relation** i venstre side af Power BI Desktop-vinduet. Dobbeltklik på pilen på den linje, der forbinder de to forespørgsler, for at åbne dialogboksen **Rediger relation** og få vist eller ændre relationen. 

![Relationsvisning](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

Hvis du vil vende tilbage til rapportvisningen fra relationsvisningen, skal du vælge ikonet **Rapportvisning**. 

![Ikonet Rapportvisning](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Opret visualiseringer ved hjælp af dine data

I rapportvisningen i Power BI Desktop kan du oprette en lang række visualiseringer, som kan give dig bedre indsigt i dine data. Du kan oprette rapporter på flere sider, og hver side kan indeholde flere visualiseringer. Du og andre kan arbejde med visualiseringerne for at analysere og forstå dine data. Du kan finde flere oplysninger om visning og redigering af rapporter i Power BI-tjenesten (dit websted) under [Rediger en rapport](service-interact-with-a-report-in-editing-view.md).

Du kan både bruge dine datasæt og relationen mellem dem, når du vil visualisere og analysere dine salgsdata. 

Først skal du oprette et stablet søjlediagram, der bruger felter fra begge forespørgsler, for at vise antallet af hvert produkt, der er bestilt. 

1. Vælg feltet **Quantity** fra **Orders** i ruden **Felter** til højre, eller træk det til et tomt område på lærredet. Derved oprettes der et stablet søjlediagram, der viser det samlede antal bestilte produkter. 
   
2. Vælg **ProductName** fra **Products** i ruden **Felter**, eller træk det til diagrammet for at få vist antallet af bestilte produkter. 
   
3. Hvis du vil sortere produkterne efter mest til mindst bestilt, skal du vælge ellipsen **Flere indstillinger** (**...**) øverst til højre i visualiseringen og derefter vælge **Sortér efter antal**.
   
4. Brug håndtagene i hjørnerne af diagrammet til at udvide det, så flere produktnavne bliver synlige. 
   
   ![Liggende søjlediagram med antal efter ProductName](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

Opret derefter et diagram, der viser ordrebeløbet i dollar (**LineTotal**) over tid (**OrderDate**). 

1. Mens ingenting er markeret på lærredet, skal du vælge **LineTotal** fra **Orders** i ruden **Felter** eller trække det til en tom plads på lærredet. Det stablede søjlediagram viser det samlede ordrebeløb i dollar. 
   
2. Markér diagrammet, og vælg **OrderDate** fra **Orders**, eller træk det til diagrammet. I diagrammet vises nu linjetotaler for hver ordredato. 
   
3. Tilpas størrelsen på visualiseringen ved at trække i hjørnerne, så du kan få vist flere data. 
   
   ![Kurvediagrammet LineTotals efter OrderDate](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >Hvis du kun får vist Years i diagrammet (kun tre datapunkter), skal du klikke på rullepilen ud for **OrderDate** i feltet **Akse** i ruden **Visualiseringer** og vælge **OrderDate** i stedet for **Datohierarki**. 

Endelig skal du oprette en kortvisualisering, der viser ordrebeløb for de enkelte lande. 

1. Mens ingenting er markeret på lærredet, skal du vælge **ShipCountry** fra **Orders** i ruden **Felter** eller trække det til en tom plads på lærredet. Power BI Desktop registrerer, at dataene er landenavne, og opretter automatisk en kortvisualisering med et datapunkt for hvert land, der har haft ordrer. 
   
2. For at få størrelserne af datapunkterne til at afspejle beløbene for de enkelte lande skal du trække feltet **LineTotal** til kortet (eller trække det til **Træk datafelter hertil** under **Størrelse** i nederste halvdel af ruden **Visualiseringer**). Størrelserne på cirklerne på kortet afspejler nu ordrebeløbene i dollar for de enkelte lande. 
   
   ![Kortvisualiseringen LineTotals efter ShipCountry](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Arbejd med visualiseringerne i rapporten for at analysere yderligere

I Power BI Desktop kan du se flere tendenser ved at arbejde med visualiseringerne, som viser fremhævninger og filtreres på tværs af hinanden. Du kan finde flere oplysninger under [Filtrering og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md). 

På grund af relationen mellem dine forespørgsler påvirker interaktioner med én visualisering alle andre visualiseringer på siden. 

Vælg cirklen for **Canada** på kortvisualiseringen. Bemærk, at de andre to visualiseringer filtreres for at fremhæve linjetotalerne og ordremængderne kun for Canada.

![Salgsdata filtreret for Canada](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

Hvis du vælger et af produkterne i diagrammet **Quantity efter ProductName**, filtreres kortet og datodiagrammet, så de afspejler dataene for dette produkt, og hvis du vælger en af datoerne i diagrammet **LineTotal efter OrderDate**, filtreres kortet og produktdiagrammet, så de viser dataene for denne dato. 
>[!TIP]
>Hvis du vil fjerne en markering, skal du vælge den igen eller vælge en af de andre visualiseringer. 

## <a name="complete-the-sales-analysis-report"></a>Færdiggør salgsanalyserapporten

I den færdige rapport kombineres data fra Excel-filen Products.xlsx og Northwind OData-feedet i visualiseringer, der hjælper med at analysere ordreoplysningerne for de forskellige lande, tidsrammer og produkter. Når din rapport er færdig, kan du [uploade den til Power BI-tjenesten](desktop-upload-desktop-files.md) og dele den med andre Power BI-brugere.

## <a name="next-steps"></a>Næste trin
* [Læs andre selvstudier til Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Se videoer om Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Besøg Power BI-forummet](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Læs Power BI-bloggen](http://go.microsoft.com/fwlink/?LinkID=519327)