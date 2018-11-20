---
title: Brug SAML til SSO (enkeltlogon) i forbindelse med datakilder i det lokale miljø
description: Konfigurer din gateway med SAML (Security Assertion Markup Language) for at aktivere enkeltlogon (SSO – single sign-on) fra Power BI til datakilder i det lokale miljø.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 8762e575574b717965ac55d4cf32a5c925c298ab
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507778"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Brug SAML (Security Assertion Markup Language) til enkeltlogon (SSO) fra Power BI til datakilder i det lokale miljø

Brug [SAML (Security Assertion Markup Language)](https://www.onelogin.com/pages/saml) til at aktivere problemfri forbindelse via enkeltlogon. Aktivering af SSO gør det nemt for Power BI-rapporter og -dashboards at opdatere data fra kilder i det lokale miljø.

## <a name="supported-data-sources"></a>Understøttede datakilder

Vi understøtter i øjeblikket SAP HANA med SAML. Få mere at vide om opsætning og konfiguration af enkeltlogon til SAP HANA ved hjælp af SAML under emnet [SAML SSO på BI-platformen til HANA](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) i dokumentationen til SAP HANA.

Vi understøtter flere datakilder med [Kerberos](service-gateway-sso-kerberos.md).

## <a name="configuring-the-gateway-and-data-source"></a>Konfiguration af gatewayen og datakilden

For at bruge SAML skal du først generere et certifikat for SAML-identitetsudbyderen og derefter knytte en Power BI-bruger til identiteten.

1. Generér et certifikat. Sørg for at bruge FQDN for SAP HANA-serveren, når du udfylder *almindeligt navn*. Certifikatet udløber om 365 dage.

    ```
    openssl req -newkey rsa:2048 -nodes -keyout samltest.key -x509 -days 365 -out samltest.crt
    ```

1. I SAP HANA Studio skal du højreklikke på din SAP HANA-server og derefter navigere til **Sikkerhed** > **Åbn sikkerhedskonsollen** > **SAML-identitetsudbyder** > **Kryptografisk OpenSSL-bibliotek**.

1. Vælg **Importér**, naviger til samltest.crt, og importér den.

    ![Identitetsudbydere](media/service-gateway-sso-saml/identity-providers.png)

1. Vælg mappen **Sikkerhed** i SAP HANA Studio.

    ![Mappen Sikkerhed](media/service-gateway-sso-saml/security-folder.png)

1. Udvid **Brugere**, og vælg derefter den bruger, du vil knytte din Power BI-bruger til.

1. Vælg **SAML** og derefter **Konfigurer**.

    ![Konfigurer SAML](media/service-gateway-sso-saml/configure-saml.png)

1. Vælg den identitetsudbyder, du oprettede i trin 2. Angiv UPN for Power BI-brugeren under **Ekstern identitet**, og vælg derefter **Tilføj**.

    ![Vælg identitetsudbyder](media/service-gateway-sso-saml/select-identity-provider.png)

Valider derefter konfigurationen med en *SAML-assertion* ved hjælp af [xmlsec1-værktøjet](http://sgros.blogspot.com/2013/01/signing-xml-document-using-xmlsec1.html).

1. Gem assertionen nedenfor som assertion-template.xml. Erstat \<MyUserId\> med det UPN for Power BI-brugeren, som du angav i trin 7.

    ```xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <saml2:Assertion ID="Assertion12345789" IssueInstant="2015-07-16T04:47:49.858Z" Version="2.0" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
      <saml2:Issuer></saml2:Issuer> 
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
        <SignedInfo>
          <CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
          <SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1"/>
          <Reference URI="">
            <Transforms>
              <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
              <Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
            </Transforms>
            <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
            <DigestValue />
          </Reference>
        </SignedInfo>
        <SignatureValue />
        <KeyInfo>
          <X509Data />
        </KeyInfo>
      </Signature>
      <saml2:Subject>
        <saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified"><MyUserId></saml2:NameID>
      </saml2:Subject>
      <saml2:Conditions NotBefore="2010-01-01T00:00:00Z" NotOnOrAfter="2050-01-01T00:00:00Z"/>
    </saml2:Assertion>
    ```

1. Kør følgende kommando. saltest.key og samltest.crt er den nøgle og det certifikat, du genererede i trin 1.

    ```
    xmlsec1 --sign --privkey-pem samltest.key, samltest.crt --output signed.xml assertion-template.xml
    ```

1. Åbn et SQL-konsolvindue i SAP HANA Studio, og kør følgende kommando. Erstat \<SAMLAssertion\> med indholdet af xml-filen fra forrige trin.

    ```SQL
    CONNECT WITH SAML ASSERTION '<SAMLAssertion>'
    ```

Hvis forespørgslen lykkes, betyder det, at konfigurationen af SAML SSO for SAP HANA er fuldført.

Nu, hvor du har konfigureret certifikatet og identiteten korrekt, kan du konvertere certifikatet til et pfx-format og konfigurere gatewaycomputeren til at bruge certifikatet.

1. Konvertér certifikatet til pfx-formatet ved at køre følgende kommando.

    ```
    openssl pkcs12 -inkey samltest.key -in samltest.crt -export -out samltest.pfx
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

1. Naviger til gatewaymappen, der som standard ligger her C:\Programmer\Datagateway i det lokale miljø.

1. Åbn PowerBI.DataMovement.Pipeline.GatewayCore.dll.config, og find afsnittet \*SapHanaSAMLCertThumbprint\*. Indsæt det aftryk, du har kopieret.

1. Genstart gatewaytjenesten.

## <a name="running-a-power-bi-report"></a>Kørsel af en Power BI-rapport

Nu kan du bruge siden **Administrer gateway** i Power BI til at konfigurere datakilden og aktivere SSO under **Avancerede indstillinger**. Du kan derefter publicere rapporter og datasæt med binding til den pågældende datakilde.

![Avancerede indstillinger](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om **datagatewayen i det lokale miljø** og **DirectQuery** i følgende ressourcer:

* [Datagateway i det lokale miljø](service-gateway-onprem.md)
* [DirectQuery i Power BI](desktop-directquery-about.md)
* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)