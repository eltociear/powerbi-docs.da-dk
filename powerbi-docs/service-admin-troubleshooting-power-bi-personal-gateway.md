---
title: Fejlfinding af Power BI Gateway – Personal
description: Fejlfinding af Power BI Gateway – Personal
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 5/06/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: bc6eaccc2976266102dcca0d20df73df810fa5f3
ms.sourcegitcommit: bf535771c9ef495f9bb658569403fa5e3dd82e6a
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2019
ms.locfileid: "65853555"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Fejlfinding af Power BI Gateway – Personal
De følgende afsnit går gennem nogle almindelige problemer, du kan støde på, når du bruger Power BI Gateway – Personal.

> [!NOTE]
> Den aktuelle version af gatewayen til personlig brug er **datagateway i det lokale miljø (personlig)**. Opdater din installation, hvis du vil bruge denne version.
> 
> 

## <a name="update-to-the-latest-version"></a>Opdater til den nyeste version
Mange problemer kan opstå gatewayversionen er forældet.  Det er generelt en god idé at sikre, at du er på den nyeste version. Hvis du ikke har opdateret gatewayen i en måned eller mere, kan du overveje at installere den nyeste version af gatewayen. Se, om du kan genskabe problemet.

## <a name="installation"></a>Installation
**Personlig gateway er 64-bit** – Hvis computeren er 32-bit, kan du ikke installere den personlige gateway. Operativsystemet har skal være 64-bit versionen. Installere en 64-bit version af Windows eller installere den personlige gateway på en 64-bit-computer.

**Personlig gateway kan ikke installere som en tjeneste, selvom du er en lokal administrator på computeren** -installationen kan mislykkes, hvis brugeren er i computerens lokale administratorgruppe, men gruppepolitikken ikke tillader det pågældende brugernavn at logge på som en tjenesten. I øjeblikket, sikre, at gruppepolitikken giver mulighed for en bruger logge på som en tjeneste. Vi arbejder på at finde en rettelse på problemet. [Få mere at vide](https://technet.microsoft.com/library/cc739424.aspx)

**Handlingen fik timeout** -denne meddelelse er almindeligt, hvis computeren (fysisk maskine eller VM), du installerer den personlige gateway, der har en enkeltkerne-processor. Luk alle programmer, afbryd alle ikke-essentielle processer, og prøv at installere igen.

**Datastyringsgateway eller Analysis Services-forbindelseskomponent kan ikke installeres på samme computer som en personlig gateway** – Hvis du allerede har en Analysis Services-forbindelseskomponent eller Datastyringsgateway installeret, skal du først fjerne Connectoren eller gatewayen. Prøv derefter at installere den personlige gateway.

> [!NOTE]
> Hvis der opstår et problem under installationen, kan installationslogfilerne give oplysninger for at hjælpe dig med at løse problemet. Du kan finde flere oplysninger i [installationslogfiler](#SetupLogs).
> 
> 

 **Konfiguration af proxy** du opleve problemer med at konfigurere den personlige gateway, hvis dit miljø kræver brugen af en proxy. Hvis du vil vide mere om, hvordan du konfigurerer proxyoplysninger, skal du se [Konfiguration af proxyindstillinger til Power BI Gateways](service-gateway-proxy.md)

## <a name="schedule-refresh"></a>Planlæg opdatering
**Fejl: De cloudlagrede legitimationsoplysninger mangler.**

Du kan få denne fejl i indstillinger for \<datasæt\> Hvis du har en planlagt opdatering og derefter fjernes og geninstalleret den personlige gateway. Når du fjerner en personlig gateway, fjernes legitimationsoplysningerne for datakilden for et datasæt, der er blevet konfigureret til opdatering fra Power BI-tjenesten.

**Løsning:** I Power BI skal du gå til opdateringsindstillingerne for et datasæt. I Administrer datakilder for datakilder med en fejl, skal du vælge **Rediger legitimationsoplysninger** og logge på datakilden igen.

**Fejl: De angivne legitimationsoplysninger for datasættet er ugyldige. Opdater legitimationsoplysningerne ved at opdatere eller vælge at fortsætte på dialogskærmen Indstillinger for datakilde.**

**Løsning**: Hvis du får vist en meddelelse om legitimationsoplysninger, skal du muligvis:

* Kontrollér, at brugernavne og adgangskoder til at logge på datakilder er opdateret. I Power BI skal du gå til opdateringsindstillingerne for datasættet. Vælg i Administrer datakilder **Rediger legitimationsoplysninger** til at opdatere legitimationsoplysningerne for datakilden.
* Miks af en cloudbaseret datakilde og en datakilde i det lokale miljø, i en enkelt forespørgsel, ikke opdateres i den personlige gateway, hvis en af kilderne bruger OAuth til godkendelse. Et eksempel på dette problem er et miks af CRM Online samt en lokal SQL Server. Mikset mislykkes, fordi CRM Online kræver OAuth.
  
  Denne fejl er et kendt problem er det der kigges på. Du kan løse problemet ved at have en separat forespørgsel for cloudkilden og kilden i det lokale miljø. Brug en fletning derefter, eller Føj forespørgsel for at kombinere dem.

**Fejl: Datakilde understøttes ikke.**

**Løsning:** Hvis du får en meddelelse om, at datakilden ikke understøttes, i indstillingerne for planlægning af en opdatering, kan det betyde følgende: 

* Datakilden understøttes ikke i øjeblikket for opdatering i Power BI. 
* Excel-projektmappen indeholder ikke en datamodel, men kun regnearksdata. Power BI understøtter i øjeblikket kun opdatering, hvis den uploadede Excel-projektmappe indeholder en datamodel. Når du importerer data ved hjælp af Power-forespørgsel i Excel, skal du vælge funktionen til indlæsning af data i datamodellen. Denne indstilling sikrer, at data importeres i en datamodel. 

**Fejl: [Dataene kan ikke kombineres] &lt;forespørgselsdelen&gt;/&lt;... &gt; / &lt;... &gt; får adgang til datakilder med niveauer for beskyttelse af personlige oplysninger, som ikke kan bruges sammen. Byg denne datakombination igen.**

**Løsning**: Denne fejl er på grund af begrænsninger for niveauet for beskyttelse af personlige oplysninger og typerne af datakilder, du bruger.

**Fejl: Fejl i datakilde: Vi kan ikke konvertere værdien "\[Tabel\]" til typen Tabel.**

**Løsning**: Denne fejl er på grund af begrænsninger for niveauet for beskyttelse af personlige oplysninger og typerne af datakilder, du bruger.

**Fejl: Der er ikke tilstrækkelig plads til denne række.**

Denne fejl opstår, hvis du har en enkelt række, der er større end 4 MB i størrelse. Find rækken fra din datakilde og forsøge at filtrere den ud eller mindske den pågældende rækkes størrelse.

## <a name="data-sources"></a>Datakilder
**Manglende dataudbyder** – den personlige gateway er kun 64-bit-version. Du skal bruge en 64-bit-version af dataudbyderne, for at de kan installeres på den samme computer, som den personlige gateway er installeret. Hvis datakilden i datasættet f.eks. er Microsoft Access, skal du installere 64-bit-ACE-udbyderen på den samme computer, som du har installeret den personlige gateway.  

>[!NOTE]
>Hvis du har 32-bit-versionen af Excel, kan du ikke installere en 64-bit versionen ACE-udbyder på den samme computer.

**Windows-godkendelse understøttes ikke for Access-databaser** – Power BI understøtter for øjeblikket kun anonymt for Access-databaser. Vi arbejder på at aktivere Windows-godkendelse for Access-database.

**Logonfejl ved angivelse af legitimationsoplysninger for en datakilde** – Hvis du får en fejl, som dette, når du angiver Windows-legitimationsoplysninger for en datakilde, kan du stadig en ældre version af den personlige gateway. [Installér den nyeste version af Power BI Gateway – Personal](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Fejl: Logonfejl, når du vælger Windows-godkendelse for en datakilde ved hjælp af ES OLEDB** – hvis du modtager den følgende fejl, når du angiver legitimationsoplysninger til datakilden med ES OLEDB-udbyderen:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Powerbi understøtter i øjeblikket ikke Windows-godkendelse for en datakilde ved hjælp af ACE OLEDB-udbyder.

**Løsning:** Du kan løse denne fejl, kan du vælge **anonym godkendelse**. Anonyme legitimationsoplysninger er lig med Windows-legitimationsoplysninger for ældre ACE OLEDB-udbydere.

## <a name="tile-refresh"></a>Opdatering af felter
Hvis du modtager en fejl med felter i dashboardet opdateres, kan du se følgende artikel.

[Fejlfinding af feltfejl](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Værktøjer til fejlfinding
### <a name="refresh-history"></a>Opdater historik
**Opdater historik** hjælper med at se, hvilke fejl er opstået og giver nyttige data, hvis du vil oprette en supportanmodning. Du kan få vist både planlagte og opdateringer efter behov. Her er, hvordan du kommer til den **opdateringshistorik**.

1. I Power BI-navigationsruden i **Datasæt** skal du vælge et datasæt &gt; Åbn menu &gt; **Planlæg opdatering**.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. I **indstillinger for...** , skal du vælge **opdateringshistorik**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Hændelseslogge
Adskillelige hændelseslogge kan give oplysninger. De første to **Data Management Gateway** og **PowerBIGateway**, der vises, hvis du er administrator på computeren.  Hvis du ikke er administrator, og du bruger den personlige Gateway, får du vist logposterne i den **program** log.

Loggene **Datastyringsgateway** og **PowerBIGateway** findes under **Program- og tjenestelogfiler**.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler-sporing
[Fiddler](http://www.telerik.com/fiddler) er et gratis værktøj fra Telerik, der overvåger HTTP-trafik. Du kan se kommunikationen med Power BI-tjenesten fra klientcomputeren. Denne meddelelse kan vise fejl og andre relaterede oplysninger.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Installationslogge
Hvis den **personlige Gateway**, ikke kan installeres, får du vist et link til visning af installationsloggen. Af installationsloggen kan du få vist oplysninger om fejlen. Disse logfiler er Windows-installationslogge, også kaldet MSI-logge. De kan være ret komplekse og svære at læse. Typisk er den resulterende fejl i bunden, men ikke nemt at bestemme årsagen til fejlen. Der kan være tale om resultatet af fejl i en anden log eller resultatet af en fejl højere oppe i loggen.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Eller, kan du gå til din **Temp-mappen** (% temp %) og søge efter filer, der starter med **Power\_BI\_**.

> [!NOTE]
> Når du går til %temp%, kan du blive ført til en undermappe i temp. Den **Power\_BI\_**  filer er i roden af temp-mappen.  Du skal muligvis gå et niveau eller to op.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Næste trin
[Konfiguration af proxyindstillinger for Power BI Gateways](service-gateway-proxy.md)  
[Opdatering af data](refresh-data.md)  
[Power BI-gateway – personal](service-gateway-personal-mode.md)  
[Fejlfinding af feltfejl](refresh-troubleshooting-tile-errors.md)  
[Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

