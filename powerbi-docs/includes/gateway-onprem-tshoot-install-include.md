## <a name="update-to-the-latest-version"></a>Opdater til den nyeste version
Der kan opstå mange problemer, hvis gatewayversionen er forældet.  Det er generelt en god idé at sikre, at du anvender den nyeste version.  Hvis du ikke har opdateret gatewayen i en måned eller mere, bør du overveje at installere den nyeste version af gatewayen, og se, om du kan genskabe problemet.

## <a name="common-issues"></a>Almindelige problemer
Her er nogle almindelige problemer og løsninger, som har hjulpet en række kunder i miljøer, der begrænser adgangen til internettet.

### <a name="authentication-to-proxy-server"></a>Godkendelse til proxyserver
Din kræver muligvis godkendelse fra en domænebrugerkonto. Gatewayen anvender som standard et tjeneste-SID til brugerens logon på Windows-tjenesten. Hvis du ændrer brugeren til en domænebruger, kan det hjælpe. Du kan få mere at vide i [Ændring af gatewaytjenestekontoen til en domænebruger](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>Din proxy tillader kun trafik på port 80 og 443
Nogle proxyer begrænser trafikken til port 80 og 443. Som standard sker kommunikation til Azure Service Bus på andre porte end 443.

Du kan tvinge gatewayen til at kommunikere med Azure Service Bus ved hjælp af HTTPS i stedet for direkte TCP. Du skal ændre filen *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*. Ret værdien fra `AutoDetect` til `Https`. Filen er som standard placeret i *C:\Programmer\On-premises data gateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>Installation
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Fejl: Brugeren kunne ikke føjes til gruppen.  (-2147463168   PBIEgwService   Performance Log Users   )
Du får evt. vist denne fejlmeddelelse, hvis du forsøger at installere gatewayen på en domænecontroller. Installation på en domænecontroller understøttes ikke. Du skal installere gatewayen på en computer, der ikke er en domænecontroller.

### <a name="installation-fails"></a>Installationen mislykkedes
Du kan komme ud for, at en installation mislykkes, hvis antivirussoftwaren på computeren er forældet. Du kan enten opdatere antivirussoftwaren eller deaktivere antivirusfunktionen for gatewayen, indtil du har installeret, og derefter aktivere antivirussoftwaren igen.

