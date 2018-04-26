---
title: Opret forbindelse til en Impala-database i Power BI Desktop
description: Du kan nemt oprette forbindelse til og bruge en Impala-database i Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: bef087b485573ba9a629887bfb05d875c88c8b4c
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/26/2018
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Opret forbindelse til en Impala-database i Power BI Desktop
I Power BI Desktop kan du oprette forbindelse til en **Impala**-database og bruge de underliggende data på samme måde som enhver anden datakilde i Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Opret forbindelse til en Impala-database
Hvis du vil oprette forbindelse til en **Impala**-database, skal du vælge **Hent data** på båndet **Hjem** i Power BI Desktop. Vælg **Database** blandt kategorierne til venstre, hvorefter du kan se **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

I vinduet **Impala**, der åbnes, skal du skrive eller indsætte navnet på din Impala-server i feltet og derefter vælge **OK**. Bemærk, at du kan vælge at **importere** data direkte i Power BI, eller du kan bruge **DirectQuery**. Du kan få mere at vide om [brug af DirectQuery](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Når du bliver spurgt, skal du skrive dit brugernavn og din adgangskode eller oprette forbindelse anonymt – begge metoder understøttes.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Når du angiver dit brugernavn og din adgangskode for en bestemt **Impala**-server, anvendes de samme legitimationsoplysninger i efterfølgende forsøg på at oprette forbindelse via Power BI Desktop. Du kan ændre disse legitimationsoplysninger ved at gå til **Filer > Indstillinger > Indstillinger for datakilde**.
> 
> 

Når du har oprettet forbindelse, vises der et vindue af typen **Navigator**, hvor de data, der er tilgængelige på serveren, vises. Her kan du vælge et eller flere elementer, der skal importeres og bruges i **Power BI Desktop**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
Der er et par begrænsninger og overvejelser, du skal være opmærksom på i forbindelse med **Impala**-forbindelsen:

* Fremtidige planer omfatter aktivering af understøttelse af opdatering ved hjælp af **Power BI Gateway**.

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

