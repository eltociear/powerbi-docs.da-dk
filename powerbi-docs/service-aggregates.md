---
title: Aggregater (sum, gennemsnit, maksimum, osv.) i Power BI
description: Tilpas aggregeringen i et diagram (sum, gennemsnit, maksimum, osv.) i Power BI
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/23/2017
ms.author: mihart
ms.openlocfilehash: c1b926e129e8d82edd9c329a51623908c4e7c9e0
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/27/2017
---
# <a name="aggregates-in-power-bi"></a>Aggregeringer i Power BI
## <a name="what-is-an-aggregate"></a>Hvad er en aggregering?
Du kan sommetider få brug for matematisk at kombinere værdierne i rækkerne i en kolonne. Den matematiske handling kan f.eks. være sum, gennemsnit, maksimum, antal, osv. Når værdier af data kombineres i rækker i kolonner, kaldes det aggregering. Resultatet af den matematiske handling er en *aggregering*. 

Et numerisk felt er en værdi, der skal aggregeres (f.eks. sammenlægges eller have beregnet gennemsnittet af) over et relevant kategorifelt.  Det kan f.eks. være "salgsbeløb efter produkt" og "antal defekter efter område". Numeriske felter kaldes også for **mål**. I listen Felter vises mål med ∑-symbolet. Du kan finde flere oplysninger under [Rapporteditoren... få en introduktion](service-the-report-editor-take-a-tour.md).

Sommetider er et *mål* faktisk et *beregnet mål*. Beregnede mål i Power BI importeres med dataene (der er defineret i datamodellen, som din rapport er baseret på). Hvert beregnede mål har sin egen hard-coded formel. Du kan ikke ændre den brugte aggregering – f.eks. hvis det er en sum, kan det kun være en sum. På listen Felter vises *beregnede mål* med lommeregnersymbolet. For at få flere oplysninger om, hvordan beregnede mål oprettes, skal du se [Mål i Power BI Desktop](desktop-measures.md).

Kategorifelter er ikke numeriske, men de kan stadig aggregeres.  Når kategorifelter placeres i intervallet *udelukkende med numerisk* indhold, som f.eks. **Værdier** eller **Værktøjstip**, så kan Power BI tælle forekomsterne af hver kategori eller tælle de særskilte forekomster af hver kategori.  I Power BI kan strenge og datoer aggregeres på yderligere et par måder: tidligste, seneste, første og sidste.  

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Hvorfor fungerer aggregeringer ikke, som jeg vil have dem til?
Arbejdet med aggregeringer i Power BI kan være forvirrende; måske har du et numerisk felt, og Power BI vil ikke lade dig ændre aggregeringen. Eller måske har du et felt, som f.eks. et år, som du ikke vil aggregere, men kun vil tælle antallet af forekomster af.

Kilden til problemet er oftest måden, hvorpå feltet er kategoriseret i Power BI-datasættet. Måske er feltet kategoriseret som tekst, hvilket forklarer, hvorfor sammenlægning eller beregning af gennemsnit ikke virker. Desværre [kan kun datasættets ejer ændre måden, hvorpå et felt er kategoriseret](desktop-measures.md).  

Du kan med fordel bruge det særlige afsnit til slut i denne artikel kaldet **Tip og fejlfinding** for at få hjælp til at skære igennem forvirringen.  Hvis du ikke kan finde løsningen her, kan du stille dit spørgsmål i [Power BI-community-forummet](http://community.powerbi.com) for at få et hurtigt svar fra Power BI-teamet.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Tilpas måden, hvorpå et numerisk felt aggregeres
Lad os antage, at du har et diagram, der sammenlægger salgsdata for forskellige områder, men du hellere vil beregne gennemsnittet. 

1. Føj målet til en visualisering i rapportens Redigeringsvisning.
2. Find det pågældende felt i ruden Visualizations, højreklik, og vælg aggregeringstypen, du skal bruge. Hvis du ikke kan se den ønskede aggregering, skal du kontakte ejeren af datasættet. Problemet kan skyldes, at feltet er blevet kategoriseret på en bestemt måde af ejeren.  
   
   ![](media/service-aggregates/aggregate_new.png)
   
   > [!NOTE]
   > De tilgængelige indstillinger i rullemenuen varierer afhængig af 1) det valgte felt og 2) måden, som feltet er kategoriseret på af datasættets ejer.
   > 
   > 

Nedenfor følger nogen af indstillingerne, der kan være tilgængelige ved aggregering af et felt:

* **Opsummer ikke**. Når du har valgt denne indstilling, bliver hvert felt behandlet særskilt og opsummeres ikke. Denne indstilling bruges ofte, hvis du har en numerisk id-kolonne, der ikke skal summeres.
* **Sum**. Dette lægger alle værdier i feltet sammen.
* **Gennemsnit**. Beregner et matematisk gennemsnit af værdierne.
* **Minimum**. Viser den mindste værdi.
* **Maksimum**. Viser den største værdi.
* **Antal (ikke tomme)**. Tæller antallet af værdier i feltet, der ikke er tomme.
* **Antal (distinkt).** Denne indstilling tæller antallet af forskellige værdier i feltet.
* **Standardafvigelse.**
* **Varians**.
* **Median**.  Viser median (middel)-værdien. Dette er den værdi, der har det samme antal elementer, over og under.  Hvis der er to medianer, beregner Power BI gennemsnittet af dem.

F.eks. disse data:

| Land | Antal |
|:--- |:--- |
| USA |100 |
| Storbritannien |150 |
| Canada |100 |
| Tyskland |125 |
| Frankrig | |
| Japan |125 |
| Australien |150 |

Giver de følgende resultater:

* **Opsummer ikke**: Hver værdi vises særskilt
* **Sum**: 750
* **Gennemsnit**: 125
* **Maksimum**:  150
* **Minimum**: 100
* **Antal (ikke tomme)**: 6
* **Antal (distinkt)**: 4
* **Standardafvigelse**: 20.4124145...
* **Varians**: 416.666...
* **Median**: 125

## <a name="use-a-non-aggregated-field-as-a-numeric-field"></a>Brug et ikke-aggregeret felt som et numerisk felt
Du kan også bruge et ikke-aggregeret felt som et numerisk felt. Hvis du f.eks. har et felt med Produktnavn, så kan du tilføje det som en værdi og derefter indstille det til **Antal** eller **Distinkt antal**. 

1. For eksempel hvis du vælger **Butik > Kæde**.
   
   ![](media/service-aggregates/count-of-chain-do_not_summarize.png)
2. Hvis du desuden ændrer aggregeringen fra standarden **Opsummer ikke** til **Antal (distinkt)**, så tælles antallet af forskellige kæder i Power BI. I dette tilfælde er der 2: Fashions Direct og Lindseys.
   
   ![](media/service-aggregates/aggregates_count.png)
3. Hvis du desuden ændrer aggregeringen til **Antal**, så tælles det samlede antal i Power BI. I dette tilfælde er der 104 poster for **Kæde**. Hvis du tilføjer **Kæde** som et filter, så kan du se, at der er 37 rækker for Fashions Direct og 67 rækker for Lindseys.  
   
   ![](media/service-aggregates/count_of_chain_104.png)

## <a name="tips-and-troubleshooting"></a>Tip og fejlfinding
Sp: Hvorfor har jeg ikke en **Opsummer ikke**-indstilling?

Sv: Det valgte felt er sandsynligvis et beregnet mål. Husk, at hvert beregnede mål har sin egen hard-coded formel. Du kan ikke ændre beregningen.

Sp: Mit felt **er** numerisk, så hvorfor kan jeg kun vælge **Antal** og **Distinkt antal**?

Sv: Den sandsynlige forklaring er, at datasættets ejer, utilsigtet eller bevidst, *ikke* har klassificeret feltet som et tal. Hvis et datasæt for eksempel har et felt med **år**, så kan datasættets ejer kategorisere det som tekst, fordi der er større sandsynlighed for, at feltet **år** bliver talt (dvs. antallet af personer født i 1974), og ikke at det bliver opsummeret eller gennemsnitsberegnet. Hvis du er ejeren, kan du åbne datasættet i Power BI Desktop og bruge fanen **Udformning** for at ændre datatypen.  

Sv: En anden mulighed er, at du har valgt at benytte feltet i et *interval*, der kun tillader kategoriværdier.  Hvis dette er tilfældet, så har du kun adgang til antal og distinkt antal.

Sv: En tredje mulighed er, at du bruger feltet for en akse. Eksempelvis på en akse i et søjlediagram – her vises én søjle i Power BI for hver distinkte værdi – her vises slet ikke aggregerede feltværdier. 

>[!NOTE]
>Undtagelsen for denne regel er punktdiagrammer, som *kræver* aggregerede værdier for X- og Y-akserne.


Sp: Jeg har et punktdiagram, og jeg vil *ikke* have, at mit felt aggregerer.  Hvordan gør jeg det?

Sv: Føj feltet til intervallet **Oplysninger** og ikke til intervallerne X- eller Y-akser.

Sp: Når jeg føjer et tekstfelt til en visualisering, så indstilles de fleste af dem automatisk til sum, men nogle indstilles automatisk til gennemsnit eller antal eller en anden aggregering.  Hvorfor er standardakkumuleringen ikke altid den samme?

Sv: Datasætejere har mulighed for at indstille standardopsummeringen for hvert felt. Hvis du er ejer af et datasæt, skal du ændre standardopsummeringen på fanen **Udformning** i Power BI Desktop.

Sp: Mit felt **er** numerisk, så hvorfor har jeg ikke aggregerede indstillinger på rullelisten?

Sv: Hvis feltet har et regnemaskineikon, er det et *beregnet mål*, og hvert beregnede mål har sin egen hard-coded formel, der ikke kan ændres i Power BI-tjenesten. Den benyttede beregning kan være en simpel aggregering som f.eks. et gennemsnit eller en sum, men det kan også være noget mere kompliceret som f.eks. en "procentdel af bidraget til forældrekategori" eller "løbende totalværdi siden årets begyndelse". I Power BI bliver der ikke opsummeret eller beregnet gennemsnit af resultaterne, men blot udført en genberegning (vha. den hard-coded formel) for hvert datapunkt.

Sp: Jeg er datasætejer, og jeg vil gerne sikre, at et felt aldrig bliver aggregeret.

Sv: I Power BI Desktop, på fanen **Uformning**, skal du indstille **Datatype** til **Tekst**.

Sp: Jeg kan ikke se **Opsummer ikke** på rullelisten.

Sv: Prøv at fjerne feltet og tilføje det igen.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

