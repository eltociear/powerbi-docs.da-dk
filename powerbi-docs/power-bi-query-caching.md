---
title: Cachelagring af forespørgsler i Power BI Premium
description: Cachelagring af forespørgsler i Power BI Premium
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/03/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: fbfd8c98743144e0c9604aca4174d6ef32916e77
ms.sourcegitcommit: de0b72915183a8a784d3227838bd704c1c209422
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/04/2019
ms.locfileid: "58914270"
---
# <a name="query-caching-in-power-bi-premium"></a>Cachelagring af forespørgsler i Power BI Premium

Organisationer med Power BI Premium kan drage fordel af *cachelagring af forespørgsler* for at fremskynde rapporter, der er knyttet til et datasæt. Ved cachelagring af forespørgsler beordres Premium-kapaciteten til at bruge dens lokale cachelagringstjeneste til at bevare forespørgselsresultaterne, derved undgår man, at den underliggende datakilde skal beregne disse resultater.

> [!IMPORTANT]
> Cachelagring af forespørgsler er kun tilgængelig til Power BI Premium. Det gælder ikke for LiveConnect-datasæt, der gør brug af Azure Analysis Services eller SQL Server Analysis Services.

Cachelagrede forespørgselsresultater er specifikke for brugeren og datasættets kontekst, og sikkerhedsreglerne overholdes altid. På nuværende tidspunkt udfører tjenesten kun cachelagring af forespørgsler for den første side, du lander på. Med andre ord, så cachelagres forespørgsler ikke, når du interagerer med rapporten. Cachen afspejler personlige bogmærker og faste filtre. [Dashboardfelter](service-dashboard-tiles.md), der leveres af de samme forespørgsler, får samme fordel, når forespørgslen cachelagres. Det er særligt en fordel for ydeevnen, når et datasæt tilgås ofte og ikke skal opdateres så ofte. Cachelagring af forespørgsler kan også reducere belastningen på Premium-kapaciteten ved at reducere det samlede antal forespørgsler.

Du styrer funktionsmåden af cachelagring af forespørgsler på siden **Indstillinger** for datasættet i Power BI-tjenesten. Der er tre mulige indstillinger:

- **Standardkapacitet**: Datasættet arver indstillingen fra Premium-kapaciteten. Standardkapaciteten styres af administratoren af Power BI Premium-kapaciteten.

- **Fra**: Cachelagring af forespørgsler bruges ikke for dette datasæt.

- **Til**: Cachelagring af forespørgsler bruges for dette datasæt.

![Dialogboks for cachelagring af forespørgsler](media/power-bi-query-caching/power-bi-query-caching.png)

> [!NOTE]
> Når du ændrer indstillingerne for cachelagring fra **Til** til **Fra**, fjernes alle tidligere gemte forespørgselsresultater for datasættet fra kapacitetscachen. Du kan enten slå cachelagring fra eksplicit eller ved at gå tilbage til indstillingen Standardkapacitet, som en administrator har angivet til **Fra**. Når indstillingen slås fra, kan det medføre en lille forsinkelse, næste gang en rapport kører forespørgsler i forhold til dette datasæt. Forsinkelsen skyldes, at disse rapportforespørgsler kører efter behov, og at der ikke gøres brug af gemte resultater. Det krævede datasæt skal muligvis også indlæses i hukommelsen, før det kan håndtere forespørgsler.


