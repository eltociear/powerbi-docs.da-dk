---
title: Modelvisning i Power BI Desktop
description: Modelvisning i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/17/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 1c580d403ef33f1c61d5fcd0707d78b4b331da5d
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85239862"
---
# <a name="work-with-model-view-in-power-bi-desktop"></a>Arbejde med modelvisning i Power BI Desktop

I *Modelvisning* vises alle tabellerne, kolonnerne og relationerne i din model. Denne visning kan være særligt nyttig, når din model indeholder komplekse relationer mellem mange tabeller.

Vælg ikonet **Model** i siden af vinduet for at få vist en visning af den eksisterende model. Hold markøren over en relationslinje for at få vist de kolonner, der bruges.

![Modelvisning, Power BI Desktop](media/desktop-relationship-view/model-view-full-screen.png)

I figuren har tabellen *Stores* en *StoreKey*-kolonne, der er relateret til tabellen *Salg*, som også har en *StoreKey*-kolonne. De to tabeller har en relation af typen *mange til én* (\*: 1). En pil midt på linjen viser retningen af kontekstflowet for filteret. De dobbelte pile betyder, at den tværgående filterretning er angivet til *Begge*.

Du kan dobbeltklikke på en relation for at åbne den i dialogboksen **Rediger relationer**. Du kan finde flere oplysninger om relationer under [Opret og administrer relationer i Power BI Desktop](desktop-create-and-manage-relationships.md).
