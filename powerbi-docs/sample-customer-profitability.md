---
title: 'Eksempel på kunderentabilitet til Power BI: Få en introduktion'
description: 'Eksempel på kunderentabilitet til Power BI: Få en introduktion'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/11/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 2b89125cd2ad45bdad18bd198385e1117b5e3f16
ms.sourcegitcommit: 69a0e340b1bff5cbe42293eed5daaccfff16d40a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/13/2019
ms.locfileid: "67039508"
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Eksempel på kunderentabilitet til Power BI: Få en introduktion

## <a name="overview-of-the-customer-profitability-sample"></a>Oversigt over eksemplet på kunderentabilitet
Indholdspakken Eksempel på kunderentabilitet indeholder et dashboard, en rapport og datasæt for en virksomhed, der producerer markedsføringsmateriale. Dette dashboard blev oprettet af en økonomidirektør med henblik på at se nøgletal for hendes fem afdelingsledere (direktører), produkter, kunder og bruttoavance (BA). Hun kan hurtigt se, hvilke faktorer der påvirker rentabiliteten.

![Power BI-dashboard](media/sample-customer-profitability/power-bi-dash.png)

Dette eksempel er en del af en række, der illustrerer, hvordan du kan bruge Power BI med forretningsrelaterede data, rapporter og dashboards. Dette eksempel blev oprettet med rigtige data fra obviEnce ([www.obvience.com](http://www.obvience.com/)), som er blevet anonymiseret. Dataene er tilgængelige i flere formater: indholdspakke/app, Excel-projektmappe eller .pbix Power BI Desktop-fil. Se [Eksempler til Power BI](sample-datasets.md).

## <a name="prerequisites"></a>Forudsætninger
Vil du følge med? I dette selvstudium bruges Power BI-tjenesten og indholdspakken Eksempel på kunderentabilitet. Da rapportoplevelserne ligner hinanden rigtig meget, kan du også følge med ved hjælp af Power BI Desktop og .pbix-eksempelfilen. Instruktioner til oprettelse af forbindelse til indholdspakken og .pbix-filen er beskrevet i følgende afsnit.

### <a name="get-the-content-pack-for-this-sample"></a>Hent indholdspakken for dette eksempel

1. Åbn Power BI-tjenesten (app.powerbi.com), log på, og åbn det arbejdsområde, hvor du vil gemme eksemplet.

2. Vælg **Hent data** i nederste venstre hjørne.

    ![Hent data](media/sample-datasets/power-bi-get-data.png)
3. På siden **Hent data**, der vises, skal du vælge **Eksempler**.

4. Vælg **Eksempel på kunderentabilitet**, og vælg derefter **Opret forbindelse**.  

   ![Hent data](media/sample-customer-profitability/get-supplier-sample.png)
5. Power BI importerer indholdspakken og føjer derefter et nyt dashboard, en rapport og datasæt til dit aktuelle arbejdsområde.

   ![Posten Eksempel på kunderentabilitet](media/sample-customer-profitability/customer-profitability-sample-entry.png)

### <a name="get-the-pbix-file-for-this-sample"></a>Hent .pbix-filen knyttet til dette eksempel

Alternativt kan du downloade [Eksempel på kunderentabilitet](http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer%20Profitability%20Sample%20PBIX.pbix) som en .pbix-fil, der er designet til at blive brugt sammen med Power BI Desktop.


### <a name="get-the-excel-workbook-for-this-sample"></a>Hent Excel-projektmappen for dette eksempel

Hvis du vil have vist datakilden for dette eksempel, er den også tilgængelig som en [Excel-projektmappe](http://go.microsoft.com/fwlink/?LinkId=529781). Projektmappen indeholder Power View-ark, som du kan få vist og redigere. Hvis du vil se rådataene, skal du aktivere tilføjelsesprogrammerne Dataanalyse og derefter vælge **Power Pivot > Administrer**. Hvis du vil aktivere tilføjelsesprogrammerne Power-visning og Power Pivot, skal se [Se nærmere på Excel-eksemplerne fra selve Excel](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself) for at få flere oplysninger.



## <a name="what-is-our-dashboard-telling-us"></a>Hvad fortæller vores dashboard os?

Find dashboardet Kunderentabilitet i det arbejdsområde, hvor du gemte eksemplet, og vælg den:

![Dashboard for eksempel på Kunderentabilitet](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>Virksomhedsdækkende dashboardfelter
1. Åbn dashboardet i Power BI-tjenesten. Dashboardfelterne giver vores økonomidirektør et overblik over de vigtige virksomhedsdata. Når hun ser noget interessant, kan hun vælge et felt for at grave ned i dataene.

2. Gennemse felterne i venstre side af dashboardet.

    ![Felter til ledere](media/sample-customer-profitability/power-bi-manager.png)

- Virksomhedens bruttoavance er på 42,5 %.
- Den har 80 kunder.
- Den sælger fem forskellige produkter.
- Den havde den laveste omsætningsafvigelse i % ift. budgettet for februar efterfulgt af den højeste i marts.
- Den største omsætning stammer fra de østlige og nordlige områder. Bruttoavancen har aldrig overskredet budgettet, men forretningsenhederne ER-0 og MA-0 skal undersøges nærmere.
- Den samlede omsætning for året ligger tæt på budgettet.


### <a name="manager-specific-dashboard-tiles"></a>Chefspecifikke dashboardfelter
Ved hjælp af felterne i højre side af dashboardet får du et teamscorecard. Økonomidirektøren skal holde styr på sine ledere, og disse felter giver hende et godt overblik over fortjenesten ved hjælp af BA i %. Hvis BA%-tendensen er uventet for en given chef, så kan hun undersøge det nærmere.

![BA% til ledere](media/sample-customer-profitability/power-bi-manager2.png)

Ved at analysere de ledelsesspecifikke dashboardfelter kan vi se følgende:

- Alle direktører, med undtagelse af Carlos, har allerede overskredet deres salgsmål. Carlos' faktiske salg er dog det højeste.
- Annelies BA% er den laveste, men vi kan se en konstant stigning siden marts.
- Men Valery har oplevet et væsentligt fald i sin BA%.
- Andrew har haft et svingende år.

## <a name="explore-the-dashboards-underlying-data"></a>Udforsk dashboardets underliggende data
Dette dashboard indeholder felter, der linker til en rapport og til en Excel-projektmappe.

### <a name="open-the-excel-online-data-source"></a>Åbn Excel Online-datakilden
To felter på dette dashboard **Mål vs. Faktisk** og **Omsætningsstigning år for år** er fastgjort fra en Excel-projektmappe. Når du vælger et af disse felter, åbnes datakilden i Power BI – i dette tilfælde Excel Online.

![Excel Online](media/sample-customer-profitability/power-bi-excel-online.png)

1. Vælg et af de felter, der er fastgjort fra Excel. Excel Online åbnes i Power BI-tjenesten.
2. Bemærk, at der er tre faner med data i projektmappen. Åben **Omsætning**.
3. Lad os se, hvorfor Carlos endnu ikke har nået sit mål:  
    a. Via skyderen **Direktør** skal du vælge **Carlos Grilo**.   
    b. Den første pivottabel fortæller os, at Carlos' omsætningsstigning for det bedste produkt, Primus, er faldet med 152 % siden sidste år. Diagrammet over omsætningsafvigelse år-til-år viser, at han i de fleste måneder lå under budgettet.  

    ![Pivottabel](media/sample-customer-profitability/power-bi-pivotchart.png)

    ![Resultater for Carlos](media/sample-customer-profitability/power-bi-carlos.png)

4. Fortsæt med at udforske. Hvis du finder noget interessant, skal du vælge **Fastgør** ![ikon for fastgørelse](media/sample-customer-profitability/power-bi-excel-pin.png) i øverste højre hjørne for at [fastgøre det til et dashboard](service-dashboard-pin-tile-from-excel.md).

5. Brug pil tilbage i browseren for at vende tilbage til dashboardet.

### <a name="open-the-underlying-power-bi-report"></a>Åbn den underliggende Power BI-rapport
Mange af felterne på dashboardet med Eksempel på kunderentabilitet er fastjort fra den underliggende rapport Eksempel på kunderentabilitet.

1. Vælg et af disse felter for at åbne rappporten i Læsevisning.

   Hvis feltet blev oprettet i Spørgsmål og svar, åbnes vinduet for Spørgsmål og svar, når det vælges. Vælg **Afslut Spørgsmål og svar** for at vende tilbage til dashboardet og prøve et andet felt.

2. Rapporten indeholder tre sider. Hver fane nederst i rapporten repræsenterer en ny side.

    ![Tre faner nederst](media/sample-customer-profitability/power-bi-report-tabs.png)

    * På **Teamscorecard** fokuseres der på de fem lederes præstation og deres forretningsbøger.
    * Med **Branchemargenanalyse** kan man analysere rentabiliteten sammenlignet med, hvad der sker i hele branchen.
    * Med **Direktørscorecard** får man et overblik over hver leder formateret til at blive vist i Cortana.

### <a name="team-scorecard-page"></a>Siden Teamscorecard
![Rapportsiden Teamscorecard](media/sample-customer-profitability/customer2.png)

Lad os se nærmere på to af teammedlemmerne, og på hvad det giver os af indsigter. I feltet **Direktør** til venstre skal du vælge Andrews navn for at filtrere rapportsiden, så der kun vises data for Andrew.

* Hvis du vil se et hurtigt KPI, skal du kigge på Andrews **Omsætningsstatus (Samlet for året)** . Det er grøn, hvilket betyder, at han præsterer godt.
* Diagrammet **Omsætningsafvigelse i % for budget pr. måned** viser, at Andrew generelt klarer sig godt med undtagelse af et fald i februar. Hans stærkeste område er det østlige område, og han håndterer 49 kunder og 5 ud af 7 produkter. Hans BA i % er hverken den højeste eller den laveste.
* Diagrammet **Samlet omsætning i år og omsætningsafvigelse i % ift. budget pr. måned** viser en konstant og tilmed rentabel historie. Men hvis du filtrerer ved at vælge firkanten ud for **Central** i områdetræstrukturen, opdager du, at Andrew kun har omsætning i marts og kun i Indiana. Er dette bevidst, eller er det noget, der skal undersøges nærmere?

Nu videre til Valery. Vælg Valerys navn i feltet **Direktør** for at filtrere rapportsiden og kun få vist data om hende. 

![Valerys data](media/sample-customer-profitability/customer3.png)

* Bemærk det røde KPI for **Omsætningsstatus (Samlet for året)** . Dette skal helt sikkert undersøges nærmere.
* Hendes omsætningsafvigelse tegner også et bekymrende billede: Hun opfylder ikke sine omsætningsmargener.
* Valery har kun ni kunder, håndterer kun to produkter og arbejder næsten udelukkende med kunder i det nordlige område. Denne specialisering kan være forklaringen på de stærkt svingende tal.
* Hvis du vælger firkanten **Nord** i træstrukturen, kan du se, at Valerys bruttoavance i det nordlige område svarer til hendes overordnede margen.
* Hvis du vælger de andre firkanter **Samlet omsætning efter område**, kan du se et interessant billede: Hendes BA i % strækker sig fra 23 % til 79 %. Hendes omsætningstal i alle områder undtagen det nordlige område er ekstremt sæsonafhængige.

Fortsæt med udforskningen for at finde ud af, hvorfor Valerys område ikke præsterer så godt. Kig på områder, de andre forretningsenheder og den næste side i rapporten: **Branchemargenanalyse**.

### <a name="industry-margin-analysis"></a>Branchemargenanalyse
Denne rapportside indeholder et andet udsnit af dataene. Den ser på bruttoavancen for hele branchen, opdelt efter segment. Økonomidirektøren bruger denne side til at sammenligne virksomheds- og afdelingsdata som en hjælp til at forklare tendenser og lønsomhed. Du undrer dig måske over, hvorfor områdediagrammet **Bruttoavance i % efter måned og direktør** er på denne side, da det er teamspecifikt. Den er placeret her, fordi vi så kan filtrere siden efter afdelingschef.  

![Rapportsiden Branchemargenanalyse](media/sample-customer-profitability/customer6.png)

Hvor meget varierer lønsomheden efter branche? Hvordan fordeler produkter og kunder sig efter branche? For at besvare disse spørgsmål skal du vælge en eller flere brancher øverst til venstre (start med CPG-branchen). Vælg viskelæderikonet for at fjerne filteret.

I boblediagrammet (**Omsætningsafvigelse i % ift. budget, BA i % og samlet omsætning i år efter branche**) kigger økonomidirektøren efter de største bobler, fordi de har den største indvirkning på omsætningen. Hvis du nemt vil se hver leders indvirkning efter branchesegment, skal du filtrere siden ved at klikke på hver leders navn i områdediagrammet.

* Andrews indvirkning ses i mange forskellige branchesegmenter med meget varierende BA% (mest positiv) og Var%.
* Annelies diagram er lignende, bortset fra at hun kun koncentrerer sig om en håndfuld branchesegmenter med fokus på det delstatsmæssige segment og fokus på Gladius-produktet.
* Carlos har et klart fokus på segmentet for serviceydelser med et godt overskud. Han har markant forbedret afvigelsen i % for segmentet for højteknologi, og et nyt segment for ham, industriel, præsterede rigtigt godt i forhold til budgettet.
* Tina arbejder inden for en håndfuld segmenter og har den højeste BA%, men hendes bobler er generelt små, hvilket viser, at hendes indvirkning på virksomhedens bundlinje er minimal.
* Valery, som kun har ansvaret for et enkelt produkt, arbejder i kun fem branchesegmenter. Hendes indvirkning er sæsonafhængig, men leverer altid en stor boble, hvilket viser, at hun har en stor indvirkning på virksomhedens bundlinje. Er branchesegmenterne forklaringen på hendes negative præstation?

### <a name="executive-scorecard"></a>Chefscorecard
Denne side er formateret som en Cortana-svarside til Cortana. Du kan finde flere oplysninger i [Opret et brugerdefineret svarside til Cortana](service-cortana-answer-cards.md).

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Grav dybere ned i dataene ved at stille spørgsmål med spørgsmål og svar
I forhold til vores analyse kan det være nyttigt at få fastlagt, hvilken branche der genererer den største omsætning for Valery. Lad os bruge spørgsmål og svar.

1. Åbn rapporten i Redigeringsvisning ved at vælge **Rediger rapport**. Redigeringsvisning er kun tilgængelig, hvis du ejer rapporten. Denne visning kaldes nogle gange for **oprettertilstand**. Hvis rapporten i stedet kun er delt med dig, kan du ikke åbne den i Redigeringsvisning.

2.  På menulinjen øverst kan du vælge **Stil et spørgsmål** for at åbne dialogboksen Spørgsmål og svar.

    ![Stil et spørgsmål om dine data](media/sample-customer-profitability/power-bi-ask-question.png)

3. Typen *samlet omsætning efter branche for Valery Ushakov*. Se, hvordan visualiseringen opdateres, mens du skriver spørgsmålet.

    ![skriv spørgsmål i feltet til spørgsmål](media/sample-customer-profitability/power-bi-qna.png)

   Som du kan se, er branchen Distribution det største omsætningsområde for Valery.

### <a name="dig-deeper-by-adding-filters"></a>Grav dybere ned ved at tilføje filtre
Lad os se på branchen Distribution.  

1. Åbn rapportsiden **Branchemargenanalyse**.
2. Uden at vælge en visualisering på rapportsiden skal du udvide filterruden til højre (hvis den ikke allerede er udvidet). Ruden **Filtre** bør kun vise **filtre på Sideniveau**.  

   ![Filtre på sideniveau](media/sample-customer-profitability/power-bi-filters.png)
3. Find filteret for **Branche**, og vælg pilen for at udvide listen. Lad os tilføje et sidefilter for Distributionsbranchen. Først skal du rydde alle markeringer ved at rydde afkrydsningfeltet **Vælg alle**. Vælg derefter kun **Distribution.**  

   ![Filtrer efter distribution](media/sample-customer-profitability/customer7.png)
4. I områdediagrammet **Bruttoavance i % efter måned og direktør** kan du se, at det kun er Valery og Tina, der har kunder i denne branche, og at Valery kun arbejdede med denne branche fra juni til november.   
5. Vælg **Tina** og derefter **Valery** i områdediagramforklaringen **Bruttoavance efter måned og direktør**. Bemærk, at Tinas andel af **Samlet omsætning efter produkt** er meget lille i forhold til Valery.
6. Hvis du vil se den faktiske omsætning, skal du bruge Spørgsmål og svar til at angive *samlet omsætning pr. direktør for distribution efter scenarie*.  

     ![skriv et spørgsmål i feltet til spørgsmål for at få vist søjlediagram](media/sample-customer-profitability/power-bi-qna2.png)

    Vi kan ligeledes granske andre brancher og endog føje kunder til vores visuals for at få indsigt i årsagerne til Valerys præstation.

Dette er et sikkert miljø at lege i. Du kan altid vælge ikke at gemme dine ændringer. Hvis du gemmer dem, kan du altid vælge **Hent data** for at få en ny kopi af dette eksempel.

Du kan også nøjes med at [downloade datasættet (Excel-projektmappe) til dette eksempel](http://go.microsoft.com/fwlink/?LinkId=529781).

## <a name="next-steps-connect-to-your-data"></a>Næste trin: Opret forbindelse til dine data
Vi håber, at denne rundtur har vist, hvordan Power BI-dashboards, spørgsmål og svar og rapporter kan give indsigt i kundedata. Nu er det din tur: Opret forbindelse til dine egne data. Med Power BI kan du oprette forbindelse til en lang række datakilder. Få mere at vide om, hvordan du [kommer i gang med Power BI](service-get-started.md).

[Eksempler til Power BI](sample-datasets.md)  
