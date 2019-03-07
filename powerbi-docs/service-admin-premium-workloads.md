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
ms.date: 02/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 5b9bec67fef672d219b11bf3b3750959e72410b6
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226060"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Konfigurer arbejdsbelastninger i en Premium-kapacitet

I denne artikel beskrives, hvordan du aktiverer og konfigurerer arbejdsbelastninger for Power BI Premium-kapaciteter. Kapaciteter understøtter som standard kun de arbejdsbelastninger, der er tilknyttet kørende Power BI-forespørgsler. Arbejdsbelastninger for forespørgsler optimeres til og begrænses af de ressourcer, som er fastlagt af din SKU for Premium-kapacitet. Premium-kapaciteter understøtter også yderligere arbejdsbelastninger, der kan bruge kapacitetsressourcer.

## <a name="configure-workloads"></a>Konfigurer arbejdsbelastninger

Du kan aktivere og konfigurere yderligere arbejdsbelastninger for [Dataflow](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium) og [Sideinddelte rapporter](paginated-reports-save-to-power-bi-service.md). Standardværdier for hukommelse for disse arbejdsbelastninger er baseret på de kapacitetsnoder, der er tilgængelige for din SKU. Det maksimale antal hukommelsesindstillinger kan ikke akkumuleres. Hukommelse op til den angivne maksimale værdi tildeles dynamisk for dataflow, men tildeles statisk for sideinddelte rapporter. 

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


## <a name="next-steps"></a>Næste trin

[Administration og optimering af ressourcer for Power BI Premium-kapacitet](service-premium-understand-how-it-works.md)   
[Selvbetjent dataforberedelse i Power BI med Dataflow](service-dataflows-overview.md)   
[Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)   

Har du flere spørgsmål? [Spørg Power BI-community'et](http://community.powerbi.com/)