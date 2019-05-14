---
title: Gateway ydelsesovervågning (offentlig prøveversion)
description: I denne artikel indeholder oplysninger om overvågning af ydeevnen af aktiviteterne data gateway i det lokale miljø.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 8c5f4170383f31ea465ebb7035aebfb53f551982
ms.sourcegitcommit: af2b2238fe77eaa1b2392a19a143a0250b8665cf
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/11/2019
ms.locfileid: "65535361"
---
# <a name="gateway-performance-monitoring-public-preview"></a>Gateway ydelsesovervågning (offentlig prøveversion)

Du kan overvåge ydelsen, har gateway-administratorer traditionelt afhængig manuelt overvågning ydelsestællere Windows Ydelsesmåler-værktøjet. Vi tilbyder nu yderligere logføring og en [Gateway ydeevne PBI-skabelonfil](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) til at visualisere resultaterne. Denne funktion giver ny indsigt i brugen af gatewayen og gør det muligt at foretage fejlfinding af ydende være langsomme.

> [!NOTE]
> Denne funktion er tilgængelig i øjeblikket kun for datagatewayen i det lokale miljø i tilstanden standard, og ikke til personlig tilstand.

## <a name="enable-performance-logging"></a>Aktivér logføring af ydeevne

Hvis du vil aktivere denne funktion, Foretag følgende ændringer til den *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* fil i den "\Program Files\On-datagatewayen i det lokale miljø" mappe:

1. Opdater **QueryExecutionReportOn** til _True_ til at aktivere yderligere logføring for forespørgsler, der udføres ved hjælp af gatewayen. Når denne indstilling aktiveres opretter både rapporten forespørgsel udførelse og filerne forespørgsel Udførelsesrapport sammenlægning.

   ``` xml
   <setting name="QueryExecutionReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Opdater **SystemCounterReportOn** til _True_ til at aktivere yderligere logføring for hukommelse og CPU system tællere. Når denne indstilling aktiveres, opretter System tæller sammenlægning rapport filen.

   ```xml
   <setting name="SystemCounterReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Der er andre værdier i konfigurationsfilen, som du kan opdatere efter behov.

    - **ReportFilePath**: Angiver den sti, hvor de tre logfiler lagres. Som standard er denne sti enten "\Users\PBIEgwService\AppData\Local\Microsoft\On-premises data gateway\Report" eller "Windows\ServiceProfiles\PBIEgwService\AppData\Local\Microsoft\On lokale data gateway\Report", afhængigt af OS-version. Hvis du bruger en tjenestekonto til gatewayen bortset _PBIEgwService_, erstatter denne del af stien med navnet på tjenesten.
    - **ReportFileCount**: Angiver antallet af logfiler til hver form til at beholde. Standardværdien er 10.
    - **ReportFileSizeInBytes**: Angiver størrelsen på filen for at vedligeholde. Standardværdien er 104857600.
    - **QuerExecutionAggregationTimeInMinutes**: Angiver antallet minutter, som oplysninger om kørsel af forespørgsel aggregeres. Standardværdien er 5.
    - **SystemCounterAggregationTimeInMinutes**: Angiver antallet minutter, som systemet tællerne aggregeres. Standardværdien er 5.

1. Når du har foretaget ændringerne af konfigurationsfilen, genstarte gatewayen for disse config-værdier kan træde i kraft. Nu vil du se genereres på den placering, du angav for rapportfiler **ReportFilePath**.

    > [!NOTE]
    > Det kan tage op til 10 minutter, plus tidsrum, der er angivet for **QuerExecutionAggregationTimeInMinutes** i konfigurationsfilen indtil filer start vises i mappen.

## <a name="understand-performance-logs"></a>Forstå tjenesten performance logs

Når du slår denne funktion, kan vi oprette tre nye logfiler:

- Forespørgslen kørsel af rapporten
- Forespørgslen udførelse sammenlægning rapporten
- Systemet tæller sammenlægning rapporten

Forespørgslen udførelse rapporten indeholder oplysninger om kørsel af detaljerede forespørgsel. Vi har capture følgende attributter:

|Attribut |Beskrivelse |
| ---- | ---- |
|**GatewayObjectId** |Entydigt id for gatewayen. |
|**Anmodnings-id** |Entydigt id for en gateway-anmodning. Det kan være det samme for flere forespørgsler. |
|**DataSource** |Indeholder både datakildetype og datakilden. |
|**QueryTrackingId** |Entydigt id for en forespørgsel. |  
|**QueryExecutionEndTimeUTC** |Den tid, når forespørgslen udførelsen er fuldført. |
|**QueryExecutionDuration**(ms) |Varighed for udførelse af en forespørgsel. |
|**Forespørgselstype** |Typen af forespørgsel – f.eks, sendes forespørgslen kan være en Power BI-opdatering/DirectQuery eller forespørgsler fra PowerApps og Microsoft Flow. |
|**DataProcessingEndTimeUTC** |Den tid, når behandling af aktiviteter som sat i kø, hentning af data, komprimering, databehandling og fuldført osv. |
|**DataProcessingDuration**(ms) |Varighed for behandling af aktiviteter som sat i kø, hentning af data, komprimering, databehandling og osv. |
|**Succes** |Angiver, om forespørgslen lykkedes eller mislykkedes. |
|**ErrorMessage** |Angiver fejlmeddelelsen, hvis forespørgslen mislykkedes. |
| | |

Forespørgslen udførelse sammenlægning rapporten indeholder forespørgslen oplysninger, der aggregeres til et tidsinterval ved **GatewayObjectId**, **DataSource**, **succes**, og **Forespørgselstype**. Standardværdien er fem minutter, men du kan tilpasse den, som beskrevet nedenfor. Vi har capture følgende attributter:

|Attribut |Beskrivelse |
| ---- | ---- |
|**GatewayObjectId** |Entydigt id for gatewayen. |
|**AggregationStartTimeUTC** |Start på det tidsrum, som forespørgsel attributter blev samlet. |
|**AggregationEndTimeUTC** |Slutningen af det tidsrum, for hvilke forespørgsel blev samlet attributter. |
|**DataSource** |Indeholder både datakildetype og datakilden. |
|**Succes** |Angiver, om forespørgslen lykkedes eller mislykkedes. |
|**AverageQueryExecutionDuration**(ms) |Gennemsnitlig forespørgsel udførelsestid for aggregering tidsrum. |
|**MaxQueryExecutionDuration**(ms) |Maksimal forespørgsel udførelsestid for aggregering tidsrum. |
|**MinQueryExecutionDuration**(ms) |Mindste forespørgsel udførelsestid for aggregering tidsrum. |
|**Forespørgselstype** |Typen af forespørgsel – f.eks, sendes forespørgslen kan være en Power BI-opdatering/DirectQuery eller forespørgsler fra PowerApps og Microsoft Flow. |
|**AverageDataProcessingDuration**(ms) |Gennemsnitlig tid til behandling af aktiviteter som sat i kø, hentning af data, komprimering, databehandling, og så videre til aggregering tidsrum. |
|**MaxDataProcessingDuration**(ms) |Maksimale tid til behandling af aktiviteter som sat i kø, hentning af data, komprimering, databehandling og så videre til aggregering tidsrum. |
|**MinDataProcessingDuration**(ms) |Mindste tid til behandling af aktiviteter som sat i kø, hentning af data, komprimering, databehandling og så videre for aggregering tidsrum. |
|**Antal** |Antallet af forespørgsler. |
| | |

Systemet tæller sammenlægning rapporten indeholder værdier i systemets tæller sammenlægges til et tidsinterval. Standardværdien er fem minutter, men du kan tilpasse den, som beskrevet nedenfor. Vi har capture følgende attributter:

|Attribut |Beskrivelse |
| ---- | ---- |
|**GatewayObjectId** |Entydigt id for gatewayen. |
|**AggregationStartTimeUTC** |Start på det tidsrum, som har været samlet system tællere. |
|**AggregationEndTimeUTC** |Slutningen af den tidsvindue, for hvilket system tællere har været aggregeres. |
|**CounterName** |Systemet tællere, herunder hukommelse og CPU-forbrug af gatewayen, miks, og den generelle af maskinen vært for gatewayen. |
|**Maks.** |Maksimumværdien for system tælleren for aggregering tidsrum. |
|**Min** |Minimumværdien for system tælleren for aggregering tidsrum. |
|**Gennemsnit** |Gennemsnitlig værdi for system tælleren for aggregering tidsrum. |
| | |

## <a name="visualize-gateway-performance"></a>Visualiser gatewayens ydeevne

Nu kan du visualisere de data, der er i logfilerne.

1. Download den [Gateway ydeevne PBI skabelon](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) og åbne den ved hjælp af Power BI desktop.

1. I den dialogboks, der åbnes, kan du kontrollere, at stien til mappen svarer til værdien i **ReportFilePath**.

    ![Pop op-vindue til stien til mappen](media/service-gateway-performance-monitoring/gateway-folder-path-pop-up.png)

1. Vælg **Load**, og skabelonfilen starter indlæsningen af data fra dine logfiler. Alle visuelle elementer skal derefter udfyldes ved hjælp af dataene i rapporter.

1. Du kan eventuelt Gem denne fil som en PBIX og udgive den til din tjeneste til automatiske opdateringer.

Derudover kan du tilpasse skabelonfilen til dine behov. Få mere at vide om Power BI-skabeloner, kan du se dette [Microsoft Power BI-blogindlæg](https://powerbi.microsoft.com/en-us/blog/deep-dive-into-query-parameters-and-power-bi-templates/).