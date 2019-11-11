---
title: Administrer din datakilde – Oracle
description: Sådan administrerer du en datagateway i det lokale miljø samt de datakilder, der hører til denne gateway.
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: cb7856b0b5ac84684e8d0648b91e45805218cead
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73872476"
---
# <a name="manage-your-data-source---oracle"></a>Administrer din datakilde – Oracle

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Når du har [installeret datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-install), skal du [tilføje datakilder](service-gateway-data-sources.md#add-a-data-source), der kan bruges sammen med gateway'en. Denne artikel indeholder oplysninger om, hvordan du arbejder med gateways og Oracle-datakilder, der enten bruges til planlagte opdateringer eller DirectQuery.

## <a name="install-the-oracle-client"></a>Installér Oracle-klienten

Oracle Data Provider til .NET (ODP.NET) skal være installeret og konfigureret, før du kan oprette forbindelse mellem din gateway og Oracle-serveren. ODP.NET er en del af Oracle Data Access Components (ODAC).

Til 32-bit versioner af Power BI Desktop skal du bruge følgende link til at downloade og installere 32-bit Oracle-klienten:

* [32-bit Oracle Data Access Components (ODAC) med Oracle Developer Tools til Visual Studio (12.1.0.2.4)](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Til 64-bit versioner af Power BI Desktop eller til datagatewayen i det lokale miljø skal du bruge følgende link til at downloade og installere 64-bit Oracle-klienten:

* [64-bit ODAC 12.2c Release 1 (12.2.0.1.0) til Windows x64](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

Når klienten er installeret, skal du konfigurere filen tnsnames.ora med de korrekte oplysninger om din database. Power BI Desktop og gatewayen forsvinder fra net_service_name, der er defineret i filen tnsnames.ora. Hvis net_service_name ikke er konfigureret, kan du ikke oprette forbindelse. Standardstien til tnsnames.ora er `[Oracle Home Directory]\Network\Admin\tnsnames.ora`. Se flere oplysninger om, hvordan du konfigurerer tnsnames.ora-filer ved at se [Oracle: Lokale navngivningsparametre (tnsnames.ora)](https://docs.oracle.com/cd/B28359_01/network.111/b28317/tnsnames.htm).

### <a name="example-tnsnamesora-file-entry"></a>Eksempel på indtastning i filen tnsnames.ora

Her er det grundlæggende format for en post i tnsnames.ora:

```
net_service_name=
 (DESCRIPTION=
   (ADDRESS=(protocol_address_information))
   (CONNECT_DATA=
     (SERVICE_NAME=service_name)))
```

Her er et eksempel på udfyldte server- og portoplysninger:

```
CONTOSO =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracleserver.contoso.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = CONTOSO)
    )
  )
```

## <a name="add-a-data-source"></a>Tilføj en datakilde

Du kan finde flere oplysninger om, hvordan du tilføjer en datakilde i [Tilføj en datakilde](service-gateway-data-sources.md#add-a-data-source). Under **Datakildetype** skal du vælge **Oracle**.

![Tilføj Oracle-datakilden](media/service-gateway-onprem-manage-oracle/data-source-oracle.png)

Når du har valgt Oracle-datakildetypen, skal du udfylde oplysningerne om datakilden, hvilket omfatter **Server** og **Database**. 

Under **Godkendelsesmetode** kan du vælge enten **Windows**  eller **Basic**. Vælg **Basic**, hvis du har planer om at bruge en konto, der er oprettet i Oracle, i stedet for Windows-godkendelse. Angiv derefter de legitimationsoplysninger, der skal bruges til denne datakilde.

> [!NOTE]
> Alle forespørgsler til datakilden kører ved hjælp af disse legitimationsoplysninger. Hvis du vil have mere at vide om, hvor legitimationsoplysningerne gemmes, skal du se [Lagring af krypterede legitimationsoplysninger i cloudmiljøet](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Angivelse af indstillinger for datakilden](media/service-gateway-onprem-manage-oracle/data-source-oracle2.png)

Når du har udfyldt alt, skal du vælge **Tilføj**. Du kan nu bruge denne datakilde til planlagt opdatering eller DirectQuery mod en Oracle-server, der er i det lokale miljø. Du får vist *Forbindelsen blev oprettet*, hvis det lykkes.

![Visning af forbindelsesstatus](media/service-gateway-onprem-manage-oracle/datasourcesettings4.png)

### <a name="advanced-settings"></a>Avancerede indstillinger

Du kan eventuelt konfigurere niveauet for beskyttelse af personlige oplysninger for datakilden. Denne indstilling styrer, hvordan data kan kombineres. Det bruges kun for planlagte opdateringer. Indstillingen for beskyttelse af personlige oplysninger gælder ikke for DirectQuery. Hvis du vil vide mere om niveauer for beskyttelse af personlige oplysninger, skal du se [Niveauer for beskyttelse af personlige oplysninger (Power-forespørgsel)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Angivelse af niveauet for beskyttelse af personlige oplysninger](media/service-gateway-onprem-manage-oracle/datasourcesettings9.png)

## <a name="use-the-data-source"></a>Brug datakilden

Når du opretter datakilden, er den tilgængelig til brug med enten DirectQuery-forbindelser eller via en planlagt opdatering.

> [!WARNING]
> Server- og databasenavne skal matche mellem Power BI Desktop og datakilden i datagatewayen i det lokale miljø.

Linket mellem dit datasæt og datakilden i gatewayen er baseret på dit servernavn og databasenavn. Disse navne skal være ens. Hvis du f.eks. angiver en IP-adresse for servernavnet i Power BI Desktop, skal du bruge IP-adressen for datakilden i konfigurationen af gatewayen. Dette navn skal også stemme overens med et alias defineret i filen tnsnames.ora. Se flere oplysninger om filen tnsnames.ora i [Installér Oracle-klienten](#install-the-oracle-client).

Dette krav gælder både for DirectQuery og planlagt opdatering.

### <a name="use-the-data-source-with-directquery-connections"></a>Brug datakilden med DirectQuery-forbindelser

Sørg for, at servernavnet og databasenavnet matcher mellem Power BI Desktop og den konfigurerede datakilde for gatewayen. Du skal også at sørge for, at din bruger er angivet under fanen **Brugere** i datakilden for at kunne udgive DirectQuery-datasæt. Valget til DirectQuery sker i Power BI Desktop, når du importerer data første gang. Du kan finde flere oplysninger om, hvordan du bruger DirectQuery under [Brug DirectQuery i Power BI Desktop](desktop-use-directquery.md).

Når du publicerer fra enten Power BI Desktop eller **Hent Data**, bør dine rapporter begynde at fungere. Det kan tage flere minutter, efter du har oprettet datakilden i gateway'en, før forbindelsen kan bruges.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Brug datakilden med planlagt opdatering

Hvis du er angivet under fanen **Brugere** i den datakilde, der er konfigureret i gatewayen, og servernavnet og databasenavnet stemmer overens, får du vist gatewayen som en mulighed, der kan bruges sammen med en planlagt opdatering.

![Visning af brugerne](media/service-gateway-onprem-manage-oracle/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="troubleshooting"></a>Fejlfinding

Du kan støde på flere fejl fra Oracle, når navngivningssyntaksen enten er forkert eller ikke konfigureret korrekt:

* ORA-12154: TNS: Den angivne forbindelsesidentifikator kunne ikke løses.
* ORA-12514: TNS: Lyttefunktionen kender i øjeblikket ikke til den anmodede tjeneste i forbindelsesbeskrivelsen.
* ORA-12541: TNS: Ingen lyttefunktion.
* ORA-12170: TNS: Der opstod timeout for forbindelsen.
* ORA-12504: TNS: Lyttefunktionen fik ikke SERVICE_NAME i CONNECT_DATA.

Disse fejl kan opstå, hvis Oracle-klienten enten ikke er installeret eller konfigureret korrekt. Hvis den er installeret, skal du bekræfte, at filen tnsnames.ora er konfigureret korrekt, og at du bruger det korrekte net_service_name. Du skal også sikre, at net_service_name er det samme for den maskine, der bruger Power BI Desktop, og den maskine, der kører gatewayen. Du kan finde flere oplysninger under [Installér Oracle-klienten](#install-the-oracle-client).

> [!NOTE]
> Du støder måske også på et kompatibilitetsproblem mellem Oracle-serverversionen og Oracle-klientversionen. Disse versioner skal normalt stemme overens.

Du kan finde yderligere oplysninger om fejlfinding i forbindelse med gatewayen i [Fejlfinding af datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-tshoot).

## <a name="next-steps"></a>Næste trin

* [Foretag fejlfinding af gateways – Power BI](service-gateway-onprem-tshoot.md)
* [Power BI Premium](service-premium.md)

Har du flere spørgsmål? Prøv at spørge [Power BI-community'et](https://community.powerbi.com/).

