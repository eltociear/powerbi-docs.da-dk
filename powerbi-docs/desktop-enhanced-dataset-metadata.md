---
title: Brug af forbedrede metadata for datasæt i Power BI Desktop (eksempelvisning)
description: I denne artikel beskrives det, hvordan du bruger forbedrede metadata for datasæt i Power BI.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/13/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3812f16489d304912ec9574352897e1effb29d4a
ms.sourcegitcommit: 7e845812874b3347bcf87ca642c66bed298b244a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/13/2020
ms.locfileid: "79201395"
---
# <a name="using-enhanced-dataset-metadata-preview"></a>Brug af forbedrede metadata for datasæt (prøveversion)

Når der oprettes rapporter i Power BI Desktop, oprettes der også metadata for datasæt i de tilsvarende PBIX- og PBIT-filer. Tidligere blev metadataene lagret i et format, der var specifikt for Power BI Desktop. Der blev brugt base-64-kodede M-udtryk og -datakilder, og der blev opstillet forudsætninger for, hvordan disse metadata blev lagret.

Med udgivelsen af funktionen til **forbedrede metadata for datasæt** er mange af disse begrænsninger fjernet. Når funktionen til **forbedrede metadata for datasæt** er aktiveret, bruger metadata, der er oprettet af Power BI Desktop, et format, der ligner det, der bruges til tabellariske Analysis Services-modeller, baseret på den [tabellariske objektmodel](https://docs.microsoft.com/bi-reference/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo).


Funktionen til **forbedrede metadata for datasæt** er strategisk og grundlæggende, da den fremtidige Power BI-funktionalitet bygges på dens metadata. Nogle yderligere funktioner, der kan drage fordel af forbedrede metadata for datasæt, omfatter [XMLA-læsning/-skrivning](https://docs.microsoft.com/power-platform-release-plan/2019wave2/business-intelligence/xmla-readwrite) til administration af Power BI-datasæt og migreringen af Analysis Services-arbejdsbelastninger til Power BI, der kan drage fordel af den næste generation af funktioner.

## <a name="enable-enhanced-dataset-metadata"></a>Aktiver forbedrede metadata for datasæt

Funktionen til **forbedrede metadata for datasæt** er i øjeblikket tilgængelig som prøveversion. Hvis du vil aktivere forbedrede metadata for datasæt, skal du i Power BI Desktop vælge **Filer > Indstillinger > Indstillinger > Funktioner i prøveversionen**og derefter markere afkrydsningsfeltet **Gem datasæt ved hjælp af forbedret metadataformat** som vist på følgende billede. 

![Aktiver prøveversionsfunktionen](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-01.png)

Du bliver spurgt, om du vil genstarte Power BI Desktop.

![Prompt om genstart](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-02.png)

Når prøveversionsfunktionen er aktiveret, forsøger Power BI Desktop at opgradere PBIX- og PBIT-filer, der bruger det tidligere metadataformat. 

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

I prøveversionen gælder følgende begrænsninger, når prøveversionsfunktionen er aktiveret.

Når du åbner en eksisterende PBIX- eller PBIT-fil, der ikke er blevet opgraderet, mislykkes opgraderingen, hvis datasættet indeholder en af følgende funktioner eller connectors. Hvis denne fejl opstår, påvirker det normalt ikke brugeroplevelsen med det samme, og Power BI Desktop fortsætter med at bruge det tidligere metadataformat.

* Python-scripts
* Brugerdefinerede forbindelser
* Azure DevOps Server
* BI Connector
* Denodo
* Dremio
* Exasol
* Indexima
* IRIS
* Jethro ODBC
* Kyligence Enterprise
* MarkLogic ODBC
* Qubole Presto
* Team Desk
* M-udtryk, der indeholder visse tegnkombinationer, f. eks. "\\n", i kolonnenavne
* Når du bruger datasæt med funktionen til **forbedrede metadata for datasæt** aktiveret, kan der ikke konfigureres enkeltlogondatakilder (SSO) i Power BI-tjenesten

Derudover kan PBIX- og PBIT-filer, der allerede er blevet opgraderet til at bruge **forbedrede metadata for datasæt**, *ikke* bruge ovenstående funktioner eller connectors i den aktuelle version.


## <a name="next-steps"></a>Næste trin

Du kan gøre mange forskellige ting med Power BI Desktop. Du kan finde flere oplysninger om funktionerne i følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Nyheder i Power BI Desktop](desktop-latest-update.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datatyper i Power BI Desktop](desktop-data-types.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)

