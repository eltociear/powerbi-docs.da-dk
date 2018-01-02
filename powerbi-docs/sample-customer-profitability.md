---
title: "Eksempel på kunderentabilitet til Power BI: Få en rundvisning"
description: "Eksempel på kunderentabilitet til Power BI: Få en rundvisning"
services: powerbi
documentationcenter: 
author: amandacofsky
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
ms.date: 10/29/2017
ms.author: mihart
ms.openlocfilehash: 9a100b7d13c11a8bd066b72a570f45d0c2bc08be
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Eksempel på kunderentabilitet til Power BI: Få en rundvisning
Indholdspakken "Eksempel på kunderentabilitet" indeholder et dashboard, en rapport og datasæt for en virksomhed, der producerer markedsføringsmateriale. Dette dashboard blev oprettet af en økonomidirektør med henblik på at se nøgletal knyttet til sine fem afdelingschefer (dvs. direktører), produkter, kunder og bruttoavance (BA). Hun kan hurtigt se, hvilke faktorer der påvirker lønsomheden.

Dette eksempel er en del af en række, der illustrerer, hvordan du kan bruge Power BI med forretningsrelaterede data, rapporter og dashboards. Der er anvendt rigtige data fra obviEnce ([www.obvience.com](http://www.obvience.com/)), der er blevet anonymiseret.

Du kan også nøjes med at [downloade datasættet (Excel-projektmappe) til dette eksempel](http://go.microsoft.com/fwlink/?LinkId=529781).  
![](media/sample-customer-profitability/power-bi-dash.png)

## <a name="what-is-our-dashboard-telling-us"></a>Hvad fortæller vores dashboard os?
### <a name="company-wide-dashboard-tiles"></a>Virksomhedsdækkende dashboardfelter
Disse felter giver vores økonomidirektør et overblik over vigtige virksomhedsdata.  Når hun ser noget interessant, kan hun vælge et felt for at grave ned i dataene.

1. Vores firmas bruttoavance er på 42,5 %.
2. Vi har 80 kunder.
3. Vi sælger fem forskellige produkter.
4. Vi havde vores laveste indtægtsvarians i % i budgettet i februar efterfulgt af vores højeste i marts.
5. De fleste af vores indtægter kommer fra de østlige og nordlige områder. Bruttoavancen overskrider aldrig budgettet, mens ER-0 og MA-0 skal granskes nærmere.
6. Den samlede omsætning for året ligger tæt på budgettet.

### <a name="manager-specific-dashboard-tiles"></a>Chefspecifikke dashboardfelter
Disse felter indeholder et teamscorekort. Økonomidirektøren skal holde styr på sine chefer, og disse felter giver hende et godt overblik over fortjenesten – vha. BA%. Hvis BA%-tendensen er uventet for en given chef, så kan hun undersøge det nærmere.

Annelies BA% er den laveste, men vi kan se en konstant stigning siden marts. Men Valery har oplevet et væsentligt fald i sin BA%. Og Andrew har haft et svingende år. Klik på en af de chefspecifikke felter for at åbne den underliggende rapport. Rapporten er på tre sider og åbner på siden "Branchemargenanalyse".

## <a name="explore-the-pages-in-the-report"></a>Gransk siderne i rapporten
Rapporten er på tre sider:

* "Teamscorecard" fokuserer på de fem chefers præstation og deres "forretningsbøger."
* "Branchemargenanalyse" beskriver en måde at analysere vores lønsomhed på sammenlignet med tilstanden i hele branchen.
* "Chefscorecard" giver et overblik over hver af vores chefer formateret til at blive vist i Cortana.

### <a name="team-scorecard-page"></a>Siden Teamscorecard
![](media/sample-customer-profitability/customer2.png)

Lad os se nærmere på to af teammedlemmerne, og på hvad det giver os af indsigter. Vælg Andrews navn i udsnitsværktøjet til venstre for at filtrere rapportsiden og kun få vist data om Andrew.

* Et hurtigt blik på KPI viser Andrews **Indtægtsstatus** – han er grøn. Han præsterer godt.
* Områdediagrammet "Indtægtsvariation i % for budget pr. måned" afspejler dette med undtagelse af et fald i februar. Andrew klarer sig generelt godt. Hans stærkeste område er øst, og han håndterer 49 kunder og fem (ud af syv) produkter. Hans BA% er hverken den højeste eller laveste.
* "Indtægter dette år and Indtægtsvariation % for budget pr. måned" viser, at tallene for udbyttet har ligget jævnt. Men hvis du filtrerer ved at klikke på firkanten for **Central** i områdetræstrukturen, så opdager du, at Andrew kun har indtægter i marts og kun i Indiana. Er dette bevidst eller noget, der skal undersøges nærmere?

Nu videre til Valery. Vælg Valerys navn i udsnitsværktøjet for at filtrere rapportsiden og kun få vist data om hende.  
![](media/sample-customer-profitability/customer3.png)

* Bemærk det røde KPI for **Status for Indtægter dette år**. Dette skal helt sikkert undersøges nærmere.
* Hendes svingende indtægtstal tegner også et bekymrende billede – hun opfylder ikke sine indtægtsmargener.
* Valery har kun ni kunder, håndterer kun to produkter og arbejder næsten udelukkende med kunder i nord. Denne specialisering kan være forklaringen på de stærkt svingende tal.
* Hvis du vælger firkanten **Nord** i træstrukturen, så ses det, at Valerys bruttoavance i nord svarer til hendes generelle margen.
* Når du vælger de andre **Område**-firkanter, så ser man et interessant billede: Hendes BA% svinger fra 23 % til 79 %, og hendes indtægtstal i alle områder, undtagen i nord, er ekstremt sæsonafhængige.

Fortsæt med at grave for at finde ud af, hvorfor Valerys område ikke klarer sig godt. Kig på områder, de andre afdelinger og næste side i rapporten – "Branchemargenanalyse."

### <a name="industry-margin-analysis"></a>Branchemargenanalyse
Denne rapportside indeholder et andet udsnit af dataene. Den ser på bruttoavancen for hele branchen, opdelt efter segment. Økonomidirektøren bruger denne side til at sammenligne virksomheds- og afdelingsdata som en hjælp til at forklare tendenser og lønsomhed. Du undrer dig måske over, hvorfor områdediagrammet "Bruttoavancemargen efter måned og chefnavn" er på denne side, siden den er teamspecifik. Den er placeret her, fordi vi så kan filtrere siden efter afdelingschef.  
![](media/sample-customer-profitability/customer6.png)

Hvor meget varierer lønsomheden efter branche? Hvordan fordeler produkter og kunder sig efter branche? Vælg en eller flere brancher øverst til venstre. (Start fra CPG-branche) Vælg viskelæderikonet for at rydde filteret.

På boblediagrammet kigger økonomidirektøren efter de største bobler, fordi de har den største indvirkning på indtægten. Hvis du filtrerer siden efter cheferne ved at klikke på deres navne i områdediagrammet, så er det let at se hver chefs indvirkning efter branchesegment.

* Andrews indvirkning ses i mange forskellige branchesegmenter med meget varierende BA% (mest positiv) og Var%. 
* Annelies diagram er tilsvarende, bortset fra at hun kun koncentrerer sig om en håndfuld branchesegmenter med fokus på det delstatsmæssige segment og fokus på Gladius-produkt. 
* Carlos har klar fokus på segmentet for serviceydelser med et godt overskud. Han har markant forbedret varians % for højteknologisegmentet, og et nyt segment for ham, industri, præsterede rigtigt godt sammenlignet med budgettet. 
* Tina arbejder inden for en håndfuld segmenter og har den højeste BA%, men hendes bobler er generelt små, hvilket viser, at hendes indvirkning på virksomhedens bundlinje er minimal. 
* Valery, som kun har ansvaret for et enkelt produkt, arbejder i kun fem branchesegmenter. Hendes indvirkning er sæsonafhængig, men leverer altid en stor boble, hvilket viser, at hun har en stor indvirkning på virksomhedens bundlinje. Er branchen forklaringen på hendes negative præstation?

### <a name="executive-scorecard"></a>Chefscorecard
Denne side er formateret som et svarkort for Cortana. Hvis du vil vide mere, kan du se [Opret svarkort for Cortana](service-cortana-answer-cards.md)

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Grav dybere ned i dataene ved at stille spørgsmål med spørgsmål og svar
Med hensyn til vores analyse kunne det være gavnligt at få fastlagt, hvilken branche der genererer den største indtjening for Valery. Lad os bruge spørgsmål og svar.

1. Vælg **Power BI** i den øverste navigationslinje for at vende tilbage til dashboard'et.
2. Vælg feltet Spørgsmål og svar øverst i dashboard'et.
   
    ![](media/sample-customer-profitability/customer4.png)
3. Skriv **samlet omsætning efter branche for Valery**. Se, hvordan visualiseringen opdateres, mens du skriver spørgsmålet.
   
    ![](media/sample-customer-profitability/customer5.png)
   
   Distribution er det største indtægtsområde for Valery.

### <a name="dig-deeper-by-adding-filters"></a>Grav dybere ned ved at tilføje filtre
Lad os se på branchen *Distribution*.  

1. Vend tilbage til dashboard'et, og vælg områdediagrammet med Andrews bruttoavancetendens. Herved åbnes rapporten på siden "Branchemargenanalyse".
2. Undlad at vælge nogen visualisering på rapportsiden, men udvid filterruden til højre. Ruden Filtre bør kun vise filtre på Sideniveau.  
   
   ![](media/sample-customer-profitability/power-bi-filters.png)
3. Find filteret for **Branche**, og vælg pilen for at udvide listen. Lad os tilføje et sidefilter for Distributionsbranchen. Først skal du rydde alle markeringer ved at rydde afkrydsningfeltet **Vælg alle**. Vælg derefter **Distribution.**  
   
   ![](media/sample-customer-profitability/customer7.png)
4. Områdediagrammet "Bruttoavance efter måned og chefnavn" fortæller os, at kun Valery og Tina har kunder i denne branche, og at Valery kun arbejdede med denne branche fra juni til november.   
5. Vælg **Tina** og derefter **Valery** i områdediagramforklaringen "Bruttoavance efter måned og chef". Bemærk, at Tinas andel af "Samlet indtægt efter produkt" er meget lille i forhold til Valery. 
6. Hvis du vil se den faktiske indtægt, skal du vende tilbage til dashboard'et og bruge Spørgsmål og svar for at spørge om **samlet indtægt til distribution efter scenarie efter chef**.  
   
   ![](media/sample-customer-profitability/customer8.png)

Vi kan ligeledes granske andre brancher og endog føje kunder til vores visuelle elementer for at få indsigt i årsagerne til Valerys præstation.

Dette er et sikkert miljø at lege i. Du kan altid vælge ikke at gemme dine ændringer. Hvis du gemmer dem, kan du altid gå til **Hent data** for at få en ny kopi af dette eksempel.

## <a name="next-steps-connect-to-your-data"></a>Næste trin: Opret forbindelse til dine data
Vi håber, at denne rundtur har vist, hvordan Power BI-dashboards, spørgsmål og svar og rapporter kan give indsigt i kundedata. Nu er det din tur – opret forbindelse til dine egne data. Med Power BI kan du oprette forbindelse til en lang række datakilder. Få mere at vide om, hvordan du [kommer i gang med Power BI](service-get-started.md).

[Tilbage til eksempler i Power BI](sample-datasets.md)  

