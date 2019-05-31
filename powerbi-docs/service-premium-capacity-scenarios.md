---
title: Microsoft Power BI Premium-kapacitet scenarier
description: I denne artikel beskrives almindelige scenarier for Power BI Premium-kapacitet.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 1d666a6702515a935d93549d026f207848f2bca8
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565326"
---
# <a name="premium-capacity-scenarios"></a>Premium-kapacitet scenarier

Denne artikel beskrives virkelige scenarier, hvor der er implementeret Power BI premium-kapaciteter. Almindelige problemer og udfordringer, der er beskrevet, også hvordan du kan identificere problemer, og hjælpe med at løse dem:

- [Holde datasæt, der er opdateret](#keeping-datasets-up-to-date)
- [Sådan identificeres datasæt med lange svartider](#identifying-slow-responding-datasets)
- [Sådan identificeres årsager til datasæt med sporadisk langsomme svartider](#identifying-causes-for-sporadically-slow-responding-datasets)
- [Sådan fastlægges det, om der er tilstrækkelig hukommelse](#determining-whether-there-is-enough-memory)
- [Sådan fastlægges det, om der er tilstrækkelig CPU](#determining-whether-there-is-enough-cpu)

Trinnene, sammen med diagram og tabel eksempler fra den **Power BI Premium-kapacitet målepunkter app** , at en Power BI-administrator har adgang til.

## <a name="keeping-datasets-up-to-date"></a>Holde datasæt, der er opdateret

I dette scenarie blev en undersøgelse udløst, da brugerne klagede over, at rapportdata nogle gange forekom gamle eller "forældede".

I appen interagerer administratoren med visualiseringen **Refreshes**, der sorterer datasæt efter statistikken **Max Wait Time** i faldende rækkefølge. Denne visual hjælper dem med at få vist datasæt, der har de længste ventetider, der er grupperet efter navn på arbejdsområde.

![Datasætopdateringer sorteret i faldende rækkefølge efter maksimal ventetid, grupperet efter arbejdsområde](media/service-premium-capacity-scenarios/dataset-refreshes.png)

I den **pr. time gennemsnitlige Opdater vente gange** visual, de læg mærke til, at opdatering ventetider spidsbelastninger konsekvent rundt Klokken hver dag.

![Opdateringsventetider peaker periodisk kl. 16.00](media/service-premium-capacity-scenarios/peak-refresh-waits.png)

Der er flere mulige forklaringer til disse resultater:

- For mange forsøg af opdatering kunne sker på samme tid, overskrider de grænser, der er defineret af noden kapacitet. I dette tilfælde seks samtidige opdateringer på en P1 med standard hukommelsesallokering.

- Datasæt opdateres muligvis for stor til at passe til den tilgængelige hukommelse (kræver mindst 2 x den hukommelse, der kræves til fuld opdatering).
- Ineffektiv logik i Power-forespørgslen kan resultere i en spidsbelastning af hukommelsesforbruget under opdateringen af datasæt. På en optaget kapacitet når denne samling kan undertiden fysiske grænsen, fail opdateringen og potentielt påvirke andre rapport Vis handlinger på kapaciteten.
- Ofte forespurgte datasæt, der har brug for at holde dig i hukommelsen kan påvirke andre datasæt evne til at opdatere på grund af begrænset tilgængelig hukommelse.

Hjælper med at undersøge og kan Power BI-administratoren søge efter:

- Tilstrækkelig ledig hukommelse på tidspunktet for data opdateres, når tilgængelig hukommelse er mindre end 2 x størrelsen på datasættet opdateres.
- Datasæt ikke opdateres og ikke i hukommelsen før opdatering startet endnu til at vise interaktive trafik under tunge opdateringstidspunkter. Hvis du vil se, hvilke datasæt er indlæst i hukommelsen på et givet tidspunkt, en Power BI-administratoren kan se området datasæt **datasæt** fane i appen. Administratoren kan derefter tværgående filter til et givent tidspunkt ved at klikke på en af søjlerne i den **pr. time indlæses datasæt tæller**. En lokal spidsbelastning, vises på billedet nedenfor, angiver en time, når flere datasæt blev indlæst i hukommelsen, som kan forsinke starten af planlagte opdateringer.
- Øget datasæt evictions tager placere, når dataene opdateres er planlagt til at starte. Evictions kan angive der højt hukommelsesforbrug skyldtes forsyne for mange forskellige interaktive rapporter, før tidspunktet for opdatering. Visualiseringen **Hourly Dataset Evictions and Memory Consumption** viser tydlige stigninger i antallet af fjernelser.

På følgende billede vises en lokal stigning i indlæste datasæt, hvilket antyder, at interaktive forespørgsler forsinkede påbegyndelsen af opdateringerne. Hvis du vælger en bestemt periode i visualiseringen **Hourly Loaded Dataset Counts**, filtreres visualiseringen **Dataset Sizes** på tværs.

![En lokal stigning i de indlæste datasæt antyder, at interaktive forespørgsler forsinkede påbegyndelsen af opdateringerne](media/service-premium-capacity-scenarios/hourly-loaded-dataset-counts.png)

Power BI-administratoren kan forsøge at løse problemet ved at sikre, at tilstrækkelig hukommelse er tilgængelig for at dataopdateringerne kan starte, ved at:

- At kontakte datasæt opdatere ejere og bede dem om at Forskyd og mellemrum ud af data tidsplaner.
- Reducerer datasæt indlæsning af forespørgsel ved at fjerne unødvendige dashboards eller dashboard-felter, især dem, der anvendes sikkerhed på rækkeniveau.
- Hurtigere dataopdateringer ved at optimere logic Power-forespørgsel. Du kan forbedre udformning beregnede kolonner eller tabeller. Reducer datasæt størrelser, eller Konfigurer større datasæt for at udføre trinvise dataopdatering.

## <a name="identifying-slow-responding-datasets"></a>Identificerer langsomt svar datasæt

I dette scenarie begyndte en undersøgelse, når brugere klagede over, at visse rapporter tog for lang tid at åbne, og nogle gange hænge.

I appen kan Power BI-administratoren bruge visualiseringen **Query Durations** til at fastsætte, hvilke datasæt der har den dårligste ydeevne, ved at sortere datasættene efter **gennemsnitlig varighed**. Denne visualisering viser også antallet af datasætforespørgsler, så du kan se, hvor ofte datasættene forespørges.

![Dårligst præsterende datasæt](media/service-premium-capacity-scenarios/worst-performing-datasets.png)

Administratoren kan referere til den **forespørgsel varighed Distribution** visual, der viser en overordnede fordeling af kørsel af forespørgsler, der skal inddeles (< = 30ms, 0-100 MS) for den filtrerede tidsperiode. Forespørgsler, der tager ét sekund eller mindre betragtes som dynamiske af de fleste brugere. Forespørgsler, der tager længere tid, har tendens til at blive opfattet som dårlig ydeevne.

I visualiseringen **Hourly Query Duration Distribution** kan Power BI-administratoren identificere entimes perioder, hvor kapacitetsydeevnen kan være blevet opfattet som dårlig. Jo større de søjler, der repræsenterer varigheder over ét sekund for forespørgsler, er, desto større er risikoen for, at brugerne oplever det som dårlig ydeevne.

Visualiseringen er interaktiv, og når en del af søjlen vælges, filtreres den tilsvarende tabelvisualisering **Query Durations** på rapportsiden på tværs for at vise de datasæt, den repræsenterer. Denne filtrering på tværs gør det muligt for Power BI-administratoren nemt at identificere datasæt med lange svartider.

På følgende billede vises en visualisering, der er filtreret efter **Hourly Query Duration Distributions**, og som fokuserer på datasættet med den dårligste ydeevne i buckets på én time. 

![Filtreringen af visualiseringen Hourly Query Duration Distributions viser datasættet med den dårligste ydeevne](media/service-premium-capacity-scenarios/hourly-query-duration-distributions.png)

Når dårlig ydeevne datasættet i et bestemt én time-timespan er identificeret, kan Power BI-administratoren kan undersøge, om dårlig ydeevne er forårsaget af en overbelastet kapacitet, eller på grund af et dårligt designet datasæt eller en rapport. De kan referere til den **forespørgsel venter gange** visual og datasæt, Sortér faldende efter forespørgsel gennemsnitlige ventetid. Hvis en stor procentdel af forespørgsler, der venter på, er en stor efterspørgsel for datasættet sandsynligvis årsagen til for mange forespørgsel venter. Hvis forespørgslen gennemsnitlige ventetid er væsentlig (> 100 ms), kan det være værd at gennemse datasættet og rapporten for at se, om der kan foretages optimeringer. Eksempelvis givet færre visuelle elementer på rapportsider eller en optimering af DAX-udtryk.

![Visualiseringen Query Wait Times hjælper med at vise datasæt med en dårlig ydeevne](media/service-premium-capacity-scenarios/query-wait-times.png)

Der er flere mulige årsager til forespørgsel Vent tid ophobning i datasæt:

- Modeldesign en suboptimale, målingsudtryk eller endda rapportdesign – alle omstændigheder, der kan bidrage til langvarige forespørgsler, der anvender høj grad af CPU. Dette tvinger nye forespørgsler til at vente, indtil CPU-tråde bliver tilgængelige, og kan skabe en prop, hvilket ofte ses på travle tidspunkter. Siden **Query Waits** er den primære ressource til at afgøre, om datasæt har en høj gennemsnitlig forespørgselsventetid.
- Et højt antal samtidige kapacitetsbrugere (hundredvis eller tusindvis), der forbruger den samme rapport eller det samme datasæt. Selv veludformede datasæt kan have en dårlig ydeevne, hvis grænsen for samtidighed overskrides. Dette er normalt er angivet med et enkelt datasæt, der viser en dramatisk højere værdi til forespørgsel tæller end andre datasæt Vis (f.eks, 300 K forespørgsler for sammenlignet med ét datasæt < 30K forespørgsler for alle andre datasæt). På nogle pege på forespørgsel venter for dette datasæt begynder at Forskyd, som kan ses i den **forespørgsel varigheder** visual.
- Mange forskellige datasæt, der forespørges samtidigt, og som medfører hukommelsesudskiftning, da datasæt ofte bevæger sig ind og ud af hukommelsen. Dette medfører, at brugerne oplever langsom ydeevne, når datasættet indlæses i hukommelsen. For at bekræfte, Power BI-administratoren kan referere til den **pr. time datasæt Evictions og hukommelsesforbrug** visual, hvilket kan indikere, at et højt antal datasæt, der er indlæst i hukommelsen er der gentagne gange fjernes.

## <a name="identifying-causes-for-sporadically-slow-responding-datasets"></a>Identificerer årsager for sporadisk langsomt – besvarelse af datasæt

I dette scenarie begyndte en undersøgelse, når brugere, der er beskrevet, visuelle elementer er langsom at besvare nogle gange eller kunne reagere, men de var udviser acceptable resultater dynamisk på andre tidspunkter.

Afsnittet **Query Durations** i appen blev brugt til at finde det pågældende datasæt på følgende måde:

- I visualiseringen **Query Durations** filtrerede administratoren datasæt efter datasæt (startende med de datasæt, der forespørges mest hyppigt) og undersøgte de krydsfiltrerede søjler i visualiseringen **Hourly Query Distributions**.
- Når en enkelt søjle i én time viste betydelige ændringer i forholdet mellem alle forespørgsel varighed grupper vs. andre én time søjler for dette datasæt (f.eks, forhold mellem farverne, der ændres drastisk), betyder det, at dette datasæt, der vises en sporadisk ændring i ydeevne.
- De én-timers søjler, der viser en uregelmæssig del af forespørgsler med dårlig ydeevne, viste en tidsperiode, hvor datasættet blev påvirket af andre datasæts aktiviteter.

På billedet nedenfor vises én time den 30. januar, hvor der opstod en betydelig tilbagegang i et datasæts ydeevne, hvilket er angivet af størrelsen "(3,10s]" på udførelsesvarigheden for den pågældende bucket. Alle de datasæt, der indlæses i hukommelsen i løbet af tid, vise mulige datasæt, der forårsager effekten støjende viser, at klikke på søjlen én time.

![Søjle, der viser datasættene med den dårligste](media/service-premium-capacity-scenarios/worst-performing-queries.png)

Når et problematiske timespan er identificeret (f.eks, i løbet af 30. parameteren i billedet ovenfor) kan fjerne alle datasætfiltre Power BI-administratoren derefter kun filtrere ved denne timespan til at afgøre, hvilke datasæt var aktivt forespørges i denne periode. Det pågældende element datasæt for støjende effekten er normalt øverste forespurgt datasættet, eller det, der har den længst tid den gennemsnitlige varighed forespørgsel.

En løsning på dette problem kunne være at distribuere de pågældende datasæt over forskellige arbejdsområder i forskellige Premium-kapaciteter eller i en delt kapacitet, hvis datasætstørrelsen, forbrugskravene og mønstrene for dataopdateringer understøttes.

Det modsatte kan også være tilfældet. Power BI-administratoren kan identificere de tidspunkter, hvor forespørgselsydeevnen for et datasæt forbedres og lægge mærke til, hvad der forsvandt. Hvis der mangler visse oplysninger på dette tidspunkt, kan det være med til at pege på problemet.

## <a name="determining-whether-there-is-enough-memory"></a>Der bestemmer, om der er tilstrækkelig hukommelse

Power BI-administratoren kan benytte visualiseringen **Consumed Memory Percentages** på fanen **Datasæt** i appen til at bestemme, om der er tilstrækkelig hukommelse til, at kapaciteten kan fuldføre dens arbejdsbelastninger. **Al** hukommelse (i alt) repræsenterer den hukommelse, der forbruges af datasæt, der indlæses i hukommelsen, uanset om de aktivt forespørges eller behandles. **Aktiv** hukommelse repræsenterer den hukommelse, der forbruges af datasæt, der behandles aktivt.

Visualiseringen i en sund kapacitet ser ud som følger og viser et mellemrum mellem al hukommelse (i alt) og aktiv hukommelse:

![I en sund kapacitet vises et mellemrum mellem al hukommelse (i alt) og aktiv hukommelse](media/service-premium-capacity-scenarios/memory-healthy-capacity.png)

I en kapacitet, oplever belastning på hukommelsen, viser den samme visualisering tydeligt aktive hukommelse og samlede hukommelse konvergeres, hvilket betyder, at det er umuligt at indlæse ekstra datasæt derefter i hukommelsen. I dette tilfælde kan Power BI-administratoren klikke på **Genstart af kapacitet** (i **Avancerede indstillinger**  i området med kapacitetsindstillinger i administrationsportalen). Genstart af kapaciteten resulterer i, at alle datasæt trækkes fra hukommelsen og indlæses igen i hukommelsen efter behov (af forespørgsler eller dataopdateringer).

![**Aktiv** hukommelse konvergerer med **al** hukommelse](media/service-premium-capacity-scenarios/memory-unhealthy-capacity.png)

## <a name="determining-whether-there-is-enough-cpu"></a>Der bestemmer, om der er tilstrækkelig CPU

Generelt skal en kapacitets gennemsnitlige CPU-forbrug forblive under 80 %. Hvis denne værdi overskrides, betyder det, at kapaciteten nærmer sig CPU-mætning.

Konsekvenserne af at CPU mætning udtrykkes af handlinger, der tager længere tid end de skal, på grund af den kapacitet, udføre mange CPU kontekster parametre, når det forsøger at behandle alle handlinger. Dette er angivet ved høj forespørgsel ventetider i en Premium-kapacitet med et højt antal samtidige forespørgsler. En konsekvens af lange forespørgselsventetider er langsommere svartider end normalt. Power BI-administratoren kan let kan identificere, når CPU'en er mættet ved at få vist visualiseringen **Hourly Query Wait Time Distributions**. Periodiske spidsbelastninger af forespørgselsventetider indikerer en potentiel CPU-mætning.

![Periodiske spidsbelastninger af forespørgselsventetider indikerer en potentiel CPU-mætning](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Et tilsvarende mønster kan nogle gange registreres i handlinger i baggrunden, hvis de bidrager til CPU-mætning. En Power BI-administrator kan søge efter en periodiske stigning i et specifikt datasæt, hvilket kan indikere CPU mætning på tidspunktet (sandsynligvis på grund af andre igangværende datasæt opdateres eller interaktive forespørgsler) opdateringer til tidspunkter. I dette tilfælde afslører visningen **System** i appen ikke nødvendigvis, at CPU'en er på 100 %. Visningen **System** viser timgegennemsnitten, men CPU'en kan blive mættet under adskillige minutter med mange handlinger, hvilket vises som stigninger i ventetider.

Effekten af CPU-mætningen kan ses flere steder. Selvom antallet af forespørgsler, der venter er vigtigt, opstår der altid forespørgselsventetider til en vis grad, uden at det giver anledning til forringelse af ydeevnen. For visse datasæt (med længere gennemsnitlige forespørgselstider, hvilket skyldes kompleksitet eller størrelse) er mere udsatte for konsekvenserne af CPU-mætning end andre. Power BI-administratoren kan nemt finde disse datasæt ved at søge efter ændringer i farvesammensætningen af søjlerne i visualiseringen **Hourly Wait Time Distribution**. Når en søjle med udenforliggende værdier er blevet fundet, kan administratoren søge efter de datasæt, der havde forespørgselsventetid på det pågældende tidspunkt og også kigge på den gennemsnitlige forespørgselsventetid sammenlignet med den gennemsnitlige varighed af forespørgslen. Når disse to målinger har den samme størrelse og arbejdsbelastningen for forespørgslen for datasættet ikke er ubetydelig, er det sandsynligt, at datasættet er påvirket af utilstrækkelig CPU.

Denne effekt kan være særligt synlige, når et datasæt, der forbruges i korte bølger af høj hyppighed forespørgsler af flere brugere (f.eks, i en træningssession), hvilket resulterer i CPU mætning under hver burst. I dette tilfælde kan der opstå betydelige forespørgselsventetider for dette datasæt, og andre datasæt i kapaciteten kan også blive påvirket.

I nogle tilfælde kan Power BI-administratorer anmode datasætejerne om at oprette en mindre svingende forespørgselsarbejdsbelastning ved at oprette et dashboard (som forespørger med jævne mellemrum med datasætopdateringer af cachelagrede felter) i stedet for en rapport. Dette kan forhindre stigninger, når dashboardet indlæses. Denne løsning er ikke altid mulig for det givne forretningsmæssige krav, men det kan være en effektiv måde at undgå CPU-mætning på uden at ændre datasættet.

## <a name="acknowledgements"></a>Godkendelser

I denne artikel er skrevet af Peter Myers, Data Platform MVP og uafhængige BI-ekspert med [bitvis løsninger](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Næste trin

> [!div class="nextstepaction"]
> [Overvåg Premium-kapaciteter med appen](service-admin-premium-monitor-capacity.md)    
> [!div class="nextstepaction"]
> [Overvåg kapaciteter i Admin-portalen](service-admin-premium-monitor-portal.md)   

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

||||||