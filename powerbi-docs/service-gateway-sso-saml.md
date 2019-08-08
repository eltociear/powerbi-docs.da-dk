---
title: Brug SAML til SSO (enkeltlogon) i forbindelse med datakilder i det lokale miljø
description: Konfigurer din gateway med SAML (Security Assertion Markup Language) for at aktivere enkeltlogon (SSO – single sign-on) fra Power BI til datakilder i det lokale miljø.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: a240d84b20f63542c33bb7cbbb9a9c97af7db2f7
ms.sourcegitcommit: d74aca333595beaede0d71ba13a88945ef540e44
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/03/2019
ms.locfileid: "68757686"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Brug SAML (Security Assertion Markup Language) til enkeltlogon (SSO) fra Power BI til datakilder i det lokale miljø

Brug [SAML (Security Assertion Markup Language)](https://www.onelogin.com/pages/saml) til at aktivere problemfri forbindelse via enkeltlogon. Aktivering af SSO gør det nemt for Power BI-rapporter og -dashboards at opdatere data fra kilder i det lokale miljø.

## <a name="supported-data-sources"></a>Understøttede datakilder

Vi understøtter i øjeblikket SAP HANA med SAML. Få mere at vide om opsætning og konfiguration af enkeltlogon til SAP HANA ved hjælp af SAML under emnet [SAML SSO på BI-platformen til HANA](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) i dokumentationen til SAP HANA.

Vi understøtter flere datakilder med [Kerberos](service-gateway-sso-kerberos.md).

Bemærk! Det anbefales på det **kraftigste**, at kryptering for HANA aktiveres, før der etableres en SAML SSO-forbindelse, dvs. du skal konfigurere HANA-serveren til at acceptere krypterede forbindelser og også konfigurere gatewayen til at bruge kryptering, når der kommunikeres med HANA-serveren. HANA ODBC-driveren kan som standard **ikke** kryptere SAML-påstande, og hvis kryptering ikke er slået til, bliver den signerede SAML-påstand sendt fra gatewayen til HANA-serveren som "godkendt" og er sårbar over for opfangelse og genbrug af tredjeparter.

## <a name="configuring-the-gateway-and-data-source"></a>Konfiguration af gatewayen og datakilden

Hvis du vil bruge SAML, skal du etablere et tillidsforhold mellem de HANA-servere, du vil aktivere SSO for, og den gateway, der fungerer som SAML-identitetsudbyderen (IdP) i dette scenarie. Der er forskellige måder at etablere denne relation på, f.eks. ved at importere X509-certifikatet for gatewayens IdP til HANA-servernes tillidslager eller ved at få signeret X509-certifikatet for gatewayen af et rodnøglecenter, som HANA-serverne har tillid til. Vi beskriver den sidste fremgangsmåde i denne vejledning, men du kan bruge en anden fremgangsmåde, hvis det er nemmere.

Bemærk også, at selvom denne vejledning bruger OpenSSL som HANA-serverens kryptografiske provider, anbefales det af SAP at bruge SAP Cryptographic Library (også kendt som CommonCryptoLib eller sapcrypto) i stedet for OpenSSL til at fuldføre konfigurationstrinnene, der hvor tillidsforholdet etableres. Se den officielle SAP-dokumentation for at få flere oplysninger.

I følgende trin beskrives, hvordan du etablerer et tillidsforhold mellem en HANA-server og gatewayens IdP ved at signere X509-certifikatet for gatewayens IdP ved hjælp af et rodnøglecenter, som HANA-serveren har tillid til.

1. Opret X509-certifikatet og den private nøgle for rodnøglecentret. Du opretter f.eks. X509-certifikatet og den private nøgle for rodnøglecentret i .pem-format ved at gøre følgende:

   ```
   openssl req -new -x509 -newkey rsa:2048 -days 3650 -sha256 -keyout CA_Key.pem -out CA_Cert.pem -extensions v3_ca
   ```
  Sørg for, at rodnøglecenterets certifikat er beskyttet korrekt. Hvis det er hentet af tredjeparter, kan det bruges til at få uautoriseret adgang til HANA-serveren. 

  Føj certifikatet (f.eks. CA_Cert.pem) til HANA-serverens tillidslager, så HANA-serveren har tillid til alle certifikater, der er signeret af det rodnøglecenter, du lige har oprettet. Du finder placeringen af din HANA-servers tillidslager ved at undersøge konfigurationsindstillingen **ssltruststore**. Hvis du har fulgt SAP-dokumentationen, der dækker den måde, du konfigurerer OpenSSL på, har din HANA-server måske allerede tillid til et rodnøglecenter, som du kan genbruge. Du kan finde oplysninger i [Sådan konfigureres Open SSL til SAP HANA Studio til SAP HANA Server](https://archive.sap.com/documents/docs/DOC-39571). Hvis du har flere HANA-servere, som du vil aktivere SAML SSO for, skal du kontrollere, at alle serverne har tillid til dette rodnøglecenter.

1. Opret X509-certifikatet for gatewayens idP. Hvis du f.eks. vil oprette en anmodning om signering af certifikat (IdP_Req.pem) og en privat nøgle (IdP_Key.pem), som er gyldige i ét år, skal du udføre følgende kommando:

   ```
   openssl req -newkey rsa:2048 -days 365 -sha256 -keyout IdP_Key.pem -out IdP_Req.pem -nodes
   ```

   Signer anmodningen om signering af certifikat ved hjælp af det rodnøglecenter, som dine HANA-servere har tillid til. Hvis du f.eks. vil signere IdP_Req.pem ved hjælp af CA_Cert.pem og CA_Key.pem (rodnøglecentrets certifikat og nøgle), skal du udføre følgende kommando:

   ```
   openssl x509 -req -days 365 -in IdP_Req.pem -sha256 -extensions usr_cert -CA CA_Cert.pem -CAkey CA_Key.pem -CAcreateserial -out IdP_Cert.pem
   ```

Det resulterende IdP-certifikat er gyldigt i ét år (se indstillingen -dage). Importér nu certifikatet for din IdP i HANA Studio for at oprette en ny SAML-identitetsudbyder.

1. I SAP HANA Studio skal du højreklikke på din SAP HANA-server og derefter navigere til **Sikkerhed** > **Åbn sikkerhedskonsollen** > **SAML-identitetsudbyder** > **Kryptografisk OpenSSL-bibliotek**.

    ![Identitetsudbydere](media/service-gateway-sso-saml/identity-providers.png)

1. Vælg **Importér**, naviger til IdP_Cert.pem, og importér det.

1. Vælg mappen **Sikkerhed** i SAP HANA Studio.

    ![Mappen Sikkerhed](media/service-gateway-sso-saml/security-folder.png)

1. Udvid **Brugere**, og vælg derefter den bruger, du vil knytte din Power BI-bruger til.

1. Vælg **SAML** og derefter **Konfigurer**.

    ![Konfigurer SAML](media/service-gateway-sso-saml/configure-saml.png)

1. Vælg den identitetsudbyder, du oprettede i trin 2. Angiv Power BI-brugerens UPN (typisk den mailadresse, brugeren logger på Power BI med) som **Ekstern identitet**, og vælg derefter **Tilføj**. Bemærk! Hvis du har konfigureret din gateway til at bruge konfigurationsindstillingen *ADUserNameReplacementProperty*, så skal du angive den værdi, der skal erstatte Power BI-brugerens oprindelige UPN. Hvis du f.eks. angiver *ADUserNameReplacementProperty* til **SAMAccountName**, så skal du angive brugerens **SAMAccountName**.

    ![Vælg identitetsudbyder](media/service-gateway-sso-saml/select-identity-provider.png)

Nu, hvor du har konfigureret certifikatet og identiteten for gatewayen, kan du konvertere certifikatet til et pfx-format og konfigurere gatewaymaskinen til at bruge certifikatet.

1. Konvertér certifikatet til pfx-formatet ved at køre følgende kommando. Bemærk, at denne kommando indstiller "root" som adgangskode for pfx-filen.

    ```
    openssl pkcs12 -export -out samltest.pfx -in IdP_Cert.pem -inkey IdP_Key.pem -passin pass:root -passout pass:root
    ```

1. Kopiér pfx-filen til gatewaycomputeren:

    1. Dobbeltklik på samltest.pfx, og vælg derefter **Lokal maskine** > **Næste**.

    1. Angiv adgangskoden, og vælg derefter **Næste**.

    1. Vælg **Placer alle certifikater i følgende lager,** og vælg derefter **Gennemse** > **Personlig** > **OK**.

    1. Vælg **Næste** og derefter **Udfør**.

    ![Importér certifikat](media/service-gateway-sso-saml/import-certificate.png)

1. Giv kontoen for gatewaytjenesten adgang til den private nøgle for certifikatet:

    1. Kør Microsoft Management Console (MMC) på gatewaycomputeren.

        ![Kør MMC](media/service-gateway-sso-saml/run-mmc.png)

    1. Under **Filer** skal du vælge **Tilføj/fjern snap-in**.

        ![Tilføj snap-in](media/service-gateway-sso-saml/add-snap-in.png)

    1. Vælg **Certifikater** > **Tilføj**, og vælg derefter **Computerkonto** > **Næste**.

    1. Vælg **Lokal computer** > **Udfør** > **OK**.

    1. Udvid **Certifikater** > **Personlig** > **Certifikater**, og find certifikatet.

    1. Højreklik på certifikatet, og naviger til **Alle opgaver** > **Administrer private nøgler**.

        ![Administrer private nøgler](media/service-gateway-sso-saml/manage-private-keys.png)

    1. Føj kontoen for gatewaytjenesten til listen. Kontoen er som standard **NT SERVICE\PBIEgwService.** Du kan finde ud af, hvilken konto der kører gatewaytjenesten ved at køre **services.msc** og finde **Datagatewaytjeneste i det lokale miljø**.

        ![Gatewaytjeneste](media/service-gateway-sso-saml/gateway-service.png)

Følg til sidst disse trin for at føje certifikataftrykket til konfigurationen af gatewayen.

1. Kør følgende PowerShell-kommando for at angive certifikaterne på din computer på listen.

    ```powershell
    Get-ChildItem -path cert:\LocalMachine\My
    ```
1. Kopiér aftrykket for det certifikat, du har oprettet.

1. Naviger til gatewaymappen, der som standard ligger her C:\Programmer\On-premises data gateway.

1. Åbn PowerBI.DataMovement.Pipeline.GatewayCore.dll.config, og find afsnittet \*SapHanaSAMLCertThumbprint\*. Indsæt det aftryk, du har kopieret.

1. Genstart gatewaytjenesten.

## <a name="running-a-power-bi-report"></a>Kørsel af en Power BI-rapport

Nu kan du bruge siden **Administrer gateway** i Power BI til at konfigurere datakilden og aktivere SSO under **Avancerede indstillinger**. Du kan derefter publicere rapporter og datasæt med binding til den pågældende datakilde.

![Avancerede indstillinger](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="troubleshooting"></a>Fejlfinding

Når du har konfigureret SSO, får du muligvis vist følgende fejl på Power BI-portalen: "De angivne legitimationsoplysninger kan ikke bruges til SapHana-kilden." Denne fejl tyder på, at SAML legitimationsoplysningerne blev afvist af SAP HANA.

Godkendelsessporinger på serversiden indeholder detaljerede oplysninger om fejlfinding af problemer med legitimationsoplysninger på SAP HANA. Følg disse trin for at konfigurere sporing for din SAP HANA-server.

1. Slå godkendelsessporing til på SAP HANA-serveren ved at køre følgende forespørgsel.

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') set ('trace', 'authentication') = 'debug' with reconfigure 
    ```

1. Genskab problemet.

1. Åbn administrationskonsollen i HANA Studio, og gå til fanen **Diagnosticeringsfiler**.

1. Åbn den nyeste indexserversporing, og søg efter SAMLAuthenticator.cpp.

    Du bør finde en detaljeret fejlmeddelelse, der angiver rodårsagen, som i følgende eksempel.

    ```
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815797 d Authentication   SAMLAuthenticator.cpp(00091) : Element '{urn:oasis:names:tc:SAML:2.0:assertion}Assertion', attribute 'ID': '123123123123123' is not a valid value of the atomic type 'xs:ID'.
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815914 i Authentication   SAMLAuthenticator.cpp(00403) : No valid SAML Assertion or SAML Protocol detected
    ```

1. Når fejlfindingen er fuldført, kan du slå godkendelsessporingen fra ved at køre følgende forespørgsel.

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') UNSET ('trace', 'authentication');
    ```

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om **datagateway i det lokale miljø** og **DirectQuery** i følgende ressourcer:

* [Hvad er en datagateway i det lokale miljø?](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
