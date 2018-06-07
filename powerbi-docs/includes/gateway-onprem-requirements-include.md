## <a name="requirements"></a>Krav
**Minimumskrav:**

* .NET 4.6 Framework
* 64-bit-version af Windows 7 / Windows Server 2008 R2 (eller nyere)

**Anbefalet:**

* CPU med 8 kerner
* 8 GB hukommelse
* 64-bit-version af Windows 2012 R2 (eller nyere)

**Relaterede overvejelser:**

* Gatewayen kan ikke installeres på en domænecontroller
* Hvis du planlægger at bruge Windows-godkendelse, skal du installere en gateway på en computer, der er medlem af det samme Active Directory-miljø som datakilderne.
* Du skal ikke installere en gateway på en computer, f.eks. en bærbar computer, der kan slukkes, sættes i slumretilstand eller ikke har forbindelse til internettet, da gatewayen ikke kan køre under disse omstændigheder. Desuden kan gatewayens ydeevne blive påvirket af et trådløst netværk.
* Analysis Services er ikke påkrævet for at bruge gatewayen. Du kan bruge gatewayen til at oprette forbindelse til en Analysis Services-datakilde.

