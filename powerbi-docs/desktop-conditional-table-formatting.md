---
title: Betinget formatering af tabeller i Power BI Desktop
description: Anvend brugerdefineret formatering på tabeller
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
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1626c2af5906004b6b4f79f4830f003b96e241fc
ms.sourcegitcommit: 509be8852ba7595b9441c9479224f9dca298b26d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/09/2018
---
# <a name="conditional-formatting-in-tables"></a>Betinget formatering af tabeller
Med betinget formatering af tabeller kan du angive brugerdefinerede baggrundsfarver for celler baseret på celleværdier eller baseret på andre værdier eller felter, og du kan bruge gradueringsfarver. Du får adgang til betinget formatering på følgende måde: I brønden **Felter** i ruden **Visualiseringer** i Power BI Desktop skal du vælge pil ned ved siden af værdien i brønden **Værdier**, som du vil formatere (eller du skal højreklikke på feltet). Du kan kun administrere betinget formatering for felter i området **Værdier** under **Felter**.

![betinget tabelformatering](media/desktop-conditional-table-formatting/table-formatting_1.png)

Du kan konfigurere farven og *Minimum*- og *Maksimum*-værdierne i den dialogboks, der vises. Hvis du vælger feltet **Divergerende**, kan du også konfigurere en valgfri værdi af typen *Centreret*.

![divergerende farver](media/desktop-conditional-table-formatting/table-formatting_2.png)

Du kan også basere farvegradueringen på et felt fra din datamodel. Du kan desuden angive sammenlægningstypen for det markerede felt (det valgte felt er angivet i feltet **Anvend farve på**, så du kan følge med).

![grundlæggende farver fra et felt](media/desktop-conditional-table-formatting/table-formatting_2b.png)

Ved anvendelse i en tabel tilsidesætter den brugerdefinerede formatering, som anvendes ved hjælp af de trin, der er beskrevet ovenfor, alle brugerdefinerede tabeltypografier, som anvendes på de formaterede celler.

![tabelformatering](media/desktop-conditional-table-formatting/table-formatting_3.png)

Du kan også anvende betinget formatering på tekst- og datofelter, hvis du har valgt en numerisk værdi som udgangspunkt for formateringen. 

Hvis du vil fjerne betinget formatering fra en visualisering, skal du blot højreklikke på feltet igen og vælge **Fjern betinget formatering**.

![fjerne tabelformatering](media/desktop-conditional-table-formatting/table-formatting_4.png)

