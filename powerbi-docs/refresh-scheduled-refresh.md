---
title: Konfigurer planlagt opdatering
description: Følgende forklarer, hvordan man vælger en gateway og konfigurerer planlagt opdatering.
author: mgblythe
ms.reviewer: kayu''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/06/2019
ms.author: mblythe
LocalizationGroup: Data refresh
ms.openlocfilehash: 89f8b3d609b9433cc85d8af709eec828f924ad8e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73860712"
---
# <a name="configure-scheduled-refresh"></a>Konfigurer planlagt opdatering

>[!NOTE]
>Efter to måneders inaktivitet bliver planlagt opdatering af dine datasæt midlertidigt afbrudt. Du kan finde flere oplysninger under [*Planlagt opdatering*](#scheduled-refresh) senere i denne artikel.
>
>

Hvis dine datasæt understøtter planlagt opdatering ved hjælp af **Opdater nu** og **Planlagt opdatering**, er der et par krav og indstillinger, som er vigtige, for at opdateringen bliver en succes. Det er: **Gatewayforbindelse**, **Legitimationsoplysninger for datakilde** og **Planlagt opdatering**. Lad os se nærmere på dem hver især.

Følgende beskriver de tilgængelige indstillinger for både [Datagateway i det lokale miljø (personlig tilstand)](service-gateway-personal-mode.md) og [Datagateway i det lokale miljø](service-gateway-onprem.md).

Du kan gøre følgende for at åbne skærmen **Planlagt opdatering**.

1. Vælg **Flere indstillinger (...)** ud for et datasæt, der er angivet under **Datasæt**.
2. Vælg **Planlæg opdatering**.

    ![Planlæg opdatering](media/refresh-scheduled-refresh/dataset-menu.png)

## <a name="gateway-connection"></a>Gatewayforbindelse
Her vil du se forskellige valgmuligheder, afhængigt af om du har en personlig gateway eller en virksomhedsgateway, der er online og tilgængelig.

Hvis ingen gateway er tilgængelig, kan du se, at **Gatewayforbindelse** er deaktiveret. Du vil også se en besked om, hvordan du kan installere en personlig gateway.

![Gateway ikke konfigureret](media/refresh-scheduled-refresh/gateway-not-configured.png)

Hvis du har konfigureret en personlig gateway, kan den vælges, hvis den er online. Den vil blive vist som offline, hvis den ikke er tilgængelig.

![Gatewayforbindelse](media/refresh-scheduled-refresh/gateway-connection.png)

Du kan også vælge en virksomhedsgateway, hvis en sådan er tilgængelig for dig. Du kan kun se en tilgængelig virksomhedsgateway, hvis din konto er angivet på fanen **Brugere** i den datakilde, der er konfigureret for den pågældende gateway.

## <a name="data-source-credentials"></a>Legitimationsoplysninger for datakilde
### <a name="power-bi-gateway---personal"></a>Power BI Gateway – Personlig
Hvis du bruger den personlige gateway til at opdatere data, skal du angive legitimationsoplysningerne for at oprette forbindelse til backend-datakilden. Hvis du har oprettet forbindelse til en indholdspakke fra en onlinetjeneste, føres de legitimationsoplysninger, du angav for at oprette forbindelse, videre til planlagte opdateringer.

![Legitimationsoplysninger for datakilde](media/refresh-scheduled-refresh/data-source-credentials-pgw.png)

Du skal kun logge på en datakilde, første gang du opdaterer det pågældende datasæt. Når de er indtastet, gemmes disse legitimationsoplysninger sammen med datasættet.

> [!NOTE]
> I forbindelse med visse godkendelsesmetoder skal du også ændre adgangskoden for datakilden i **Legitimationsoplysninger til datakilde**, hvis den adgangskode, du brugte til at logge på en datakilde, udløber eller ændres.
>
>

Hvis noget går galt, har problemet som regel enten noget at gøre med, at gatewayen er offline, fordi den ikke kunne logge på Windows og starte tjenesten, eller at Power BI ikke kunne logge på datakilderne for at anmode om opdaterede data. Hvis opdateringen mislykkes, skal du tjekke datasættets indstillinger. Hvis gatewaytjenesten er offline, kan du se fejlen under **Status**. Hvis Power BI ikke kan logge på datakilderne, kan du se fejlen under Legitimationsoplysninger til datakilde.

### <a name="on-premises-data-gateway"></a>Datagateway i det lokale miljø
Hvis du bruger datagatewayen i det lokale miljø til at opdatere data, skal du ikke angive legitimationsoplysninger, da de defineres for datakilden af gatewayadministratoren.

![Kommandoen Planlæg opdatering](media/refresh-scheduled-refresh/data-source-credentials-egw.png)

> [!NOTE]
> Når du opretter forbindelse til SharePoint i det lokale miljø for at udføre en dataopdatering, understøtter Power BI kun godkendelsesmekanismerne: *Anonym*, *Basis* og *Windows (NTLM/Kerberos)* . Power BI understøtter ikke *ADFS* eller nogen form for *formularbaserede godkendelsesmekanismer* til dataopdatering af SharePoint-datakilder i lokale miljøer.
>
>

## <a name="scheduled-refresh"></a>Planlagt opdatering
I afsnittet **Planlagt opdatering** angiver du frekvensen og tidspunktet for opdatering af datasæt. Nogle datakilder kræver ikke, at en gateway skal kunne konfigureres til opdatering, og andre datakilder kræver en gateway.

Du skal indstille skyderen **Hold dine data opdateret** til **Ja** for at konfigurere indstillingerne.

> [!NOTE]
> Power BI-tjenesten stiler efter at starte opdateringen af dine data inden for **15 minutter** efter dit planlagte opdateringstidspunkt.
>
>

![Dialogboksen Planlagt opdatering](media/refresh-scheduled-refresh/scheduled-refresh.png)

> [!NOTE]
> Efter to måneders inaktivitet bliver planlagt opdatering af dine datasæt midlertidigt afbrudt. Et datasæt anses for at være inaktivt, når ingen brugere har besøgt et dashboard eller en rapport, der er baseret på datasættet. På dette tidspunkt modtager datasættets ejer en mail, der fortæller, at planlagte opdateringer er midlertidigt afbrudt, og tidsplanen for opdatering af datasættet vises som **deaktiveret**. For at fortsætte med planlagte opdateringer skal du ganske enkelt besøge et vilkårligt dashboard eller en vilkårlig rapport, der er baseret på datasættet.
>
>

## <a name="whats-supported"></a>Hvad understøttes?
Visse datasæt understøttes i forhold til forskellige gateways til planlagte opdateringer. Her er en forklaring på, hvad der er tilgængeligt.

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
**Power BI Desktop**

* Alle onlinedatakilder, der vises i **Hent data** og Forespørgselseditor i Power BI Desktop.
* Alle datakilder i det lokale miljø, der vises i **Hent data** og Forespørgselseditor i Power BI Desktop, undtagen Hadoop-fil (HDFS) og Microsoft Exchange.

**Excel**

> [!NOTE]
> I Excel 2016 og nyere udgaver angives Power-forespørgsel nu i afsnittet **Data** på båndet under **Hent og omdan data**.
>
>

* Alle onlinedatakilder, der vises i Power Query.
* Alle datakilder i det lokale miljø, der vises i Power Query, undtagen Hadoop-fil (HDFS) og Microsoft Exchange.
* Alle onlinedatakilder, der vises i Power Pivot.
* Alle datakilder i det lokale miljø, der vises i Power Pivot, undtagen Hadoop-fil (HDFS) og Microsoft Exchange.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

## <a name="troubleshooting"></a>Fejlfinding
Nogle gange går opdateringen af data muligvis ikke som forventet. Dette skyldes som regel et problem i forbindelse med en gateway. Se artiklerne om fejlfinding af gatewayen for at få oplysninger om værktøjer og kendte problemer.

- [Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)
- [Fejlfinding af Power BI Gateway – Personlig](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Næste trin
- [Opdatering af data i Power BI](refresh-data.md)  
- [Power BI Gateway – Personal](service-gateway-personal-mode.md)  
- [Datagateway i det lokale miljø (personlig tilstand)](service-gateway-onprem.md)  
- [Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  
- [Fejlfinding af Power BI Gateway – Personlig](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

