---
title: Sådan konfigurerer du arbejdsbelastninger i Power BI Premium
description: Få mere at vide om, hvordan du konfigurerer arbejdsbelastninger i en Power BI Premium-kapacitet.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/15/2019
LocalizationGroup: Premium
ms.openlocfilehash: c84bebef5589ec391e3640ff3be674b1fb5a0ebd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564871"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Konfigurer arbejdsbelastninger i en Premium-kapacitet

I denne artikel beskrives, hvordan du aktiverer og konfigurerer arbejdsbelastninger for Power BI Premium-kapaciteter. Kapaciteter understøtter som standard kun de arbejdsbelastninger, der er tilknyttet kørende Power BI-forespørgsler. Du kan også aktivere og konfigurere yderligere arbejdsbelastninger for **[AI (Cognitive Services)](service-cognitive-services.md)** , **[Dataflow](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** og **[Sideinddelte rapporter](paginated-reports-save-to-power-bi-service.md)** .

## <a name="default-memory-settings"></a>Standardindstillinger for hukommelse

Arbejdsbelastninger for forespørgsler optimeres til og begrænses af de ressourcer, som er fastlagt af din SKU for Premium-kapacitet. Premium-kapaciteter understøtter også yderligere arbejdsbelastninger, der kan bruge din kapacitets ressourcer. Standardværdier for hukommelse for disse arbejdsbelastninger er baseret på de kapacitetsnoder, der er tilgængelige for din SKU. Det maksimale antal hukommelsesindstillinger kan ikke akkumuleres. Hukommelse op til den angivne maksimale værdi tildeles dynamisk for AI og dataflow, men tildeles statisk for sideinddelte rapporter. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office-SKU'er til SaaS-scenarier (Software som en service)

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI | I/T | I/T | 20 % som standard, minimum 20 % | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % |
| Dataflow | I/T |20 % som standard, minimum 12 %  | 20 % som standard, minimum 5 %  | 20 % som standard, minimum 3 % | 20 % som standard, minimum 2 %  |
| Sideinddelte rapporter | I/T |I/T | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure-SKU'er til PaaS-scenarier (Platform as a Service)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI | I/T                      | standard med 20%. 100% minimum                     | standard med 20%. 50% minimum                     | 20 % som standard, minimum 20 % | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % |
| Dataflow         | 40 % som standard, minimum 40 % | 24 % som standard, minimum 24 % | 20 % som standard, minimum 12 % | 20 % som standard, minimum 5 %  | 20 % som standard, minimum 3 % | 20 % som standard, minimum 2 %   |
| Sideinddelte rapporter | I/T                      | I/T                      | I/T                     | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| | | | | | |

## <a name="workload-settings"></a>Indstillinger for arbejdsbelastning

### <a name="ai-preview"></a>AI (prøveversion)

I tillæg til de **Max Memory** indstilling, AI-arbejdsbelastningen er en ekstra indstilling, **fra Power BI Desktop at tillade brug**. Standarden er **fra**. Denne indstilling er reserveret til fremtidig brug og må ikke optræde i alle lejere.

### <a name="datasets-preview"></a>Datasæt (prøveversion)

Som standard arbejdsbyrden datasæt er aktiveret og kan ikke deaktiveres. Denne arbejdsbelastning indeholder en yderligere indstilling, **XMLA-slutpunktet**. Standarden er **1**, betydning, der er aktiveret. Denne indstilling angiver forbindelser fra klientprogrammer overholde medlemskab af sikkerhedsgrupper angivet på app-arbejdsområde og de niveauer. Hvis du vil vide mere, kan du se [Opret forbindelse til datasæt med klientprogrammer og værktøjer](service-premium-connect-tools.md).

### <a name="dataflows"></a>Dataflow

I tillæg til de **Max Memory** indstilling, Dataflows arbejdsbyrden har en yderligere indstilling, **Container størrelse**. Denne indstilling giver dig mulighed at optimere dataflowet arbejdsbelastning til behandling af mere komplekse, beregning tunge dataflows.

Når du opdaterer en dataflowet, lægge dataflowet arbejdsbyrden æg en objektbeholder for hver enhed i dataflowet. Hver beholder kan tage hukommelse op til diskenheden i, der er angivet i indstillingen Container størrelse. Er standard for alle varenumre **700 MB**. Du vil ændre denne indstilling, hvis:

- Dataflows tage for lang tid at opdatere eller dataflowet opdatering mislykkes på en timeout.
- Dataflowet objekter indeholder trin beregninger, f.eks, en joinforbindelse.  

Det er anbefales, at du bruger den [Power BI Premium-kapacitet målepunkter](service-admin-premium-monitor-capacity.md) app til at analysere arbejdsbelastningen dataflowet. 

I nogle tilfælde kan kan øge størrelsen objektbeholder ikke forbedre ydeevnen. For eksempel hvis dataflowet er hentning af data fra en kilde uden at udføre betydelige beregninger, hjælpe ændring af størrelsen på container sandsynligvis ikke. Øge størrelsen objektbeholder kan hjælpe, hvis det vil muliggøre dataflowet arbejdsbyrden til at allokere mere hukommelse til enhed opdatering. Ved at have mere hukommelse, der er allokeret, kan det reducere den tid, det tager for at opdatere stærkt beregnet enheder. 

Container størrelse værdien må ikke overstige den maksimale hukommelse for Dataflows arbejdsbelastningen. F.eks, har en kapacitet på P1 25GB hukommelse. Hvis dataflowet arbejdsbyrden Max Memory (%) er angivet til 20%, Container størrelse (MB) må ikke overstige 5000. Container størrelsen må ikke overstige den Max Memory, i alle tilfælde, selvom du har angivet en højere værdi. 

### <a name="paginated-reports-preview"></a>Sideinddelte rapporter (prøveversion)

Sideinddelte rapporter giver mulighed for brugerdefineret kode til at køre gengivelse af en rapport. F.eks, dynamisk at ændre tekstfarven, der er baseret på indhold, som kan gøre mere hukommelse. Power BI Premium kører sideinddelte rapporter i et afgrænset området i kapaciteten. Den Max Memory angivet, bruges *hvorvidt* arbejdsbyrden er aktiv. Hvis du ændrer indstillingen Max hukommelse fra standard Sørg for, at du konfigurere den lave er nok til, at det ikke påvirke andre arbejdsbelastninger.

I nogle tilfælde kan sideinddelte rapporter arbejdsbyrden bliver utilgængelige. I dette tilfælde arbejdsbelastningen viser fejltilstand i administrationsportalen, og brugere se timeouts til gengivelse af rapporten. For at afhjælpe dette problem, skal du deaktivere arbejdsbelastningen og derefter aktivere den igen.

## <a name="configure-workloads"></a>Konfigurer arbejdsbelastninger

Maksimer din kapacitets tilgængelige ressourcer ved kun at aktivere arbejdsbelastninger, hvis de skal bruges. Rediger kun hukommelsesindstillinger, når du har bestemt, at standardindstillingerne ikke opfylder dine krav til kapacitetsressourcer.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Sådan konfigurerer du arbejdsbelastninger på Power BI-administrationsportalen

1. Under **Kapacitetsindstillinger** > **PREMIUM-KAPACITETER** skal du vælge en kapacitet.

1. Udvid **Arbejdsbelastninger** under **FLERE INDSTILLINGER**.

1. Aktivér en eller flere arbejdsbelastninger, og angiv en værdi for **Maks. hukommelse**.   

    
    ![Aktivér arbejdsbelastninger](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. Klik på **Anvend**.

### <a name="rest-api"></a>REST API

Arbejdsbelastninger kan aktiveres og tildeles til en kapacitet ved hjælp af REST API'erne for [Kapaciteter](https://docs.microsoft.com/rest/api/power-bi/capacities).

## <a name="monitoring-workloads"></a>Overvågning af arbejdsbelastninger

[Power BI Premium-appen Capacity Metrics](service-admin-premium-monitor-capacity.md) omfatter datasæt, dataflows og målepunkter i sideinddelte rapporter til overvågning af arbejdsbelastninger, der er aktiveret for dine kapaciteter. 

## <a name="next-steps"></a>Næste trin

[Optimering af Power BI Premium-kapaciteter](service-premium-capacity-optimize.md)     
[Selvbetjent dataforberedelse i Power BI med Dataflow](service-dataflows-overview.md)   
[Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)   

Har du flere spørgsmål? [Spørg Power BI-community'et](http://community.powerbi.com/)