---
title: Brug af SAP BW Connector i Power BI Desktop
description: Brug af SAP BW Connector i Power BI Desktop
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
ms.openlocfilehash: 13f6a3fa5fc5ae5c2bea2fb6b91250216eebcc01
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>Brug af SAP BW Connector i Power BI Desktop
Med Power BI Desktop har du adgang til data i **SAP BusinessWarehouse (BW)**.

## <a name="installation-of-sap-bw-connector"></a>Installation af SAP BW Connector
Når du vil bruge **SAP BW Connector**, skal du gennemføre følgende installationstrin:

1. Installér biblioteket **SAP NetWeaver** på din lokale computer. Du kan hente biblioteket **SAP Netweaver** fra SAP-administratoren eller direkte fra [SAP Software Download Center](https://support.sap.com/swdc). Da strukturen i **SAP Software Download Center** ofte ændres, kan vi ikke give en mere specifik vejledning til, hvordan du henter programmet. **SAP NetWeaver**-biblioteket er som regel medtaget i installationen af SAP-klientværktøjer.
   
   Du kan eventuelt søge efter *SAP-bemærkning nr. 1025361* for at få oplyst downloadplaceringen af den seneste version. Kontrollér, at arkitekturen i **SAP NetWeaver**-biblioteket (32-bit eller 64-bit) svarer til din **Power BI Desktop**-installation, og installér derefter alle filer, der er medtaget i **SAP NetWeaver RFC SDK** , i henhold til SAP-bemærkningen.
2. Dialogboksen **Hent data** omfatter et element til **SAP Business Warehouse-server** i kategorien **Database**.
   
   ![](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="sap-bw-connector-features"></a>Funktioner i SAP BW Connector
Eksempelvisningen af **SAP BW Connector** i Power BI Desktop gør det muligt for brugere at importere data fra deres kuber i **SAP Business Warehouse-server**. Du kan også bruge DirectQuery sammen med **SAP BW Connector**. Du skal angive en *server*, et *systemnummer* og et *klient-id* for at oprette forbindelsen.

![](media/desktop-sap-bw-connector/sap_bw_3a.png)

Du kan også angive to ekstra **avancerede indstillinger**: sprogkode og en brugerdefineret MDX-sætning, der skal køre mod den angivne server.

![](media/desktop-sap-bw-connector/sap_bw_4a.png)

Hvis der ikke er angivet en MDX-sætning, får du vist vinduet **Navigator**, som viser listen over de kuber, der er tilgængelige på serveren, og du får mulighed for at foretage detailudledning og vælge elementer fra de tilgængelige kuber, herunder dimensioner og målinger. Power BI viser forespørgsler og kuber, der er vist af [BW Open Analysis Interface OLAP BAPI'er](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm).

Når du vælger ét eller flere elementer fra serveren, oprettes der et eksempel på outputtabellen baseret på valget.

![](media/desktop-sap-bw-connector/sap_bw_5.png)

Vinduet **Navigator** indeholder også et par **visningsindstillinger**, der giver dig mulighed at gøre følgende:

* **Vis *Only Selected Items* (Kun markerede elementer) over for *All Items* (Alle elementer) (standardvisning):** Denne indstilling er nyttig, når det sidste sæt elementer, der er valgt, skal bekræftes. En alternativ metode til at få vist dette er at vælge *Kolonnenavne* i området *Preview* (Eksempel).
* **Aktivér datavisninger (standard):** Du kan også styre, om dataeksempler skal vises i denne dialogboks. Deaktivering af dataeksempler reducerer antallet af kald til serveren, fordi der ikke længere anmodes om data til eksempelvisningerne.
* **Tekniske navne:** SAP BW understøtter *tekniske navne* for objekter i en kube. Tekniske navne giver ejeren af en kube mulighed for at vise *brugervenlige* navne for kubeobjekter i modsætning til kun at vise de *fysiske navne* for disse objekter i kuben.

![](media/desktop-sap-bw-connector/sap_bw_6.png)

Når du har valgt alle nødvendige objekter i **Navigator**, kan du bestemme, hvad du derefter vil foretage dig, ved at vælge en af følgende knapper nederst i **Navigator**-vinduet:

* Vælger du **Indlæs**, starter dette indlæsning af hele rækkesæt til outputtabellen til Power BI Desktop-datamodellen, og derefter kommer du til visningen **Rapport**, hvor du kan begynde at visualisere dataene eller foretage yderligere ændringer ved hjælp af visningerne **Data** eller **Relationer**.
* Hvis du vælger **Rediger**, vises **Forespørgselseditor**, hvor du kan udføre yderligere datatransformation og filtrere trin, før hele sættet af rækker overføres til Power BI Desktop-datamodellen.

Ud over at importere data fra **SAP BW**-kuber, skal du huske på, at du også kan importere data fra en lang række andre datakilder i Power BI Desktop og derefter samle dem til en enkelt rapport. Dette giver mange typer interessante scenarier til rapportering og analyser ud fra **SAP BW**-data.

## <a name="troubleshooting"></a>Fejlfinding
Dette afsnit indeholder fejlfindingssituationer (og løsninger) til arbejdet med denne prøveversion af **SAP BW**-connectoren.

1. Numeriske data fra **SAP BW** returnerer decimaltegn i stedet for kommaer. 1,000,000 returneres f.eks. som 1.000.000.
   
   **SAP BW** returnerer decimaldata med enten et *,* (komma) eller et *.* (punktum) som decimalseparator. Når det skal angives, hvilken af dem **SAP BW** skal bruge som decimalseparator, foretager driveren, der bruges af **Power BI Desktop**, et kald til *BAPI_USER_GET_DETAIL*. Dette kald returnerer en struktur kaldet **DEFAULTS** (Standarder), som indeholder feltet *DCPFM*, hvor *decimalformatets notation* er gemt. Det kan have en af følgende tre værdier:
   
       ‘ ‘ (space) = Decimal point is comma: N.NNN,NN
       'X' = Decimal point is period: N,NNN.NN
       'Y' = Decimal point is N NNN NNN,NN
   
   Kunder, der har rapporteret dette problem, har registreret, at kaldet til *BAPI_USER_GET_DETAIL* mislykkes for en bestemt bruger (den bruger, der vises de forkerte data), med en fejlmeddelelse, der er meget lig følgende:
   
       You are not authorized to display users in group TI:
           <item>
               <TYPE>E</TYPE>
               <ID>01</ID>
               <NUMBER>512</NUMBER>
               <MESSAGE>You are not authorized to display users in group TI</MESSAGE>
               <LOG_NO/>
               <LOG_MSG_NO>000000</LOG_MSG_NO>
               <MESSAGE_V1>TI</MESSAGE_V1>
               <MESSAGE_V2/>
               <MESSAGE_V3/>
               <MESSAGE_V4/>
               <PARAMETER/>
               <ROW>0</ROW>
               <FIELD>BNAME</FIELD>
               <SYSTEM>CLNTPW1400</SYSTEM>
           </item>
   
   For at løse problemet skal brugere bede deres SAP-administrator om at give den SAPBW-bruger, der anvendes i Power BI, ret til at udføre *BAPI_USER_GET_DETAIL*. Det er også en god ide at bekræfte, at brugeren har den krævede *DCPFM*-værdi som beskrevet tidligere i denne fejlfindingsløsning.
2. **Forbindelse til SAP BEx-forespørgsler**
   
   Du kan udføre **BEx**-forespørgsler i Power BI Desktop ved at aktivere en bestemt egenskab som vist i følgende billede:
   
   ![](media/desktop-sap-bw-connector/sap_bw_8.png)

