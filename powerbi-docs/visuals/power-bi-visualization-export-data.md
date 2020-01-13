---
title: Eksportér data fra en Power BI-visualisering
description: Eksportér data fra en rapportvisualisering og en dashboardvisualisering, og få dem vist i Excel.
author: mihart
manager: kvivek
ms.reviewer: tessa
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/13/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 5c2f448ff705f00bc443a6a27fa80e1b5164a901
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2020
ms.locfileid: "75757801"
---
# <a name="export-the-data-that-was-used-to-create-a-visualization"></a>Eksportér de data, der blev brugt til at oprette en visualisering

Hvis du gerne vil have vist de data, der bruges til at oprette en visualisering, [kan du få vist de pågældende data i Power BI](service-reports-show-data.md). Du kan også eksportere disse data til Excel som en *.xlsx*- eller *.csv*-fil. Indstillingen for eksport af data kræver en Pro- eller Premium-licens og redigeringstilladelser til datasættet og rapporten. <!--If you have access to the dashboard or report but the data is classified as *highly confidential*, Power BI will not allow you to export the data.-->

Se med, når Will eksporterer dataene fra en af visualiseringerne i hans rapport, gemmer dem som en *.xlsx*-fil og åbner dem i Excel. Følg derefter den trinvise vejledning under videoen for at prøve det selv.

<iframe width="560" height="315" src="https://www.youtube.com/embed/KjheMTGjDXw" frameborder="0" allowfullscreen></iframe>

## <a name="export-data-from-a-power-bi-dashboard"></a>Eksportér data fra et Power BI-dashboard

1. Vælg ellipsen i øverste højre hjørne af visualiseringen.

    ![Skærmbillede af en visualisering med en pil, der peger på ellipseknappen.](media/power-bi-visualization-export-data/pbi-export-tile3.png)

1. Vælg ikonet **Eksportér data**.

    ![Skærmbillede af ellipsens rulleliste, hvor indstillingen Eksportér data vises.](media/power-bi-visualization-export-data/pbi_export_dash.png)

1. Power BI eksporterer dataene til en *.csv*-fil. Hvis du har filtreret visualiseringen, filtrerer appen de downloadede data.

1. Via browseren bliver du bedt om at gemme filen.  Når du har gemt *.csv-filen*, kan du åbne den i Excel.

    ![Skærmbillede af .csv-filen, hvor de eksporterede data vises.](media/power-bi-visualization-export-data/pbi-export-to-excel.png)

## <a name="export-data-from-a-report"></a>Eksportér data fra en rapport

Hvis du vil følge med, skal du åbne [eksempelrapporten med en indkøbsanalyse](../sample-procurement.md) i redigeringsvisning. Tilføj en ny tom rapportside. Følg derefter nedenstående trin for at tilføje en aggregering og et filter på visualiseringsniveau.

1. Opret et nyt **stablet søjlediagram**.

1. I ruden **Felter** skal du vælge **Placering > By** og **Faktura > Rabatprocent**.  Du skal muligvis flytte **Rabatprocent** til området **Værdi**.

    ![Skærmbillede af den visualisering, der oprettes, hvor By og Antal rabatprocenter vises.](media/power-bi-visualization-export-data/power-bi-export-data3.png)

1. Skift aggregering for **Rabatprocent** fra **Antal** til **Gennemsnit**. I området **Værdi** skal du vælge pilen til højre for **Rabatprocent** (der kan f.eks. stå **Antal rabatprocenter**) og vælge **Gennemsnit**.

    ![Skærmbillede af sammenlægningslisten, hvor indstillingen Gennemsnit vises.](media/power-bi-visualization-export-data/power-bi-export-data6.png)

1. Føj et filter til **By**, vælg alle byer, og fjern derefter **Atlanta**.

    ![Skærmbillede af filteret By, hvor afkrydsningsfeltet Atlanta, GA, der er ryddet, fremhæves.](media/power-bi-visualization-export-data/power-bi-export-data4.png)

   Vi er nu klar til at prøve begge muligheder for eksport af data.

1. Vælg ellipsen i øverste højre hjørne af visualiseringen. Vælg **Eksportér data**.

    ![Skærmbillede af øverste højre hjørne, hvor ellipseknappen og indstillingen Eksportér data vises.](media/power-bi-visualization-export-data/power-bi-export-data2.png)

    I Power BI online, hvis visualiseringen har en aggregering (f.eks. hvis du har ændret **Antal** til *gennemsnit*, *sum* eller *minimum*), har du to valgmuligheder:

    - **Opsummerede data**

    - **Underliggende data**

    I Power BI Desktop har du kun indstillingen **Opsummerede data**. Hvis du vil have hjælp til at forstå sammenlægninger, kan du se under [Aggregater i Power BI](../service-aggregates.md).

1. Fra **Eksportér data** skal du vælge **Opsummerede data**, enten vælge *.xlsx* eller *.csv* og derefter vælge **Eksportér**. Dataene eksporteres i Power BI.

    ![Skærmbillede af Eksportér data, hvor indstillingerne Opsummerede data, xlsx og Eksportér vises.](media/power-bi-visualization-export-data/power-bi-export-data5.png)

    Hvis du har anvendt filtre på visualiseringen, vil de eksporterede data være filtreret. Når du vælger **Eksportér**, bliver du i browseren bedt om at gemme filen. Når du har gemt den, skal du åbne filen i Excel.
    
    Alle de data, der bruges af hierarkiet, eksporteres, og ikke blot de data, der bruges til det aktuelle detaljeniveau for visualiseringen. Hvis visualiseringen f.eks. endnu ikke er blevet analyseret ned fra det øverste niveau, vil de eksporterede data indeholde alle dataene i hierarkiet, og ikke kun de data, der bruges til at oprette visualiseringen på det aktuelt analyserede niveau.

    **Opsummerede data**: Vælg denne indstilling, hvis du vil eksportere dataene til det, du ser i visualiseringen.  Denne type eksport viser kun de data, (kolonner og målinger), du vælger for at oprette visualiseringen.  Hvis visualiseringen har en aggregering, skal du eksportere aggregerede data. Hvis du f.eks. har et søjlediagram med fire søjler, vises der fire rækker med data. Opsummerede data er tilgængelige som *.xlsx* og *.csv*.

    I dette eksempel vises én total for hver by i Excel-eksporten. Da vi har filtreret Atlanta fra, er denne by ikke inkluderet i resultaterne. I den første række i regnearket vises de filtre, der blev brugt under udtrækningen af data.

    ![Skærmbillede af .csv-filen, hvor de eksporterede data vises.](media/power-bi-visualization-export-data/power-bi-export-data7.png)

1. Nu skal du prøve at vælge **Underliggende data**, *.xlsx* og derefter **Eksportér**. Dataene eksporteres i Power BI. 

    > [!NOTE]
    > Afhængigt af rapportindstillinger har du mulighed for at eksportere de underliggende data.

    Hvis du har anvendt filtre på visualiseringen, vil de eksporterede data være filtreret. Når du vælger **Eksportér**, bliver du i browseren bedt om at gemme filen. Når du har gemt den, skal du åbne filen i Excel.
    
    Alle de data, der bruges af hierarkiet, eksporteres, og ikke blot de data, der bruges til det aktuelle detaljeniveau for visualiseringen. Hvis visualiseringen f.eks. endnu ikke er blevet analyseret ned fra det øverste niveau, vil de eksporterede data indeholde alle dataene i hierarkiet, og ikke kun de data, der bruges til at oprette visualiseringen på det aktuelt analyserede niveau.

    >[!WARNING]
    >Eksport af underliggende data giver brugerne mulighed at se alle de detaljerede data – for alle kolonner i dataene. Administratorer af Power BI-tjenesten kan slå denne funktion fra for deres organisation. Hvis du ejer datasættet, kan du angive, at beskyttede kolonner skal være **skjult**, så de ikke vises på listen **Felter** i Desktop- eller Power BI-tjenesten.

    **Underliggende data**: Vælg denne indstilling, hvis du vil se dataene i visualiseringen ***og*** yderligere data fra modellen (se mere i diagrammet nedenfor). Hvis visualiseringen har en aggregering, fjernes det, hvis du vælger *Underliggende data*. Når du vælger **Eksportér**, eksporterer Power BI dataene til en *.xlsx*-fil, og i browseren bliver du bedt om at gemme filen. Når du har gemt den, skal du åbne filen i Excel.

    I dette eksempel vises der kun én række for hver enkelt By-række i Excel-eksporten samt rabatprocenten for den pågældende post. I Power BI fladgøres dataene. De aggregeres ikke. I den første række i regnearket vises de filtre, der blev brugt under udtrækningen af data.  

    ![Skærmbillede af .csv-filen, hvor de eksporterede data vises.](media/power-bi-visualization-export-data/power-bi-export-data8.png)

## <a name="export-underlying-data-details"></a>Eksporter oplysninger om underliggende data

Det kan variere, hvad du ser, når du vælger **Underliggende data**. Du skal eventuelt have hjælp af administratoren eller it-afdelingen for at forstå disse oplysninger. I Power BI Desktop eller -tjenesten vises en *måling* på listen **Felter** med et lommeregnerikon, der ![viser ikonet](media/power-bi-visualization-export-data/power-bi-calculator-icon.png), i rapportvisning. I Power BI Desktop oprettes der målinger. Det gør der ikke i Power BI-tjenesten.

| Visualiseringen indeholder | Hvad eksporten viser  |
|---------------- | ---------------------------|
| Aggregeringer | den *første* aggregering og ikke-skjulte data fra hele tabellen for denne aggregering |
| Aggregeringer | relaterede data – hvis der i visualiseringen bruges data fra andre datatabeller, som er *relaterede* til den datatabel, der indeholder aggregeringen (så længe relationen er \*:1 eller 1:1) |
| Målinger | alle målinger i visualiseringen *og* alle målinger fra en hvilken som helst datatabel med en måling, der bruges i visualiseringen |
| Målinger | alle ikke-skjulte data fra tabeller, der indeholder målingen (så længe relationen er \*:1 eller 1:1) |
| Målinger | alle data fra alle tabeller, der er relateret til tabel(ler) med målingerne via en kæde af \*:1 af 1:1) |
| Kun målinger | alle ikke-skjulte kolonner fra alle relaterede tabeller (for at udvide målingen) |
| Kun målinger | opsummerede data for duplikerede rækker for modelmålinger |

### <a name="set-the-export-options"></a>Angiv eksportindstillingerne

Designere af Power BI-rapporter styrer, hvilke typer eksportindstillinger af data der er tilgængelige for deres forbrugere. Valgmulighederne er:

- Tillad, at slutbrugere eksporterer opsummerede data fra Power BI-tjenesten eller Power BI-rapportserveren

- Tillad, at slutbrugere eksporterer både akkumulerede og underliggende data fra tjenesten eller rapportserveren

- Tillad ikke, at slutbrugere eksporterer data fra tjenesten eller rapportserveren

    > [!IMPORTANT]
    > Vi anbefaler, at rapportdesignere går tilbage til tidligere rapporter og manuelt nulstiller eksportindstillingen efter behov.

Sådan angiver du disse indstillinger:

1. Start i Power BI Desktop.

1. I øverste venstre hjørne skal du vælge **Filer** > **Indstillinger** > **Indstillinger**.

1. Under **AKTUEL FIL** skal du vælge **Rapportindstillinger**.

    ![rapportindstillinger for desktop](media/power-bi-visualization-export-data/desktop-report-settings.png)

1. Vælg din indstilling i sektionen **Eksportér data**.

Du kan også opdatere denne indstilling i Power BI-tjenesten.

Vigtigt! Hvis der er konflikt mellem indstillingerne på Power BI-administratorportalen og rapportindstillingerne for eksport af data, overskriver administratorindstillingerne indstillingerne for eksport af data.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Disse begrænsninger og overvejelser gælder for Power BI Desktop og Power BI-tjenesten, herunder Power BI Pro og Premium.

- Hvis du vil eksportere dataene fra en visualisering, skal du have [tilladelse til at oprette for det underliggende datasæt](https://docs.microsoft.com/power-bi/service-datasets-build-permissions).

-  Det maksimale antal rækker, som **Power BI Desktop** og **Power BI-tjenesten** kan eksportere fra en **rapport for importtilstand** til en *.csv-fil* er 30.000.

- Det maksimale antal rækker, som programmerne kan eksportere fra en **rapport for importtilstand** til en *.xlsx-fil* er 150.000.

- Eksport ved hjælp af *underliggende data* fungerer ikke, hvis:

  - Versionen er ældre end 2016.

  - Tabellerne i modellen ikke har en entydig nøgle.
    
  -  En administrator eller rapportdesigner har deaktiveret denne funktion.

- Eksport ved hjælp af *underliggende data* fungerer ikke, hvis du aktiverer indstillingen *Vis elementer uden data* for den visualisering, som Power BI eksporterer.

- Når du bruger DirectQuery, kan Power BI maks. eksportere 16 MB dekomprimerede data. Det kan være et utilsigtet resultat, hvis du eksporterer mindre end det maksimale antal rækker. Dette er sandsynligt, hvis:

    - Der er mange kolonner.

    - Der er data, som er vanskelige at komprimere.

    - Der er andre faktorer, som medfører, at filstørrelsen øges, og antallet af rækker, som Power BI kan eksportere, reduceres.

- Hvis visualiseringen bruger data fra mere end én datatabel, og der ikke findes nogen relation for disse tabeller i datamodellen, eksporterer Power BI kun data for den første tabel.

- Brugerdefinerede visualiseringer og R-visualiseringer understøttes ikke i øjeblikket.

- I Power BI kan du omdøbe et felt (en kolonne) ved at dobbeltklikke på feltet og skrive et nyt navn. Power BI henviser til det nye navn som et *alias*. Det er muligt at have dublerede feltnavne i en Power BI-rapport, men det understøttes ikke i Excel. Hvis Power BI eksporterer dataene til Excel, gendannes feltaliasserne derfor til de oprindelige feltnavne (kolonnenavne).  

- Hvis der er Unicode-tegn i *.csv*-filen, vises teksten muligvis ikke korrekt i Excel. Valutasymboler og fremmedord er eksempler på Unicode-tegn. Du kan åbne filen i Notesblok, hvor Unicode vises korrekt. Hvis du vil åbne filen i Excel, er løsningen at importere *.csv*-filen. Sådan importerer du filen til Excel:

  1. Åbn Excel.

  1. Gå til fanen **Data**.
  
  1. Vælg **Hent eksterne data** > **Fra tekst**.
  
  1. Gå til den lokale mappe, hvor filen er gemt, og vælg *.csv*-filen.

- Power BI-administratorer kan deaktivere dataeksporten.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
