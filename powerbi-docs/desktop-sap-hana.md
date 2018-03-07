---
title: Brug SAP HANA i Power BI Desktop
description: Brug SAP HANA i Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c048a83dad3ea800f50b08bd15c0cec18d6d86cf
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Brug SAP HANA i Power BI Desktop
Med Power BI Desktop har du nu adgang til **SAP HANA**-databaser. Hvis du vil bruge **SAP HANA**, skal SAP HANA ODBC-driveren være installeret på den lokale klientcomputer, for at Power BI Desktop **SAP HANA**-dataforbindelsen skal fungere korrekt. Du kan hente SAP HANA ODBC-driveren fra [SAP Software Download Center](https://support.sap.com/swdc). Herfra kan du søge efter SAP HANA CLIENT til Windows-computere. Da strukturen i **SAP Software Download Center** ofte ændres, kan vi ikke give en mere specifik vejledning til, hvordan du henter programmet.

Hvis du vil oprette forbindelse til en **SAP HANA**-database, skal du vælge **Hent data > Database > SAP HANA-database** som vist i følgende billede.

![](media/desktop-sap-hana/sap-hana-1.png)

Når du opretter forbindelse til en SAP HANA-database, skal du angive servernavnet og porten i følgende format: *serve:port*. På billedet nedenfor kan du se et eksempel på en server med navnet *ServerXYZ* og port *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

I denne version understøttes **SAP HANA** i [DirectQuery](desktop-use-directquery.md)-tilstand i Power BI Desktop og Power BI-tjenesten, og du kan publicere og overføre de rapporter, der bruger **SAP HANA** i DirectQuery-tilstand, til Power BI-tjenesten. Du kan også publicere og overføre rapporter til Power BI-tjenesten, når du ikke bruger **SAP HANA** i DirectQuery-tilstand.

### <a name="supported-features-for-sap-hana"></a>Understøttede funktioner til SAP HANA
Denne version indeholder mange funktioner til **SAP HANA** som vist på listen nedenfor:

* Power BI-forbindelseskomponenten til **SAP HANA** bruger SAP ODBC-driveren til at give den bedste brugeroplevelse.
* **SAP HANA** understøtter både DirectQuery og Import.
* Power BI understøtter HANA-oplysningsmodeller (f.eks visningerne Analytics og Calc), og navigation er optimeret.
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

