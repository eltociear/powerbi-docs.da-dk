---
title: Datakategorisering i Power BI Desktop
description: Datakategorisering i Power BI Desktop
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
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: f5eb26eee9bedbdd804dfba1912a1aa328310816
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2018
---
# <a name="data-categorization-in-power-bi-desktop"></a>Datakategorisering i Power BI Desktop
I **Power BI Desktop** kan du angive datakategorien for en kolonne, så Power BI Desktop ved, hvordan dens værdier skal behandles i en visualisering.

Når der importeres data i Power BI Desktop, henter du ikke kun selve dataene, du henter også oplysninger som f.eks. tabel- og kolonnenavne, om det er en primær nøgle osv.  Med disse oplysninger angiver Power BI Desktop nogle forudsætninger for, hvordan du får en god standardoplevelse, når du opretter en visualisering. 

Her er et eksempel: Når der i Power BI Desktop registreres en kolonne, der indeholder numeriske værdier, vil du muligvis samle dem på en måde. Derfor placeres den i området Værdier. Det kan også være, at det forudsættes for en kolonne med dato- og klokkeslætsværdier, at du muligvis vil bruge den som en hierarkiakse for tid i et kurvediagram.

Men der er nogle tilfælde, der er lidt mere udfordrende, f.eks. geografi. Se nærmere på følgende tabel fra et Excel-regneark:

![](media/desktop-data-categorization/datacategorizationtable.png)

Skal Power BI Desktop behandle koderne i kolonnen GeoCode som en forkortelse for et land eller en stat i USA?  Det er ikke klart, da en kode som denne kan betyde begge dele.  AL kan f.eks. betyde Alabama eller Albanien, AR kan betyde Arkansas eller Argentina og CA kan betyde Californien eller Canada. Det gør en forskel, når vi vil oprette et GeoCode-felt på et kort.  Skal Power BI Desktop vise et billede over verden, hvor lande er fremhævet, eller skal det i stedet være et billede over USA, hvor stater er fremhævet?  Du kan angive en datakategori for data som disse. Datakategorisering finjusterer oplysningerne, som kan bruges i Power BI Desktop, så du kan få de bedste visualiseringer.  

**Sådan angiver du en datakategori**

1. I Rapportvisning eller Datavisning på listen **Felter** skal du vælge det felt, der skal sorteres efter en anden kategorisering.
2. På fanen **Modellering** på båndet skal du klikke på rullelisten **Datakategori:**.  Dermed får du vist listen over mulige datakategorier, du kan vælge imellem til kolonnen.  Nogle valgmuligheder kan være deaktiveret, hvis de ikke fungerer med den aktuelle datatype for kolonnen.  Hvis en kolonne f.eks. er en binær datatype, kan du ikke vælge geografiske datakategorier i Power BI Desktop. 

![](media/desktop-data-categorization/datacategorization.gif)

Det var det hele!  Alle funktionsmåder, der normalt opsummeres for en visualisering, fungerer nu automatisk.  

Du vil måske også være interesseret i at få mere at vide om [geografisk filtrering af Power BI-mobilapps](desktop-mobile-geofiltering.md).

