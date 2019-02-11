---
title: Overvåg Power BI Premium-kapaciteter ved hjælp af administrationsportalen
description: Brug Power BI-administrationsportalen til at overvåge dine Premium-kapaciteter.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: 59097c07719e4bb8db188e8a86db377076aea7a9
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794110"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Overvåg kapaciteter på administrationsportalen

Denne artikel indeholder en beskrivelse af, hvordan du kan bruge området Kapacitetsindstillinger på administrationsportalen til at få et hurtigt overblik over ydeevnen af din kapacitet.  Du får de mest detaljerede målepunkter for din kapacitet ved at bruge programmet [Power BI Premium Capacity Metrics](service-admin-premium-monitor-capacity.md).

## <a name="capacity-metrics"></a>Målepunkter for kapacitet

Området **Kapacitetsindstillinger** på administrationsportalen indeholder fire målere, der angiver de placerede belastninger og de ressourcer, der er brugt af din kapacitet i løbet af de seneste syv dage. Disse fire felter arbejder på timebasis og angiver, hvor mange timer i løbet af de seneste syv dage det tilknyttede målepunkt oversteg 80 %. Dette målepunkt angiver en potentiel forringelse af slutbrugerens oplevelse.

![Forbrug i løbet af syv dage](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Målepunkt** | **Beskrivelse** |
| --- | --- |
| CPU |Det antal gange, CPU-forbruget har overskredet 80 %. |
| Hukommelsesudskiftning |Repræsenterer hukommelsesforbrug på backend-kerner. Disse data angiver specifikt, hvor mange gange datasæt ryddes fra hukommelsen pga. hukommelsesforbrug grundet brugen af flere datasæt. |
| Hukommelsesforbrug |Gennemsnitligt hukommelsesforbrug vist i GB. |
| DQ/s | Det antal gange, antallet af direkte forespørgsler og direkte forbindelser har overskredet 80 % af grænsen. <br>  Det samlede antal forespørgsler af typen DirectQuery og direkte forbindelse pr. sekund er begrænset. Grænserne er 30/sek. for P1, 60/sek. for P2 og 120/sek. for P3.  Antallet af forespørgsler af typen DirectQuery og direkte forbindelse indgår også i ovenstående begrænsning. Hvis du f.eks. har 15 DirectQueries og 15 direkte forbindelser på et sekund, er grænsen nået<br> Dette gælder både for forbindelser i det lokale miljø og cloudbaserede forbindelser. |
|  |  |

Målepunkter afspejler udnyttelse i løbet af den seneste uge.  Hvis du vil se en mere detaljeret visning af målepunkter, kan du gøre det ved at klikke på et af oversigtsfelterne.  Derved åbnes detaljerede diagrammer over de enkelte målepunkter for din Premium-kapacitet. I følgende diagram vises der oplysninger om CPU-målepunktet.

![Detaljeret diagram over forbrug, CPU](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Disse diagrammer opsummeres for hver time i løbet af den seneste uge og kan hjælpe med at identificere, hvornår du har haft særlige hændelser relateret til ydeevne i din Premium-kapacitet.

Du kan også eksportere de underliggende data for et eller flere målepunkter til en CSV-fil.  Via denne eksport får du detaljerede oplysninger i tre minutters intervaller for hver dag fra den seneste uge.

## <a name="next-steps"></a>Næste trin

Nu, hvor du har en forståelse af, hvordan du overvåger Power BI Premium-kapaciteter, kan du få mere at vide om optimering af kapaciteter.

> [!div class="nextstepaction"]
> [Administration og optimering af ressourcer med Power BI Premium-kapacitet](service-premium-understand-how-it-works.md)
