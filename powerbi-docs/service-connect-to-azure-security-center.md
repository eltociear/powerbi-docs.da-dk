---
title: Opret forbindelse til Azure Security Center med Power BI
description: Azure Security Center til Power BI
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
ms.openlocfilehash: d052bc054e55eabfab53ad3b1ac9229f0a750785
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Opret forbindelse til Azure Security Center med Power BI
Få indsigt i din sikkerhedsrelaterede Azure-arbejdsbelastning ved at oprette forbindelse mellem dine Azure-sikkerhedsdata og Power BI. Power BI opretter automatisk et dashboard og en rapport oven på dine Azure Security Center-data, som gør det muligt at analysere og udforske dataene.

Opret forbindelse til [Azure Security Center-indholdspakken](https://app.powerbi.com/getdata/services/azure-security-center) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. Vælg **Azure Security Center** \>  **Hent**.
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. Angiv dit abonnements-id. Se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams), nedenfor.
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. Som **Godkendelsesmetode** skal du vælge **oAuth2** \> **Log på**. Angiv dine Azure-legitimationsoplysninger, når du bliver bedt om dem.
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. Efter godkendelsen starter importprocessen automatisk. Når processen er færdig, vises et nyt dashboard samt rapport og model i navigationsruden. Vælg dashboardet for at få vist dine importerede data.
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**Hvad nu?**

* Prøv at [stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Indholdspakken giver indsigt i statistikker om ressourcesikkerhed, analyse af advarsler og af forebyggelse.

## <a name="system-requirements"></a>Systemkrav
Denne indholdspakke kræver adgang til et abonnements-id med Azure Security Center aktiveret. Få mere at vide i [Azure Security Center](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2) på Azure-portalen.

Indholdspakken kræver også, at brugeren opretter forbindelse til en organisationskonto (ikke en personlig konto).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Sådan finder du parametre
Der er to måder til nemt at finde sit abonnements-id.

1. Fra https://portal.azure.com -&gt; Gennemse -&gt; Abonnementer -&gt; Abonnements-id
2. Fra https://manage.windowsazure.com -&gt; Indstillinger -&gt; Abonnements-id

Abonnements-id'et er et langt sæt tal og tegn, der ligner eksemplet i trin \#4 ovenfor. 

## <a name="troubleshooting"></a>Fejlfinding
Det kan tage et stykke tid at indlæse dataene afhængigt af størrelsen på din konto. Hvis du støder på en fejl under login, skal du bekræfte dine parametre og at kontoen har Azure Security Center aktiveret.

Hvis indholdspakken indlæses, men ikke viser nogen data, skal du bekræfte, at du opretter forbindelse med en organisationskonto. Selvom personlige konti understøttes af Azure Security Center, returnerer API'en (og derfor indholdspakken) ikke de forventede værdier, hvis brugeren opretter forbindelse til en ikke-organisationskonto. Giv adgang til en organisationskonto, og prøv at oprette forbindelse igen.

## <a name="next-steps"></a>Næste trin
[Kom i gang i Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

