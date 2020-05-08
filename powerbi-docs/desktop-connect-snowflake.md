---
title: Opret forbindelse til Snowflake-databehandlingswarehouse i Power BI Desktop
description: Opret let forbindelse til og brug Snowflake-databehandlingswarehouse i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e7534fd0da2039a2dafaf3ca80ee6957fa8d8754
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "77464295"
---
# <a name="connect-to-a-snowflake-computing-warehouse-in-power-bi-desktop"></a>Opret forbindelse til et Snowflake-databehandlingswarehouse i Power BI Desktop
I Power BI Desktop kan du oprette forbindelse til et **Snowflake**-databehandlingswarehouse og bruge de underliggende data på samme måde som enhver anden datakilde i Power BI Desktop. 

> [!NOTE]
> Du *skal* også installere **Snowflake ODBC-driveren** på computere, der bruger **Snowflake**-connectoren, vha. den arkitektur, der svarer til installationen af  **Power BI Desktop**, dvs. enten 32-bit eller 64-bit. Du skal blot følge nedenstående link og [downloade den relevante Snowflake ODBC-driver](https://go.microsoft.com/fwlink/?LinkID=823762).
> 
> 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Opret forbindelse til et Snowflake-databehandlingswarehouse
Hvis du vil oprette forbindelse til et **Snowflake**-databehandlingswarehouse, skal du vælge **Hent data** på båndet **Hjem** i Power BI Desktop. Vælg **Database** blandt kategorierne til venstre, hvorefter du kan se **Snowflake**.

![](media/desktop-connect-snowflake/connect-snowflake-2b.png)

I det viste vindue, **Snowflake**, skal du skrive eller indsætte navnet på dit Snowflake-databehandlingswarehouse i feltet og vælge **OK**. Bemærk, at du kan vælge at **importere** data direkte i Power BI, eller du kan bruge **DirectQuery**. Du kan få mere at vide om [brug af DirectQuery](desktop-use-directquery.md). Bemærk, at AAD SSO kun understøtter DirectQuery.

![](media/desktop-connect-snowflake/connect-snowflake-3.png)

Når du bliver bedt om det, skal du angive dit brugernavn og din adgangskode.

![](media/desktop-connect-snowflake/connect-snowflake-4.png)

> [!NOTE]
> Når du angiver dit brugernavn og din adgangskode for en bestemt **Snowflake**-server, anvendes de samme legitimationsoplysninger i efterfølgende forsøg på at oprette forbindelse via Power BI Desktop. Du kan ændre disse legitimationsoplysninger ved at gå til **Filer > Indstillinger > Indstillinger for datakilde**.
> 
> 

Hvis du vil bruge indstillingen Microsoft-konto, skal Snowflake AAD-integrationen konfigureres på Snowflake-siden. Det kan du gøre ved at læse afsnittet med introduktionen i [dokumentationen til Snowflake om emnet](https://docs.snowflake.net/manuals/user-guide/oauth-powerbi.html#power-bi-sso-to-snowflake).

![Godkendelsestype af Microsoft-konto i Snowflake-connector.](media/desktop-connect-snowflake/connect-snowflake-6.png)


Når du har oprettet forbindelse, vises et vindue af typen **Navigator**, hvor de data, der er tilgængelige på serveren, vises. Her kan du vælge et eller flere elementer, der skal importeres og bruges i **Power BI Desktop**.

![ODBC-fejl 28000 medfører, at der ikke kan oprettes forbindelse.](media/desktop-connect-snowflake/connect-snowflake-5.png)

Du kan **indlæse** den valgte tabel, der fører hele tabellen ind i **Power BI Desktop**, eller du kan **redigere** forespørgslen, der åbner **Forespørgselseditor**, så du kan filtrere og finindstille det datasæt, du vil bruge, og derefter indlæse dette finindstillede datasæt i **Power BI Desktop**.

## <a name="next-steps"></a>De næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Hvis du vil have mere at vide om datakilder, kan du se følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

