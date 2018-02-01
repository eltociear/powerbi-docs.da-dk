---
title: DirectQuery til SAP HANA i Power BI
description: Overvejelser ved brug af DirectQuery med SAP HANA
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 2b2e59371c96928a2b7c6b23bd393a80ecc3041a
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/25/2018
---
# <a name="directquery-and-sap-hana"></a>DirectQuery og SAP HANA
Du kan oprette forbindelse til **SAP HANA**-datakilder direkte ved hjælp af **DirectQuery**.

Når du bruger **SAP HANA**, er det er vigtigt at forstå visse aspekter af, hvordan forbindelser til det behandles, for at sikre, at:

* Resultaterne er som forventet, når SAP HANA-visningen indeholder målinger, som ikke kan adderes (f.eks. distinct counts eller gennemsnit i stedet for en almindelig sum-funktion)
* De oprettede forespørgsler er effektive

Det er en god idé at bruge et øjeblik på at præcisere den måde, en relationel kilde fungerer på, f.eks **SQL Server**, når den forespørgsel, der er defineret i **Hent data** eller **Forespørgselseditor** udfører en aggregering. I eksemplet nedenfor returnerer en forespørgsel, der er defineret i **Forespørgselseditor**, gennemsnitsprisen efter **ProductID**.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Hvis dataene importeres til Power BI (i modsætning til at bruge DirectQuery), vil følgende ske:

* Dataene importeres på det aggregeringsniveau, der er defineret i den forespørgsel, som er oprettet i **Forespørgselseditor**. Eksempelvis gennemsnitspris efter produkt. Dette giver en tabel med to kolonner, *ProductID* og *AveragePrice*, som kan bruges i visuelle gengivelser.
* I en visuel gengivelse udføres alle efterfølgende aggregeringer, f.eks. *Sum*, *Average*, *Min* og andre, på de importerede data.  Hvis du f.eks. medtager *AveragePrice* i en visuel gengivelse, vil funktionen *Sum* blive brugt som standard, og det vil returnere summen af *AveragePrice* for hvert *ProductID* – som i dette tilfælde ville være 13,67. Det samme gælder for alle alternative aggregeringsfunktioner, som f.eks. *Min*, *Average*osv., der bruges på den visuelle gengivelse. *Average* af *AveragePrice* returnerer f.eks. gennemsnittet af 6,66, 4 og 3, som giver 4,56, og *ikke* gennemsnittet af *Price* for de 6 poster i den underliggende tabel, som er 5,17.

Hvis du bruger **DirectQuery** i stedet for at importere dataene, gælder den samme semantik, og resultaterne vil være nøjagtigt de samme:

* Hvis du bruger den samme forespørgsel, vil det logisk set være de samme data, som bruges i rapporteringslaget – selvom dataene egentlig ikke importeres.
* I en visuel gengivelse udføres alle efterfølgende aggregeringer, f.eks. *Sum*, *Average*, *Min* og andre, på de importerede data. Og igen returnerer en visuel gengivelse, der indeholder *Average* af *AveragePrice*, resultatet 4,56.

Lad os nu se på **SAP HANA**. Power BI kan fungere med både *Analytic Views* og *Calculation Views* i SAP HANA, som begge kan indeholde mål. Men i dag følger tilgangen til SAP HANA de samme principper som beskrevet før: Den forespørgsel, der defineres i **Hent data** eller **Forespørgselseditor**, bestemmer, hvilke data der er tilgængelige, og alle efterfølgende aggregeringer i en visuel gengivelse udføres på de data, og det samme gælder for både Import og DirectQuery.

Som det er naturligt med HANA, vil den forespørgsel, der oprindeligt er defineret i dialogboksen **Hent data** eller i **Forespørgselseditor**. altid være en aggregeringsforespørgsel, og den vil generelt inkludere målinger, hvor den aktuelle aggregering, der bruges, er defineret i HANA-visningen.

Tilsvarende SQL Server-eksemplet herover er der en HANA-visning, der indeholder **ID**, **ProductID**, **DepotID** og målinger, inklusive **AveragePrice**, som er defineret i visningen som **Average of Price**.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

Hvis der er valgt felter for **ProductID** og målingen **AveragePrice** i **Hent data**, vil det definere en forespørgsel for visningen, som anmoder om de aggregerede data (i eksemplet herover bruges der pseudo-SQL, som ikke stemmer overens med den præcise syntaks i HANA SQL). Hvis der defineret flere aggregeringer i en visualisering, vil disse være resultatet af en sådan forespørgsel. Som beskrevet herover for **SQL Server** gælder dette både for import og ved brug af DirectQuery. Vær opmærksom på, at når der bruges DirectQuery, vil forespørgslen fra **Hent data** eller **Forespørgselseditor** blive brugt i en underliggende Select, der sendes i en enkelt forespørgsel til HANA, og det er ikke alle data, der indlæses, før den ekstra aggregering.

Det medfører, at det er vigtigt at overveje følgende, inden du bruger DirectQuery i stedet for HANA:

* Du skal være opmærksom på eventuel ekstra aggregering, der udføres i visualiseringer, når målingen i HANA ikke adderer (f.eks. ikke en simpel *Sum*, *Min* eller *Max*).
* I **Hent data** eller **Forespørgselseditor** skal du kun inkludere de kolonner, som er nødvendige for at hente de nødvendige data. Resultatet skal være en forespørgsel, der kan sendes til HANA. Hvis der f.eks. vælges mange kolonner, fordi de muligvis skal bruges efterfølgende i visualiseringer, så vil det selv for DirectQuery medføre, at en simpel visualisering vil indeholde disse mange kolonner, og det vil medføre en dårlig ydeevne.

Lad os tage et kig på et eksempel. I det følgende eksempel vælges der fem kolonner (CalendarQuarter, Color, LastName, ProductLine, SalesOrderNumber) i dialogboksen **Hent data** sammen med målingen OrderQuantity. Det betyder, at hvis der senere oprettes en simpel visualisering med Min OrderQuantity, vil det give følgende SQL-forespørgsel til HANA. Den gråtonede del af den efterfølgende Select indeholder forespørgslen fra **Hent data** / **Forespørgselseditor**. Hvis denne Select gives en høj kardinalitet, vil ydelsen for HANA sandsynligvis blive dårlig.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

Derfor anbefales det, at de elementer, der vælges i **Hent data** eller **Forespørgselseditor** skal være begrænset til de elementer, der er brug for, da det samtidig medfører, at der sendes en rimelig forespørgsel til HANA.

### <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om DirectQuery i følgende ressourcer:

* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [Datagateway i det lokale miljø](service-gateway-onprem.md)

