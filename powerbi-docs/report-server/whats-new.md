---
title: Nyheder i Power BI-rapportserver
description: "Læs om nyheder i Power BI-rapportserver. Dette dækker de primære funktionsområder og opdateres i takt med, at der frigives nye elementer."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/31/2017
ms.author: asaxton
ms.openlocfilehash: d351a117307e86c7b0750e9bcdf813b08b28bb0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="whats-new-in-power-bi-report-server"></a>Nyheder i Power BI-rapportserver
Læs om nyheder i Power BI-rapportserver. Dette dækker de primære funktionsområder og opdateres i takt med, at der frigives nye elementer.

Hvis du vil downloade Power BI-rapportserver og Power BI Desktop optimeret til Power BI-rapportserver, skal du gå til [Rapportering i det lokale miljø med Power BI-rapportserver](https://powerbi.microsoft.com/report-server/).

![tip](media/whats-new/fyi-tip.png "tip") Se de aktuelle produktbemærkninger i [Power BI-rapportserver – produktbemærkninger](release-notes.md).

Du kan finde relaterede oplysninger om nyheder under:

* [Nyheder i Power BI-tjenesten](../service-whats-new.md)
* [Nyheder i Power BI Desktop](../desktop-latest-update.md)
* [Nyheder i mobilappsene til Power BI](../mobile-whats-new-in-the-mobile-apps.md)
* [Power BI-temaets blog](https://powerbi.microsoft.com/blog/)

## <a name="october-2017-release"></a>Udgivelse fra oktober 2017
### <a name="power-bi-report-data-sources"></a>Power BI-rapportdatakilder
Power BI-rapporter i Power BI-rapportserver kan oprette forbindelse til en række forskellige datakilder. Du kan importere data og planlægge dataopdateringer, eller du kan forespørge på dem direkte ved hjælp af DirectQuery eller en liveforbindelse til SQL Server Analysis Services. Se listen over datakilder, der understøtter planlagt opdatering, og dem, der understøtter DirectQuery, i "Power BI-rapportdatakilder i Power BI-rapportserver".

### <a name="scheduled-data-refresh-for-imported-data"></a>Planlagt dataopdatering for importerede data
I Power BI-rapportserver kan du konfigurere planlagt opdatering af data for at sikre, at dataene er opdateret i Power BI-rapporter ved hjælp af en integreret model i stedet for en liveforbindelse eller DirectQuery. Med en integreret model importerer du dataene, så forbindelsen til den oprindelige datakilde afbrydes. Den skal opdateres for at holde dataene friske, og planlagt opdatering er måden at gøre det på. Læs mere om planlagt opdatering til Power BI-rapporter i Power BI-rapportserver.

### <a name="editing-power-bi-reports-from-the-server"></a>Redigering af Power BI-rapporter fra serveren
Du kan åbne og redigere Power BI-rapportfiler (.pbix) fra serveren, men du får den oprindelige fil tilbage, du har uploadet.  Det betyder, at **hvis dataene er blevet opdateret af serveren, opdateres dataene ikke, når du åbner filen første gang**. Du skal opdatere manuelt lokalt for at se ændringen.

### <a name="large-file-uploaddownload"></a>Upload/download af store filer
Du kan uploade filer på op til 2 GB, men som standard er denne grænse indstillet til 1 GB i indstillingerne for rapportserver i SQL Server Management Studio (SSMS).  Disse filer gemmes, som de er, i databasen til SharePoint, og der kræves ingen særlig konfiguration for SQL Server-kataloget.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Få adgang til delte datasæt såsom OData-feeds
Du kan få adgang til delte datasæt fra Power BI Desktop med et OData-feed. Du kan få mere at vide i [Få adgang til delte datasæt såsom OData-feeds på Power BI-rapportserver](access-dataset-odata.md).

### <a name="scale-out"></a>Scale-out
Denne udgave understøtter scale-out. Brug en belastningsjustering, og angiv servertilknytning for at få den bedste oplevelse. Bemærk, at scenariet endnu ikke er optimeret til scale-out, så du får vist modeller, som kan være replikeret på tværs af flere noder. Scenariet fungerer uden Network Load Balancer og sticky sessions. Du vil dog ikke kun se et overforbrug af hukommelse på tværs af noder, fordi modellen indlæses N gange, men ydeevnen sænkes mellem forbindelserne, da modellen streames, når den rammer en ny node mellem anmodningerne.  

### <a name="administrator-settings"></a>Administratorindstillinger
Administratorer kan angive følgende egenskaber for serverfarmen under Avancerede egenskaber i SSMS:

* EnableCustomVisuals: Sand/Falsk
* EnablePowerBIReportEmbeddedModels: Sand/Falsk
* EnablePowerBIReportExportData: Sand/Falsk
* MaxFileSizeMb: Standard er nu 1000
* ModelCleanupCycleMinutes: Hvor ofte der kontrolleres for at fjerne modeller fra hukommelsen
* ModelExpirationMinutes: Hvor lang tid, før model er udløbet og fjernes, baseret på sidste gang den blev brugt
* ScheduleRefreshTimeoutMinutes: Hvordan længe dataopdatering kan vare for en model. Som standard er dette to timer.  Der er ingen fastsat øvre grænse.

**Konfigurationsfil rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Udvikler-API
Udvikler-API'en (REST-API), der blev introduceret i SSRS 2017, er blevet udvidet til Power BI-rapportserver for at fungere sammen med både Excel-filer og .pbix-filer. En potentiel use case er programmeringsmæssigt at downloade filer fra serveren, opdatere dem og publicere dem igen. Dette er eksempelvis den eneste måde, hvorpå du kan opdatere Excel-projektmapper med PowerPivot-modeller.

Bemærk, at der er en ny separat API til store filer, som vil blive opdateret i Power BI-rapportserverversionen af Swagger. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>Hukommelsesfodaftryk for SQL Server Analysis Services (SSAS) og Power BI-rapportserver
Power BI-rapportserver hoster nu SQL Server Analysis Services (SSAS) internt. Dette er ikke specifikt for planlagt opdatering. At hoste SSAS kan markant udvide hukommelsesfodaftrykket for rapportserveren. AS.ini-konfigurationsfilen findes på servernoderne, så hvis du kender SSAS, kan du opdatere indstillingerne, herunder største hukommelsesgrænse og cachelagring på disk osv. Se [Serveregenskaber i Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services), for at få mere at vide.

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Få vist og interager med Excel-projektmapper
Excel og Power BI indeholder en portefølje af værktøjer, som er de eneste af deres slags i branchen. Tilsammen giver de forretningsanalytikere mulighed for nemmere at indsamle, forme, analysere og udforske deres data visuelt. Foruden at få vist Power BI-rapporter i webportalen kan virksomhedsbrugerne nu gøre det samme med Excel-projektmapper i Power BI-rapportserver, hvilket giver dem én samlet placering til at publicere og få vist deres Microsoft BI-indhold til selvbetjening.

Vi har udgivet en [gennemgang af, hvordan du tilføjer Office Online Server (OOS) i miljøet i din prøveversion af Power BI-rapportserver](excel-oos.md). Kunder, der har en volumenlicenskonto, kan downloade OOS fra Volume License Service Center uden omkostninger og få skrivebeskyttet funktionalitet. Efter konfigurationen kan brugerne få vist og interagere med Excel-projektmapper, der:

* ikke har nogen afhængigheder af eksterne data
* har en direkte forbindelse til en ekstern SQL Server Analysis Services-datakilde
* har en PowerPivot-datamodel.

### <a name="support-for-new-table-and-matrix-visuals"></a>Understøttelse af nye tabel- og matrixvisuals
Power BI-rapportserver understøtter nu de nye Power BI-tabel- og matrixvisuals. Hvis du vil oprette rapporter med disse visuelle elementer, skal du bruge en opdateret version af Power BI Desktop-udgave til versionen fra oktober 2017. Den kan ikke installeres side om side med versionen af Power BI Desktop fra juni 2017. Hvis du vil have den seneste version af Power BI Desktop, skal du vælge **Avancerede indstillinger for hentning af filer** på [siden til download af Power BI-rapportserver](https://powerbi.microsoft.com/report-server/).

## <a name="june-2017"></a>Juni 2017
* Power BI-rapportserver er blevet gjort offentligt tilgængeligt (GA).

## <a name="may-2017"></a>Maj 2017
* Prøveversion af Power BI-rapportserver gjort tilgængelig
* Mulighed for at publicere Power BI-rapporter i det lokale miljø
  * Understøttelse af brugerdefinerede visuelle elementer
  * Kun understøttelse af Analysis Services-liveforbindelser, men med flere datakilder på vej.
  * Appen Power BI - Mobil er blevet opdateret til at vise Power BI-rapporter, der hostes i Power BI-rapportserver
* Forbedret samarbejde i rapporter med kommentarer

## <a name="next-steps"></a>Næste trin
[Produktbemærkninger til Power BI-rapportserver](release-notes.md)  
[Brugerhåndbog](user-handbook-overview.md)  
[Administratorhåndbog](admin-handbook-overview.md)  
[Hurtig introduktion: Installér Power BI-rapportserver](quickstart-install-report-server.md)  
[Installér Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

