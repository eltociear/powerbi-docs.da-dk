---
title: "Selvstudium: Importér og analysér data fra en webside ved hjælp af Power BI Desktop"
description: "Selvstudium: Importér og analysér data fra en webside ved hjælp af Power BI Desktop"
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
ms.openlocfilehash: c5139c6f9f7b2098b51a608fb7719f371173c291
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
---
# <a name="analyzing-web-page-data-using-power-bi-desktop-tutorial"></a>Analyse af data på en webside ved hjælp af Power BI Desktop (selvstudium)
I dette selvstudium får du mere at vide om, hvordan du importerer en tabel med data fra en webside og opretter en rapport for at visualisere disse data. Som en del af denne proces skal du navigere på tværs af tabeller, der er tilgængelige på en webside, og anvende data transformationstrin til at give tabellen en ny form.

 I denne artikel:

* **Opgave 1:** Opret forbindelse til en webdatakilde
* **Opgave 2:** Form data i forespørgselsvisningen
  * Trin 1: Fjern andre kolonner for kun at få vist de kolonner, du skal bruge
  * Trin 2: Erstat værdier for at rydde værdier i en markeret kolonne
  * Trin 3: Filtrér værdier i en kolonne
  * Trin 4: Omdøb en kolonne
  * Trin 5: Filtrér null-værdier i en kolonne
  * Trin 6: Omdøb en forespørgsel
  * Oprettede forespørgselstrin
* **Opgave 3:** Opret visualiseringer ved hjælp af rapportvisningen
  * Trin 1: Indlæs forespørgslen i rapporten
  * Trin 2: Opret en kortvisualisering

## <a name="task-1-connect-to-a-web-data-source"></a>Opgave 1: Opret forbindelse til en webdatakilde
 I opgave 1 kan du importere en tabel med turneringsoversigt fra UEFA's Wikipedia-side med europæiske fodboldsmesterskaber på følgende adresse: http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

### <a name="add-a-wikipedia-page-data-source"></a>Tilføj en Wikipedia-side som datakilde
1. Vælg **Hent data** i dialogboksen **Introduktion** eller under fanen **Hjem** på båndet.
2. Dette åbner dialogboksen **Hent Data**, hvor du kan vælge mellem en lang række datakilder for at importere data til Power BI Desktop. Vi vil vælge **Web**, som findes under gruppen **Alle** eller **Andre**.
3. I dialogboksen **Webindhold** skal du i tekstfeltet **URL-adresse** indsætte URL-adressen til Wikipedia (http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship).
4. Klik på **OK**.

Når du har oprettet forbindelse til websiden, får du vist en liste over tabeller, der er tilgængelige på denne Wikipedia-side, i dialogboksen **Navigator**. Du kan klikke én gang på hver af tabellerne for at få vist et eksempel på dataene.

I **Navigator**-ruden til venstre skal du vælge tabellen **Results[edit]** (Resultater[rediger]) til resultaterne af turneringsoversigten eller vælge tabellen **Results[edit]** (Resultater[rediger]) og vælge  **Edit** (Rediger). Det giver os mulighed for at omforme denne tabel, før den indlæses i rapporten, eftersom dataene ikke er i den form, vi skal bruge til vores analyse.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

Det genererer en eksempelvisning af tabellen i forespørgselsvisning, hvor vi kan anvende et sæt transformationstrin til at rydde ud i dataene.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="task-2-shape-data-in-the-subject-table"></a>Opgave 2: Form data i emnetabellen
Nu, hvor du har valgt emnetabel til din dataforespørgsel, kan du se, hvordan du udfører forskellige trin til udformning og rensning af data.

**Trin 1:** Fjern andre kolonner for kun at få vist de kolonner, du skal bruge

I dette trin skal du fjerne alle kolonner undtagen **Year** (År) og **Final Winners** (Endelige vindere).

1. I gitteret **Query Preview** (Forhåndsvisning af forespørgsel) skal du markere kolonnerne **Year** (År) og **Final Winners** (Endelige vindere) (brug **CTRL** + **klik**).
2. Højreklik på en kolonneoverskrift i gitteret **Query Preview** (Forhåndsvisning af forespørgsel), og klik på **Fjern andre kolonner** for at fjerne ikke-markerede kolonner. Bemærk, at denne funktion også kan vælges i gruppen **Administrer kolonner** under fanen **Hjem** på båndet.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

**Trin 2:** Erstat værdier for at rydde værdier i en markeret kolonne

I dette trin erstatter du suffikset Detaljer i kolonnen **Year** (År). Bemærk, at dette suffiks er på en ny linje, så det ikke er synligt i eksempelvisningen af tabellen. Men hvis du klikker på en af cellerne med en numerisk værdi i kolonnen Year (År), får du vist hele værdien i den detaljerede visning.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage5.png)

1. Vælg kolonnen **Year** (År).
2. På båndet **Forespørgselsvisning** skal du klikke på **Erstat værdier** under fanen **Hjem** eller højreklikke på kolonnen **Year** (År) og klikke på **Erstat værdier** for at erstatte Detaljer med tom tekst.
3. I dialogboksen **Erstat værdier** skal du indtaste detaljer i tekstfeltet **Værdi, der skal søges efter** og undlade at udfylde tekstfeltet **Replace With** (Erstat med).
4. Klik på **OK**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

 **Trin 3:** Filtrér værdier i en kolonne

I dette trin kan du filtrere kolonnen **Year** (År) for at få vist rækker, der ikke indeholder "Year".

1. Klik på rullelistepilen til filtrering i kolonnen **Year** (År).
2. I rullelisten **Filtrér** skal du fjerne markeringen af indstillingen **Year** (År).
3. Klik på **OK**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**Trin 4:** Omdøb en kolonne

Nu, hvor vi har ryddet dataene i kolonnen **Year** (År), skal vi arbejde med kolonnen **Final Winner** (Endelig vinder).

Da vi kun ser på listen over vindere, kan vi omdøbe denne kolonne til **Land**.

1. Markér kolonnen **Final Winner**  (Endelig vinder) i eksempelvisningen af forespørgslen.
2. På båndet med **forespørgselsvisning** under fanen **Transform** (Transformér) og gruppen **Any Column** (Vilkårlig kolonne) finder du **Rename** (Omdøb).
3. Det gør det muligt at redigere kolonnenavnet. Vi omdøber denne kolonne til **Land**.

**Trin 5:** Filtrér null-værdier i en kolonne væk

Du skal også filtrere null-værdier i kolonnen **Land** væk. Til at gøre dette kan vi bruge filtermenuen som beskrevet i trin 3, eller også kan vi:

1. Højreklikke på en af cellerne i den **Land**-kolonne, der indeholder en null-værdi.
2. Vælge **Tekstfiltre -\> Forskellig fra** i genvejsmenuen.
3. Dette opretter et nyt filtertrin til at fjerne rækker med null-værdier i kolonnen **Land**.

**Trin 6:** Navngiv en forespørgsel

I dette trin navngiver du den endelige forespørgsel **Vindere af Euro Cup**.

1. Skriv **Vindere af Euro Cup** i tekstfeltet **Navn** i ruden **Forespørgselsindstillinger**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

## <a name="task-3-create-visualizations-using-the-report-view"></a>Opgave 3: Opret visualiseringer ved hjælp af rapportvisningen
Nu, hvor dataene er konverteret til de former, vi skal bruge i analysen, kan vi indlæse den færdige tabel i vores rapport og oprette nogle få visualiseringer.

**Trin 1**: Indlæs forespørgslen i rapporten

For at kunne indlæse forespørgselsresultaterne til Power BI Desktop og oprette en rapport skal vi vælge **Luk og indlæs** fra båndet **Hjem**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Dette vil udløse evaluering af forespørgslen og indlæsning af tabeloutputtet til rapporten. I Power BI Desktop skal du vælge ikonet **Rapport** for at få vist Power BI Desktop i rapportvisning.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage10.png)

Du kan se de tabelfelter, der er resultatet, i ruden **Felter** til højre for **rapportvisningen**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

**Trin 2:** Opret en kortvisualisering

Når du vil oprette en visualisering, kan du trække felter fra listen **Felter** og placere dem på dit **rapportcanvas**.

1. Træk i feltet **Land**, og placer det på dit **rapportcanvas**. Dette opretter en ny visualisering på dit **rapportcanvas**. I dette tilfælde, og da vi har en liste over lande, oprettes der en **kortvisualisering**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage12.png)
2. Det er nemt at ændre typen af visualisering ved at klikke på et andet ikon i ruden **Visualisering**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage13.png)
3. Vi holder os til visualiseringstypen **Kort**. Vi kan også ændre størrelsen på visualiseringen ved at trække i et af hjørnerne i visualiseringen, til vi får den ønskede størrelse.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
4. Bemærk, at i øjeblikket har alle punkterne i kortet den samme størrelse. Vi vil ændre dette, så lande med flere vundne Euro Cup-turneringer repræsenteres af et større punkt på kortet. For at kunne gøre dette kan vi trække feltet **År** på listen **Felter** til feltet **Værdier** i nederste halvdel af ruden **Felter**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

Som du kan se, er det særdeles nemt at tilpasse visualiseringer i din rapport for at præsentere dataene på den måde, du vil. Med Power BI Desktop er det nemt at hente data fra en lang række forskellige datakilder og forme dem til dine behov for at kunne fremvise analyser visuelt og interaktivt. Når din rapport er færdig, kan du [uploade den til Power BI](desktop-upload-desktop-files.md) og oprette dashboards ud fra den, som du derefter kan dele med andre Power BI-brugere.

Dette afslutter selvstudiet **Import af data fra internettet**. Du kan downloade en færdig Power BI Desktop-fil [her](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Data_From_The_Web.pbix).

## <a name="where-else-can-i-get-more-information"></a>Hvor kan jeg finde flere oplysninger?
* [Læs andre selvstudier til Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Se videoer om Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Besøg Power BI-forummet](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Læs Power BI-bloggen](http://go.microsoft.com/fwlink/?LinkID=519327)

