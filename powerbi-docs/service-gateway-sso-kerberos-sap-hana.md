---
title: Brug Kerberos til enkeltlogon (SSO) til SAP HANA
description: Konfigurer din SAP HANA-server for at aktivere SSO fra Power BI-tjenesten
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 4e94781b3a424e894e0f0e2209ec48efb25c5db5
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106302"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>Brug Kerberos til enkeltlogon (SSO) til SAP HANA

I denne artikel beskrives, hvordan du konfigurerer din SAP HANA-server for at aktivere SSO fra Power BI-tjenesten.

> [!NOTE]
> Fuldfør trinnene i denne artikel ud over trinnene i [Konfigurer SSO i Kerberos](service-gateway-sso-kerberos.md), før du forsøger at opdatere en SAP HANA-baseret rapport, der bruger SSO i Kerberos.

## <a name="enable-sso-for-sap-hana"></a>Aktivér SSO til SAP HANA

Hvis du vil aktivere SSO til SAP HANA, skal du følge disse trin:

* Kontrollér, at SAP HANA-serveren kører den påkrævede minimumversion, hvilket afhænger af niveauet af din SAP HANA-serverplatform:
  * [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* Installér SAP's seneste HANA ODBC-driver på gatewaycomputeren.  Minimumversionen er HANA ODBC version 2.00.020.00 fra august 2017.

Kontrollér, at SAP HANA-serveren er konfigureret til Kerberos-baseret SSO. Du kan finde flere oplysninger om konfiguration af SSO til SAP HANA ved hjælp af Kerberos under [Enkeltlogon ved hjælp af Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) i Sikkerhedsvejledning til SAP HANA. Se også linket på den side – især SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory.

Det anbefales også, at du følger disse ekstra trin, som kan give en mindre forbedring af ydeevnen.

1. Find og åbn denne konfigurationsfil i installationsmappen for gatewayen: *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

2. Find egenskaben *FullDomainResolutionEnabled*, og rediger dens værdi til *True*.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

Nu kan du [køre en Power BI-rapport](service-gateway-sso-kerberos.md#run-a-power-bi-report).

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om **datagateway i det lokale miljø** og **DirectQuery** i følgende ressourcer:

* [Hvad er en datagateway i det lokale miljø?](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
