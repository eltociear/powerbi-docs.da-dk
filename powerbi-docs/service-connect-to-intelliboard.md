---
title: Opret forbindelse til IntelliBoard med Power BI
description: IntelliBoard til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e912c47c58c96de8d2875b83a530468135e93ef2
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185920"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Opret forbindelse til IntelliBoard med Power BI
IntelliBoard giver forenklet adgang til dine data i Moodle-systemet til læringsstyring via Reporting Services. IntelliBoard-indholdspakken til Power BI indeholder yderligere analyse, herunder målinger af dine kurser, registrerede brugere, samlet ydeevne og din LMS-aktivitet.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Opret forbindelse til [IntelliBoard-indholdspakken](https://app.powerbi.com/getdata/services/intelliboard) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. Vælg **IntelliBoard**, og vælg derefter **Hent**.  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. Vælg **OAuth 2** og derefter **Log på**. Når du bliver spurgt, skal du angive dine legitimationsoplysninger til IntelliBoard.
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. Når der er oprettet forbindelse, indlæses der automatisk et dashboard, en rapport og et datasæt. Når det er fuldført, opdateres felterne med data fra din IntelliBoard-konto.
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Indholdspakken indeholder data fra følgende tabeller:  

    - Activity  
    - Agents  
    - Auth  
    - Countries  
    - CoursesProgress  
    - Enrollments
    - Lang  
    - Platform  
    - Totals  
    - UsersProgress    

## <a name="system-requirements"></a>Systemkrav
Der kræves en IntelliBoard-konto med rettigheder til overstående tabeller for at kunne instantiere denne indholdspakke.

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](power-bi-overview.md)

[Grundlæggende begreber for designere i Power BI-tjenesten](service-basic-concepts.md)

