---
title: "Eksempel på analyse af salgsmuligheder til Power BI: Få en introduktion"
description: "Eksempel på analyse af salgsmuligheder til Power BI: Få en introduktion"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/04/2017
ms.author: mihart
ms.openlocfilehash: 878738eb3f588c461b687451062a1641479e77ed
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/08/2017
---
# <a name="opportunity-analysis-sample-for-power-bi-take-a-tour"></a>Eksempel på analyse af salgsmuligheder til Power BI: Få en introduktion
**Opportunity Tracking Sample** indeholder et dashboard (og en tilknyttet rapport) for en softwarevirksomhed, der har 2 salgskanaler: *direkte* og *partner*. Salgschefen har oprettet dette dashboard for at spore muligheder og omsætning efter område, handlens størrelse samt kanal.

Salgschefen er afhængig af 2 målinger af indtægter:

* **Indtægter** – dette er en sælgers estimat over, hvad vedkommende mener omsætningen vil blive.
* **Indregnede indtægter** – dette beregnes som indtægter X sandsynligheds-% og anerkendes generelt som værende en mere nøjagtig indikator for de faktiske salgsindtægter. Sandsynligheden afhænger af, hvor i ***salgsfasen*** handlen befinder sig.
  * Lead – 10 %  
  * Qualify – 20 %  
  * Solution – 40 %  
  * Proposal – 60 %  
  * Finalize – 80 %

Dette eksempel er en del af en række, der illustrerer, hvordan du kan bruge Power BI med forretningsrelaterede data, rapporter og dashboards. Der er anvendt rigtige data fra obviEnce ([www.obvience.com)](http://www.obvience.com/), som er blevet anonymiseret.

>[!Note] 
Du kan også nøjes med at [downloade datasættet (Excel-projektmappe) til dette eksempel](http://go.microsoft.com/fwlink/?LinkId=529782). Projektmappen indeholder Power View-ark, som du kan få vist og redigere.  Du kan se de rå data ved at vælge **Power Pivot > Administrer**. 

![](media/sample-opportunity-analysis/opportunity1.png)

## <a name="what-is-our-dashboard-telling-us"></a>Hvad fortæller vores dashboard os?
Salgschefen har oprettet et dashboard for at spore de vigtigste målepunkter. Når hun ser noget interessant, kan hun vælge et felt for at grave ned i dataene.

1. Virksomhedens indtægter er $2 milliarder, og indregnede indtægter er $461 millioner.
2. Antal salgsmuligheder og indtægter følger et velkendt tragtformet mønster, hvor totaler formindskes hvert efterfølgende trin.
3. De fleste af vores salgsmuligheder er i det østlige område. 
4. Store salgsmuligheder genererer større indtægter end mellemstore eller små muligheder.
5. Store partnerhandler genererer større indtægter: $8 millioner i gennemsnit i forhold til $6 millioner for direkte salg. 

Eftersom indsatsen for at få handlen i hus er den samme, uanset om handlen er klassificeret som stor, mellemstor eller lille, bør vores virksomhed grave ned i dataene for at lære mere om store muligheder. 

Vælg feltet **Opportunity Count by Partner Driven and Sales Stage** for at åbne side 1 i rapporten.  
![](media/sample-opportunity-analysis/opportunity2.png)

## <a name="explore-the-pages-in-the-report"></a>Udforsk siderne i rapporten
### <a name="page-1-of-our-report-is-titled-opportunity-count-overview"></a>Side 1 i rapporten har titlen "Opportunity Count Overview".
![](media/sample-opportunity-analysis/opportunity3.png)

* East er vores største område med hensyn til antallet af salgsmuligheder.  
* Vælg hvert område ét ad gangen på cirkeldiagrammet for at filtrere siden. For hvert område forfølger partnere markant flere store muligheder.   
* Søjlediagrammet Opportunity Count by Partner Driven and Opportunity Size viser tydeligt, at de fleste af de store salgsmuligheder er partnerdrevet, og flere af de små og mellemstore muligheder ikke er partnerdrevet. 
* Vælg hver salgsfase i det liggende søjlediagram nederst til venstre for at se forskellen i regionalt antal, og læg mærke til, at selvom East er vores største område med hensyn til antal, har alle tre sammenlignelige antal i faserne Solution, Proposal og Finalize. Det betyder, at vi lukker en højere procentdel af handler i Central og West. 

### <a name="page-2-of-our-report-is-titled-revenue-overview"></a>Side 2 i vores rapport har titlen "Revenue Overview".
Denne side ser på samme måde på dataene, men med et indtægtsperspektiv i stedet for antal.  
![](media/sample-opportunity-analysis/opportunity4.png)

* East er ikke blot vores største område, hvad angår antallet af salgsmuligheder, men også hvad angår indtægter.  
* Filtrering efter Partner driven (vælg **Yes** i forklaringen øverst til højre) viser indtægter på $1,5 milliarder og $294 millioner. Sammenlign det med $644 milliarder og $166 millioner for ikke-partnerdrevne indtægter.  
* Gennemsnitlige indtægter for store kunder er større (8 millioner), hvis muligheden er partnerdrevet, sammenlignet med 6 millioner for ikke-partnerdrevet forretning.  
* For partnerdrevet forretning er de gennemsnitlige indtægter for store muligheder næsten dobbelt så store som for mellemstore muligheder (4 millioner).  
* Gennemsnitlige indtægter for små og mellemstore virksomheder er sammenlignelige for både partnerdrevet og ikke-partnerdrevet forretning.   

Det er tydeligt, at vores partnere er bedre til at sælge til kunder.  Det kan give mening at gennemføre flere handler via vores partnere.

### <a name="page-3-of-our-report-is-titled-region-stage-counts"></a>Side 3 i vores rapport har titlen "Region Stage Counts"
Denne side ser på tilsvarende data, men opdeler dem efter område og fase.  
![](media/sample-opportunity-analysis/opportunity5.png)

* Filtrering efter East (vælg **East** i cirkeldiagrammet) viser, at salgsmuligheder i det østlige er næsten lige opdelt mellem partnerdrevet og ikke-partnerdrevet. 
* Store salgsmuligheder er mest almindelige i det centrale område, små salgsmuligheder er mest almindelige i det østlige område, og mellemstore salgsmuligheder er mest almindelige i det vestlige område. 

### <a name="page-4-of-our-report-is-titled-upcoming-opportunities"></a>Side 4 i vores rapport har titlen "Upcoming Opportunities"
Vi ser igen på lignende faktorer, men denne gang fra et dato-/klokkeslætsperspektiv.  
![](media/sample-opportunity-analysis/opportunity6.png)

Vores CFO bruger denne side til at administrere arbejdsbyrde. Ved at se på indtægtsmuligheder efter salgsfase og måned kan hun planlægge hensigtsmæssigt.

* Gennemsnitlig omsætning for fasen Finalize er den højeste. Det har højeste prioritet at lukke disse handler.
* Filtrering efter måned (ved at vælge månedsnavnet i venstre udsnit) viser, at januar har en høj andel af store handler i fasen Finalize med indregnede indtægter på $75 millioner. Februar har på den anden side hovedsageligt mellemstore handler i fasen Solution og Proposal.
* Tallene for indregnede indtægter varierer generelt baseret på salgsfase, antal muligheder og handlens størrelse. Tilføj filtre (ved hjælp af filterruden til højre) for disse faktorer for at få yderligere indsigt.

Dette er et sikkert miljø at lege i. Du kan altid vælge ikke at gemme dine ændringer. Hvis du gemmer dem, kan du altid gå til **Hent data** for at få en ny kopi af dette eksempel.

## <a name="next-steps-connect-to-your-data"></a>Næste trin: Opret forbindelse til dine data
Vi håber, at denne rundtur har vist, hvordan Power BI-dashboards, Spørgsmål og svar samt rapporter kan give indsigt i data til sporing af salgsmuligheder. Nu er det din tur – opret forbindelse til dine egne data. Med Power BI kan du oprette forbindelse til en lang række datakilder. Få mere at vide om, hvordan du [kommer i gang med Power BI](service-get-started.md).

[Download eksempler](sample-datasets.md)  

