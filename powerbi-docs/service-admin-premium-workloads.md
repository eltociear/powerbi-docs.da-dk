---
title: Sådan konfigurerer du arbejdsbelastninger i Power BI Premium
description: Få mere at vide om, hvordan du konfigurerer arbejdsbelastninger i en Power BI Premium-kapacitet.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/15/2019
LocalizationGroup: Premium
ms.openlocfilehash: e22b598b81f34e80431d0def93d52f7301c500d4
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/18/2019
ms.locfileid: "57964634"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Konfigurer arbejdsbelastninger i en Premium-kapacitet

I denne artikel beskrives, hvordan du aktiverer og konfigurerer arbejdsbelastninger for Power BI Premium-kapaciteter. Kapaciteter understøtter som standard kun de arbejdsbelastninger, der er tilknyttet kørende Power BI-forespørgsler. Du kan også aktivere og konfigurere yderligere arbejdsbelastninger for **[AI (Cognitive Services)](service-cognitive-services.md)**, **[Dataflow](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** og **[Sideinddelte rapporter](paginated-reports-save-to-power-bi-service.md)**.

## <a name="default-memory-settings"></a>Standardindstillinger for hukommelse

Arbejdsbelastninger for forespørgsler optimeres til og begrænses af de ressourcer, som er fastlagt af din SKU for Premium-kapacitet. Premium-kapaciteter understøtter også yderligere arbejdsbelastninger, der kan bruge din kapacitets ressourcer. Standardværdier for hukommelse for disse arbejdsbelastninger er baseret på de kapacitetsnoder, der er tilgængelige for din SKU. Det maksimale antal hukommelsesindstillinger kan ikke akkumuleres. Hukommelse op til den angivne maksimale værdi tildeles dynamisk for AI og dataflow, men tildeles statisk for sideinddelte rapporter. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office-SKU'er til SaaS-scenarier (Software som en service)

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI (Cognitive Services) | 20 % som standard, min. TBD| 20 % som standard, min. TBD | 20 % som standard, min. TBD | 20 % som standard, min. TBD | 20 % som standard, min. TBD |
| Dataflow | I/T |20 % som standard, minimum 12 %  | 20 % som standard, minimum 5 %  | 20 % som standard, minimum 3 % | 20 % som standard, minimum 2 %  |
| Sideinddelte rapporter | I/T |I/T | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure-SKU'er til PaaS-scenarier (Platform as a Service)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI (Cognitive Services) | I/T                      | 20 % som standard, min. TBD                      | 20 % som standard, min. TBD                     | 20 % som standard, min. TBD | 20 % som standard, min. TBD | 20 % som standard, min. TBD |
| Dataflow         | 40 % som standard, minimum 40 % | 24 % som standard, minimum 24 % | 20 % som standard, minimum 12 % | 20 % som standard, minimum 5 %  | 20 % som standard, minimum 3 % | 20 % som standard, minimum 2 %   |
| Sideinddelte rapporter | I/T                      | I/T                      | I/T                     | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| | | | | | |

## <a name="configure-workloads"></a>Konfigurer arbejdsbelastninger

Maksimer din kapacitets tilgængelige ressourcer ved kun at aktivere arbejdsbelastninger, hvis de skal bruges. Rediger kun hukommelsesindstillinger, når du har bestemt, at standardindstillingerne ikke opfylder dine krav til kapacitetsressourcer.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Sådan konfigurerer du arbejdsbelastninger på Power BI-administrationsportalen

1. Under **Kapacitetsindstillinger** > **PREMIUM-KAPACITETER** skal du vælge en kapacitet.

1. Udvid **Arbejdsbelastninger** under **FLERE INDSTILLINGER**.

1. Aktivér en eller flere arbejdsbelastninger, og angiv en værdi for **Maks. hukommelse**.   

    
    ![Aktivér arbejdsbelastninger](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. Klik på **Anvend**.

> [!NOTE]
> Hvis arbejdsbelastningen for sideinddelte rapporter aktiveres, giver sideinddelte rapporter dig mulighed for at køre din egen kode, når du gengiver en rapport (f.eks. når du ændrer tekstfarven dynamisk baseret på indhold). Power BI Premium kører sideinddelte rapporter i et afgrænset området i kapaciteten. Den maksimale hukommelse, du angiver for dette område, bruges, uanset om arbejdsbelastningen er aktiv eller ej. Hvis du bruger Power BI-rapporter eller -dataflow i den samme egenskab, skal du sørge for, at du har angivet hukommelsen lavt nok til sideinddelte rapporter, så det ikke påvirker andre arbejdsbelastninger. I sjældne tilfælde kan arbejdsbelastningen i sideinddelte rapporter blive utilgængelige. I dette tilfælde viser arbejdsbelastningen en fejltilstand på administrationsportalen, og brugere får vist timeout for gengivelse af rapporter. Du kan afhjælpe dette problem ved at deaktivere arbejdsbelastningen og derefter aktivere den igen.

### <a name="rest-api"></a>REST API

Arbejdsbelastninger kan aktiveres og tildeles til en kapacitet ved hjælp af REST API'erne for [Kapaciteter](https://docs.microsoft.com/rest/api/power-bi/capacities).

## <a name="monitoring-workloads"></a>Overvågning af arbejdsbelastninger

[Power BI Premium-appen Capacity Metrics](service-admin-premium-monitor-capacity.md) omfatter datasæt, dataflows og målepunkter i sideinddelte rapporter til overvågning af arbejdsbelastninger, der er aktiveret for dine kapaciteter. 

## <a name="next-steps"></a>Næste trin

[Administration og optimering af ressourcer for Power BI Premium-kapacitet](service-premium-understand-how-it-works.md)   
[Selvbetjent dataforberedelse i Power BI med Dataflow](service-dataflows-overview.md)   
[Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)   

Har du flere spørgsmål? [Spørg Power BI-community'et](http://community.powerbi.com/)