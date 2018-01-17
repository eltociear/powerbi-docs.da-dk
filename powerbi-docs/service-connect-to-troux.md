---
title: Opret forbindelse til Troux med Power BI
description: Troux til Power BI
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
ms.openlocfilehash: ec225639ed23f57735081d556c1ac3283dc4d691
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-troux-for-power-bi"></a>Opret forbindelse til Troux til Power BI
Med Troux-indholdspakken kan du visualisere dit Enterprise Architecture-lager på helt nye måder direkte i Power BI. Indholdspakken giver dig indsigt i din virksomheds egenskaber, de programmer, der leverer disse egenskaber, og de teknologier, der understøtter disse programmer, som kan tilpasses fuldt ud ved hjælp af Power BI.

Opret forbindelse til [Troux-indholdspakken](https://app.powerbi.com/getdata/services/troux) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-troux/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-troux/services.png)
3. Vælg **Troux** \> **Hent**.
   
   ![](media/service-connect-to-troux/troux.png)
4. Angiv URL-adressen til dine Troux OData. Se detaljer om, hvordan du [finder de pågældende parametre](#FindingParams), nedenfor.
   
   ![](media/service-connect-to-troux/params.png)
5. Som **Godkendelsesmetode** skal du vælge **Grundlæggende** og angive dit brugernavn og din adgangskode (der skelnes mellem små og store bogstaver), og derefter skal du vælge **Log på**.
   
    ![](media/service-connect-to-troux/creds.png)
6. Efter godkendelsen starter importprocessen automatisk. Når processen er færdig, vises et nyt dashboard samt rapport og model i navigationsruden. Vælg dashboardet for at få vist dine importerede data.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Hvad nu?**

* Prøv at [stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Adgang til Troux OData-feed og Troux 9.5.1 eller derover er påkrævet.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Sådan finder du parametre
Dit kundeplejeteam kan give dig den entydige URL-adresse til dit Troux OData-feed

## <a name="troubleshooting"></a>Fejlfinding
Hvis du får vist en timeoutfejl, når du har angivet legitimationsoplysninger, skal du prøve at oprette forbindelse igen.

## <a name="next-steps"></a>Næste trin
[Kom i gang i Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)
