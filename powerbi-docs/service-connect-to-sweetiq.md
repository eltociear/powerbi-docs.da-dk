---
title: Opret forbindelse til SweetIQ med Power BI
description: SweetIQ til Power BI
services: powerbi
documentationcenter: 
author: SarinaJoan
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
ms.author: sarinas
ms.openlocfilehash: 5cbc48fc8c5787bcc5b7507284aaa5673dd0010d
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-sweetiq-with-power-bi"></a>Opret forbindelse til SweetIQ med Power BI
Power BI-indholdspakken henter data fra din SweetIQ-konto, og der oprettes standardindhold, så du nemt kan udforske dine data. Du kan bruge SweetIQ-indholdspakken til at analysere data om dine placeringer, annoncer, bedømmelser og anmeldelser. Dataene er indstillet til daglig opdatering for at sikre, at de data, du overvåger, er opdateret.

Opret forbindelse til [SweetIQ-indholdspakken](https://app.powerbi.com/groups/me/getdata/services/sweetiq) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. I navigationsruden til venstre skal du klikke på **Hent data.**
   
    ![](media/service-connect-to-sweetiq/getdata.png)
2. Vælg **SweetIQ**, og klik på **Hent.**
   
    ![](media/service-connect-to-sweetiq/sweetiq.png)
3. Angiv dit SweetIQ-klient-id. Dette er normalt en alfanumerisk værdi. Du får flere oplysninger om at finde denne værdi nedenfor.
   
    ![](media/service-connect-to-sweetiq/parameter.png)
4. Vælg godkendelsestypen **Nøgle**, og opgiv din Sweet IQ API-nøgle. Dette er normalt en alfanumerisk værdi. Se nedenfor for at få flere oplysninger om, hvordan du finder denne værdi.
   
    ![](media/service-connect-to-sweetiq/credentials.png)
5. Power BI begynder at indlæse dine data, hvilket kan tage noget tid, afhængigt af størrelsen af dataene i din konto. Når Power BI har importeret dataene, vises der et nyt dashboard og datasæt samt en ny rapport i venstre navigationsrude.
   
    ![](media/service-connect-to-sweetiq/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved at bruge **Opdater nu**

## <a name="finding-parameters"></a>Søg efter parametre
Klient-id'et og API-nøglen til denne indholdspakke er ikke de samme som dit SweetIQ-brugernavn og -adgangskode.

Vælg et klient-id for en af de klienter, din konto har adgang til. Du kan finde listen over klienter under "Klientadministration" i din SweetIQ-konto.

Kontakt administratoren for at få din API-nøgle for at få adgang til dataene for en bestemt klient.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data til Power BI](service-get-data.md)

