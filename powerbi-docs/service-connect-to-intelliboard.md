---
title: Opret forbindelse til IntelliBoard med Power BI
description: IntelliBoard til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c397ec0f302ec558e0277c92a871a94dd7f28e87
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34241501"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Opret forbindelse til IntelliBoard med Power BI
IntelliBoard giver forenklet adgang til dine data i Moodle-systemet til læringsstyring via rapporteringstjenester. IntelliBoard-indholdspakken til Power BI indeholder yderligere analyse, herunder målinger af dine kurser, registrerede brugere, samlet ydeevne og din LMS-aktivitet.

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

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
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
[Kom i gang med Power BI](service-get-started.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

