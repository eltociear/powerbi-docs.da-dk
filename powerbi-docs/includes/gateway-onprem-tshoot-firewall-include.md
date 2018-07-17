## <a name="firewall-or-proxy"></a>Firewall eller proxy
Du kan finde oplysninger om, hvordan du angiver proxyoplysninger for din gateway, under [Konfigurer proxyindstillinger for Power BI-gateways](../service-gateway-proxy.md).

Du kan teste, om din firewall eller proxy blokerer forbindelser. Det gør du ved at køre [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection) fra en PowerShell-prompt. Dette tester forbindelsen til Azure Service Bus. Det er kun netværksforbindelsen, der testes, og det har ikke noget med cloudservertjenesten eller gatewayen at gøre. Det hjælper med at finde ud af, om din computer faktisk kan få forbindelse til internettet.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection er kun tilgængeligt på Windows Server 2012 R2 og nyere versioner. Det er også tilgængeligt på Windows 8.1 og nyere. På tidligere operativsystemversioner kan du bruge Telnet til at teste portforbindelser.
> 
> 

Resultatet ligner dette eksempel. Forskellen vil være TcpTestSucceeded. Hvis **TcpTestSucceeded** ikke er *true*, er du muligvis blokeret af en firewall.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Hvis du vil se mere omfattende oplysninger, skal du udskifte værdierne for **computernavn** og **port** med de værdier, der vises for [porte](../service-gateway-onprem.md#ports).

Firewallen kan også blokere de forbindelser, som Azure Service Bus opretter til Azure-datacentrene. Hvis det er tilfældet, kan du føje IP-adresserne for dit område til hvidlisten (fjerne blokeringen) for de pågældende datacentre. Du kan få vist en liste over Azure IP-adresser [her](https://www.microsoft.com/download/details.aspx?id=41653).

