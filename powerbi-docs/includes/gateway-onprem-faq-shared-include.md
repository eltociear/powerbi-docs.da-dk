## <a name="general"></a>Generelt
**Spørgsmål:** Hvad hedder den faktiske Windows-tjeneste?  
**Svar:** Gatewayen kaldes i for Gatewaytjeneste i det lokale miljø under Tjenester

**Spørgsmål:** Hvilke krav er der til gatewayen?  
**Svar:** Du kan se afsnittet om krav i den primære [gatewayartikel](../service-gateway-onprem.md).

**Spørgsmål:** Hvilke datakilder understøttes med gatewayen?  
**Svar:** Se tabellen over datakilder i den primære [gatewayartikel](../service-gateway-onprem.md).

**Spørgsmål:** Skal jeg have en gateway til clouddatakilder som en Azure SQL-database?  
**Svar:** Nej! Tjenesten kan oprette forbindelse til datakilden uden en gateway.

**Spørgsmål:** Er der indgående forbindelser til gatewayen fra clouden?  
**Svar:** Nej. Gatewayen bruger udgående forbindelser til Azure Service Bus.

**Spørgsmål:** Hvad sker der, hvis jeg blokerer for udgående forbindelser? Hvad skal jeg åbne?  
**Svar:** Se [listen over de porte](../service-gateway-onprem.md#ports) og værter, som gatewayen bruger.

**Spørgsmål:** Skal gatewayen være installeret på samme computer som datakilden?  
**Svar:** Nej. Gatewayen opretter forbindelse til datakilden vha. de angivne forbindelsesoplysninger. Tænk på gatewayen som et klientprogram i denne forstand. Den skal blot skal kunne oprette forbindelse til det angivne servernavn.

**Spørgsmål:** Hvad er ventetiden for kørsel af forespørgsler til en datakilde fra gatewayen? Hvad er den bedste arkitektur?  
**Svar:** Det anbefales at have gatewayen så tæt som muligt på datakilden for at undgå netværksventetid. Hvis du kan installere gatewayen på den faktiske datakilde, minimeres den introducerede ventetid. Overvej også datacentrene. Hvis din tjeneste f.eks. bruger et datacenter i det vestlige USA, og du har SQL Server hostet på en Azure VM, skal du også have Azure-VM'en placeret i det vestelige USA. Dermed minimeres ventetiden, og du undgår gebyrer for udgående data på Azure VM'en.

**Spørgsmål:** Er der nogen krav til båndbredden på netværket?  
**Svar:** Det anbefales, at du har en god dataoverførselshastighed for netværksforbindelsen. Alle miljøer er forskellige, og den sendte datamængde påvirker resultaterne. Hvis du bruger ExpressRoute, får du en garanti for niveauet for dataoverførselshastigheden mellem datacentre i det lokale miljø og Azure-datacentre.

Du kan bruge tredjepartsværktøjet [Azure Speed Test-app](http://azurespeedtest.azurewebsites.net/) til at måle dataoverførselshastigheden.

**Spørgsmål:** Kan gatewayen for Windows-tjenesten køre med en Azure Active Directory-konto?  
**Svar:** Nej. Windows-tjenesten skal have en gyldig Windows-konto. Som standard køres den med Service SID, *NT SERVICE\PBIEgwService*.

**Spørgsmål:** Hvordan sendes resultaterne tilbage til cloudmiljøet?  
**Svar:** Det sker via Azure Service Bus. Du kan finde flere oplysninger om dette under[sådan fungerer det](../service-gateway-onprem.md#how-the-gateway-works).

**Spørgsmål:** Hvor gemmes mine legitimationsoplysninger?  
**Svar:** De legitimationsoplysninger, du angiver for en datakilde, krypteres og gemmes i cloudtjenesten for gatewayen. Legitimationsoplysningerne dekrypteres i gatewayen i det lokale miljø.

**Spørgsmål:** Kan jeg placere gatewayen i et perimeternetværk (også kaldet DMZ (demilitariseret zone) og afskærmet undernet)?  
**Svar:** Gatewayen skal have forbindelse til datakilden. Hvis der ikke er adgang til datakilden på perimeternetværket, kan gatewayen evt. ikke oprette forbindelse til den. Din SQL Server er f.eks. ikke nødvendigvis på dit perimeternetværk. Og du kan ikke oprette forbindelse til SQL Server fra perimeternetværket. Hvis du har placeret gatewayen i perimeternetværket, kan den ikke får forbindelse til SQL Server.

**Spørgsmål:** Er det muligt at gennemtvinge, at gatewayen bruger HTTPS-trafik med Azure Service Bus i stedet for TCP?  
**Svar:** Ja. Det vil dog reducere ydeevnen markant. Du skal ændre filen *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*. Vil du ændre værdien fra `AutoDetect` til `Https`. Filen er som standard placeret i *C:\Programmer\On-premises data gateway*.

**Spørgsmål:** Skal jeg placere Azure Datacenter IP-listen på min hvidliste? Hvor finder jeg listen?  
**Svar:** Hvis du blokerer udgående IP-trafik, skal du muligvis placere Azure Datacenter IP-listen på din hvidliste. Gatewayen kommunikerer i øjeblikket med Azure Service Bus ved hjælp af IP-adressen foruden det fuldt kvalificerede domænenavn. Azure Datacenter IP-listen opdateres ugentligt. Du kan downloade [Microsoft Azure Datacenter IP-listen](https://www.microsoft.com/download/details.aspx?id=41653).

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>Høj tilgængelighed/it-katastrofeberedskab
**Spørgsmål:** Er der planer om at aktivere scenarier med høj tilgængelighed med gatewayen?  
**Svar:** Ja, det arbejder Power BI-teamet på. Du kan følge [Power BI-bloggen](https://powerbi.microsoft.com/blog/) for at få de seneste nyheder om denne funktion.

**Spørgsmål:** Hvilke indstillinger er der tilgængelige for it-katastrofeberedskabet?  
**Svar:** Du kan bruge genoprettelsesnøglen til at gendanne eller flytte en gateway. Du skal angive genoprettelsesnøglen, når du installerer gatewayen.

**Spørgsmål:** Hvad er fordelen ved genoprettelsesnøglen?  
**Svar:** Den giver dig mulighed for at overføre eller genoprette dine gatewayindstillinger. Dette bruges også til dit it-katastrofeberedskab.

## <a name="troubleshooting"></a>Fejlfinding
**Spørgsmål:** Hvor er gatewayloggene placeret?  
**Svar:** Se afsnittet om værktøjer i [artiklen om fejlfinding](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting).

**Spørgsmål:** Hvordan kan jeg se, hvilke forespørgsler der sendes til datakilden i det lokale miljø?  
**Svar:** Du kan aktivere forespørgselssporing.  Dette omfatter de forespørgsler, der sendes. Husk at ændre det tilbage til den oprindelige værdi, når du er færdig med fejlfindingen. Hvis du lader forespørgselssporing være aktiveret, medfører det, at loggene bliver større.

Du kan også prøve de værktøjer, som datakilden indeholder til forespørgselssporing. Du kan f.eks. bruge Extended Events eller SQL Profiler til SQL Server og Analysis Services.

