---
title: Opret forbindelse til Snowflake med Power BI
description: Snowflake med SSO til Power BI
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: gepopell
LocalizationGroup: Connect to services
ms.openlocfilehash: 5e5519e30be30d6367791d1b6822196b407a21b1
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83300315"
---
#  <a name="connecting-to-snowflake-in-power-bi-service"></a>Oprettelse af forbindelse til Snowflake i Power BI-tjenesten

## <a name="introduction"></a>Introduktion

Oprettelse af forbindelse til Snowflake i Power BI-tjenesten adskiller sig kun fra andre connectors på én måde, og det er, at der tilbydes en ekstra funktion til AAD (med mulighed for SSO). Forskellige dele af integrationen kræver forskellige administrative roller på tværs af Snowflake, Power BI og Azure. Du kan også vælge at aktivere AAD-godkendelse uden at bruge SSO. Grundlæggende godkendelse fungerer på samme måde som andre connectors i tjenesten.

Hvis du er interesseret i at konfigurere AAD-integration samt eventuelt aktivere SSO:
* Hvis du er Snowflake-administrator, skal du læse artiklen [Power BI SSO til Snowflake – introduktion](https://docs.snowflake.net/manuals/LIMITEDACCESS/oauth-powerbi.html) i dokumentationen til Snowflake.
* Hvis du er Power BI-administrator, kan du se i afsnittet 'Power BI tjenestekonfiguration – Administrationsportal'
* Hvis du er Power BI-administrator, kan du se afsnittet 'Konfiguration af Power BI-tjeneste – Administrationsportal'

## <a name="power-bi-service-configuration"></a>Konfiguration af Power BI-tjeneste

### <a name="admin-portal"></a>Administrationsportal

Hvis du vil aktivere SSO, skal lejeradministratoren gå til administrationsportalen og godkende, at der sendes Power BI AAD-legitimationsoplysninger til Snowflake.

![Lejeradministrations indstilling for Snowflake SSO](media/service-connect-snowflake/snowflakessotenant.png)

Gå til "Administrationsportal", vælg elementet "Lejerindstillinger" i sidepanelet, rul ned til "Integrationsindstillinger", hvorefter du får vist en indstilling for "Snowflake SSO".

Som nævnt skal du aktivere indstillingen manuelt for at kunne sende dit AAD-token til Snowflake-serverne. Hvis du vil aktivere den, skal du klikke på til/fra-knappen 'Deaktiveret', trykke på Anvend og vente på, at ændringen af indstillingerne træder i kraft. Det kan tage op til en time for tjenesten at overføre konfigurationen.

Når det er gjort, kan du bruge rapporter sammen med SSO.

### <a name="configuring-a-dataset-with-aad"></a>Konfiguration af et datasæt med AAD

Når en rapport, der er baseret på Snowflake-connectoren, er publiceret på internettet, skal opretteren af datasættet gå til det relevante arbejdsområde i Power BI-webtjenesten, vælge 'Datasæt' og vælge 'Indstillinger' (under menuen '... ' for at få vist yderligere handlinger ud for det relevante datasæt).

På grund af den måde, Power BI fungerer på, fungerer SSO kun, når der ikke køres nogen datakilder via datagatewayen i det lokale miljø.

* Hvis du kun bruger en Snowflake-kilde i din datamodel, kan du bruge SSO, hvis du vælger ikke at bruge datagatewayen i det lokale miljø
* Hvis du bruger en Snowflake-kilde sammen med en anden kilde, kan du bruge SSO, hvis ingen af kilderne bruger datagatewayen i det lokale miljø
* Hvis du benytter en Snowflake-kilde via en datagateway i det lokale miljø, understøttes AAD-legitimationsoplysninger ikke i øjeblikket. Det kan være relevant, hvis du forsøger at få adgang til en VNet fra en enkelt IP-adresse, hvor gatewayen er installeret, i stedet for fra hele Power BI-IP-intervallet.
* Hvis du bruger en Snowflake-kilde sammen med en anden kilde, der kræver en gateway, skal du også bruge Snowflake via datagatewayen i det lokale miljø og kan ikke bruge SSO.

Du kan finde flere oplysninger om, hvordan du bruger datagatewayen i det lokale miljø, i artiklen [Hvad er en datagateway i det lokale miljø?](https://docs.microsoft.com/power-bi/service-gateway-onprem)

Hvis du ikke bruger gatewayen, er du klar. Hvis du har Snowflake-legitimationsoplysninger konfigureret i din datagateway i det lokale miljø, men kun bruger den pågældende datakilde i din model, kan du klikke på til/fra-knappen på siden Indstillinger for datasæt for at slå gatewayen for den pågældende datamodel fra.

![Datasætindstilling, hvor gatewayen er slået fra](media/service-connect-snowflake/snowflake_gateway_toggle_off.png)

Opretteren af datasættet skal vælge 'Legitimationsoplysninger for datakilde' og logge på. Datasættet kan logges på Snowflake med grundlæggende legitimationsoplysninger eller OAuth2-legitimationsoplysninger (AAD). Hvis du vælger at bruge AAD, kan datasættet aktiveres til at bruge SSO. Når denne første bruger logger på Snowflake for datasættet, skal brugeren vælge den indstilling, der kræver, at andre brugere skal have brugt deres Oauth2-legitimationsoplysninger til at hente data. Dette aktiverer AAD SSO. Uanset om den oprindelige bruger logger på med grundlæggende godkendelse eller OAuth2 (AAD), sendes AAD-legitimationsoplysningerne til SSO. 

![Datasætindstilling for Snowflake SSO](media/service-connect-snowflake/snowflakessocredui.png)

Når det er gjort, skal eventuelle yderligere brugere automatisk bruge AAD-godkendelsen til at oprette forbindelse til data fra det pågældende Snowflake-datasæt.

Hvis du vælger ikke at aktivere SSO, anvender de brugere, der opdaterer rapporten, legitimationsoplysningerne for den bruger, der er logget på, som de fleste andre Power BI-rapporter.

### <a name="troubleshooting"></a>Fejlfinding

Hvis du støder på problemer med integrationen, skal du se [fejlfindingsvejledningen](https://docs.snowflake.net/manuals/LIMITEDACCESS/oauth-powerbi.html#troubleshooting) til Snowflake.

