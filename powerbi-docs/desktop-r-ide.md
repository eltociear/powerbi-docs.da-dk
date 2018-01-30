---
title: Brug et eksternt R IDE med Power BI
description: Du kan starte og bruge et eksternt IDE med Power BI
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
ms.openlocfilehash: bbc0b90c36272c5a30865d92d78039c20f667ee9
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/17/2017
---
# <a name="use-an-external-r-ide-with-power-bi"></a>Brug et eksternt R IDE med Power BI
Med **Power BI Desktop** kan du bruge dit eksterne R IDE (integreret udviklingsmiljø) til at oprette og afgrænse R scripts og derefter bruge disse scripts i Power BI.

![](media/desktop-r-ide/r-ide_1a.png)

## <a name="enable-an-external-r-ide"></a>Aktivér et eksternt R IDE
Tidligere var du nødt til at bruge editoren til R-script i **Power BI Desktop** til at oprette og køre R scripts. Med denne version kan du starte din eksterne R-IDE fra **Power BI Desktop** og automatisk få dine data importeret og vist i R-IDE. Herfra kan du ændre scriptet i den eksterne R-IDE, og du kan sætte dem tilbage i **Power BI Desktop** for at oprette visuelle Power BI-elementer og -rapporter.

Fra og med september 2016-versionen af **Power BI Desktop** (version 2.39.4526.362), kan du angive, hvilken R-IDE, du vil bruge, og få den til at starte automatisk fra **Power BI Desktop**.

### <a name="requirements"></a>Krav
Hvis du vil bruge denne funktion, skal du installere en **R-IDE** på din lokale computer. **Power BI Desktop** indeholder, implementerer eller installerer ikke R-komponenten, så du skal installere **R** separat på din lokale computer. Du kan vælge, hvilken R-IDE du vil bruge, med følgende indstillinger:

* Du kan installere din foretrukne R-IDE, hvoraf mange er gratis, som f.eks. [overførselssiden Revolution Open](https://mran.revolutionanalytics.com/download/), og [CRAN-lageret](https://cran.r-project.org/bin/windows/base/).
* **Power BI Desktop** understøtter også [R Studio](https://www.rstudio.com/) og **Visual Studio 2015** med [ *R-værktøjer til Visual Studio*](https://beta.visualstudio.com/vs/rtvs/)-editorer.
* Du kan også installere en anden R-IDE og få **Power BI Desktop** til at starte denne **R-IDE** ved at gøre en af følgende ting:
  
  * Du kan knytte **. R**-filer til den eksterne IDE, som du ønsker **Power BI Desktop** skal starte.
  * Du kan angive den .exe, **Power BI Desktop** skal starte, ved at vælge *Andre* fra sektionen **Indstillinger for R-script** i dialogboksen **Indstillinger**. Du kan få vist dialogboksen **Indstillinger** ved at gå til **Fil > Indstillinger > Indstillinger**.
    
    ![](media/desktop-r-ide/r-ide_1b.png)

Hvis du har installeret flere R-IDE'er, kan du angive, hvilken, der skal startes, ved at vælge den på rullelisten *Fundne R-IDE'er* i dialogboksen **Indstillinger**.

Som standard starter **Power BI Desktop** **R Studio** som den eksterne R-IDE, hvis den er installeret på din lokale computer. Hvis **R Studio** ikke er installeret, og du har **Visual Studio 2015** med **R-værktøjer til Visual Studio**, startes dette i stedet. Hvis ingen af disse R-IDE'er er installeret, startes det program, som er knyttet til **. R**-filer.

Og hvis der ikke findes nogen **.R**-fil-tilknytning, er det muligt at angive en sti til en brugerdefineret IDE i sektionen *Søg efter din foretrukne R-IDE* i dialogboksen **Indstillinger**. Du kan også starte en anden R-IDE ved at vælge udstyrsikonet **Indstillinger** ud for pileikonet **Start R-IDE** i **Power BI Desktop**.

## <a name="launch-an-r-ide-from-power-bi-desktop"></a>Start en R-IDE fra Power BI Desktop
Benyt følgende fremgangsmåde for at starte en R-IDE fra **Power BI Desktop**.

1. Indlæs data i **Power BI Desktop**.
2. Vælg nogle felter fra ruden **Felter**, som du vil arbejde med. Hvis du endnu ikke har aktiveret visuelle script-elementer, bliver du bedt om at gøre dette.
   
   ![](media/desktop-r-ide/r-ide_3.png)
3. Når visuelle script-elementer er aktiveret, kan du vælge et visuelt R-element fra ruden **Visualiseringer**, som opretter et tomt visuelt R-element, der er klart til at vise resultaterne af scriptet. Ruden **R-scripteditor** vises også.
   
   ![](media/desktop-r-ide/r-ide_4.png)
4. Nu kan du vælge de felter, som du ønsker at bruge i R-scriptet. Når du vælger et felt, opretter feltet **R-scripteditor** automatisk script-kode, der er baseret på det eller de felter, du vælger. Du kan enten oprette (eller indsætte) R-scriptet direkte i ruden **R-Scripteditor** eller lade feltet være tomt.
   
   ![](media/desktop-r-ide/r-ide_5.png)
   
   > [!NOTE]
   > Standardsammenlægningstypen for visuelle R-elementer er *Opsummer ikke*.
   > 
   > 
5. Du kan nu starte din R-IDE direkte fra **Power BI Desktop**. Vælg knappen **Start R-IDE**, der findes til højre for titellinjen **R-scripteditor**, som vist nedenfor.
   
   ![](media/desktop-r-ide/r-ide_6.png)
6. Den angivne R-IDE startes af Power BI Desktop, som det vises på følgende billede (på dette billede er **RStudio** standard-R-IDE).
   
   ![](media/desktop-r-ide/r-ide_7.png)
   
   > [!NOTE]
   > **Power BI Desktop** tilføjer de første tre linjer af scriptet, således at den kan importere dine data **Power BI Desktop**, når du kører scriptet.
   > 
   > 
7. De scripts, som du har oprettet i **R-scripteditor-ruden** på **Power BI Desktop**, vises med start på linje 4 i din R-IDE. Herefter kan du oprette R-scriptet i R-IDE'en. Når R-scriptet er fuldført i din R-IDE, skal du kopiere det og sætte det tilbage i **R-scripteditor**-ruden i **Power BI Desktop** og *udelade* de første tre linjer i det script, som **Power BI Desktop** automatisk genererede. Kopier ikke de første tre linjer af scriptet tilbage til **Power BI Desktop**. Disse linjer blev kun brugt til at importere dine data til din R-IDE fra **Power BI Desktop**.

### <a name="known-limitations"></a>Kendte begrænsninger
Start af en R-IDE direkte fra Power BI Desktop har nogle få begrænsninger:

* Automatisk eksport af dit script fra din R-IDE til **Power BI Desktop** understøttes ikke.
* **R-klient**-editoren (RGui.exe) understøttes ikke, fordi selve editoren ikke understøtter åbning af filer.

## <a name="next-steps"></a>De næste trin
Du kan finde yderligere oplysninger om R i Power BI i følgende artikler.

* [Kørsel af R-scripts i Power BI Desktop](desktop-r-scripts.md)
* [Opret visuelle Power BI-elementer ved hjælp af R](desktop-r-visuals.md)
