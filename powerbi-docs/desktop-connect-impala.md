---
title: Opret forbindelse til en Impala-database i Power BI Desktop
description: Du kan nemt oprette forbindelse til og bruge en Impala-database i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7feb562c5d2d96c4d726b93393a0b4a26c658415
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37134748"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Opret forbindelse til en Impala-database i Power BI Desktop
I Power BI Desktop kan du oprette forbindelse til en **Impala**-database og bruge de underliggende data på samme måde som enhver anden datakilde i Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Opret forbindelse til en Impala-database
Hvis du vil oprette forbindelse til en **Impala**-database, skal du vælge **Hent data** på båndet **Hjem** i Power BI Desktop. Vælg **Database** blandt kategorierne til venstre, hvorefter du kan se **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

I vinduet **Impala**, der åbnes, skal du skrive eller indsætte navnet på din Impala-server i feltet og derefter vælge **OK**. Bemærk, at du kan vælge at **importere** data direkte i Power BI, eller du kan bruge **DirectQuery**. Du kan få mere at vide om [brug af DirectQuery](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Angiv dine legitimationsoplysninger, når du bliver bedt om det, eller opret forbindelse anonymt. Impala-connectoren understøtter Anonymous-, Basic- (brugernavn + adgangskode) og Windows-godkendelse.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Når du angiver dit brugernavn og din adgangskode for en bestemt **Impala**-server, anvendes de samme legitimationsoplysninger i efterfølgende forsøg på at oprette forbindelse via Power BI Desktop. Du kan ændre disse legitimationsoplysninger ved at gå til **Filer > Indstillinger > Indstillinger for datakilde**.
> 
> 

Når du har oprettet forbindelse, vises der et vindue af typen **Navigator**, hvor de data, der er tilgængelige på serveren, vises. Her kan du vælge et eller flere elementer, der skal importeres og bruges i **Power BI Desktop**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
Der er et par begrænsninger og overvejelser, du skal være opmærksom på i forbindelse med **Impala**-forbindelsen:

* Connectoren Impala understøttes i datagatewayen i det lokale miljø vha. en af de tre understøttede godkendelsesmetoder.

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

