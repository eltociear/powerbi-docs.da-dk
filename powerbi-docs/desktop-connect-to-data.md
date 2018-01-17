---
title: Opret forbindelse til data i Power BI Desktop
description: Opret forbindelse til data i Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 3acd0f833990fa590a6d17468c110ded713b7daa
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
---
# <a name="connect-to-data-in-power-bi-desktop"></a>Opret forbindelse til data i Power BI Desktop
I Power BI Desktop kan du nemt oprette forbindelse til en verden af data, der konstant udvides. Hvis du ikke har Power BI Desktop, kan du [downloade](http://go.microsoft.com/fwlink/?LinkID=521662) og installere det.

I Power BI Desktop findes der *alle mulige* forskellige datakilder. På følgende billede kan du se, hvordan du opretter forbindelse til data ved at vælge båndet **Filer** og derefter **Hent data \> Flere**.

![](media/desktop-connect-to-data/getdatavid_smallv2.gif)

I dette eksempel opretter vi forbindelse til en datakilde af typen **Web**.

Forestil dig, at du går på pension – du vil gerne bo et sted, hvor der er masser af solskin, bedre skatter og et godt sundhedsvæsen. Eller… du er måske dataanalytiker, og du ønsker, at oplysningerne skal hjælpe dine kunder – f.eks. hjælpe en kunde, der producerer regnfrakker, med at målrette salg, hvor det regner *meget*.

Uanset hvad, kan du finde en webressource, der indeholder interessante data om disse og andre emner:

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Vælg **Hent data \> Web**, og skriv adressen.

![](media/desktop-connect-to-data/connecttodata_3.png)

Når du vælger **OK**, begynder funktionen **Forespørgsel** i Power BI Desktop at arbejde. Power BI Desktop kontakter webressourcen, og i **navigatorvinduet** returneres resultaterne af det, der blev fundet på den pågældende webside. I dette tilfælde blev der fundet en tabel (Table 0) og det generelle dokument. Vi er interesseret i tabellen, så vi vælger den på listen. I **navigatorvinduet** vises der et eksempel.

![](media/desktop-connect-to-data/datasources_fromnavigatordialog.png)

På nuværende tidspunkt kan vi redigere forespørgslen, før tabellen indlæses, ved at vælge **Rediger** nederst i vinduet, eller vi kan indlæse tabellen.

Hvis vi vælger **Rediger**, indlæses tabellen, og forespørgselseditoren startes. Ruden **Forespørgselsindstillinger** vises (hvis ikke, kan du vælge **Vis** på båndet og derefter vælge **Vis \> Forespørgselsindstillinger** for at få vist ruden **Forespørgselsindstillinger**). Sådan ser det ud.

![](media/desktop-connect-to-data/designer_gsg_editquery.png)

Alle disse resultater er tekst i stedet for tal, og vi skal bruge tal. Det er ikke noget problem – du skal bare højreklikke på kolonneoverskriften og vælge **Skift type \> Heltal** for at ændre dem. Hvis vi vil vælge mere end én kolonne, skal vi først vælge en kolonne og derefter holde **Skift** nede, vælge yderligere tilstødende kolonner og derefter højreklikke på en kolonneoverskrift for at ændre alle de valgte kolonner. Brug **Ctrl** til at vælge de kolonner, der ikke er tilstødende.

![](media/desktop-connect-to-data/designer_gsg_changedatatype.png)

Under **Forespørgselsindstillinger** afspejler **Anvendte trin** de ændringer, der er foretaget. Når du foretager yderligere ændringer af dataene, registrerer forespørgselseditoren disse ændringer i sektionen **Anvendte trin**, som du kan tilpasse, vende tilbage til, omarrangere eller slette efter behov.

![](media/desktop-connect-to-data/designer_gsg_appliedsteps_changedtype.png)

Der kan stadig foretages yderligere ændringer i tabellen, når den er indlæst, men på nuværende tidspunkt er det fint, som det er. Når vi er færdige, vælger vi **Luk og anvend** på båndet **Hjem**, og Power BI Desktop anvender vores ændringer og lukker forespørgselseditoren.

![](media/desktop-connect-to-data/connecttodata_closenload.png)

Mens datamodellen indlæst, kan vi i **rapportvisningen** i Power BI Desktop gå i gang med at oprette visualiseringer ved at trække felter til lærredet.

![](media/desktop-connect-to-data/connecttodata_dragontoreportview.png)

Det er selvfølgelig en simpel model med en enkelt dataforbindelse. De fleste Power BI Desktop-rapporter vil have forbindelser til forskellige datakilder, formet til dine behov, med relationer, der opretter en mere omfattende datamodel. 

### <a name="next-steps"></a>Næste trin
Du kan gøre mange forskellige ting med Power BI Desktop. Du kan finde flere oplysninger om funktionerne i følgende ressourcer:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)   

Vil du give os feedback? Dejligt – Brug menupunktet **Send feedback** i Power BI Desktop. Vi ser frem til at høre fra dig!

![](media/desktop-connect-to-data/sendfeedback.png)
