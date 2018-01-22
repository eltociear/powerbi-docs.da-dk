## <a name="sign-in-account"></a>Loginkonto
Brugere skal logge på med enten en arbejds- eller skolekonto. Dette er din organisationskonto. Hvis du har tilmeldt dig et tilbud på Office 365 og ikke angav din rigtige arbejdsmailadresse, kan den se ud som nancy@contoso.onmicrosoft.com. På en cloudtjeneste gemmes din konto i en lejer i Azure Active Directory (AAD). I de fleste tilfælde vil AAD-kontoens UPN svare til mailadressen.

## <a name="windows-service-account"></a>Windows-tjenestekonto
Datagatewayen i det lokale miljø er konfigureret til at bruge *NT SERVICE\PBIEgwService* for legitimationsoplysninger til logon på Windows-tjenesten. Som standard er rettighederne de samme som i forbindelse med Log på som en tjeneste. Dette er i forbindelse med den computer, du installerer gatewayen på.

> [!NOTE]
> Hvis du har valgt personlig tilstand, skal du konfigurere kontoen til Windows-tjenesten separat.
> 
> 

Det er ikke denne konto, der bruges til at oprette forbindelse til datakilder i det lokale miljø.  Det er heller ikke din arbejds- eller skolekonto, som du bruger til at logge på cloudtjenester med.

Hvis du oplever problemer med din proxyserver på grund af godkendelse, kan du evt. ændre Windows-tjenestekontoen til en domænebruger- eller administreret tjenestekonto. Du kan se, hvordan du skifter konto i [proxykonfiguration](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

## <a name="ports"></a>Porte
Gatewayen opretter en udgående forbindelse til Azure Service Bus. Den kommunikerer via udgående porte: TCP 443 (standard), 5671, 5672, 9350 til 9354.  Gatewayen kræver ikke indgående porte. [Få mere at vide](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)

Det anbefales, at du føjer IP-adresserne for dit dataområde til hvidlisten i din firewall. Du kan downloade [Microsoft Azure Datacenter IP-listen](https://www.microsoft.com/download/details.aspx?id=41653). Listen opdateres ugentligt. Gatewayen kommunikerer med Azure Service Bus ved hjælp af IP-adressen foruden det fuldt kvalificerede domænenavn (FQDN). Hvis du tvinger gatewayen til at kommunikere ved hjælp af HTTPS, vil det gennemtvinge kun at bruge FQDN, og der sker ingen kommunikation via IP-adressen.

> [!NOTE]
> På listen over IP-adresser til Azure Datacenter er adresserne angivet i CIDR-notation. For eksempel er 10.0.0.0/24 ikke det samme som 10.0.0.0 til og med 10.0.0.24. Få mere at vide om [CIDR-notation](http://whatismyipaddress.com/cidr).
> 
> 

Her er en liste over de fuldt kvalificerede domænenavne, der anvendes af gatewayen.

| Domænenavne | Udgående porte | Beskrivelse |
| --- | --- | --- |
| *.download.microsoft.com |80 |Der bruges HTTP til at downloade installationsprogrammet. |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Lyttere på Service Bus Relay via TCP (kræver 443 til anskaffelse af adgangskontroltoken) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Bruges til at teste internetforbindelsen, hvis der ikke kan oprettes forbindelse til gatewayen fra Power BI-tjenesten. |
| *.microsoftonline-p.com |443 |Bruges til godkendelse afhængigt af konfigurationen. |

> [!NOTE]
> Den trafik, der kommer gennem visualstudio.com eller visualstudioonline.com er ikke til appindsigt, og det er ikke krævet for at gatewayen kan fungere.
> 
> 

## <a name="forcing-https-communication-with-azure-service-bus"></a>Gennemtving HTTPS-kommunikation med Azure Service Bus
Du kan tvinge gatewayen til at kommunikere med Azure Service Bus ved hjælp af HTTPS i stedet for direkte TCP. Dette kan påvirke ydeevnen. Det kan du gøre ved at ændre filen *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* ved at ændre værdien fra `AutoDetect` til `Https` som vist i kodestykket efter dette afsnit. Filen er som standard placeret under *C:\Programmer\On-premises data gateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

Der skelnes mellem store og små bogstaver i parameteren *ServiceBusSystemConnectivityModeString*. Gyldige værdier er *AutoDetect* og *Https*.

Alternativt kan du tvinge gatewayen til at fungere på denne måde ved hjælp af gatewaybrugergrænsefladen fra og med versionen fra [marts 2017](https://powerbi.microsoft.com/blog/power-bi-gateways-march-update/). I gatewaybrugergrænsefladen skal du vælge **Netværk** og derefter angive **Azure Service Bus-forbindelsestilstand**  til **Til**.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_01.png)

Når indstillingen er ændret, kan du vælge **Anvend** (en knap, der kun vises, når du har ændret noget), og *Windows-gatewaytjenesten* bliver automatisk genstartet, så ændringen kan træde i kraft.

Til fremtidig reference kan du genstarte *Windows-gatewaytjenesten* fra dialogboksen ved at vælge **Tjenesteindstillinger** og derefter vælge *Genstart nu*.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_02.png)

## <a name="support-for-tls-1112"></a>Understøttelse af TLS 1.1/1.2
Med opdateringen fra august 2017 og senere opdateringer bruger datagatewayen i det lokale miljø TLS 1.1 eller 1.2 (Transport Layer Security) til at kommunikere med **Power BI-tjenesten** som standard. Tidligere versioner af datagatewayen i det lokale miljø bruger som standard TLS 1.0. Fra den 15. marts 2018 slutter understøttelsen af TLS 1.0, herunder gatewayens mulighed for at interagere med **Power BI-tjenesten** via TLS 1.0. Fra den dato skal du derfor opgradere installationerne af datagatewayen i det lokale miljø til udgaven fra august 2017 eller en nyere udgave for at sikre, at din gateway fortsat fungerer.

Det er vigtigt at bemærke, at TLS 1.0 stadig understøttes af datagatewayen i det lokale miljø fra før 1. november, og den bruges af gatewayen som fallback-løsning. Hvis du vil sikre, at al gatewaytrafik bruger TLS 1.1 eller 1.2 (og for at forhindre, at der bruges TLS 1.0 på din gateway), skal du tilføje eller ændre følgende registreringsdatabasenøgler på den computer, hvor gatewaytjenesten kører:

        [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
        [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001

> [!NOTE]
> Når du tilføjer eller ændrer disse registreringsdatabasenøgler, anvendes ændringerne for alle .NET-programmer. Hvis du vil vide mere om, hvilke ændringer i registreringsdatabasen der påvirker TLS for andre programmer, skal du se [Indstillinger for TLS (Transport Layer Security) i registreringsdatabasen](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).
> 
> 

## <a name="how-to-restart-the-gateway"></a>Sådan genstarter du gatewayen
Gatewayen kører som en Windows-tjeneste. Du kan starte og stoppe den som enhver anden Windows-tjeneste. Det kan gøres på flere forskellige måder. Her kan du se, hvordan du kan gøre det fra kommandoprompten.

1. Start en kommandoprompt som administrator på den computer, hvor gatewayen kører.
2. Brug følgende kommando for at stoppe tjenesten.
   
   net stop PBIEgwService
3. Brug følgende kommando for at starte tjenesten.
   
   net start PBIEgwService

