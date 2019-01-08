---
title: Opret forbindelse til Troux med Power BI
description: Troux til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9152538204089ed9c75b69b79a08dc7496a8cca9
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007700"
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
6. Efter godkendelsen starter importprocessen automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
Adgang til Troux OData-feed og Troux 9.5.1 eller derover er påkrævet.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Sådan finder du parametre
Dit kundeplejeteam kan give dig den entydige URL-adresse til dit Troux OData-feed

## <a name="troubleshooting"></a>Fejlfinding
Hvis du får vist en timeoutfejl, når du har angivet legitimationsoplysninger, skal du prøve at oprette forbindelse igen.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

