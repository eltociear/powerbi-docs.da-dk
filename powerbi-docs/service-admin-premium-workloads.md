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
ms.openlocfilehash: 49a1f02e5aa327c2704b6c2d789934a43b760ad0
ms.sourcegitcommit: 0e50ebfa8762e19286566432870ef16d242ac78f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2019
ms.locfileid: "68962020"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Konfigurer arbejdsbelastninger i en Premium-kapacitet

I denne artikel beskrives, hvordan du aktiverer og konfigurerer arbejdsbelastninger for Power BI Premium-kapaciteter. Kapaciteter understøtter som standard kun de arbejdsbelastninger, der er tilknyttet kørende Power BI-forespørgsler. Du kan også aktivere og konfigurere yderligere arbejdsbelastninger for **[Kunstig intelligens (Cognitive Services)](service-cognitive-services.md)**, **[Dataflow](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** og **[Sideinddelte rapporter](paginated-reports-save-to-power-bi-service.md)**.

## <a name="default-memory-settings"></a>Standardindstillinger for hukommelse

Arbejdsbelastninger for forespørgsler optimeres til og begrænses af de ressourcer, som er fastlagt af din SKU for Premium-kapacitet. Premium-kapaciteter understøtter også yderligere arbejdsbelastninger, der kan bruge din kapacitets ressourcer. Standardværdier for hukommelse for disse arbejdsbelastninger er baseret på de kapacitetsnoder, der er tilgængelige for din SKU. Det maksimale antal hukommelsesindstillinger kan ikke akkumuleres. Hukommelse op til den angivne maksimale værdi tildeles dynamisk for kunstig intelligens og dataflow, men tildeles statisk for sideinddelte rapporter.

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office-SKU'er til SaaS-scenarier (Software som en service)

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| Kunstig intelligens | I/T | I/T | 20 % som standard, minimum 20 % | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % |
| Dataflow | I/T |20 % som standard, minimum 12 %  | 20 % som standard, minimum 5 %  | 20 % som standard, minimum 3 % | 20 % som standard, minimum 2 %  |
| Sideinddelte rapporter | I/T |I/T | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure-SKU'er til PaaS-scenarier (Platform as a Service)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Kunstig intelligens | I/T                      | 20 % som standard, minimum 100 %                     | 20 % som standard, minimum 50 %                     | 20 % som standard, minimum 20 % | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % |
| Dataflow         | 40 % som standard, minimum 40 % | 24 % som standard, minimum 24 % | 20 % som standard, minimum 12 % | 20 % som standard, minimum 5 %  | 20 % som standard, minimum 3 % | 20 % som standard, minimum 2 %   |
| Sideinddelte rapporter | I/T                      | I/T                      | I/T                     | 20 % som standard, minimum 10 % | 20 % som standard, minimum 5 % | 20 % som standard, minimum 2,5 % |
| | | | | | |

## <a name="workload-settings"></a>Indstillinger for arbejdsbelastning

### <a name="ai-preview"></a>Kunstig intelligens (prøveversion)

Udover indstillingen **Maks. hukommelse** findes der en yderligere indstilling for arbejdsbelastningen for kunstig intelligens, nemlig **Tillad brug fra Power BI Desktop**. Standarden er **Fra**. Denne indstilling er reserveret til fremtidig brug og vises muligvis ikke i alle lejere.

### <a name="datasets-preview"></a>Datasæt (prøveversion)

Arbejdsbelastningen for datasæt er som standard aktiveret og kan ikke deaktiveres. Denne arbejdsbelastning indeholder en yderligere indstilling for _XMLA-slutpunktet_ og et sæt indstillinger, der er relateret til ydeevne. Indstillingen for **XMLA-slutpunkt** angiver, at forbindelser fra klientprogrammer overholder medlemskabet af sikkerhedsgrupper, der er angivet for arbejdsområdet og appniveauerne. Du kan få mere at vide under [Opret forbindelse til datasæt med klientprogrammer og -værktøjer](service-premium-connect-tools.md).

Indstillingerne, der er relateret til ydeevne, er beskrevet i følgende tabel.

| Navn på indstilling | Beskrivelse | Forbrug |
|---------------------------------|----------------------------------------|----------------------------------------|
| **Maks. antal mellemliggende rækker** | Det maksimale antal mellemliggende rækker, der blev returneret af DirectQuery. Standardværdien er indstillet til 1000000, og det tilladte interval er mellem 100000 og 2147483647 | Styr effekten af ressourcetunge eller dårligt designede rapporter. |
| **Maksimal størrelse på offlinedatasæt (GB)** | Den maksimale størrelse på offlinedatasæt i hukommelsen. Dette er den komprimerede størrelse på disken. Standardværdien er angivet af SKU, og det tilladte interval er fra 0,1-10 GB | Undgå, at forfattere af rapporter publicerer et stort datasæt, der kan have negativ indvirkning på kapaciteten. |
| **Maks. antal resulterende rækker** | Angiver det maksimale antal rækker, der returneres i en DAX-forespørgsel. Standardværdien er angivet til -1 (ingen grænse), og det tilladte interval er mellem 100000 og 2147483647 | Styr effekten af ressourcetunge eller dårligt designede rapporter. |
| **Grænse for forespørgselshukommelse (%)** | Gælder kun for DAX-målinger og -forespørgsler. Angivet i % og begrænser, hvor meget hukommelse der kan bruges af midlertidige resultater under en forespørgsel. | Styr effekten af ressourcetunge eller dårligt designede rapporter. |
| **Timeout for forespørgsel (sekunder)** | Et heltal, der definerer timeout i sekunder for forespørgsler. Standarden er 3600 sekunder (eller 60 minutter). Nul (0) angiver, at der ikke er timeout for nogen forespørgsler. | Bevar bedre kontrol over forespørgsler, der kører i lang tid. |
|  |  |  |

### <a name="dataflows"></a>Dataflow

Udover indstillingen **Maks. hukommelse** findes der en yderligere indstilling for arbejdsbelastningen for dataflow, nemlig **Størrelse af objektbeholder**. Med denne indstilling kan du optimere ydeevnen af arbejdsbelastningen for dataflow, så der kan behandles mere komplekse, beregningstunge dataflow.

Når du opdaterer et dataflow, opretter arbejdsbelastningen for dataflow en objektbeholder for hver enhed i dataflowet. Hver objektbeholder kan have hukommelse op til den mængde, der er angivet i indstillingen Størrelse af objektbeholder. Standarden for alle SKU'er er **700 MB**. Det kan være en god idé at ændre denne indstilling, hvis:

- det tager for lang tid at opdatere dataflow, eller opdateringen af dataflow mislykkes pga. timeout.
- Dataflowenheder omfatter beregningstrin, f.eks. en joinforbindelse.  

Det anbefales, at du bruger appen [Power BI Premium Capacity Metrics](service-admin-premium-monitor-capacity.md) til at analysere ydeevnen af arbejdsbelastningen for dataflow. 

I nogle tilfælde forbedres ydeevnen ikke ved at øge størrelsen af objektbeholderen. Hvis dataflowet f.eks. kun henter data fra en kilde uden at udføre betydelige beregninger, vil det sandsynligvis ikke hjælpe at ændre størrelsen af objektbeholderen. Det kan hjælpe at øge størrelsen af objektbeholderen, hvis det giver arbejdsbelastningen for dataflowet mulighed for at allokere mere hukommelse til opdateringshandlinger. Når der er allokeret mere hukommelse, kan det reducere den tid, det tager at opdatere beregningstunge enheder.

Værdien af Størrelse på objektbeholder kan ikke overstige den maksimale hukommelse for arbejdsbelastningen for dataflow. En P1-kapacitet har f.eks. 25 GB hukommelse. Hvis Maks. hukommelse (%) for arbejdsbelastningen for dataflow er angivet til 20 %, kan Størrelse af objektbeholder (MB) ikke overstige 5000. I alle tilfælde kan Størrelse på objektbeholder ikke overstige Maks. hukommelse, heller ikke selvom du har angivet en højere værdi.

### <a name="paginated-reports-preview"></a>Sideinddelte rapporter (prøveversion)

Med sideinddelte rapporter kan der køres brugerdefineret kode, når en rapport gengives. Det kan f.eks. være at ændre tekstfarven dynamisk på baggrund af indhold, hvilket kan optage yderligere hukommelse. Power BI Premium kører sideinddelte rapporter i et afgrænset området i kapaciteten. Den angivne Maks. hukommelse bruges, *uanset om* arbejdsbelastningen er aktiv eller ej. Hvis du ændrer indstillingen Maks. hukommelse fra standardindstillingen, skal du sørge for, at du angiver den til at være lav nok til, at den ikke har negativ indvirkning på andre arbejdsbelastninger.

I nogle tilfælde kan arbejdsbelastningen for sideinddelte rapporter blive utilgængelig. I dette tilfælde vises der en fejltilstand for arbejdsbelastningen på administrationsportalen, og brugere får vist timeout for rapportgengivelse. Du kan afhjælpe dette problem ved at deaktivere arbejdsbelastningen og derefter aktivere den igen.

## <a name="configure-workloads"></a>Konfigurer arbejdsbelastninger

Maksimer din kapacitets tilgængelige ressourcer ved kun at aktivere arbejdsbelastninger, hvis de skal bruges. Rediger kun hukommelse og andre indstillinger, når du har fastslået, at standardindstillingerne ikke opfylder kravene til dine kapacitetsressourcer.

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Sådan konfigurerer du arbejdsbelastninger på Power BI-administrationsportalen

1. Under **Kapacitetsindstillinger** > **PREMIUM-KAPACITETER** skal du vælge en kapacitet.

1. Udvid **Arbejdsbelastninger** under **FLERE INDSTILLINGER**.

1. Aktivér en eller flere arbejdsbelastninger, og angiv en værdi for **Maks. hukommelse** og andre indstillinger.

1. Vælg **Anvend**.

### <a name="rest-api"></a>REST API

Arbejdsbelastninger kan aktiveres og tildeles til en kapacitet ved hjælp af REST API'erne for [Kapaciteter](https://docs.microsoft.com/rest/api/power-bi/capacities).

## <a name="monitoring-workloads"></a>Overvågning af arbejdsbelastninger

[Power BI Premium-appen Capacity Metrics](service-admin-premium-monitor-capacity.md) omfatter datasæt, dataflows og målepunkter i sideinddelte rapporter til overvågning af arbejdsbelastninger, der er aktiveret for dine kapaciteter. 

## <a name="next-steps"></a>Næste trin

[Optimering af kapaciteter i Power BI Premium](service-premium-capacity-optimize.md)     
[Selvbetjent dataforberedelse i Power BI med Dataflow](service-dataflows-overview.md)   
[Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)   

Har du flere spørgsmål? [Spørg Power BI-community'et](http://community.powerbi.com/)