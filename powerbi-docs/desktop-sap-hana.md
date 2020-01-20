---
title: Brug SAP HANA i Power BI Desktop
description: Brug SAP HANA i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/21/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7c70c4f4e5fec55ffd98d0156944c9973cffdb2a
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/09/2020
ms.locfileid: "75760290"
---
# <a name="connect-to-sap-hana-databases-in-power-bi-desktop"></a>Opret forbindelse til SAP Hana-databaser i Power BI Desktop
Med Power BI Desktop har du nu adgang til **SAP HANA**-databaser. Hvis du vil bruge **SAP HANA**, skal SAP HANA ODBC-driveren være installeret på den lokale klientcomputer, for at Power BI Desktop **SAP HANA**-dataforbindelsen skal fungere korrekt. Du kan downloade SAP HANA-klientværktøjer fra [SAP-udviklingsværktøjer](https://tools.hana.ondemand.com/#hanatools), som indeholder den nødvendige ODBC-driver. Du kan også få dem i [SAP software Download Center](https://support.sap.com/swdc). I softwareportalen kan du søge efter SAP HANA CLIENT til Windows-computere. Da strukturen i **SAP Software Download Center** ofte ændres, kan vi ikke give en mere specifik vejledning til, hvordan du henter programmet.

Hvis du vil oprette forbindelse til en **SAP HANA**-database, skal du vælge **Hent data > Database > SAP HANA-database** som vist på følgende billede:

![](media/desktop-sap-hana/sap-hana-1.png)

Når du opretter forbindelse til en SAP HANA-database, skal du angive servernavnet. Derefter skal du angive porten fra rullelisten og inputfeltet.

I denne version understøttes **SAP HANA** i [DirectQuery](desktop-directquery-sap-hana.md)-tilstand i Power BI Desktop og Power BI tjenesten, og du kan publicere og uploade de rapporter, der bruger **SAP HANA** i DirectQuery-tilstand, til Power BI tjenesten. Du kan også publicere og overføre rapporter til Power BI-tjenesten, når du ikke bruger **SAP HANA** i DirectQuery-tilstand.

## <a name="supported-features-for-sap-hana"></a>Understøttede funktioner til SAP HANA
Denne version indeholder mange funktioner til **SAP HANA** som vist på listen nedenfor:

* Power BI-forbindelseskomponenten til **SAP HANA** bruger SAP ODBC-driveren for at give den bedste brugeroplevelse.
* **SAP HANA** understøtter både DirectQuery og Import.
* Power BI understøtter HANA-oplysningsmodeller (f.eks visningerne Analytic og Calculation) og har optimeret navigation.
* Med **SAP HANA** kan du også bruge funktionen Direct SQL til at oprette forbindelse til række- og kolonnetabeller.
* Indeholder optimeret navigation for HANA-modeller.
* Power BI understøtter **SAP HANA**-parametrene Variabler og Input.
* VHDI-objektbeholderbaserede beregningsvisninger
  * Understøttelse af HDI-objektbeholderbaserede beregningsvisninger findes i den offentlige prøveversion i august 2019-udgivelsen af Power BI Desktop. Hvis du vil have adgang til HDI-objektbeholderbaserede beregningsvisninger i Power BI, skal du sørge for, at den eller de HANA-databasebrugere, du bruger sammen med Power BI, har tilladelse til at få adgang til HDI-kørselsobjektbeholderen, der gemmer de visninger, du vil have adgang til. Hvis du vil tildele denne adgang, skal du oprette en rolle, der giver adgang til din HDI-objektbeholder, og tildele rollen til den HANA-databasebruger, du vil bruge sammen med Power BI (denne bruger skal også have tilladelse til at læse fra systemtabeller i \_SYS\_ BI-skemaet som sædvanlig). Se den officielle SAP-dokumentation for at få mere at vide om, hvordan du opretter og tildeler databaseroller. [Dette SAP-blogindlæg](https://blogs.sap.com/2018/01/24/the-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user/) kan være et godt sted at starte.
  * Bemærk, at der i øjeblikket er nogle begrænsninger for HANA-variabler, der er knyttet til HDI-baserede beregningsvisninger. Disse begrænsninger skyldes fejl på HANA-siden og bliver behandlet i fremtidige versioner af SAP HANA. For det første er det ikke muligt at anvende en HANA-variabel i en delt kolonne i en HDI-objektbeholderbaseret beregningsvisning. Denne begrænsning kan løses ved at opgradere til HANA 2 version 37.02 og nyere eller HANA 2 version 42 og nyere. For det andet vises standardværdierne for variabler og parametre ikke i brugergrænsefladen i Power BI. Dette skyldes også en fejl i SAP HANA, men SAP har endnu ikke annonceret en rettelse.

## <a name="limitations-of-sap-hana"></a>Begrænsninger i SAP HANA
Der er også nogle begrænsninger i at bruge **SAP HANA**:

* NVARCHAR-strenge afkortes til maksimumlængden på 4.000 Unicode-tegn.
* SMALLDECIMAL understøttes ikke.
* VARBINARY understøttes ikke.
* Kun datoer mellem 30.12.1899 og 31.12.9999 er gyldige.


## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om SAP HANA og DirectQuery i følgende ressourcer:

* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [Aktivér kryptering for SAP HANA](desktop-sap-hana-encryption.md)


