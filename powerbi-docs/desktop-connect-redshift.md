---
title: Opret forbindelse til en Amazon Redshift-database i Power BI Desktop
description: Opret nemt forbindelse til og brug en Amazon Redshift-database i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b1085c3715d9b4b75925cec1b94ec49b0f5792f7
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "34813129"
---
# <a name="connect-to-amazon-redshift-in-power-bi-desktop"></a>Opret forbindelse til Amazon Redshift i Power BI Desktop
I **Power BI Desktop** kan du oprette forbindelse til en **Amazon Redshift**-database og bruge de underliggende data på samme måde som enhver anden datakilde i Power BI Desktop.

## <a name="connect-to-an-amazon-redshift-database"></a>Opret forbindelse til en Amazon Redshift-database
Hvis du vil oprette forbindelse til en **Amazon Redshift**-database, skal du vælge **Hent data** på båndet **Hjem** i Power BI Desktop. Vælg **Database** blandt kategorierne til venstre, hvorefter du kan se **Amazon Redshift**.

![](media/desktop-connect-redshift/connect_redshift_3.png)

I det **Amazon Redshift**-vindue, der åbnes, skal du skrive eller indsætte navnet på din **Amazon Redshift**-server og -database i feltet. I feltet *Server* kan brugerne angive en port i følgende format: *ServerURL:Port*

![](media/desktop-connect-redshift/connect_redshift_4.png)

Når du bliver bedt om det, skal du angive dit brugernavn og din adgangskode. Du bør bruge et servernavn, der passer nøjagtigt til SSL-certifikatet, for at undgå fejl. 

![](media/desktop-connect-redshift/connect_redshift_5.png)

Når du har oprettet forbindelse, vises der et vindue af typen **Navigator**, hvor de data, der er tilgængelige på serveren, vises. Her kan du vælge et eller flere elementer, der skal importeres og bruges i **Power BI Desktop**.

![](media/desktop-connect-redshift/connect_redshift_6.png)

Når du har foretaget valg i vinduet **Navigator**, kan du enten **indlæse** eller **redigere** dataene.

* Hvis du vælger at **indlæse** data, bliver du spurgt, om du vil bruge tilstanden *Import* eller *DirectQuery* til at indlæse dataene. Du kan finde flere oplysninger i denne [artikel, der forklarer DirectQuery](desktop-use-directquery.md).
* Hvis du vælger at **redigere** data, vises **forespørgselseditoren**, hvor du kan anvende alle mulige forskellige transformeringer og filtre på dataene, hvoraf mange anvendes på selve den underliggende **Amazon Redshift**-database (hvis det understøttes).

## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

