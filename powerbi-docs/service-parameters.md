---
title: Få vist og rediger parameterindstillinger for datasæt i Power BI-tjenesten
description: Forespørgselsparametre oprettes i Power BI Desktop, men kan gennemses og opdateres i Power BI-tjenesten
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: ac271e8013bce5824931153351a651644a716a2f
ms.sourcegitcommit: 5eb8632f653b9ea4f33a780fd360e75bbdf53b13
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965153"
---
# <a name="what-is-a-query-parameter"></a>Hvad er en forespørgselsparameter?
Forespørgselsparametre tilføjes i Power BI Desktop af rapportoprettere. Parametre gør det muligt at lave dele af rapporter, der afhænger af en eller flere parameter*værdier*. En rapportopretter kan f.eks. oprette en parameter, der begrænser dataene til et enkelt land/område, eller en parameter, der definerer acceptable formater for felter, såsom datoer, klokkeslæt og tekst.

![Fanen Hjem, der viser indstillingen Administrer parametre i Desktop](media/service-parameters/power-bi-manage-parameters.png)


## <a name="review-and-edit-parameters-in-power-bi-service"></a>Gennemse og rediger parametre i Power BI-tjenesten

Når parametrene er defineret i Desktop, når denne [rapport publiceres i Power BI-tjenesten](desktop-upload-desktop-files.md), følger parameterindstillingerne og valgene med denne rapport. Nogle parameterindstillinger kan gennemses og redigeres i Power BI-tjenesten – ikke de parametre, der begrænser de tilgængelige data, men de parametre, der definerer og beskriver acceptable værdier.

1. Vælg tandhjulsikonet ![tandhjulsikonet](media/service-parameters/power-bi-cog.png) i Power BI-tjenesten for at åbne **Indstillinger**.

2. Vælg fanen for **Datasæt**, og fremhæv et datasæt på listen. 
    
    ![Vinduet Indstillinger med fanen Datasæt valgt](media/service-parameters/power-bi-select-dataset2.png)

3. Udvid **Parametre**.  Hvis det valgte datasæt ikke indeholder parametre, får du vist en meddelelse med et link til Få mere at vide om forespørgselsparametre. Men hvis datasættet ikke har parametre, vil udvidelse af overskriften **Parametre** vise disse parametre. 

    ![Vinduet Indstillinger med udvidede Parametre](media/service-parameters/power-bi-settings.png)

    Gennemse parameterindstillingerne, og foretag de nødvendige ændringer. Nedtonede felter kan ikke redigeres. 


## <a name="next-steps"></a>Næste trin
En ad hoc-metode til at tilføje enkle parametre er at [ændre URL-adressen](service-url-filters.md).