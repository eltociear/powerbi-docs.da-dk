---
title: Brug SAP HANA i Power BI Desktop
description: Brug SAP HANA i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 44dff39d043bb7a71c01b5103cfdf65e7d5e33cb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "34287595"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Brug SAP HANA i Power BI Desktop
Med Power BI Desktop har du nu adgang til **SAP HANA**-databaser. Hvis du vil bruge **SAP HANA**, skal SAP HANA ODBC-driveren være installeret på den lokale klientcomputer, for at Power BI Desktop **SAP HANA**-dataforbindelsen skal fungere korrekt. Du kan hente SAP HANA ODBC-driveren fra [SAP Software Download Center](https://support.sap.com/swdc). Herfra kan du søge efter SAP HANA CLIENT til Windows-computere. Da strukturen i **SAP Software Download Center** ofte ændres, kan vi ikke give en mere specifik vejledning til, hvordan du henter programmet.

Hvis du vil oprette forbindelse til en **SAP HANA**-database, skal du vælge **Hent data > Database > SAP HANA-database** som vist på følgende billede:

![](media/desktop-sap-hana/sap-hana-1.png)

Når du opretter forbindelse til en SAP HANA-database, skal du angive servernavnet og porten i følgende format: *serve:port*. På billedet nedenfor kan du se et eksempel på en server med navnet *ServerXYZ* og port *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

I denne version understøttes **SAP HANA** i [DirectQuery](desktop-directquery-sap-hana.md)-tilstand i Power BI Desktop og Power BI tjenesten, og du kan publicere og uploade de rapporter, der bruger **SAP HANA** i DirectQuery-tilstand, til Power BI tjenesten. Du kan også publicere og overføre rapporter til Power BI-tjenesten, når du ikke bruger **SAP HANA** i DirectQuery-tilstand.

### <a name="supported-features-for-sap-hana"></a>Understøttede funktioner til SAP HANA
Denne version indeholder mange funktioner til **SAP HANA** som vist på listen nedenfor:

* Power BI-forbindelseskomponenten til **SAP HANA** bruger SAP ODBC-driveren for at give den bedste brugeroplevelse.
* **SAP HANA** understøtter både DirectQuery og Import.
* Power BI understøtter HANA-oplysningsmodeller (f.eks visningerne Analytics og Calc) og har optimeret navigation.
* Med **SAP HANA** kan du også bruge funktionen Direct SQL til at oprette forbindelse til række- og kolonnetabeller.
* Indeholder optimeret navigation for HANA-modeller.
* Power BI understøtter **SAP HANA**-parametrene Variabler og Input.

### <a name="installing-the-sap-hana-odbc-driver"></a>Installation af SAP HANA ODBC-driveren
### <a name="limitations-of-sap-hana"></a>Begrænsninger i SAP HANA
Der er også nogle begrænsninger i at bruge **SAP HANA**:

* NVARCHAR-strenge afkortes til maksimumlængden på 4.000 Unicode-tegn.
* SMALLDECIMAL understøttes ikke.
* VARBINARY understøttes ikke.
* Kun datoer mellem 30.12.1899 og 31.12.9999 er gyldige.


## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om DirectQuery i følgende ressourcer:

* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)

