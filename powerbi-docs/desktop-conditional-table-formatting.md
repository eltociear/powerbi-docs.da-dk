---
title: Betinget formatering af tabeller i Power BI Desktop
description: Anvend brugerdefineret formatering på tabeller
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 70aa61d6a02bea1b7058a68b20718008ace1b8c8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34480882"
---
# <a name="conditional-formatting-in-tables"></a>Betinget formatering af tabeller 
Med betinget formatering af tabeller kan du angive brugerdefinerede farver for celler baseret på celleværdier eller baseret på andre værdier eller felter, og du kan bruge gradueringsfarver. Du kan også få vist celleværdier med datalinjer. 

Du får adgang til betinget formatering på følgende måde: I brønden **Felter** i ruden **Visualiseringer** i Power BI Desktop skal du vælge pil ned ved siden af værdien i brønden **Værdier**, som du vil formatere (eller du skal højreklikke på feltet). Du kan kun administrere betinget formatering for felter i området **Værdier** under **Felter**.

![Menuen Betinget formatering](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

I de følgende afsnit beskrives hver af disse tre indstillinger for betinget formatering. En eller flere indstillinger kan kombineres i en enkelt tabelkolonne.

> [!NOTE]
> Når betinget formatering anvendes på en tabel, tilsidesættes alle brugerdefinerede tabelformater, som er anvendt i celler med betinget formatering.

Hvis du vil fjerne betinget formatering fra en visualisering, skal du blot højreklikke på feltet igen, vælge **Fjern betinget formatering** og derefter vælge den type formatering, du vil fjerne.

![Menuen Fjern betinget formatering](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>Baggrundsfarveskalaer

Hvis du vælger **Betinget formatering** og derefter **Baggrundsfarveskalaer** vises følgende dialogboks.

![Dialogboksen Baggrundsfarveskalaer](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

Du kan vælge et felt fra din datamodel, som farverne skal baseres på, ved at angive **Farve baseret på** for dette felt. Desuden kan du angive sammenlægningstypen for det markerede felt med værdien **Opsummering**. Det felt, der skal farves, er angivet i feltet **Anvend farve på**. Du kan anvende betinget formatering på tekst- og datofelter, hvis du har valgt en numerisk værdi som udgangspunkt for formateringen.

![Farve baseret på felt](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

Hvis du vil bruge specifikke farveværdier for de givne værdiområder, skal du vælge **Farve efter regler**. Du kan bruge et farvespektrum ved at fjerne markeringen i **Farve efter regler**. 

![Dialogboksen Baggrundsfarveskalaer](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>Farve efter regler

Når du vælger **Farve efter regler**, kan du angive et eller flere værdiområder, som har hver deres eget farvesæt.  Hvert værdiområde starter med en *Hvis værdi*-betingelse, en *og*-betingelse og en farve.

![Værdiinterval for Farve efter regler](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

Tabelceller med værdier i hvert område udfyldes med den angivne farve. Der er tre regler i følgende illustration.

![Eksempel med Farve efter regler](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

Eksempeltabellen ser nu ud som følger:

![Eksempeltabel med Farve efter regler](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>Farve for minimum- og maksimumværdi

Du kan konfigurere værdierne *Minimum* og *Maksimum* og deres farver. Hvis du vælger feltet **Divergerende**, kan du også konfigurere en valgfri værdi af typen *Centreret*.

![Knappen Divergerende](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Eksempeltabellen ser nu ud som følger:

![Eksempeltabel med divergerende farver](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>Skriftfarveskalaer

Hvis du vælger **Betinget formatering** og derefter **Skriftfarveskalaer** vises følgende dialogboks. Denne dialogboks ligner dialogboksen **Baggrundsfarveskalaer**, men den ændrer skriftfarven i stedet for cellens baggrundsfarve.

![Dialogboksen Skriftfarveskalaer](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

Eksempeltabellen ser nu ud som følger:

![Eksempeltabel med skriftfarveskalaer](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>Datalinjer

Hvis du vælger **Betinget formatering** og derefter **Datalinjer**, vises følgende dialogboks. 

![Dialogboksen Datalinjer](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

Som standard er indstillingen **Vis kun linje** ikke markeret, så der vises både linje og faktisk værdi i tabelcellen.

![Eksempeltabel med datalinjer og værdier](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

Hvis indstillingen **Vis kun linje** er markeret, er det kun linjen, der vises i tabelcellen.

![Eksempeltabel kun med datalinjer](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)
