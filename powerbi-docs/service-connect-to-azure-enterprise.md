---
title: Opret forbindelse til Microsoft Azure Enterprise med Power BI
description: Microsoft Azure Enterprise til Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 39c3fd776e3aed821c7c10c1e905d7400ca64efd
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>Opret forbindelse til Microsoft Azure Enterprise med Power BI
Udforsk og overvåg dine Microsoft Azure Enterprise-data i Power BI med Power BI-indholdspakken. Dataene opdateres automatisk én gang dagligt.

Opret forbindelse til den [Microsoft Azure Enterprise-indholdspakken](https://app.powerbi.com/getdata/services/azure-enterprise) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. Vælg **Microsoft Azure Enterprise** \> **Hent**.
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. Angiv URL-adressen til Azure-miljøet, det antal måneder, du vil importere data for, og dit Azure Enterprise-tilmeldingsnummer. URL-adressen til dit Azure-miljø er `https://ea.azure.com` eller `https://ea.windowsazure.cn`. Se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams), nedenfor.
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. Angiv din adgangsnøgle for at oprette forbindelse. Du kan finde nøglen til din tilmelding i din Azure EA-portal.
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. Importprocessen starter automatisk. Når processen er færdig, vises et nyt dashboard samt rapport og model i navigationsruden. Vælg dashboardet for at få vist dine importerede data.
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**Hvad nu?**

* Prøv at [stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Azure Enterprise-indholdspakken indeholder månedlige rapporteringsdata for det interval af måneder, du angiver under forbindelsesflowet. Intervallet er et fleksibelt vindue, så de datoer, der medtages, bliver opdateret, når datasættet opdateres.

## <a name="system-requirements"></a>Systemkrav
Indholdspakken kræver adgang til virksomhedsfunktioner på Azure-portalen.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Sådan finder du parametre
Power BI-rapportering er tilgængeligt for EA-kunder af typen Direct, Partner og Indirect, som kan få vist faktureringsoplysninger. Læs nedenfor, hvis du vil have oplysninger om at finde hver af de værdier, der forventes i forbindelsesflowet.

**URL-adresse til Azure-miljøet**

* Denne værdi er normalt https://ea.azure.com, men du kan kontrollere URL-adressen, når du logger på, for at bekræfte det.
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**Antal måneder**

* Dette skal være et tal mellem 1-36, der repræsenterer det antal måneder (fra i dag) du vil importere data for.

**Tilmeldingsnummer**

* Dette er dit Azure Enterprise-tilmeldingsnummer, som findes på startskærmen på [Azure Enterprise Portal](https://ea.azure.com/) under "Enrollment Detail".
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**Adgangsnøgle**

* Du kan finde din nøgle på Azure Enterprise Portal, under "Download Usage" > "API Access Key"
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**Yderligere hjælp**

* Hvis du vil have yderligere hjælp til at konfigurere Azure Enterprise Power BI-pakken, skal du logge på Azure Enterprise Portal for at få vist API-hjælpefilen under "Help" og yderligere oplysninger under Reports -> Download Usage -> API Access Key.

## <a name="next-steps"></a>Næste trin
[Kom i gang i Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

