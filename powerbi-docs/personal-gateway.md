---
title: Power BI Gateway – Personal
description: Power BI Gateway – Personal
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 8d047e814eaa7c84ee7e1be20d1f4722c6cb1e56
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/06/2018
---
# <a name="power-bi-gateway---personal"></a>Power BI Gateway – Personlig
> [!NOTE]
> Der er en ny version af den personlige gateway til Power BI, som kaldes **datagateway i det lokale miljø (personlig tilstand)**. I følgende artikel beskrives den tidligere version af den personlige gateway, der blev kaldt **Power BI Gateway – Personal**, og som udgår og stopper med at virke efter den 31. juli 2017. Du kan finde oplysninger om den nye version af den personlige gateway, herunder, hvordan du installerer den nye version, i [ artiklen **Datagateway i det lokale miljø (personlig tilstand)**](service-gateway-personal-mode.md).
> 
> 

**Power BI Gateway – Personal** fungerer som en bro, der giver hurtige og sikre dataoverførsler mellem Power BI-tjenesten og datakilder i det lokale miljø, der understøtter [opdatering](refresh-data.md). I denne artikel får du en detaljeret beskrivelse af, hvordan gatewayen virker, og om du har brug for en gateway. Vi har også udarbejdet denne [praktiske video](https://www.youtube.com/watch?v=de58vROLqZI) om den personlige gateway. 

Den installeres og køres som en tjeneste på din computer. Da den kører som en tjeneste, køres den ved hjælp af den Windows-konto, du angiver under konfigurationen. I nogle tilfælde køres gatewayen som et program. Det kan du læse mere om senere.

Når Power BI opdaterer data fra en datakilde i det lokale miljø, sikrer gatewayen, at din Power BI-konto har de nødvendige tilladelser til at oprette forbindelse til og anmode om data fra kilden.

Dataoverførsler mellem Power BI og gatewayen sikres ved hjælp af [Azure Service Bus](http://azure.microsoft.com/documentation/services/service-bus/). Service Bus opretter en sikker kanal mellem Power BI-tjenesten og din computer. Da gatewayen sørger for denne sikre forbindelse, er det som regel ikke nødvendigt at åbne en port i din firewall.

Inden jeg kommer ind på nærmere detaljer om gatewayen, vil jeg lige beskrive nogle af de udtryk, der bruges i Power BI:

Et *datasæt* er data, der uploades til Power BI-tjenesten fra en onlinedatakilde eller en datakilde i det lokale miljø. Du kan oprette et datasæt ved at bruge Hent data til at oprette forbindelse til og uploade data. Datasæt vises i ruden Mit arbejdsområde i Power BI-arbejdsområdet i din browser. Når du opretter rapporter og fastgør felter på dine dashboards, får du vist data fra dine datasæt.

En *datakilde* er det sted, hvor de data, du uploader til et datasæt, oprindeligt kommer fra. En datakilde kan være en database, en Excel-projektmappe, en webtjeneste og meget mere. Med Excel-projektmapper kan du oprette et simpelt regneark med rækker af data, som betragtes som en datakilde. Du kan også bruge Power-forespørgsel eller Power Pivot i Excel til at oprette forbindelse til og anmode om data fra onlinedatakilder eller datakilder i det lokale miljø – og det hele kan gøres i den samme projektmappe. Med Power BI Desktop bruger du Hent data til at oprette forbindelse til og anmode om data fra onlinedatakilder eller datakilder i det lokale miljø.

Den personlige gateway installeres via datagatewayen i det lokale miljø. Du kan downloade den på [siden Power BI Gateway](https://powerbi.microsoft.com/gateway/).

## <a name="do-i-need-a-gateway"></a>Har jeg brug for en gateway?
Inden du installerer en gateway, er det vigtigt, at du ved, om du rent faktisk har brug for en gateway. Det afhænger af dine datakilder:

### <a name="on-premises-data-sources"></a>Datakilder i det lokale miljø
Der *kræves* en personlig gateway, hvis du vil kunne opdatere de datasæt, der henter data fra en understøttet datakilde i det lokale miljø.

Med en gateway understøttes OPDATER NU og PLANLÆG OPDATERING for de datasæt, der uploades fra:

* Projektmapper i Microsoft Excel 2013 (eller nyere), hvor Power-forespørgsel eller Power Pivot bruges til at oprette forbindelse til og anmode om data fra en understøttet datakilde i det lokale miljø. Alle de datakilder i det lokale miljø, der vises i Hent eksterne data i Power-forespørgsel eller Power Pivot, understøtter opdatering – dog med undtagelse af Hadoop-filer (HDFS) og Microsoft Exchange.
* Microsoft Power BI Desktop-filer, hvor Hent data bruges til at oprette forbindelse til og anmode om data fra en understøttet datakilde i det lokale miljø. Alle de datakilder i det lokale miljø, der vises i Hent data, understøtter opdatering – dog med undtagelse af Hadoop-filer (HDFS) og Microsoft Exchange.

### <a name="online-data-sources"></a>Datakilder online
Der *kræves kun* en gateway, hvis du bruger funktionen [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx). I andre tilfælde kræves der *ikke* en gateway for at opdatere de datasæt, der kun henter data fra en datakilde online.

> [!NOTE]
> Hvis du bruger funktionen [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx), skal du kun bruge en gateway, hvis du publicerer datasættet eller din rapport igen efter den 18. november 2016.
> 
> 

OPDATER NU og PLANLÆG OPDATERING understøttes uden en gateway for de datasæt, der uploades fra:

* Indholdspakker fra onlinedatakilder (indholdspakketjenester\\). Som standard bliver datasæt fra indholdspakker automatisk opdateret en gang om dagen, men du kan også opdatere manuelt eller oprette en plan for opdatering.
* Projektmapper i Microsoft Excel 2013 (eller nyere), hvor Power-forespørgsel eller Power Pivot bruges til at oprette forbindelse til og anmode om data fra en onlinedatakilde.
* Microsoft Power BI Desktop-filer, hvor Hent data bruges til at oprette forbindelse til og anmode om data fra en onlinedatakilde.

**Spørgsmål:** Hvad gør jeg, hvis min Excel-projektmappe eller Power BI Desktop-fil henter data både fra onlinedatakilder og datakilder i det lokale miljø?

**Svar:** Du *skal* bruge en gateway. Du skal installere og konfigurere en gateway for at kunne opdatere data fra dine datakilder i det lokale miljø.

**Spørgsmål:** Hvad gør jeg, hvis min Excel-projektmappe kun indeholder rækker med data, som jeg har indtastet?**

**Svar:** Du *behøver ikke* at bruge en gateway. Du skal kun installere og konfigurere en gateway, hvis din projektmappe bruger Power-forespørgsel eller Power Pivot til at anmode om og indlæse dataene i datamodellen fra en understøttet datakilde i det lokale miljø

## <a name="setting-up-a-gateway-for-the-first-time"></a>Konfigurer en gateway den første gang
Når du skal konfigurere en gateway den første gang, kræver det en proces med tre trin:

1. Download og installér en gateway
2. Konfigurer gatewayen
3. Log på datakilder i Power BI

Lad os se nærmere på hvert trin.

### <a name="download-and-install-a-gateway"></a>Download og installér en gateway
> [!NOTE]
> Der er en ny version af den personlige gateway til Power BI, som kaldes **datagateway i det lokale miljø (personlig tilstand)**. I denne artikel beskrives den tidligere version af den personlige gateway, der blev kaldt **Power BI Gateway – Personal**, og som udgår og stopper med at virke efter den 31. juli 2017. Du kan finde oplysninger om den nye version af den personlige gateway, herunder, hvordan du installerer den nye version, i [ artiklen **Datagateway i det lokale miljø (personlig tilstand)**](service-gateway-personal-mode.md).
> 
> 

Du bliver bedt om at installere en gateway, når du klikker på OPDATER NU eller PLANLÆG OPDATERING for et understøttet datasæt den første gang. Hvis du vil downloade gatewayen, skal du vælge **Datagateway** i menuen Overførsler. Download [datagatewayen i det lokale miljø](http://go.microsoft.com/fwlink/?LinkID=820925).

Du skal vælge **Personlig gateway** i stedet for **Datagateway i det lokale miljø**, hvis du vil have din egen gateway.

Det er nemt at installere en gateway. Du skal vælge den placering, hvor du vil installere den, og du skal læse og acceptere licensaftalen som for ethvert andet program. Der er dog nogle vigtige ting, du skal vide. Du skal vide, hvilken type computer du installerer gatewayen på, og du skal vide, hvilken type konto du bruger til at logge på Windows på computeren.

> [!NOTE]
> Gatewayen skal have adgang til datakilden. Hvis din personlige computer ikke kan oprette forbindelse til datakilden, kan du overveje at installere en [datagateway i det lokale miljø](service-gateway-onprem.md) på en computer, der har adgang til datakilden. Et eksempel på dette kan være SQL Server, der er installeret på en virtuel maskine (VM) i Azure. Din personlige computer har muligvis ikke adgang til den virtuelle maskine. Du kan i stedet installere datagatewayen i det lokale miljø på den virtuelle maskine og konfigurere en datakilde i Power BI tjenesten.
> 
> 

### <a name="computer-type"></a>Computertype
Den type computer, du installerer gatewayen på, er vigtig.

> [!NOTE]
> Den personlige gateway understøttes kun på 64-bit Windows.
> 
> 

På en bærbar computer – hvis du vil kunne planlægge en opdatering, skal gatewayen køre. Bærbare computere er som regel oftere lukket eller i dvaletilstand, end de er tændt. Hvis du installerer din gateway på en bærbar computer, skal du angive tiderne for planlagte opdateringer til tidspunkter, hvor den bærbare computer kører. Hvis den ikke er tændt på det planlagte tidspunkt, vil opdateringen ikke blive forsøgt igen før den næste planlagte opdatering.

På en stationær computer – her opstår der ikke mange problemer. Du skal blot sørge for, at computeren og gatewayen kører på de planlagte tidspunkter. Mange stationære computere er også indstillet til at skifte til dvaletilstand, men planlagte opdateringer kan ikke køres, hvis computeren er i dvaletilstand.

Når du installerer en gateway, skal du ikke installere en anden. Én gateway kan bruges med en lang række understøttede datasæt. Du behøver heller ikke at installere gatewayen på den computer, som du uploader din projektmappe og Power BI Desktop-filer fra. Her er et eksempel: Lad os sige, at du har en Excel-projektmappe, der opretter forbindelse til en SQL Server-datakilde i din organisation. Du brugte Hent data i Power BI til at uploade projektmappen fra din bærbare computer. Du har også en stationær computer, som kører hele tiden, og du har installeret og konfigureret en gateway på den computer. I Power BI har du logget på dine datakilder, og du har planlagt en opdatering for datasættet.  Når det er tid til opdateringen, vil Power BI oprette en sikker forbindelse til den gateway, der er installeret på din stationære computer. Derefter opretter den sikker forbindelse til datakilderne for at hente opdateringerne. Når dataene opdateres, sker der ingen kommunikation med den oprindelige projektmappe, du uploadede fra din bærbare computer.

> [!NOTE]
> Du kan installere personlige gateways og virksomhedsgateways på den samme computer.
> 
> 

### <a name="windows-account"></a>Windows-konto
Når du har installeret gatewayen, bliver du logget på computeren med din Windows-konto. De tilladelser, der er tildelt din Windows-konto, vil have betydning for, hvordan gatewayen installeres, og hvordan den køres i Windows.

Når du er logget på Windows:

|  | Med administratorrettigheder | Uden administratorrettigheder |
| --- | --- | --- |
| **Power BI Gateway - Personal kører som** |En tjeneste |Et program |
| **Planlagt opdatering** |Så længe din computer og gatewaytjenesten kører, behøver du ikke at være logget på på det planlagte opdateringstidspunkt. |Du skal være logget på din computer på det planlagte opdateringstidspunkt. |
| **Skift adgangskode til din Windows-konto** |Du skal ændre din adgangskode i gatewaytjenesten. Hvis adgangskoden til den konto, der bruges af gatewayen, ikke længere er gyldig, kan opdateringen ikke gennemføres. |Gatewayen kører altid ved hjælp af den konto og adgangskode, du aktuelt er logget på med. Hvis du ikke har logget på Windows, vil gatewayen ikke køre, og opdateringen kan ikke gennemføres. |

### <a name="configure-the-gateway"></a>Konfigurer gatewayen
Når installationsguiden er færdig, bliver du bedt om at starte konfigurationsguiden. Det er nemt at konfigurere en gateway. Du skal logge på Power BI fra guiden. Guiden skal oprette forbindelse til din Power BI-konto i Power BI-tjenesten.

Hvis du er logget på Windows med en konto med administratorrettigheder, bliver du bedt om at angive logonoplysningerne til din Windows-konto. Du kan angive en anden Windows-konto, men husk på, at tilladelserne bestemmer, hvordan gatewayen køres. Gatewaytjenesten kører med denne konto.

### <a name="sign-in-to-data-sources"></a>Log på datakilder
Når konfigurationsguiden er færdig, og din gateway kører, skal du angive en godkendelsestype og logge på hver af de datakilder, der bruges til dit datasæt. Du skal fuldføre dette trin i Power BI.

![](media/personal-gateway/pg_dataset_settings_signin.png)

Du skal kun angive en godkendelsestype og logge på en datakilde én gang. Du logger på fra sektionen **Administrer datakilder** på skærmen Indstillinger for datasættet. Hvis du har flere datakilder, skal du logge på hver af dem. Gatewayen bestemmer standardgodkendelsestypen afhængigt af datakilden. I de fleste tilfælde vil det være Windows-godkendelse, men i nogle tilfælde kan din datakilde kræve en anden godkendelsestype. Hvis du ikke er sikker, skal du spørge administratoren for datakilden.

## <a name="up-and-running"></a>Når gatewayen kører.
Når din gateway kører, kan du klikke på PLANLÆG OPDATERING for et datasæt for at få vist siden med indstillinger for datasættet.

![](media/personal-gateway/pg_awintsales_settings.png)

På denne side vises:

1. Opdateringsstatus – viser, om den seneste opdatering blev fuldført samt tidspunktet for den næste planlagte opdatering.
2. **Gateway** – viser om der er installeret en gateway, og om den er online. Hvis der er installeret en gateway, men den ikke er online, er indstillingerne for Administrer datakilde og Planlæg opdatering deaktiveret.
3. **Administrer datakilder**  – viser de datakilder, som datasættet opretter forbindelse til. Du kan logge på eller vælge en anden godkendelsestype. Du skal kun logge på hver datakilde én gang.
4. **Planlæg opdatering** – her kan du angive indstillingerne for en planlagt opdatering. Hvis gatewayen ikke er online, vil disse indstillinger være deaktiveret.
5. Meddelelser om fejlbehæftet opdatering – hvis denne indstilling er aktiveret (standard), sendes der en mail til dig, hvis en planlagt opdatering ikke bliver gennemført.

## <a name="updating-your-windows-account-password"></a>Skift adgangskode til din Windows-konto
Hvis du var logget på din computer med en Windows-konto med administratorrettigheder, da du installerede din gateway, kører den som en tjeneste ved hjælp af den Windows-konto, som du angav i konfigurationsguiden. Som regel vil det være den samme Windows-konto, som du bruger, når du logger på din computer. Hvis du ændrer adgangskoden til din Windows-konto, skal du også ændre den i gatewayen. Ellers vil tjenesten muligvis ikke køre, og opdateringen kan ikke gennemføres. Hvis du vil ændre adgangskoden til din Windows-konto for gatewayen, skal du vælge ikonet for din personlige gateway på proceslinjen i Windows eller i Apps.

![](media/personal-gateway/pg_programicon.png)

Herfra kan du opdatere adgangskoden og kontrollere din gateways forbindelsesstatus.

![](media/personal-gateway/pg_credentials.png)

## <a name="ports"></a>Porte
Gatewayen kommunikerer via udgående porte: TCP 443 (standard), 5671, 5672, 9350 til og med 9354.  Gatewayen kræver ikke indgående porte.

| Domænenavne | Udgående porte | Beskrivelse |
| --- | --- | --- |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Lyttere på Service Bus Relay via TCP (kræver 443 til anskaffelse af adgangskontroltoken) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| login.windows.net |443 |HTTPS |

Hvis du har brug for at hvidliste IP-adresser i stedet for domæner, kan du downloade og bruge IP-intervallisten fra Microsoft Azure Datacenter. [Download](https://www.microsoft.com/download/details.aspx?id=41653)

## <a name="next-steps"></a>Næste trin
[Datagateway i det lokale miljø (personlig tilstand) – den nye version af den personlige gateway](service-gateway-personal-mode.md)
[Konfigurer proxyindstillingerne for gateways i Power BI](service-gateway-proxy.md)  
[Power BI Premium](service-premium.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

