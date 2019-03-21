---
title: Konfiguration af proxyindstillinger for datagatewayen i det lokale miljø
description: Oplysninger om konfiguration af proxyindstillinger for datagatewayen i det lokale miljø.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2122ce9bd6eb850a51a06188ca1c10faf78f4bb1
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/18/2019
ms.locfileid: "57964657"
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>Konfiguration af proxyindstillinger for datagatewayen i det lokale miljø
Dit arbejdsmiljø kan kræve, at du går gennem en proxy for at få adgang til internettet. Dette kan forhindre datagatewayen i det lokale miljø i at oprette forbindelse til tjenesten.

## <a name="does-your-network-use-a-proxy"></a>Bruger netværket en proxy?
I følgende indlæg på superuser.com beskrives, hvordan du kan forsøge at afgøre, om du har en proxy på netværket.

[Hvordan ved jeg, hvilken proxyserver jeg bruger? (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>Placering af konfigurationsfil og standardkonfiguration
Proxyoplysninger er konfigureret i en .NET-konfigurationsfil. Placeringen og filnavnene vil være anderledes afhængigt af den gateway, du bruger.

### <a name="on-premises-data-gateway"></a>Datagateway i det lokale miljø
Der er to overordnede konfigurationsfiler, der er involveret i datagatewayen i det lokale miljø.

**Konfiguration**

Den første er til konfigurationsskærmene, der rent faktisk konfigurerer gatewayen. Hvis du har problemer med konfiguration af gatewayen, er det denne fil, du skal se på.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows-tjeneste**

Den anden er til den faktiske Windows-tjeneste, der fungerer sammen med Power BI-tjenesten, og behandler anmodningerne.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>Konfigurer proxyindstillinger
Standardproxykonfigurationen er følgende.

```
<system.net>
    <defaultProxy useDefaultCredentials="true" />
</system.net>
```


Standardkonfigurationen fungerer sammen med Windows-godkendelse. Hvis din proxy bruger en anden form for godkendelse, skal du ændre indstillingerne. Hvis du ikke er sikker, skal du kontakte netværksadministratoren. Grundlæggende proxygodkendelse anbefales ikke, og forsøg på at bruge grundlæggende proxygodkendelse kan medføre fejl, som resulterer i, at gatewayen ikke konfigureres korrekt. Brug en stærkere proxygodkendelsesmetode for at løse problemet.

Ud over at bruge standardlegitimationsoplysninger kan du tilføje et <proxy>-element for at definere indstillingerne for proxyserveren. Du kan f.eks. angive, at din datagateway i det lokale miljø altid skal bruge proxyen til lokale ressourcer ved at angive parameteren bypassonlocal til falsk. Det kan være en hjælp til fejlfinding, hvis du vil registrere alle https-anmodninger, der stammer fra en datagateway i det lokale miljø i proxylogfilerne. Følgende eksempelkonfiguration angiver, at alle anmodninger skal gå gennem en bestemt proxy med IP-adressen 192.168.1.10.

```
<system.net>
    <defaultProxy useDefaultCredentials="true">
        <proxy  
            autoDetect="false"  
            proxyaddress="http://192.168.1.10:3128"  
            bypassonlocal="false"  
            usesystemdefault="true"
        />  
    </defaultProxy>
</system.net>
```

Derudover kan du opdatere følgende fil for at få gatewayen til at oprette forbindelse til datakilder fra cloudmiljøet via en proxy: *C:\Program Files\On-premises data gateway\Microsoft.Mashup.Container.NetFX45.exe*. I filen skal du udvide sektionen `<configurations>` for at inkludere indholdet nedenfor og opdatere attributten `proxyaddress` med dine proxyoplysninger. I følgende eksempel distribueres alle cloudanmodninger via en bestemt proxy med IP-adressen 192.168.1.10.

```
<configuration>
<system.net>
    <defaultProxy useDefaultCredentials="true" enabled="true">
    <proxy proxyaddress=""http://192.168.1.10:3128" bypassonlocal="true" />
    </defaultProxy>
</system.net>
</configuration>
```

Hvis du vil vide mere om konfiguration af proxyelementerne for .NET-konfigurationsfiler, kan du se [defaultProxy-element (netværksindstillinger)](https://msdn.microsoft.com/library/kd3cf2ex.aspx).

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>Skift gatewaytjenestekontoen til en domænebruger
Når du konfigurerer proxyindstillingerne til at bruge standardlegitimationsoplysninger, som beskrevet ovenfor, kan der opstå problemer med godkendelse med din proxy. Dette skyldes, at standardtjenestekontoen er tjeneste-SID'et og ikke en godkendt domænebruger. Du kan ændre tjenestekontoen for gatewayen for at tillade korrekt godkendelse med din proxy.

> [!NOTE]
> Det anbefales, at du bruger en administreret tjenestekonto for at undgå at skulle nulstille adgangskoder. Få mere at vide om, hvordan du opretter en [administreret tjenestekonto](https://technet.microsoft.com/library/dd548356.aspx) i Active Directory.
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>Skift kontoen til datagatewaytjenesten i det lokale miljø
1. Skift kontoen til Windows-tjenesten for **datagatewaytjenesten i det lokale miljø**.

    Standardkontoen for denne tjeneste er *NT SERVICE\PBIEgwService*. Du skal ændre denne til en domænebrugerkonto i Active Directory-domænet. Eller du skal bruge en administreret tjenestekonto for at undgå at ændre adgangskoden.

    Du skal ændre kontoen under fanen **Log på** i egenskaberne for Windows-tjenesten.
2. Genstart **datagatewaytjenesten i det lokale miljø**.

    Fra en kommandoprompt til administratorer skal du udstede følgende kommandoer.

        net stop PBIEgwService

        net start PBIEgwService
3. Start **konfiguratoren til datagatewayen i det lokale miljø**. Du kan vælge Windows-startknappen og søge efter *datagateway i det lokale miljø*.
4. Log på Power BI.
5. Gendan gatewayen ved hjælp af din genoprettelsesnøgle.

    Det betyder, at den nye tjenestekonto kan dekryptere gemte legitimationsoplysninger for datakilder.

> [!NOTE]
> Når du ændrer tjenestekontoen direkte vha. kontrolpanelet for tjenester, opdateres ACL'er ikke automatisk. Du skal til at sikre dig, at den nye tjenestekonto har adgang til installationsfilerne og -mappen. Du kan finde mappen med gatewayinstallationen under C:\Program Files\On-premises data gateway. 
> 

## <a name="next-steps"></a>Næste trin
[Datagateway i det lokale miljø (personlig tilstand)](service-gateway-personal-mode.md)
[Firewalloplysninger](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

