---
title: Deaktiver indstillingerne for beskyttelse af personlige oplysninger
description: "Sådan kan du slå Kombiner hurtigt til i den personlige gateway for at deaktivere indstillingerne for beskyttelse af personlige oplysninger ved opdatering."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 54d5f5ec2db890de0fbcef5ef0633548b90a6079
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Deaktiver indstillingerne for beskyttelse af personlige oplysninger i Power BI Gateway – Personlig
> [!NOTE]
> Der er en ny version af den personlige gateway til Power BI, der kaldes **datagateway i det lokale miljø (personlig tilstand)**. I følgende artikel beskrives den tidligere version af den personlige gateway, der blev kaldt **Power BI Gateway – Personal**, og som udgår og stopper med at virke efter den 31. juli 2017. Du kan finde oplysninger om den nye version af den personlige gateway, herunder, hvordan du installerer den nye version, i [ artiklen **Datagateway i det lokale miljø (personlig tilstand)**](service-gateway-personal-mode.md). Kombiner hurtigt er også tilgængeligt i den nye version af den personlige gateway, og den beskrives også i den artikel.
> 
> 

Du kan få vist følgende fejl baseret på indstillingerne for beskyttelse af personlige oplysninger for dine datakilder, når du bruger den personlige gateway.

> *Der opstod en fejl under behandling af dataene i datasættet.*
> 
> *[Dataene kan ikke kombineres] &lt;forespørgselsdelen&gt;/&lt;…&gt;/&lt;…&gt; får adgang til datakilder med niveauer af beskyttelse af personlige oplysninger, som ikke kan bruges sammen. Byg denne datakombination igen.*
> 
> 

Du kan løse fejlen ved at aktivere **Kombiner hurtigt**. **Kombiner hurtigt** ignorerer indstillingerne for beskyttelse af personlige oplysninger, så forskellige datakilder kan kombineres.

> [!NOTE]
> Der tages ikke højde for niveauerne for beskyttelse af personlige oplysninger, når data kombineres. Dette kunne give andre datakilder adgang til følsomme eller fortrolige oplysninger, når data kombineres.
> 
> 

## <a name="what-is-fast-combine"></a>Hvad er Kombiner hurtigt?
Hvis du vil vide mere om niveauer for beskyttelse af personlige oplysninger og Kombiner hurtigt, kan du se [Niveauer for beskyttelse af personlige oplysninger](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540). Som standard vil niveauerne for beskyttelse af personlige oplysninger blive indstillet til at være private, hvilket kan medføre ovennævnte fejl. Det skyldes, at indstillingen vil isolere datakilden fra andre datakilder. Et eksempel, hvor dette kan være et problem, er en forespørgsel med parametre, der henter input fra en anden datakilde.

Hvis du slår Kombiner hurtigt til, ignoreres indstillingen for beskyttelse af personlige oplysninger for at tillade, at forespørgslen kan udføres.

## <a name="turn-on-fast-combine"></a>Slå Kombiner hurtigt til
Du kan bruge følgende trin til at aktivere Kombiner hurtigt for din personlige gateway. Denne indstilling findes ikke for gatewayen i det lokale miljø.

1. Åbn **ConnectorConfig.xml**.  Den kan være placeret to forskellige steder på din computer.  Hvis du er administrator på computeren, er den placeret her.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Hvis du ikke er administrator på computeren, er den placeret her.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. Tilføj elementet **&lt;EnableFastCombine&gt;** med værdien true i konfigurationsfilen. Når du tilføjer dette element, slås **Kombiner hurtigt** til.
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. Afslut og genstart skærmen til konfiguration af gatewayen.
4. Der vises en status om, at Kombiner hurtigt er slået til.
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>Slå Kombiner hurtigt fra
1. Åbn **ConnectorConfig.xml**.  Den kan være placeret to forskellige steder på din computer.  Hvis du er administrator på computeren, er den placeret her.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Hvis du ikke er administrator på computeren, er den placeret her.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. Fjern elementet **&lt;EnableFastCombine&gt;** fra konfigurationsfilen. Hvis du fjerner elementet, slås **Kombiner hurtigt** fra.
3. Afslut og genstart skærmen til konfiguration af gatewayen.
4. Der vises ikke længere en status om, at **Kombiner hurtigt** er aktiveret.

## <a name="next-steps"></a>Næste trin
[Datagateway i det lokale miljø (personlig tilstand) – den nye version af den personlige gateway](service-gateway-personal-mode.md)
[Niveauer for beskyttelse af personlige oplysninger](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

