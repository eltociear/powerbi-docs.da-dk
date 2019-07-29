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
ms.openlocfilehash: 7827ce359022eccfb75798b08da164b7504c84df
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271840"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Fejlfinding af Power BI Gateway – Personal

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

I nedenstående afsnit gennemgås nogle almindelige problemer, der kan opstå, når du bruger Power BI Gateway – Personal.

## <a name="update-to-the-latest-version"></a>Opdater til den nyeste version

Den aktuelle version af gatewayen til personlig brug er **datagateway i det lokale miljø (personlig)** . Opdater din installation, hvis du vil bruge denne version.

Der kan opstå mange problemer, hvis gatewayversionen er forældet.  Det er generelt en god idé at sikre, at du anvender den nyeste version. Hvis du ikke har opdateret gateway'en i en måned eller mere, bør du overveje at installere den nyeste version af gateway'en. Se derefter, om du kan genskabe problemet.

## <a name="installation"></a>Installation
**Personlig gateway er 64-bit** – hvis din computer er 32-bit, kan du ikke installere den personlige gateway. Operativsystemet skal være en 64-bit-version. Installer en 64-bit version af Windows, eller installer den personlige gateway på en 64-bit-computer.

**Personlig gateway kan ikke installere en tjeneste, selvom du er en lokal administrator på computeren** – Installationen kan mislykkes, hvis brugeren er i computerens lokale Administratorgruppe, men gruppepolitikken ikke tillader det pågældende brugernavn at logge på som en tjeneste. I øjeblikket skal du sørge for, at gruppepolitikken tillader en bruger at logge på som en tjeneste. Vi arbejder på at finde en rettelse på problemet. [Få mere at vide](https://technet.microsoft.com/library/cc739424.aspx)

**Handlingen fik timeout** – Denne meddelelse forekommer tit, hvis computeren (fysisk maskine eller VM), du installerer den personlige gateway på, har en enkeltkerne-processor. Luk alle programmer, afbryd alle ikke-essentielle processer, og prøv at installere igen.

**Dataadministrationsgateway eller Analysis Services Connector kan ikke være installeret på samme computer som en personlig gateway**. Hvis du allerede har en Analysis Services Connector eller Dataadministrationsgateway installeret, skal du først fjerne installationen af forbindelseskomponenten eller gateway'en. Prøv derefter at installere den personlige gateway.

> [!NOTE]
> Hvis du støder på et problem under installationen, kan du muligvis få oplysninger om, hvordan du udbedrer problemet i installationslogfilerne. Se [Installationslogfiler](#SetupLogs) for at få flere oplysninger.
> 
> 

 **Proxykonfiguration** Der kan opstå problemer med at konfigurere den personlige gateway, hvis dit miljø kræver, at du bruger en proxy. Hvis du vil vide mere om, hvordan du konfigurerer proxyoplysninger, skal du se [Konfiguration af proxyindstillinger til datagateway'en i det lokale miljø](/data-integration/gateway/service-gateway-proxy).

## <a name="schedule-refresh"></a>Planlæg opdatering
**Fejl: De cloudlagrede legitimationsoplysninger mangler.**

Du kan få denne fejl i Indstillinger for \<datasæt\>, hvis du har en planlagt opdatering og derefter har installeret og geninstalleret den personlige gateway. Når du fjerner installationen af en personlig gateway, så fjernes legitimationsoplysninger for datakilden knyttet til datasæt, der er blevet konfigureret til opdatering, fra Power BI-tjenesten.

**Løsning:** I Power BI skal du gå til opdateringsindstillingerne for et datasæt. I Administrer datakilder skal du vælge **Rediger legitimationsoplysninger** for alle relevante datakilder med fejl og logge på datakilden igen.

**Fejl: De angivne legitimationsoplysninger for datasættet er ugyldige. Opdater legitimationsoplysningerne ved at opdatere eller vælge at fortsætte på dialogskærmen Indstillinger for datakilde.**

**Løsning**: Hvis du får vist en meddelelse om legitimationsoplysninger, skal du muligvis:

* Kontrollere, at brugernavne og adgangskoder til at logge på datakilder er opdaterede. I Power BI skal du gå til opdateringsindstillingerne for datasættet. Vælg **Rediger legitimationsoplysninger** for at opdatere legitimationsoplysningerne for datakilden under Administrer datakilder.
* Miks af en cloudbaseret datakilde og en datakilde i det lokale miljø i en enkelt forespørgsel kan ikke opdateres i den personlige gateway, hvis en af kilderne bruger OAuth til godkendelse. Et eksempel på denne fejl er et miks af CRM Online og en lokal SQL Server. Dette miks mislykkes, fordi CRM Online kræver OAuth.
  
  Dette er en kendt fejl, som der kigges på. Du kan løse problemet ved at have en separat forespørgsel for cloudkilden og kilden i det lokale miljø. Brug derefter en Flet eller tilføj-forespørgsel for at kombinere dem.

**Fejl: Datakilde understøttes ikke.**

**Løsning:** Hvis du får en meddelelse om, at datakilden ikke understøttes, i indstillingerne for planlægning af en opdatering, kan det betyde følgende: 

* Datakilden understøttes i øjeblikket ikke mht. opdatering i Power BI. 
* Excel-projektmappen indeholder ikke en datamodel, men kun regnearksdata. Power BI understøtter i øjeblikket kun opdatering, hvis den uploadede Excel-projektmappe indeholder en datamodel. Når du importerer data ved hjælp af Power-forespørgsel i Excel, skal du vælge funktionen til indlæsning af data i datamodellen. Denne funktion sikrer, at data importeres i en datamodel. 

**Fejl: [Dataene kan ikke kombineres] &lt;forespørgselsdel&gt;/&lt;... &gt;/&lt;...&gt; får adgang til datakilder med niveauer for beskyttelse af personlige oplysninger, der ikke kan bruges sammen. Byg denne datakombination igen.**

**Løsning**: Denne fejl opstår på grund af begrænsninger for niveauet for beskyttelse af personlige oplysninger og de typer datakilder, du bruger.

**Fejl: Fejl i datakilde: Vi kan ikke konvertere værdien "\[Tabel\]" til typen Tabel.**

**Løsning**: Denne fejl opstår på grund af begrænsninger for niveauet for beskyttelse af personlige oplysninger og de typer datakilder, du bruger.

**Fejl: Der er ikke tilstrækkelig plads til denne række.**

Denne fejl opstår, hvis du har en enkelt række, der er større end 4 MB. Find rækken fra din datakilde, og forsøg at filtrere den ud eller mindske den pågældende rækkes størrelse.

## <a name="data-sources"></a>Datakilder
**Manglende dataudbyder** – den personlige gateway er kun 64-bit-versionen. Du skal bruge en 64-bit-version af dataudbyderne, for at de kan installeres på den samme computer, som den personlige gateway er installeret. Hvis datakilden i datasættet f.eks. er Microsoft Access, skal du installere 64-bit-ACE-udbyderen på den samme computer, som du har installeret den personlige gateway.  

>[!NOTE]
>Hvis du har 32-bit-versionen af Excel, kan du ikke installere en 64-bit-version ACE-provider på den samme computer.

**Windows-godkendelse understøttes ikke for Access-databaser** – Power BI understøtter for øjeblikket kun anonymt for Access-databaser. Vi arbejder på at aktivere Windows-godkendelse for Access-databaser.

**Logonfejl ved angivelse af legitimationsoplysninger for en datakilde**. Hvis du modtager en fejl som denne, når du angiver Windows-legitimationsoplysningerne for en datakilde, så benytter du muligvis stadig en ældre version af den personlige gateway. [Installér den nyeste version af Power BI Gateway – Personal](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Fejl: Logonfejl, når du vælger Windows-godkendelse for en datakilde ved hjælp af ES OLEDB** – hvis du modtager den følgende fejl, når du angiver legitimationsoplysninger til datakilden med ES OLEDB-udbyderen:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI understøtter i øjeblikket ikke Windows-godkendelse for en datakilde ved hjælp af ACE OLEDB-udbyder.

**Løsning:** Du omgår fejlen ved at vælge **anonym godkendelse**. For ældre ACE OLEDB-udbydere svarer anonyme legitimationsoplysninger til Windows-legitimationsoplysninger.

## <a name="tile-refresh"></a>Opdatering af felter
Hvis du får vist en fejl, der opstår ved opdatering af dashboardfelter, så skal du se den følgende artikel.

[Fejlfinding af feltfejl](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Værktøjer til fejlfinding
### <a name="refresh-history"></a>Opdater historik
**Opdateringshistorikken** hjælper dig med at se, hvilke fejl der er opstået, og viser nyttige data, hvis du har brug for at oprette en supportanmodning. Du kan få vist både planlagte opdateringer og opdateringer efter behov. Sådan får du vist **Opdater historik**.

1. I Power BI-navigationsruden i **Datasæt** skal du vælge et datasæt &gt; Åbn menu &gt; **Planlæg opdatering**.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. I **Indstillinger for...** skal du vælge **Opdater historik**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Hændelseslogge
Adskillelige hændelseslogge kan levere oplysninger. De første to, **Dataadministrationsgateway** og **PowerBIGateway**, vises, hvis du er administrator på computeren.  Hvis du ikke er administrator, og du bruger den personlige gateway, får du vist logposterne i **Program**-loggen.

Loggene **Datastyringsgateway** og **PowerBIGateway** findes under **Program- og tjenestelogfiler**.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler-sporing
[Fiddler](http://www.telerik.com/fiddler) er et gratis værktøj fra Telerik, der overvåger HTTP-trafik. Du kan se kommunikationen vha. Power BI-tjenesten fra klientcomputeren. Denne kommunikation kan vise fejl og andre relaterede oplysninger.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Installationslogge
Hvis den **personlige gateway** ikke kan installeres, så modtager du et link til visning af installationsloggen. Du kan finde oplysninger om fejlen i installationsloggen. Disse logge er Windows-installationslogge, også kaldet MSI-logge. De kan være ret komplekse og svære at læse. Den resulterende fejl vises typisk i bunden, men det er ikke let at finde årsagen til fejlen. Der kan være tale om resultatet af fejl i en anden log eller resultatet af en fejl højere oppe i loggen.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Du kan også gå til **Temp-mappen** (% temp %) og søge efter filer, der starter med **Power\_BI\_** .

> [!NOTE]
> Når du går til %temp%, kan du blive ført til en undermappe i temp. **Power\_BI\_** -filerne ligger i roden af temp-mappen.  Du skal muligvis gå et niveau eller to op.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Næste trin
[Konfiguration af proxyindstillinger for datagateway i det lokale miljø](/data-integration/gateway/service-gateway-proxy)  
[Dataopdatering](refresh-data.md)  
[Power BI-gateway – personal](service-gateway-personal-mode.md)  
[Fejlfinding af feltfejl](refresh-troubleshooting-tile-errors.md)  
[Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

