---
title: Opret forbindelse til en Impala-database i Power BI Desktop
description: Du kan nemt oprette forbindelse til og bruge en Impala-database i Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 7b6abc7ee00668e8be305b52235a8c967d0c938e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
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
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder under følgende ressourcer:

* [Kom i gang med Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

