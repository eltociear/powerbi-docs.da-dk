---
title: "Selvstudium: Analysér salgsdata fra Excel og et OData-feed i Power BI Desktop"
description: "Selvstudium: Analysér salgsdata fra Excel og et OData-feed"
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 4cab3ed114d03d42c6acf1bf62f70e7d920e16b2
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/27/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Selvstudium: Analysér salgsdata fra Excel og et OData-feed
Med **Power BI Desktop** kan du oprette forbindelse til alle mulige forskellige typer datakilder og derefter kombinere og forme dem på måder, der gør det muligt at skabe interessante og overbevisende dataanalyser og visualiseringer. I dette selvstudium kan du se, hvordan du kombinerer data fra to datakilder. 

Det er almindeligt at have data, der er spredt på forskellige datakilder, for eksempel produktoplysninger i én database og salgsoplysninger i en anden. De teknikker, du lærer i dette dokument, omfatter en Excel-projektmappe og et OData-feed, men du kan bruge de samme teknikker med andre typer datakilder som SQL Server-forespørgsler, CSV-filer eller andre datakilder i Power BI Desktop.

I dette selvstudium kan du importere data fra Excel (produktoplysninger) og fra et OData-feed (ordredata). Du skal udføre trinnene med transformation og sammenlægning og kombinere data fra begge kilder for at generere en rapport over **samlet salg pr. produkt og år**, som indeholder interaktive visualiseringer. 

Sådan ser den færdige rapport ud:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Hvis du vil følge trinnene i dette selvstudium, skal du bruge projektmappen Products, som du kan downloade: **[Klik her for at downloade Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**

I dialogboksen **Save As** kan du kalde filen for **Products.xlsx**.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>Opgave 1: Hent produktdata fra en Excel-projektmappe
I denne opgave importerer du produkter fra filen Products.xlsx til Power BI Desktop.

### <a name="step-1-connect-to-an-excel-workbook"></a>Trin 1: Opret forbindelse til en Excel-projektmappe
1. Start Power BI Desktop.
2. Vælg **Hent data** under fanen Hjem. Excel vises under **Mest almindelige** dataforbindelser, så du kan vælge det direkte i menuen **Hent data**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. Hvis du vælger knappen Hent data direkte, kan du også vælge **Filer \> Excel** og vælge **Opret forbindelse**.
4. Vælg filen **Products.xlsx** i dialogboksen **Åbn fil**.
5. I ruden **Navigator** skal du vælge tabellen **Products** og derefter vælge **Rediger**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>Trin 2: Fjern andre kolonner for kun at vise de kolonner, du skal bruge
I dette trin fjerner du alle andre kolonner end **ProductID**, **ProductName**, **UnitsInStock** og **QuantityPerUnit**. I Power BI Desktop er der som regel flere måder, du kan udføre den samme opgave på. Kommandoerne for mange af de knapper, der vises på båndet, kan du for eksempel også bruge ved at højreklikke på en kolonne eller en celle.

Power BI Desktop indeholder Forespørgselseditor, som er det sted, hvor du kan forme og transformere dine dataforbindelser. Forespørgselseditor åbnes automatisk, når du vælger **Rediger** fra **Navigator**. Du kan også åbne Forespørgselseditor ved at vælge **Rediger forespørgsler** på båndet **Hjem** i Power BI Desktop. Du skal udføre disse trin i Forespørgselseditor.

1. Markér kolonnerne **ProductID**, **ProductName**, **QuantityPerUnit** og **UnitsInStock** (brug **Ctrl+klik** for at markere mere end én kolonne, eller brug **Skift+klik** for at markere kolonner, der er ved siden af hinanden).
2. Vælg **Fjern kolonner** \> **Fjern andre kolonner** på båndet, eller højreklik på en kolonneoverskrift, og klik på **Fjern andre kolonner**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>Trin 3: Vælg en anden datatype for kolonnen UnitsInStock
Når Forespørgselseditor opretter forbindelse til data, vil det gennemse hvert felt for at bestemme den bedste datatype. Til Excel-projektmappen vil antal varer på lager være et heltal, så på dette trin skal du bekræfte, at datatypen for kolonnen **UnitsInStock** er Heltal.

1. Markér kolonnen **UnitsInStock**.
2. Vælg knappen til rullemenuen **Datatype** på båndet **Hjem**.
3. Hvis der ikke allerede er valgt Heltal, skal du vælge **Heltal** som datatype på rullemenuen (knappen **Datatype:** viser også datatypen for den aktuelle markering).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Power BI Desktop-trin er oprettet
Når du udfører forespørgselsaktiviteter i Forespørgselseditor, bliver forespørgselstrinnene oprettet og vises på listen **Anvendte trin** i ruden **Forespørgselsindstillinger**. Hver forespørgselstrin har en tilsvarende formel, der også kaldes "M"-sproget. Du kan finde flere oplysninger om "M"-formelsproget under [Få mere at vide om Power BI-formler](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Opgave | Forespørgselstrin | Formel |
| --- | --- | --- |
| Opret forbindelse til en Excel-projektmappe |Kilde |Source{[Name="Products"]}[Data] |
| Hæv første række i tabellen til kolonneoverskrifter |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Products) |
| Fjern andre kolonner for kun at vise de kolonner, du skal bruge |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Skift datatype |Ændret type |Table.TransformColumnTypes(\#"Fjernede andre kolonner",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>Opgave 2: Importér ordredata fra et OData-feed
I denne opgave skal du hente ordredataene. Dette trin repræsenterer, at der oprettes forbindelse til et salgssystem. Du kan importere data til Power BI Desktop fra OData-eksempelfeedet Northwind på følgende URL-adresse, som du kan kopiere (og derefter indsætte) i trinnene herunder: <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>Trin 1: Opret forbindelse til et OData-feed
1. Gå til båndet **Hjem** i Forespørgselseditor, og vælg **Hent data**.
2. Vælg datakilden **OData-feed**.
3. Indsæt URL-adressen til OData-feedet for Northwind i feltet **URL-adresse** i dialogboksen **OData-feed**.
4. Vælg **OK**.
5. I **Navigator** skal du vælge tabellen **Orders** og derefter vælge **OK**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Du kan klikke på et tabelnavn uden at markere afkrydsningsfeltet, hvis du vil have vist et eksempel.

### <a name="step-2-expand-the-orderdetails-table"></a>Trin 2: Udvid tabellen Order\_Details
Tabellen **Orders** indeholder en reference til tabellen **Details**, som indeholder de enkelte produkter i hver ordre. Når du opretter forbindelse til datakilder med flere tabeller (for eksempel en relationel database), kan du bruge disse referencer til at bygge din forespørgsel. 

På dette trin skal du udvide tabellen **Order\_Details**, som er relateret til tabellen **Orders**, for at kombinere kolonnerne **ProductID**, **UnitPrice** og **Quantity** fra **Order\_Details** til tabellen **Orders**. Dette er en repræsentation af dataene i disse tabeller:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

Handlingen **Udvid** kombinerer kolonner fra en relateret tabel til en emnetabel. Når forespørgslen køres, bliver rækker fra den relaterede tabel (**Order\_Details**) kombineret til rækker fra emnetabellen (**Orders**).

Når du har udvidet tabellen **Order\_Details**, tilføjes der tre nye kolonner og ekstra rækker i tabellen **Orders**: en for hver række i den indlejrede eller relaterede tabel.

1. Rul til kolonnen **Order\_Details** i **Forespørgselsvisning**.
2. Vælg udvidelsesikonet (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) i kolonnen **Order\_Details**.
3. På rullemenuen **Udvid**:
   1. Vælg **(Markér alle kolonner)** for at rydde alle kolonner.
   2. Vælg **ProductID**, **UnitPrice** og **Quantity**.
   3. Klik på **OK**.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>Trin 3: Fjern andre kolonner for kun at vise de kolonner, du skal bruge
På dette trin skal du fjerne alle kolonner med undtagelse af kolonnerne **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** og **Order\_Details.Quantity**. I den forrige opgave brugte du **Fjern andre kolonner**. I denne opgave skal du fjerne de markerede kolonner.

1. I **Forespørgselsvisning** skal du markere alle kolonner ved at udføre a. og b.:
   1. Klik på den første kolonne (**OrderID**).
   2. Skift+klik på den sidste kolonne (**Shipper**).
   3. Nu, hvor alle kolonnerne er markeret, skal du bruge Ctrl+klik til at fjerne markeringen af følgende kolonner: **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** og **Order\_Details.Quantity**.
2. Nu, hvor du kun har markeret de kolonner, der skal fjernes, skal du højreklikke på en af de markerede kolonneoverskrifter og klikke på **Fjern kolonner**.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>Trin 4: Beregn linjetotalen for hver Order\_Details-række
I Power BI Desktop kan du oprette beregninger baseret på de kolonner, du importerer, så du kan få endnu mere ud af de data, du opretter forbindelse til. På dette trin skal oprette en **brugerdefineret kolonne**, hvor du skal beregne linjetotalen for hver **Order\_Details**-række.

Beregn linjetotalen for hver **Order\_Details**-række:

1. I den **Add Column** båndet fane, skal du klikke på **Tilføj** **brugerdefineret kolonne**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. I dialogboksen **Brugerdefineret kolonne** skal du skrive **[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]** i tekstfeltet **Formel for brugerdefineret kolonne**.
3. Skriv **LineTotal** i tekstfeltet **Nyt kolonnenavn**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. Klik på **OK**.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>Trin 5: Angiv datatypen for feltet LineTotal
1. Højreklik på kolonnen **LineTotal**.
2. Vælg **Rediger type**, og vælg **Decimaltal**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>Trin 6: Omdøb og ret rækkefølgen af kolonner i forespørgslen
På dette trin skal du afslutte arbejdet med at gøre modellen nem at arbejde med, når du opretter rapporter. Det gør du ved at omdøbe de færdige kolonner og ændre rækkefølgen af dem.

1. I **Forespørgselseditor** skal du trække kolonnen **LineTotal** mod venstre til lige efter **ShipCountry**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. Fjern præfikset *Order\_Details.* fra kolonnerne **Order\_Details.ProductID**, **Order\_Details.UnitPrice** og **Order\_Details.Quantity** ved at dobbeltklikke på hver kolonneoverskrift og slette den del af teksten fra kolonnenavnet.

### <a name="power-bi-desktop-steps-created"></a>Power BI Desktop-trin er oprettet
Når du udfører forespørgselsaktiviteter i Forespørgselseditor, bliver forespørgselstrinnene oprettet og vises på listen **Anvendte trin** i ruden **Forespørgselsindstillinger**. Hver forespørgselstrin har en tilsvarende Power-forespørgselsformel, der også kaldes "M"-sproget. Du kan finde flere oplysninger om dette formelsprog under [Få mere at vide om Power BI-formler](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Få mere at vide om Power Query-formler").

| Opgave | Forespørgselstrin | Formel |
| --- | --- | --- |
| Opret forbindelse til et OData-feed |Kilde |Source{[Name="Orders"]}[Data] |
| Udvid tabellen Order\_Details |Udvidet Order\_Details |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Fjern andre kolonner for kun at vise de kolonner, du skal bruge |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Udvid Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Beregn linjetotalen for hver Order\_Details-række |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Opgave 3: Kombiner forespørgslerne Products og Total Sales
I Power BI Desktop er det ikke et krav, at du kombinerer forespørgsler for at oprette rapporter ud fra dem. Du kan i stedet oprette **relationer** mellem datasæt. Disse relationer kan oprettes for enhver kolonne, som er fælles i dine datasæt. Det kan du finde flere oplysninger om under [Opret og administrer relationer](desktop-create-and-manage-relationships.md).

I dette selvstudium har vi ordredata og produktdata, som begge indeholder feltet 'ProductID', og vi skal derfor sikre, at der er en relation mellem dem i den model, vi bruger med Power BI Desktop. I Power BI Desktop skal du blot angive, at kolonnerne fra hver tabel er relateret (dvs., at kolonnerne indeholder de samme værdier). Power BI Desktop finder selv ud af relationens retning og kardinalitet for dig. I nogle tilfælde vil det også selv finde relationer automatisk.

I denne opgave skal du kontrollere, om der er oprettet en relation mellem forespørgslerne **Products** og **Total Sales** i Power BI Desktop.

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>Trin 1: Bekræft relationen mellem Products og Total Sales
1. Først skal vi indlæse den model, vi oprettede i Forespørgselseditor, i Power BI Desktop. Gå til båndet **Hjem** i Forespørgselseditor, og vælg **Luk og anvend**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop indlæser dataene fra de to forespørgsler.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. Når dataene er indlæst, skal du vælge knappen **Administrer relationer** på båndet **Hjem**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. Vælg knappen **Ny**. knappen
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. Når vi forsøger at oprette en relation, kan vi se, at der allerede findes en. Som du kan se i dialogboksen **Opret relation**, er der oprettet en relation mellem felterne **ProductsID** i hver forespørgsel.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Vælg **Annuller**, og vælg derefter visningen **Relationer** i Power BI Desktop.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Der vises følgende, som visualiserer relationen mellem forespørgslerne.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Hvis du dobbeltklikker på den pil, der forbinder de to forespørgsler, vises dialogboksen **Rediger relation**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. Det er ikke nødvendigt med nogen ændringer, så vælg **Annuller** for at lukke dialogboksen **Rediger relation**.

## <a name="task-4-build-visuals-using-your-data"></a>Opgave 4: Vis dine data visuelt
I Power BI Desktop kan du oprette en lang række visualiseringer, som kan give dig bedre indsigt i dine data. Du kan oprette rapporter på flere sider, og hver side kan indeholder flere visualiseringer. Du kan arbejde med visualiseringerne for at analysere og forstå dine data. Du kan finde flere oplysninger om redigering af rapporter under [Rediger en rapport](service-interact-with-a-report-in-editing-view.md).

I denne opgave skal du oprette en rapport baseret på de tidligere indlæste data. Du kan bruge ruden Felter til at vælge de kolonner, du vil oprette visualiseringerne ud fra.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>Trin 1: Opret diagrammer, der viser antal varer på lager efter produkt og samlet salg pr. år
Træk **UnitsInStock** fra ruden Felter (ruden Felter vises i højre side af skærmen) til et tomt område på lærredet. Der oprettes en tabelvisualisering. Derefter skal du trække ProductName til feltet Akse, som du finder i den nederste halvdel af ruden Visualisering. Derefter kan vi vælge **Sortér efter \> UnitsInStock** øverst til højre i visualiseringen.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

Træk **OrderDate** til lærredet under det første diagram, og træk LineTotal (igen fra ruden Felter) til visualiseringen, og vælg derefter Kurvediagram. Der oprettes følgende visualiseringer.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 Træk derefter **ShipCountry** til en plads øverst til højre på lærredet. Da du har valgt et geografisk felt, oprettes der automatisk et kort. Træk **LineTotal** til feltet **Værdier**. Cirklerne på kortet for hvert land er nu relative i størrelsen i forhold til **LineTotal** for de ordrer, der er sendt til det land.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>Trin 2: Arbejd med visualiseringerne i rapporten for at analysere yderligere
I Power BI Desktop kan du arbejde med visualiseringerne, som viser fremhævninger og filtreres på tværs af hinanden for at vise yderligere tendenser. Du kan læse mere under [Filtrering og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md)

1. Klik på den blå cirkel, der er centreret i **Canada.** Bemærk, hvordan de øvrige visualiseringer filtreres for at vise Stock (**ShipCountry**) og Total Orders (**LineTotal**) kun for Canada.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Færdiggør salgsanalyserapporten
Når du har udført alle disse trin, har du en salgsrapport, der kombinerer data fra filen Products.xlsx og OData-feedet for Northwind. Rapporten indeholder visualiseringer, du kan bruge til at analysere salgsoplysningerne for forskellige lande. Du kan downloade en færdig Power BI Desktop-fil til dette selvstudium [her](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix).

## <a name="next-steps"></a>Næste trin
* [Læs andre selvstudier til Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Se videoer om Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Besøg Power BI-forummet](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Læs Power BI-bloggen](http://go.microsoft.com/fwlink/?LinkID=519327)


