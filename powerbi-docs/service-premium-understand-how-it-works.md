---
title: Brug og optimering af hukommelse med Power BI Premium-kapacitet
description: Få en forståelse af administration og optimering af hukommelse med Power BI Premium-kapacitet.
ms.date: 02/05/2019
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-admin
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: d7cebbd569d16192f4acfa1c96394130731efa17
ms.sourcegitcommit: d4d36b6b200f2693b545e4a3e66d94c77a3cfafb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/01/2019
ms.locfileid: "57014570"
---
# <a name="microsoft-power-bi-premium-capacity-resource-management-and-optimization"></a>Administration og optimering af ressourcer med Microsoft Power BI Premium-kapacitet

I denne artikel beskrives, hvordan Power BI Premium administrerer ressourcer. Artiklen indeholder også eksempler og forslag til fejlfinding. Du kan få vist en oversigt i [Hvad er Power BI Premium?](service-premium.md)

## <a name="premium-capacity-memory-management"></a>Administration af hukommelse med Premium-kapacitet

 Hukommelse med Premium kapacitet bruges af:

* De datasæt, der er indlæst i hukommelsen.
* Opdatering af datasæt (både planlagte og efter behov).
* Arbejdsbelastninger, som kapaciteten understøtter
* Rapportforespørgsler.

Når der er oprettet en anmodning til et udgivet datasæt i din kapacitet, indlæses dette datasæt i hukommelsen fra det vedvarende lager (også kaldet indlæsning af afbildning). Hvis du lader datasættet forblive indlæst i hukommelsen, opnår du hurtigere svar på fremtidige forespørgsler til dette datasæt. Ud over den hukommelse, der kræves, for at datasættet kan forblive indlæst i hukommelsen, forbruger opdateringer af rapportforespørgsler og datasæt også yderligere hukommelse.

### <a name="dataset-memory-estimation"></a>Estimering af datasættets hukommelse

Når du forsøger at indlæse et datasæt i hukommelsen, estimerer Power BI mængden af hukommelse, som dette datasæt kræver for at udføre den ønskede kommando. Datasæt i hukommelsen er ofte større, end når de er gemt på disken. Under opdatering af et datasæt kræver Power BI mindst dobbelt så meget hukommelse, som når datasættet er inaktivt.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Overbebyrdelse af kapacitet, fjernelse og genindlæsning af datasæt

Power BI Premium giver dig den fordel, at du kan *overbebyrde* din kapacitet. Du kan for eksempel udgive flere datasæt, end kapaciteten kan indeholde. Hvis datasættene har brug for mere hukommelse, end der kan være i kapaciteten, lagres nogle af datasættene separat på et vedvarende lager. Det vedvarende lager er en del af 100 TB lager, der er knyttet til hver af dine kapaciteter.

Så hvilke datasæt forbliver i hukommelsen, og hvad sker der med de andre datasæt? Når en anmodning oprettes i forhold til et datasæt, indlæses den som tidligere nævnt i hukommelsen (indlæsning af afbildning). Anmodningen kan være en rapportforespørgsel eller en opdateringshandling. Da du kan overbebyrde din kapacitet, kan kapaciteten også opleve øget tryk på hukommelsen. Når en kapacitet står over for øget hukommelsesforbrug, *fjerner* noden et eller flere datasæt fra hukommelsen. Datasæt, der er inaktive (uden forespørgsels-/opdateringshandlinger, der udføres i øjeblikket), ryddes først. Derefter er fjernelsesrækkefølgen baseret på en måling af 'mindst brugt for nylig'. Hvis der sendes nye kommandoer til det datasæt, der er fjernet, forsøger tjenesten at genindlæse datasættet i hukommelsen og kommer muligvis til at fjerne andre datasæt. Denne funktionsmåde medfører en mere effektiv udnyttelse, idet kapaciteten kan betjene mange flere datasæt, end hukommelsen kan indeholde.

Indlæsning af et datasæt i hukommelsen er en relativt dyr affære. Afhængigt af størrelsen på datasættet kan det tage fra et par sekunder for små datasæt til over ti sekunder eller endog minutter for store datasæt, f.eks. datasæt på op til 10 GB. Premium-kapacitet forsøger at reducere antallet af gange, kapaciteten skal indlæses, ved at bevare de datasæt, der er anvendt mindst på det seneste, i hukommelsen så længe som muligt. Når der kræves mere hukommelse, skal der fjernes nogle datasæt, og systemet forsøger at vælge det, der har mindst indflydelse på brugeroplevelsen. Når der kræves mere hukommelse, skal der fjernes nogle datasæt, og systemet forsøger at vælge det, der har mindst indflydelse på brugeroplevelsen. Systemet vil f.eks. undgå at fjerne datasæt, der er blevet brugt aktivt inden for de sidste par minutter. Der bliver sandsynligvis snart forespurgt på disse datasæt igen.

Fjernelsesprocessen er i sig selv en hurtig handling. Hvis datasættet ikke bruges aktivt på tidspunktet for fjernelse, kan brugeren ikke fastslå, hvor stor indflydelse fjernelsen får. Men hvis der er for mange datasæt, der bruges aktivt på samme tid, og der ikke er nok hukommelse til at indeholde dem alle, kan der ske mange fjernelser. Hvis der fjernes for mange aktive datasæt, kan det føre til en situation med hukommelsesudskiftning, hvor datasæt fjernes konstant og indlæses igen, og brugere kan opleve et mærkbart fald i svartiderne og ydeevnen.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Hukommelseskrav til opdatering af datasæt i konkurrere med hukommelseskrav til aktive datasæt

Datasæt kan opdateres efter en tidsplan eller efter behov af brugere. Som beskrevet tidligere er den hukommelse, der kræves til komplette opdateringer, mindst dobbelt så stor som hukommelsen for de indlæste og inaktive datasæt. Før opdateringen starter, anslås hukommelseskravene til opdateringen. Hvis det samlede hukommelseskrav er større end den tilgængelige hukommelse i kapaciteten, fjernes der nogle datasæt. Fjernelsen er igen baseret på 'mindst brugt for nylig'.

Hvis den nødvendige hukommelse ikke er tilgængelig efter fjernelsen, sættes opdateringen i kø, og der gøres forsøg på at udføre den igen senere. Tjenesten prøver igen, indtil det lykkes, eller indtil en ny opdateringshandling starter.

Hvis der oprettes en interaktiv forespørgsel til et datasæt i kapaciteten, og der ikke er nok ledig hukommelse på grund af en igangværende opdatering, mislykkes anmodningen, og brugeren skal selv forsøge.

### <a name="workloads"></a>Arbejdsbelastninger

Som standard understøtter kapaciteter for **Power BI Premium** og **Power BI Embedded** kun den arbejdsbelastning, der er knyttet til Power BI-forespørgsler, som kører i clouden. Vi tilbyder nu understøttelse af yderligere to arbejdsbelastninger: **Sideinddelte rapporter** og **Dataflow**. Hvis funktionen er aktiveret, kan det påvirke hukommelsesforbruget i din kapacitet. 

## <a name="cpu-resource-management-in-premium-capacity"></a>CPU-ressourcestyring i Premium-kapacitet

Der er to primære forbrugere af CPU-ressourcer:

* Forespørgsler fra rapporter
* Opdatering (behandling)

### <a name="queries-from-reports"></a>Forespørgsler fra rapporter

Rapportforespørgsler forbruger CPU-ressourcer i din kapacitet. Rapporter med ineffektive forespørgsler eller mange samtidige brugere kan forbruge en masse CPU-ressourcer. Din eksisterende kapacitet er muligvis ikke tilstrækkelig til at håndtere belastningen.

### <a name="refresh-parallelization-policy"></a>Politik for parallelle opdateringer

Hukommelse er ikke den eneste ressource, der kan begrænse opdateringen af datasæt. Antallet af v-kerner på en server kan også være en faktor. Da alle opdateringshandlinger kræver et vist antal v-kerner, er der en grænse for, hvor mange opdateringer der kan køre parallelt. Grænsen pr. SKU er beskrevet i følgende tabel. Yderligere opdateringer, der er ud over disse begrænsninger, sættes i kø.

 | SKU | Backend-v-kerner | Parallel opdatering af modeller |
 | --- | --- | --- |
 | A1  | 0,5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0,5  | 1  |
 | EM2  | 1  | 2  |
 | EM3  | 2  | 3  |
 | P1  | 4  | 6  |
 | P2  | 8  | 12  |
 | P3  | 16  | 24  |
 | P4  | 32  | 48  |
 | P5  | 64  | 96  |

 > [!TIP]
> Hvis dine opdateringer bliver forsinket, kan du kontrollere antallet af parallelle opdateringer, der understøttes af din kapacitet.

## <a name="example-scenarios"></a>Eksempelscenarier

Her beskrives nogle almindelige scenarier og de handlinger, som tjenesten udfører:

**Tyve planlagte opdateringer, der alle sendes på samme tid**. Power BI forsøger at starte de første *x* opdateringer på samme tid. Værdien *x* bestemmes af politikken for parallelle opdateringer for den pågældende SKU. Hvis Power BI ikke kan få nok hukommelse ved at fjerne inaktive datasæt (datasæt, der ikke er brugt for nylig), er det ikke alle *x* opdateringer, der starter på samme tid. De opdateringer, der ikke kan startes, sættes i kø, indtil de kan starte.

**To opdateringer kører på samme tid, og der er kun nok hukommelse til, at én kan afsluttes**. Den, der kan afsluttes, starter. Den anden prøver igen senere.

**Der forespørges på et stort antal datasæt, mens flere datasæt opdateres**. Hvis der ikke er tilstrækkelig hukommelse, forsøger Power BI at stoppe aktive opdateringer for at give prioritet til interaktive forespørgsler. Derved forringes ydeevnen for opdateringer.

**Datasæt kræver for meget hukommelse til at kunne opdateres med den nuværende kapacitetsstørrelse**. Opdateringen mislykkes. Der gøres forsøg på at få mere hukommelse ved at fjerne datasæt.

**Opdatering af et enkelt datasæt, som har en stor spidsbelastning i hukommelsen**. Hvis spidsbelastningen er større end den mængde hukommelse, der kan opnås ved at fjerne inaktive datasæt, gøres der forsøg på at køre opdateringen senere, indtil der er tilstrækkelig hukommelse til at håndtere belastningen.

**Forespørgslen udføres for et datasæt, som ikke kan få nok hukommelse ved at fjerne alle inaktive datasæt og opdateringer**. Disse forespørgsler mislykkes. Der skal købes større kapacitet i forbindelse med disse krav til arbejdsbelastninger.

## <a name="troubleshooting-and-testing"></a>Fejlfinding og test

Hvis rapporter er langsomme eller ikke svarer, skal du kun starte med at teste for én bruger i rapporten. Start derefter med at øge belastningen for samtidige brugere for at finde grænsen. I mange tilfælde kan justering af DAX-forespørgsler ændre ydeevnen for dine rapporter væsentligt. Justering af forespørgsler øger også antallet af samtidige brugere, der understøttes af din kapacitet. [Overvåg din kapacitet](service-admin-premium-monitor-capacity.md) for at identificere potentielle problemer med ydeevnen.

Brug Power BI Embedded-kapacitet i Azure til at teste forskellige SKU'er og finde den bedste Premium SKU for din forventede arbejdsbelastning. Power BI Embedded A4-SKU'en er lig med P1, A5 = P2 og A6 = P3. I Azure kan du nemt skifte mellem SKU'er ved at skalere op og ned på Azure-portalen. Når du finder den SKU, der passer bedst til din arbejdsbelastning, og du er færdig med at teste, kan du slette SKU'en.

I nogle tilfælde kan du få meget at vide om problemet ved at åbne en Power BI Desktop-fil (PBIX-fil) for modellen på din computer og kontrollere forbruget af hukommelse og CPU. Dette er ikke en hjælp for meget store modeller, men for visse mindre modeller kan du prøve at åbne, opdatere og forespørge modellen fra computeren. Kontrollér modellens størrelse og forbrug af hukommelse og CPU, når du åbner modellen. Prøv at opdatere og oprette en forespørgsel. Brug joblisten til at kontrollere forbrug af CPU og hukommelse for den lokale fil. Nogle gange kan disse målepunkter på selve computeren fortælle, at en lav Premium-kapacitet, f.eks. P1 eller P2, muligvis ikke fungerer for din løsning.

