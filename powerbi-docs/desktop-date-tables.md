---
title: Angiv og brug datotabeller i Power BI Desktop
description: "Lær, hvordan du angiver en tabel som en datotabel, og hvad det betyder, i Power BI Desktop"
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
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: f95553de53729a939990e18514bc88600c2572fd
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/09/2018
---
# <a name="set-and-use-date-tables-in-power-bi-desktop"></a>Angiv og brug datotabeller i Power BI Desktop

**Power BI Desktop** arbejder i baggrunden for automatisk at identificere tabeller som **datotabeller** og opretter derefter datohierarkier og andre aktiveringsmetadata til din model for dig. Du kan bruge disse indbyggede hierarkier, når du opretter rapportfunktioner såsom visualiseringer, tabeller, hurtigmålinger, udsnitsværktøjer osv. Power BI Desktop gør dette ved at oprette skjulte tabeller for dig, som du derefter kan bruge til dine rapporter og DAX-udtryk.

Mange dataanalytikere foretrækker at oprette deres egne datotabeller, hvilket er fint. I **Power BI Desktop** kan du angive, hvilken tabel din model skal bruge som sin **datotabel**, og derefter oprette datorelaterede visualiseringer, tabeller, hurtigmålinger osv. ved hjælp af denne tabels data for datoer. Når du angiver din egen datotabel, styrer du de datohierarkier, der oprettes i modellen, og du kan bruge dem i **hurtigmålinger** og andre handlinger, der gør brug af modellens datotabel. 

![](media/desktop-date-tables/date-tables_01.png)

## <a name="setting-your-own-date-table"></a>Angivelse af din egen datotabel

Du angiver en **datotabel** ved at markere den tabel, du vil bruge som en datotabel i ruden **Felter**. Højreklik derefter på tabellen, og vælg **Markér som datotabel > Markér som datotabel** i den viste menu, som vist på følgende billede.

![](media/desktop-date-tables/date-tables_02.png)

Du kan også markere tabellen og derefter vælge **Markér som datotabel** på båndet **Udformning**, som vist her.

![](media/desktop-date-tables/date-tables_02b.png)

Når du angiver din egen **datotabel**, udfører Power BI Desktop følgende validering af kolonnen og de tilhørende data for at sikre følgende for dataene:

* at de indeholder entydige værdier,
* at de ikke indeholder null-værdier,
* at de indeholder sammenhængende datoværdier (fra start til slut),
* og hvis det er datotypen **Dato/tid**, at der er det samme tidsstempel for hver værdi.

Der er to mulige scenarier ifm. at oprette din egen datotabel, og begge tilgange er lige gode:

* I det første scenarie bruger du en vedtaget eller grundlæggende datotabel med tilsvarende hierarki. Dette er en tabel i dine data, der opfylder de tidligere beskrevne valideringskriterier for en datotabel. 

* I det andet scenarie bruger du f.eks. en tabel fra Analysis Services med et felt af typen *datodimension* som din datotabel. 

Når du har angivet en datotabel, kan du vælge, hvilken kolonne i denne tabel der er datokolonnen. Du kan angive, hvilken kolonne der skal bruges, ved at markere tabellen i ruden **Felter** og derefter højreklikke på tabellen og vælge **Markér som datotabel > Indstillinger for datatabel**. Følgende vindue vises, hvor du på rullelisten kan vælge, hvilken kolonne der skal bruges som datotabel.

![](media/desktop-date-tables/date-tables_03.png)

Vær opmærksom på, at når du angiver din egen datotabel, så opretter **Power BI Desktop** ikke automatisk de hierarkier, som ellers ville blive indbygget i modellen, for dig. Hvis du senere fravælger din datotabel (og ikke længere har en manuelt angivet datotabel), genskaber Power BI Desktop de indbyggede tabeller, der automatisk blev oprettet, for dig for datokolonnerne i tabellen.

Vær også opmærksom på, at når du markerer en tabel som en datotabel, fjernes den indbyggede datotabel (automatisk oprettet), som Power BI Desktop oprettede, og alle visualiseringer eller DAX-udtryk, du tidligere har oprettet på baggrund af disse indbyggede tabeller, fungerer ikke længere korrekt. 

## <a name="marking-your-date-table-as-the-appropriate-data-type"></a>Markering af din tabel som den korrekte datatype

Når du angiver din egen **datotabel**, skal du sikre, at datatypen er angivet korrekt. Du skal angive **Datatype** som **Dato/tid** eller **Dato**. Du kan benytte følgende fremgangsmåde:

1. Markér **datotabellen** i ruden **Felter**; du kan udvide den, hvis det er nødvendigt. Vælg derefter den kolonne, som skal bruges som dato.
   
    ![](media/desktop-date-tables/date-tables_04.png) 

2. På fanen **Udformning** skal du vælge **Datatype:** og derefter klikke på rullepilen for at få vist tilgængelige datatyper.

    ![](media/desktop-date-tables/date-tables_05.png)

3. Angiv datatypen for kolonnen. 


## <a name="next-steps"></a>Næste trin

Du vil måske også være interesseret i følgende artikler.

* [Datatyper i Power BI Desktop](desktop-data-types.md)

 