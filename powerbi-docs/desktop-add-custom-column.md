---
title: Tilføj en brugerdefineret kolonne i Power BI Desktop
description: Opret hurtigt en ny brugerdefineret kolonne i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 884723ed65e5379d0d3b79828fe22000b9b0283b
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287180"
---
# <a name="add-a-custom-column-in-power-bi-desktop"></a>Tilføj en brugerdefineret kolonne i Power BI Desktop
Du kan nemt føje en ny brugerdefineret kolonne med data til din model ved hjælp af **forespørgselseditoren** i **Power BI Desktop**. Du kan oprette og omdøbe din brugerdefinerede kolonne ved hjælp af knapper til oprettelse af [M-formler](https://msdn.microsoft.com/library/mt270235.aspx), der definerer din brugerdefinerede kolonne. M-formlen har et [indholdssæt med omfattende funktionsreference](https://msdn.microsoft.com/library/mt779182.aspx). 

![](media/desktop-add-custom-column/add-custom-column_01.png)

Du kan også oprette en brugerdefineret kolonne som et andet **anvendt trin** i forbindelse med den forespørgsel, du opretter i **forespørgselseditoren**, hvilken betyder, at den kan ændres, flyttes før eller senere eller redigeres når som helt.

## <a name="use-query-editor-to-add-a-new-custom-column"></a>Brug forespørgselseditoren til at tilføje en ny brugerdefineret kolonne
Hvis du vil oprette en ny brugerdefineret forespørgsel, skal du starte **forespørgselseditoren**. Det kan du også gøre ved at vælge **Rediger forespørgsler** på båndet **Hjem** i **Power BI Desktop**.

![](media/desktop-add-custom-column/add-column-from-example_02.png)

Når **forespørgselseditoren** er startet, og der er indlæst nogle data, kan du tilføje en brugerdefineret kolonne ved at vælge fanen **Tilføj kolonne** på båndet og derefter vælge **Brugerdefineret kolonne**.

![](media/desktop-add-custom-column/add-custom-column_02.png)

Vinduet **Tilføj brugerdefineret kolonne** vises. Vinduet beskrives i det følgende afsnit.

## <a name="the-add-custom-column-window"></a>Vinduet Tilføj brugerdefineret kolonne
I vinduet **Tilføj brugerdefineret kolonne** kan du se en liste over tilgængelige felter i ruden til højre, navnet på din brugerdefinerede kolonne øverst (du kan omdøbe den ved ganske enkelt at skrive et nyt navn i dette tekstfelt) og den [**M**-formel](https://msdn.microsoft.com/library/mt779182.aspx), du opretter (eller skriver), afhængigt af hvilke felter du indsætter fra højre, hvilke operatorer du tilføjer, og hvordan du ellers bygger den formel, som din nye brugerdefinerede kolonne defineres ud fra. 

![](media/desktop-add-custom-column/add-custom-column_03.png)

## <a name="create-formulas-for-your-custom-column"></a>Opret formler til din brugerdefinerede kolonne
Du kan vælge et felt på listen **Tilgængelige kolonner:** til højre og vælge **<< Indsæt** for at føje dem til formlen for den brugerdefinerede kolonne. Du kan også bare dobbeltklikke på en kolonne på listen for at tilføje den.

Efterhånden som du skriver formlen og bygger din kolonne, kan du nederst i vinduet se en indikator, der fortæller dig i realtid (mens du skriver), om der er registreret syntaksfejl. Hvis alt er, som det skal være, kan du se et grøn markering.

![](media/desktop-add-custom-column/add-custom-column_04.png)

Hvis der er fejl i syntaksen, vises der i stedet et gult advarselsikon sammen med den registrerede fejl og et link, som placerer markøren (i formlen) der, hvor fejlen er registreret.

![](media/desktop-add-custom-column/add-custom-column_05.png)

Når du vælger **OK**, føjes din brugerdefinerede kolonne til modellen, og trinnet **Tilføjet brugerdefineret** føjes til **Anvendte trin** for din forespørgsel.

![](media/desktop-add-custom-column/add-custom-column_06.png)

Hvis du dobbeltklikker på trinnet **Tilføjet brugerdefineret** i ruden **Anvendte trin**, åbnes vinduet **Tilføj brugerdefineret kolonne** igen, og den brugerdefinerede kolonneformel, du allerede har oprettet, er indlæst, så du evt. kan redigere den.

## <a name="using-the-advanced-editor-for-custom-columns"></a>Brug de brugerdefinerede kolonner for den avancerede editor
Du kan også oprette en brugerdefineret kolonne (og for den sags skyld også redigere alle trin i din forespørgsel) ved hjælp af den **avancerede editor**. I **forespørgselseditoren** skal du vælge fanen **Vis** og derefter vælge **Avanceret editor** for at vise den **avancerede editor**.

![](media/desktop-add-custom-column/add-custom-column_07.png)

Den **avancerede editor** giver dig fuld kontrol over din forespørgsel.

## <a name="next-steps"></a>Næste trin
Du kan også oprette en brugerdefineret kolonne på andre måder, f.eks. ved at oprette en kolonne, der er baseret på eksempler, du angiver i **forespørgselseditoren**. I følgende artikel kan du få flere oplysninger om, hvordan du opretter brugerdefinerede kolonner ud fra eksempler:

* [Tilføj en kolonne ud fra et eksempel i Power BI Desktop](desktop-add-column-from-example.md)
* [Introduktion til M-formelsprog](https://msdn.microsoft.com/library/mt270235.aspx)
* [M-funktionsreference](https://msdn.microsoft.com/library/mt779182.aspx)  

