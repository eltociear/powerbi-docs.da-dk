---
title: "Importér Excel-projektmapper til Power BI Desktop"
description: "Importér Excel-projektmapper til Power BI Desktop"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 5daed750b6e9b80c04f568c39b4e0931c01bbc05
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="import-excel-workbooks-into-power-bi-desktop"></a>Importér Excel-projektmapper til Power BI Desktop
Med **Power BI Desktop** kan du nemt importere Excel-projektmapper, der indeholder forespørgsler fra Power-forespørgsel, Power Pivot-modeller og regneark fra Power-visning, til Power BI Desktop. Rapporter og visualiseringer oprettes automatisk på basis af Excel-projektmappen, og når de er importeret, kan du fortsætte med at forbedre og tilpasse rapporterne i Power BI Desktop ved hjælp af de eksisterende funktioner og nye funktioner, der udgives sammen de månedlige opdateringer af Power BI Desktop.

Fremover planlægger vi at udvide kommunikationen mellem Excel og Power BI Desktop (f.eks. import/eksport). Den aktuelle mulighed for at importere projektmapper til Power BI Desktop gør det muligt for eksisterende Excel-brugere at komme i gang med Power BI Desktop.

## <a name="how-do-i-import-an-excel-workbook"></a>Hvordan importerer jeg en Excel-projektmappe?
Hvis du vil importere en projektmappe, skal du gå til Power BI Desktop og vælge **Filer -\> Importér -\> Indhold i Excel-projektmappe**.

![](media/desktop-import-excel-workbooks/importexceltopbi_1.png)

Der vises et vindue, hvor du kan vælge den projektmappe, der skal importeres. Der er i øjeblikket ingen begrænsninger på størrelsen eller antallet af objekter i projektmappen, men det tager længere tid for Power BI Desktop at analysere og importere større projektmapper.

> [!NOTE]
> Hvis du vil indlæse eller importere Excel-filer fra **delte OneDrive for Business**-mapper eller fra **Office 365-gruppe**-mapper, skal du bruge URL-adressen til Excel-filen og angive den i datakilden **Web** i Power BI Desktop. Der er et par trin, du skal udføre for at formatere URL-adressen til **OneDrive for Business** korrekt, så gå til [Brug OneDrive for Business-links i Power BI Desktop](desktop-use-onedrive-business-links.md) for at få flere oplysninger og de korrekte trin.
> 
> 

Når en projektmappe er markeret, analyseres projektmappen i Power BI Desktop, og den konverteres til en Power BI Desktop-fil (.pbix). Bemærk, at dette kun skal udføres én gang. Når Power BI Desktop-filen er oprettet med disse trin, har Power BI Desktop-filen ingen afhængigheder til den oprindelige Excel-projektmappe og kan redigeres eller ændres (og gemmes og deles), uden at det påvirker den oprindelige projektmappe.

![](media/desktop-import-excel-workbooks/importexceltopbi_2.png)

Når importen er fuldført, vises der en **oversigtsside**, som beskriver de elementer, der er konverteret, og en liste over elementer, der ikke kunne importeres.

![](media/desktop-import-excel-workbooks/importexceltopbi_3.png)

Når du vælger **Luk**, indlæses rapporten i Power BI Desktop. På følgende billede vises Power BI Desktop, efter at der er importeret en Excel-projektmappe: Power BI Desktop har automatisk indlæst rapporten baseret på indholdet af projektmappen.

![](media/desktop-import-excel-workbooks/importexceltopbi_4.png)

Nu, hvor projektmappen er importeret, kan du fortsætte med at arbejde med rapporten – f.eks oprette nye visualiseringer, tilføje data eller oprette nye rapportsider – ved hjælp af de funktioner og egenskaber, der er inkluderet i Power BI Desktop.

## <a name="which-workbook-elements-are-imported"></a>Hvilke elementer i projektmappen importeres?
Power BI Desktop kan importere følgende elementer, der kaldes også *objekter*, i Excel.

| Objekt i Excel-projektmappe | Endeligt resultat i Power BI Desktop-fil |
| --- | --- |
| Forespørgsler i Power-forespørgsel |Alle forespørgsler i Power-forespørgsel fra Excel konverteres til forespørgsler i Power BI Desktop. Hvis der var defineret forespørgselsgrupper i Excel-projektmappen, replikeres samme organisering i Power BI Desktop. Alle forespørgsler indlæses, medmindre de er indstillet til "Opret kun forbindelse" i Excel. Funktionsmåden Indlæs kan tilpasses i dialogboksen **Egenskaber** under fanen **Hjem** i **forespørgselseditoren** i Power BI Desktop. |
| Eksterne dataforbindelser i Power Pivot |Alle eksterne dataforbindelser i Power Pivot konverteres til forespørgsler i Power BI Desktop. |
| Sammenkædede tabeller eller aktuelle projektmappetabeller |Hvis der er en regnearkstabel i Excel, der er knyttet til datamodellen eller knyttet til en forespørgsel (ved hjælp af *tabellen From* eller funktionen *Excel.CurrentWorkbook()* i M), vises følgende indstillinger     1. Importér tabellen til Power BI Desktop-filen. Dette er et engangsøjebliksbillede af data, og herefter kan du ikke redigere dataene i tabellen i Power BI Desktop. Der er en størrelsesbegrænsning på 1 million tegn (i alt, med alle kolonneoverskrifter og celler) for tabeller, der er oprettet ved hjælp af denne indstilling.    2. Bevar forbindelsen til den oprindelige projektmappe. Du kan også bevare forbindelsen til den oprindelige Excel-projektmappe, så henter Power BI Desktop det seneste indhold i denne tabel, hver gang den opdateres, på samme måde som enhver anden forespørgsel, der oprettes i forhold til en Excel-projektmappe i Power BI Desktop. |
| Beregnede kolonner, målinger, datakategorier og datarelationer for datamodeller |Disse objekter for datamodeller konverteres til de tilsvarende objekter i Power BI Desktop. Bemærk, at der er visse datakategorier, som ikke er tilgængelige i Power BI Desktop endnu, f.eks. **Billede**. I disse tilfælde nulstilles oplysningerne om datakategorien for de pågældende kolonner. |
| Regneark i Power-visning |Der oprettes en ny rapportside for alle regneark i Power-visning i Excel. Navnet på og rækkefølgen af disse rapportsider stemmer overens med den oprindelige Excel-projektmappe. |

## <a name="are-there-any-limitations-to-importing-a-workbook"></a>Er der ingen begrænsninger for import af en projektmappe?
Der er et par begrænsninger for import af en projektmappe i Power BI Desktop, og de er følgende:

1. **Eksterne forbindelser til Analysis Services-tabelmodeller:** I Excel 2013 er det muligt at oprette forbindelse til SQL Server Analysis Services-tabelmodeller og oprette rapporter i Power-visning ud fra disse modeller uden at skulle importere dataene. Denne type forbindelse understøttes i øjeblikket ikke i forbindelse med import af Excel-projektmapper til Power BI Desktop, men vil være tilgængelig i en kommende opdatering. I mellemtiden skal du genskabe disse eksterne forbindelser i Power BI Desktop.
2. **KPI'er:** Denne type datamodelobjekt understøttes i øjeblikket ikke i Power BI Desktop. Derfor springes KPI'er over i forbindelse med import af en Excel-projektmappe til Power BI Desktop.
3. **Hierarkier:** Denne type datamodelobjekt understøttes i øjeblikket ikke i Power BI Desktop. Derfor springes hierarkier over i forbindelse med import af en Excel-projektmappe til Power BI Desktop.
4. **Binære datakolonner:** Denne type datamodelkolonne understøttes i øjeblikket ikke i Power BI Desktop. Binære datakolonner fjernes fra den tabel, der oprettes i Power BI Desktop.
5. **Ikke-understøttede elementer i Power-visning:** Der er nogle funktioner i Power-visning, der ikke er tilgængelige i Power BI Desktop endnu, f.eks. temaer eller visse typer af visualiseringer (punktdiagram med afspilningsakse, funktionsmåder for detailudledning osv.). Disse ikke-understøttede visualiseringer medfører meddelelser om *ikke-understøttet visualisering* på deres tilsvarende placeringer i Power BI Desktop-rapporten, som du kan slette eller omkonfigurere efter behov.
6. **Navngivne områder, der bruger**  ***tabellen From*** **i Power-forespørgsel, eller som bruger**  ***Excel.CurrentWorkbook*** **i M:** Import af disse navngivne områdedata i Power BI Desktop understøttes i øjeblikket ikke, men er planlagt som en opdatering til Power BI Desktop. Disse navngivne områder indlæses i øjeblikket i Power BI Desktop som en forbindelse til den eksterne Excel-projektmappe.
7. **PowerPivot til SSRS:** Eksterne PowerPivot-forbindelser til SSRS (SQL Server Reporting Services) understøttes ikke i øjeblikket, da datakilden i øjeblikket ikke er tilgængelig i Power BI Desktop.

