---
title: Opret forbindelse til Microsoft Azure Enterprise med Power BI
description: Microsoft Azure Enterprise til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7425e194bd6bda51442a128d146fb4061a77af81
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34243189"
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
5. Angiv din Access-nøgle for at oprette forbindelse. Du finder nøglen til tilmelding på Azure EA Portal.
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. Importprocessen starter automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Azure Enterprise-indholdspakken indeholder månedlige rapporteringsdata for det interval af måneder, du angiver under forbindelsesflowet. Intervallet er et fleksibelt vindue, så de datoer, der medtages, bliver opdateret, når datasættet opdateres.

## <a name="system-requirements"></a>Systemkrav
Indholdspakken kræver adgang til virksomhedsfunktioner på Azure Portal.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søg efter parametre
Power BI-rapportering er tilgængeligt for EA-kunder af typen Direct, Partner og Indirect, som kan få vist faktureringsoplysninger. Læs nedenfor, hvis du vil have oplysninger om at finde hver af de værdier, der forventes i forbindelsesflowet.

**URL-adresse til Azure-miljøet**

* Denne værdi er normalt https://ea.azure.com, men du kan kontrollere URL-adressen, når du logger på, for at bekræfte det.
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**Antal måneder**

* Dette skal være et tal mellem 1-36, der repræsenterer det antal måneder (fra i dag), du vil importere data for.

**Tilmeldingsnummer**

* Dette er dit Azure Enterprise-tilmeldingsnummer, som findes på startskærmen på [Azure Enterprise Portal](https://ea.azure.com/) under "Enrollment Detail".
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**Access-nøgle**

* Du finder din nøgle på Azure Enterprise Portal under "Download Usage" > "API Access Key"
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**Yderligere hjælp**

* Hvis du vil have yderligere hjælp til at konfigurere Azure Enterprise Power BI-pakken, skal du logge på Azure Enterprise Portal for at få vist API-hjælpefilen under "Help" og yderligere oplysninger under Reports -> Download Usage -> API Access Key.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

