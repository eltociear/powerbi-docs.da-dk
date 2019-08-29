---
title: 'DAX: DIVIDE-funktion vs. divisionsoperator (/)'
description: Vejledning til, hvornår du skal bruge DAX DIVIDE-funktionen.
author: guyinacube
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/05/2019
ms.author: v-pemyer
ms.openlocfilehash: d22491ee314ebcebd4479c4e57dbfdf7a6a1ffdb
ms.sourcegitcommit: c2197c3ad1d747b4ad490ab75771a0d32d0ae208
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/23/2019
ms.locfileid: "70010431"
---
# <a name="dax-divide-function-vs-divide-operator-"></a>DAX: DIVIDE-funktion vs. divisionsoperator (/)

Denne artikel er beregnet til datamodeldesignere, der definerer DAX-udtryk.

## <a name="background"></a>Baggrund

Når du skriver et DAX-udtryk for at opdele en tæller med en nævner, kan du vælge at bruge funktionen [DIVIDE](/dax/divide-function-dax) eller divisionsoperatoren (/-skråstreg).

Når du bruger funktionen DIVIDE, skal du overføre udtryk for tæller og nævner. Du kan også overføre en værdi, der repræsenterer et alternativt resultat.

```dax

DIVIDE(<numerator>, <denominator> [,<alternateresult>])

```

Funktionen DIVIDE er udviklet til automatisk at håndtere tilfælde, hvor der divideres med nul. Hvis et alternativt resultat ikke overføres, og nævneren er nul eller TOM, returnerer funktionen TOM. Hvis der sendes et alternativt resultat, returneres det i stedet for TOM.

Funktionen DIVIDE er praktisk, fordi udtrykket ikke først behøver at teste nævnerværdien. Funktionen er også bedre optimeret til at teste nævnerværdien end funktionen [IF](/dax/if-function-dax). Brug af DIVIDE resulterer også i et mere præcist og elegant udtryk.

## <a name="example"></a>Eksempel

Følgende målingsudtryk producerer en sikker division, men det involverer brug af tre DAX-funktioner.

```dax

=IF(ISBLANK([Sales]) || [Sales] = 0, BLANK(), [Profit] / [Sales])

```

Dette målingsudtryk opnår samme resultat, men er endnu mere effektivt og elegant.

```dax

=DIVIDE([Profit], [Sales])

```

## <a name="recommendations"></a>Anbefalinger

Vi anbefaler, at du bruger funktionen DIVIDE, når nævneren er et udtryk, der _kan_ returnere nul eller TOM.

Hvis nævneren er en konstant værdi, anbefaler vi, at du bruger divisionsoperatoren. I dette tilfælde gennemføres divisionen, og dit udtryk kører bedre, da unødvendige test undgås.

Du skal nøje overveje, om funktionen DIVIDE skal returnere en anden værdi. I forbindelse med målinger er det normalt et bedre design, at de returnerer TOM. Det skyldes, at rapportvisualiseringer som standard fjerner grupperinger, når opsummeringer er TOMME. Det gør det muligt for visualiseringen at fokusere på grupper, der indeholder data. Når det er nødvendigt, kan du konfigurere visualiseringen til at vise alle grupper (der returnerer værdier eller er TOMME) i filterkonteksten ved at aktivere indstillingen "Vis elementer uden data".
