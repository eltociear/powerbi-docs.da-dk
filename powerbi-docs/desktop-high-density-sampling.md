---
title: "Stikprøvetagning af linjer med høj tæthed i Power BI"
description: "Stikprøvetagning af linjer med høj tæthed i Power BI"
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
ms.openlocfilehash: d0b95684ee979c2e06a4d1043ffe9c6e6b12f38e
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/17/2017
---
# <a name="high-density-line-sampling-in-power-bi"></a>Stikprøvetagning af linjer med høj tæthed i Power BI
Fra og med udgivelsen af **Power BI Desktop** fra juni 2017 og opdateringerne til **Power BI-tjenesten** er der en ny algoritme til stikprøvetagning tilgængelig, som forbedrer visuelle effekter til stikprøveudtagning af data med høj tæthed. Du kan f.eks. oprette et kurvediagram ud fra dine detailbutikkers salgsresultater, hvor hver butik har mere end ti tusinde salgskvitteringer hvert år. Et kurvediagram med disse salgsoplysninger indsamler data (vælg en relevant repræsentation af disse data for at illustrere, hvordan salget varierer over tid) fra dataene for hver enkelt butik og opretter et kurvediagram med flere serier, der så repræsenterer de underliggende data. Dette er almindelig praksis i visualisering af data med høj tæthed, og Power BI Desktop har forbedret denne prøveudtagning af data med høj tæthed. Disse oplysninger er beskrevet i denne artikel.

![](media/desktop-high-density-sampling/high-density-sampling_01.png)

> [!NOTE]
> Den algoritme for **stikprøvetagning med høj tæthed**, der er beskrevet i denne artikel, gælder for og er tilgængelig både i **Power BI Desktop** og **Power BI-tjenesten**.
> 
> 

## <a name="how-high-density-line-sampling-works"></a>Sådan fungerer stikprøvetagning af linjer med høj tæthed
Tidligere valgte **Power BI** en samling af eksempeldatapunkter i alle de underliggende data på en deterministisk måde. I en visualisering med data med høj tæthed, som strækker sig over et kalenderår, kan der f.eks. være 350 eksempeldatapunkter vist i visualiseringen, som hver især er valgt for at sikre, at det komplette dataområde (den samlede serie underliggende data) er repræsenteret i visualiseringen. Som hjælp til at kunne forstå, hvordan dette sker, kan vi antage, at vi laver en afbildning af aktiekursen over en periode på ét år og har valgt 365 datapunkter til at oprette en visualisering af et kurvediagram (det er ét datapunkt for hver dag).

I denne situation er der mange værdier til en aktiekurs for hver enkelt dag. Der er naturligvis en daglig største- og mindsteværdi, men de kan optræde når som helst i løbet af dagen, når aktiemarkedet er åbent. Ved stikprøvetagning af linjer med høj tæthed, hvor det underliggende dataeksempel udføres kl. 10:30 og 12:00 hver dag, ville du få et repræsentativt snapshot af de underliggende data (kursen kl. 10:30 og 12:00), men det ville muligvis ikke registrere de faktiske højeste og laveste værdier for aktiekursen for det pågældende repræsentative datapunkt (på denne dag). I denne – og andre – situationer repræsenterer stikprøvetagningen de underliggende data, men den gengiver ikke altid vigtige punkter, som i dette tilfælde vil være de daglige højeste og laveste aktiekurser.

Pr. definition foretages der stikprøvetagning af data med høj tæthed for at gøre det muligt at oprette visualiseringer hurtigere. Dataene reagerer også på interaktivitet (for mange datapunkter i en visualisering kan fryse en visualisering og dermed forringe synligheden af tendenser). Den måde stikprøvetagning af disse data udføres på for at give den bedste visualisering, er det, der driver oprettelsen af algoritmen til stikprøvetagning. I Power BI Desktop er algoritmen blevet forbedret for at opnå den bedste kombination af svartid, repræsentation og tydelig bevarelse af vigtige punkter i hvert tidsrum.

## <a name="how-the-new-line-sampling-algorithm-works"></a>Sådan fungerer den nye algoritme for linjestikprøvetagning
Den nye algoritme for stikprøvetagning af linjer med høj tæthed er tilgængelig for visualiseringer i kurvediagrammer og områdediagrammer med en fortløbende X-akse.

I en visualisering med høj tæthed laver **Power BI** på en smart måde udsnit af dine data i dele med høj opløsning og vælger så vigtige punkter til at repræsentere hver del. Opdelingen af data med høj opløsning i udsnit er specifikt tilpasset til at sikre, at det diagram, der fås, visuelt ikke kan skelnes fra gengivelse af alle de underliggende datapunkter, men måden er væsentlig hurtigere og mere interaktiv.

### <a name="minimum-and-maximum-values-for-high-density-line-visuals"></a>Minimum- og maksimumværdier for linjevisualiseringer med stor tæthed
For enhver given visualisering gælder følgende visuelle begrænsninger:

* Det maksimale antal datapunkter, der kan **vises** i visualiseringen, er *3.500* uanset antallet af underliggende datapunkter eller -serier. Hvis du derfor har 10 serier med 350 datapunkter i hver, har visualiseringen nået grænsen for det maksimale antal samlede datapunkter. Hvis du har én serie, kan den have op til 3.500 datapunkter, hvis det i den nye algoritme skønnes, at det er den bedste prøvetagning af de underliggende data.
* Enhver visualisering kan maksimalt have **60 serier**. Hvis du har mere end 60 serier, skal du opdele dataene og oprette flere visualiseringer med 60 serier eller færre. Det er en god ide at bruge et **udsnit** til kun at vise segmenter af dataene (kun bestemte serier). Hvis du f.eks. får vist alle underkategorier i forklaringen, kan du bruge et udsnit til at filtrere efter den overordnede kategori på samme rapportside.

Disse parametre sørger for, at visualiseringer i Power BI Desktop gengives meget hurtigt og reagerer på interaktion med brugere og medfører ikke unødvendigt forbrug af beregningsressourcer på den computer, der gengiver visualiseringen.

### <a name="evaluating-representative-data-points-for-high-density-line-visuals"></a>Evaluering af repræsentative datapunkter for linjevisualiseringer med stor tæthed
Når antallet af underliggende datapunkter overstiger de datapunkter, der kan gengives i visualiseringen (overstiger 3.500), starter en proces kaldet *gruppering i beholdere*, der deler de underliggende data i grupper kaldet *placeringer* og derefter gentagne gange justerer disse placeringer.

Algoritmen opretter så mange placeringer som muligt for at skabe den bedst mulige granulering for visualiseringen. Inden for hver placering finder algoritmen minimum- og maksimumdataværdien for at sikre, at vigtige og betydningsfulde værdier (f.eks. udenforliggende værdier) registreres og vises i visualiseringen. Baseret på resultaterne af grupperingen i beholdere og den efterfølgende evaluering af dataene af Power BI, bestemmes den mindste opløsning for X-aksen i visualiseringen – for at sikre maksimal granulering for visualiseringen.

Som tidligere nævnt er minimumgranuleringen for hver serie 350 punkter, mens maksimum er 3.500.

Hver placering er repræsenteret af to datapunkter, der bliver placeringens repræsentative datapunkter i visualiseringen. Datapunkterne er simpelthen den mindste og højeste værdi for den pågældende placering og ved at vælge mindste og højeste sikrer processen til gruppering i beholdere, at vigtige høje værdier eller betydningsfulde lave værdier registreres og gengives i visualiseringen.

Det er rigtigt, at det kan lyde som en stor mængde analyse for at sikre, at lejlighedsvise udenforliggende værdier registreres og gengives i visualiseringen – og det er netop den bagvedliggende årsag til den nye algoritme og processen til gruppering i beholdere.

## <a name="tooltips-and-high-density-line-sampling"></a>Værktøjstip og stikprøvetagning af linjer med høj tæthed
Det er vigtigt at bemærke, at denne proces til gruppering af data, som resulterer i, at minimum- og maksimumværdien for en given placering registreres og vises i visualiseringen, kan påvirke måden, som værktøjstip vises på, når du peger på datapunkter. For at vise hvordan og hvorfor dette sker, kan vi gå tilbage til vores eksempel med aktiekurser tidligere i denne artikel.

Antag, at du opretter en visualisering baseret på aktiekurs, og at du sammenligner to forskellige aktier, som begge bruger **stikprøvetagning med høj tæthed**. De underliggende data for hver serie indeholder mange datapunkter (det kan være, at du registrerer aktiekursen hvert sekund på dagen). Algoritmen til stikprøvetagning af linjer med høj tæthed foretager gruppering i beholdere for hver serie uafhængigt af hinanden.

Nu antager vi, at den første aktie stiger i pris kl. 12:02 og derefter hurtigt falder tilbage ti sekunder senere – det er et vigtigt datapunkt. Når gruppering i beholdere finder sted for den pågældende aktie, vil den højeste værdi kl. 12:02 være et repræsentativt datapunkt for denne placering.

Men for den anden aktie var 12:02 hverken en høj eller en lav værdi i placeringen, der inkluderede tidspunktet – høj og lav værdi for placeringen, der inkluderer 12:02, fandt måske sted tre minutter senere. Når kurvediagrammet oprettes, og du peger på 12:02, vil du i denne situation få vist en værdi i værktøjstippet til den første aktie (fordi den steg kl. 12:02, og denne værdi blev valgt som højeste datapunkt på denne placering), men du får *ikke* vist nogen værdi i værktøjstippet kl. 12:02 for den anden aktie. Det skyldes, at den anden aktie hverken havde en høj eller en lav værdi for den placering, der inkluderede 12:02. Der er ingen data at vise for den anden aktie kl. 12:02, og derfor vises der ingen værktøjstipdata.

Denne situation vil ofte opstå med værktøjstip. De høje og lave værdier for en bestemt placering stemmer muligvis ikke perfekt overens med de ligeligt skalerede værdipunkter på X-aksen, og værktøjstippet vil derfor ikke vise værdien.  

## <a name="how-to-turn-on-high-density-line-sampling"></a>Sådan aktiveres stikprøvetagning af linjer med høj tæthed
Den nye algoritme er som standard slået **til**. Hvis du vil ændre denne indstilling, skal du gå til ruden **Formatering** på kortet **Generelt**, og nederst kan du se en til/fra-slider kaldet **High Density Sampling** (Stikprøvetagning med høj tæthed). Hvis du vil slå den fra, skal du skubbe den hen på **Fra**.

![](media/desktop-high-density-sampling/high-density-sampling_02.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
Den nye algoritme for stikprøvetagning af linjer med høj tæthed er en vigtig forbedring af Power BI, men der er endnu et par ting, du skal vide, når du arbejder med værdier med høj tæthed og data.

* På grund af større granulering og processen til gruppering i beholdere vil **Værktøjstip** muligvis kun vise en værdi, hvis de repræsentative data er justeret efter markøren. Se afsnittet tidligere i denne artikel om **Værktøjstip** for at få flere oplysninger.
* Når størrelsen på en samlet datakilde er for stor, eliminerer den nye algoritme serier (forklaringselementer) for at tilpasse maksimumbegrænsningen for dataimporten.
  
  * I denne situation placerer den nye algoritme forklaringsserier alfabetisk og starter nede på listen over elementer i forklaringen i alfabetisk rækkefølge, indtil maksimum for importen er nået, og importerer ikke flere serier.
* Når et underliggende datasæt har mere end 60 serier (det maksimale antal serier som beskrevet tidligere), placerer den nye algoritme serien alfabetisk og fjerner serier ud over den 60. alfabetisk placerede serie.
* Hvis værdierne i dataene ikke er af typen *numerisk* eller *dato/klokkeslæt* bruger Power BI ikke den nye algoritme og vender tilbage til den forrige algoritme (stikprøvetagning uden høj tæthed).
* Indstillingen **Vis elementer uden data** understøttes ikke med den nye algoritme.
* Den nye algoritme understøttes ikke, når du bruger en direkte forbindelse til en model, der hostes i SQL Server Analysis Services (version 2016 eller tidligere). Den understøttes i modeller, der hostes i **Power BI** eller Azure Analysis Services.

## <a name="next-steps"></a>Næste trin
Du kan finde oplysninger om stikprøvetagning med høj tæthed i punktdiagrammer i følgende artikel.

* [Stikprøvetagning med høj tæthed i Power BI-punktdiagrammer](desktop-high-density-scatter-charts.md)

