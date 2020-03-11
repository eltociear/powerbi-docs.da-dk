---
title: Vejledning til fejlfinding af relationer
description: Vejledning til fejlfinding af problemer med modelrelationer.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/02/2020
ms.author: v-pemyer
ms.openlocfilehash: e2854d82d858bb1963b691d32d561c7b3bbfc11a
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/04/2020
ms.locfileid: "78263639"
---
# <a name="relationship-troubleshooting-guidance"></a>Vejledning til fejlfinding af relationer

Denne artikel henvender sig til designere af datamodeller, der arbejder med Power BI Desktop. Den indeholder en vejledning i, hvordan du foretager fejlfinding af bestemte problemer, du kan støde på, når du udvikler modeller og rapporter.

[!INCLUDE [relationships-prerequisite-reading](includes/relationships-prerequisite-reading.md)]

## <a name="troubleshooting-checklist"></a>Tjekliste til fejlfinding

Når en rapportvisualisering er konfigureret til at bruge felter fra to (eller flere) tabeller, og det korrekte resultat (eller et hvilket som helst resultat) ikke vises, er problemet muligvis relateret til modelrelationer.

I dette tilfælde er der her en generel tjekliste til fejlfinding, som du kan følge. Du kan arbejde dig igennem tjeklisten gradvist, indtil du identificerer problemet/problemerne.

1. Skift visualiseringen til en tabel eller matrix, eller åbn ruden "Vis data". Det er nemmere at foretage fejlfinding af problemer, når du kan se forespørgselsresultatet
1. Hvis der er et tomt forespørgselsresultat, skal du skifte til Datavisning. Bekræft, at der er indlæst rækker af data i tabellerne
1. Skift til Modelvisning. Det er nemt at se relationerne og hurtigt bestemme deres egenskaber
1. Bekræft, at der findes relationer mellem tabellerne
1. Bekræft, at egenskaberne for kardinalitet er konfigureret korrekt. De kan være forkerte, hvis "mange"-siden af en kolonne aktuelt indeholder unikke værdier, og den er konfigureret forkert som en "en"-side
1. Bekræft, at relationerne er aktive (en ensfarvet linje)
1. Bekræft, at filterretningerne understøtter overførsel (fortolk pilehovederne)
1. Bekræft, at de korrekte kolonner er relateret. Vælg enten relationen, eller hold markøren over den for at få vist de relaterede kolonner
1. Bekræft, at de relaterede kolonnedatatyper er ens eller i det mindste kompatible. Det er muligt at relatere en tekstkolonne til en kolonne med heltal, men filtrene kan ikke finde nogen match, der skal overføres
1. Skift til Datavisning, og bekræft, at de matchende værdier findes i de relaterede kolonner

## <a name="troubleshooting-guide"></a>Fejlfindingsvejledning

Her er en liste over problemer sammen med mulige løsninger.

|Problem|Mulige årsager|
|---------|---------|
|Der vises ingen resultater i visualiseringen|– Der er endnu ikke indlæst nogen data i modellen<br />– Der findes ingen data i filterkonteksten<br />– Sikkerhed på rækkeniveau håndhæves<br />– Relationerne overføres ikke mellem tabeller. _Følg tjeklisten ovenfor_<br />– Sikkerhed på rækkeniveau håndhæves, men en tovejsrelation er ikke aktiveret til overførsel. Se [Sikkerhed på rækkeniveau med Power BI Desktop](../desktop-rls.md)|
|Den samme værdi for hver gruppering vises i visualiseringen |– Der findes ingen relationer<br />– Relationerne overføres ikke mellem tabeller. _Følg tjeklisten ovenfor_|
|Der vises resultater i visualiseringen, men de er ikke korrekte|– Visualiseringen er konfigureret forkert<br />– Målingslogikken er forkert<br />– Modeldataene skal opdateres<br />– Kildedataene er forkerte<br />– Relationskolonnerne er forkert relateret (kolonnen **Produkt-id** er f.eks. tilknyttet **Kunde-id**)<br />– Det er en relation mellem to DirectQuery-tabeller, og "en"-siden af kolonnen i en relation indeholder dubletværdier|
|Der vises TOMME grupperinger eller udsnit/filterelementer, og kildekolonnerne indeholder ikke TOMME værdier|– Det er en stærk relation, og "mange"-siden af kolonnen indeholder værdier, der ikke er gemt i "en"-siden af kolonnen. Se [Modelrelationer i Power BI Desktop (Stærke relationer)](../desktop-relationships-understand.md#strong-relationships)<br />– Det er en stærk en til en-relation, og relaterede kolonner indeholder TOMME værdier. Se [Modelrelationer i Power BI Desktop (Stærke relationer)](../desktop-relationships-understand.md#strong-relationships)<br />– Der gemmes TOMME værdier for "mange"-siden af kolonnen i en inaktiv relation, eller der er værdier, som ikke er gemt på "en"-siden|
|Der mangler data i visualiseringen|– Der er anvendt forkerte/uventede filtre<br />– Sikkerhed på rækkeniveau håndhæves<br />– Det er en svag relation, og der er TOMME værdier i relaterede kolonner, eller der er problemer med dataintegritet. Se [Modelrelationer i Power BI Desktop (Svage relationer)](../desktop-relationships-understand.md#weak-relationships)<br />– Det er en relation mellem to DirectQuery-tabeller, og relationen er konfigureret til at [antage referentiel integritet](../desktop-relationships-understand.md#assume-referential-integrity), men der er problemer med dataintegritet (uoverensstemmende værdier i relaterede kolonner)|
|Sikkerhed på rækkeniveau håndhæves ikke korrekt|– Relationerne overføres ikke mellem tabeller. _Følg tjeklisten ovenfor_<br />– Sikkerhed på rækkeniveau håndhæves, men en tovejsrelation er ikke aktiveret til overførsel. Se [Sikkerhed på rækkeniveau med Power BI Desktop](../desktop-rls.md)|
|||

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger, der er relateret til denne artikel, i følgende ressourcer:

- [Modelrelationer i Power BI Desktop](../desktop-relationships-understand.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
- Forslag? [Få ideer til at forbedre Power BI](https://ideas.powerbi.com/)
