---
title: Arbejde med aggregeringer (sum, gennemsnit osv.) i Power BI-tjenesten
description: Lær, hvordan du ændrer aggregeringen i et diagram (sum, gennemsnit, maksimum og osv.) i Power BI-tjenesten.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/03/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Reports
ms.openlocfilehash: 7cee05df6a7d13e18bc31bc1a1f34a5f89711c0d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710573"
---
# <a name="work-with-aggregates-sum-average-and-so-on-in-the-power-bi-service"></a>Arbejde med aggregeringer (sum, gennemsnit osv.) i Power BI-tjenesten

## <a name="what-is-an-aggregate"></a>Hvad er en aggregering?

Du kan sommetider få brug for matematisk at kombinere værdier i dine data. Den matematiske handling kan være sum, gennemsnit, maksimum, antal og osv. Når du kombinerer værdier i dine data, kaldes det *aggregering*. Resultatet af den matematiske handling er en *aggregering*.

Når Power BI-tjenesten og Power BI Desktop opretter visualiseringer, aggregerer de muligvis dine data. Ofte er aggregeringen lige hvad du har brug for, men andre gange vil du måske aggregere værdierne på en anden måde.  F.eks. en sum i forhold til et gennemsnit. Der er flere forskellige måder at administrere og ændre den aggregering, der bruges i en visualisering i Power BI.

Først, Lad os se nærmere på data *typer* fordi datatypen bestemmer, hvordan og om, Power BI kan aggregere.

## <a name="types-of-data"></a>Datatyper

De fleste datasæt har mere end én type data. På det mest grundlæggende serviceniveau, at dataene er numeriske, eller den er ikke. Powerbi kan samle numeriske data ved hjælp af en sum, gennemsnit, antal, minimum, VARIANS og meget mere. Tjenesten kan også aggregere tekstdata, ofte kaldet *kategoriske* data. Hvis du prøver at aggregere et kategorisk felt ved at placere det i et udelukkende numerisk interval, som **værdier** eller **værktøjstip**, Power BI tælle forekomsterne af hver kategori eller tælle de særskilte forekomster af hver kategori. Særlige typer data, som datoer, har nogle af deres egne aggregerede indstillinger: tidligste, seneste, første og sidste.

I eksemplet nedenfor:

- **Solgte enheder** og **Produktionspris** er kolonner, der indeholder numeriske data

- **Segment**, **Land**, **Produkt**, **Måned** og **Månedsnavn** indeholder kategoriske data

   ![Skærmbillede af et eksempel på datasæt.](media/service-aggregates/power-bi-aggregate-chart.png)

Når du opretter en visualisering i Power BI, samler tjenesten numeriske felter (standarden er *sum*) over nogle kategorifelter.  For eksempel "solgte enheder ***efter produkt***", "solgte enheder ***efter måned***" og "produktionspris ***efter Segment***". Powerbi, der refererer til nogle numeriske felter som **målinger**. Det er nemt at identificere mål i Power BI-rapporteditoren – den **felter** vises mål med ∑-symbolet ud for dem på listen. Se [rapporteditoren... Tag en rundvisning](service-the-report-editor-take-a-tour.md) for at få flere oplysninger.

![Skærmbillede af Power BI med listen felter kaldes.](media/service-aggregates/power-bi-aggregate-fields.png)

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Hvorfor fungerer aggregeringer ikke, som jeg vil have dem til?

Arbejdet med aggregeringer i Power BI kan være forvirrende. Måske har du et numerisk felt, og Power BI vil ikke lade dig ændre aggregeringen. Eller måske har du et felt, som f.eks. et år, som du ikke vil aggregere, men kun vil tælle antallet af forekomster af.

Det underliggende problem er normalt feltdefinitionen i datasættet. Måske datasættets ejer defineret feltet som tekst og, der forklarer, hvorfor Power BI kan ikke opsummeret eller Gennemsnitlig størrelse på den. Desværre [kan kun datasættets ejer ændre måden, hvorpå et felt er kategoriseret](desktop-measures.md). Så hvis du har ejertilladelser til datasættet, enten i Desktop eller det program, der bruges til at oprette datasættet (f.eks, Excel), kan du løse dette problem. Ellers skal du kontakte ejeren af datasættet for at få hjælp.  

Der er særlige afsnit sidst i denne artikel kaldet [ **overvejelser og fejlfinding**](#considerations-and-troubleshooting). Det giver tip og vejledning. Hvis du ikke kan finde løsningen her, kan du stille dit spørgsmål i den [Power BI-communityforummet](http://community.powerbi.com). Du får et hurtigt svar direkte fra Power BI-teamet.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Tilpas måden, hvorpå et numerisk felt aggregeres

Lad os antage, at du har et diagram, der sammenlægger solgte enheder for forskellige produkter, men du hellere vil beregne gennemsnittet.

1. Opret en **grupperet søjlediagram** , der bruger en måling og en kategori. I dette eksempel bruger vi Solgte enheder efter Produkt.  Power BI opretter som standard et diagram, der sammenlægger solgte enheder (træk målingen i den **værdi** godt) for hvert produkt (træk kategorien til den **akse** godt).

   ![Skærmbillede af diagrammet, ruden visualiseringer og listen felter med Sum påpeges.](media/service-aggregates/power-bi-aggregate-sum.png)

1. I den **visualiseringer** ruden, skal du højreklikke på målingen, og vælg den aggregeringstype, du har brug for. I dette tilfælde vælger vi **gennemsnitlige**. Hvis du ikke ser aggregeringen skal du se de [ **overvejelser og fejlfinding** ](#considerations-and-troubleshooting) afsnit.

   ![Skærmbillede af den samlede liste med gennemsnit valgt og påpeges.](media/service-aggregates/power-bi-aggregate-average.png)

   > [!NOTE]
   > De tilgængelige indstillinger i den rullelisten varierer afhængigt af 1) det valgte felt og 2) måde, at datasættets ejer kategoriseret på dette felt.

1. Din visualisering bruger nu aggregeret efter gennemsnit.

   ![Skærmbillede af diagrammet nu vise gennemsnit af solgte enheder efter produkt.](media/service-aggregates/power-bi-aggregate-average-2.png)

## <a name="ways-to-aggregate-your-data"></a>Metoder til at aggregere dine data

Nedenfor følger nogen af indstillingerne, der kan være tilgængelige ved aggregering af et felt:

- **Opsummer ikke**. Med denne indstilling, der er valgt, Power BI behandler hver værdi i dette felt separat, og Opsummer ikke dem. Brug denne indstilling, hvis du har en numerisk ID-kolonne, der ikke skal lægges til tjenesten.

- **Sum**. Lægger alle værdier i feltet sammen.

- **Gennemsnit**. Beregner et matematisk gennemsnit af værdierne.

- **Minimum**. Viser den mindste værdi.

- **Maksimum**. Viser den største værdi.

- **Antal (ikke tomme)** . Tæller antallet af værdier i feltet, der ikke er tom.

- **Antal (distinkt).** Tæller antallet af forskellige værdier i det pågældende felt.

- **Standardafvigelse.**

- **Varians**.

- **Median**.  Viser median (middel)-værdien. Denne værdi har det samme antal elementer over og under.  Hvis der er to medianer, beregner Power BI gennemsnittet af dem.

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

- **Opsummer ikke**: Hver enkelt værdi vises særskilt

- **Sum**: 750

- **Gennemsnit**: 125

- **Maksimum**:  150

- **Minimum**: 100

- **Antal (ikke tomme):** 6

- **Antal (specifikt):** 4

- **Standardafvigelse:** 20.4124145...

- **Afvigelse:** 416.666...

- **Median:** 125

## <a name="create-an-aggregate-using-a-category-text-field"></a>Opret en aggregering ved hjælp af et kategorifelt (tekstfelt)

Du kan også aggregere et felt, der ikke er et numerisk felt. Hvis du f.eks. har et felt med produktnavn, kan du tilføje det som en værdi og derefter indstille det til **Antal** **Adskilt antal**, **Første** eller **Sidste**.

1. Træk det **produkt** feltet i den **værdier** godt. Den **værdier** værdibrønden bruges typisk til numeriske felter. Powerbi genkender, at dette felt er et tekstfelt, angiver aggregeringen til **Opsummer ikke**, og giver dig en tabel med én kolonne.

   ![Skærmbillede af feltet produkt i de værdier, der er godt.](media/service-aggregates/power-bi-aggregate-value.png)

1. Hvis du ændrer aggregeringen fra standarden **Opsummer ikke** til **antal (distinkt)** , tæller Power BI antallet af forskellige produkter. I dette tilfælde, er der fire.
  
   ![Skærmbillede af adskilte antallet af produkter.](media/service-aggregates/power-bi-aggregate-count.png)

1. Hvis du desuden ændrer aggregeringen til **Antal**, så tælles det samlede antal i Power BI. I dette tilfælde er der 7 poster for **produkt**.

   ![Skærmbillede af antallet af produkter.](media/service-aggregates/power-bi-aggregate-count-2.png)

1. Ved at trække det samme felt (i dette tilfælde **produkt**) i den **værdier** værdibrønden og lade standardsammenlægningen **Opsummer ikke**, Power BI opdeler antallet af produkt.

   ![Skærmbillede af produktet og antallet af produkter.](media/service-aggregates/power-bi-aggregate-final.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

Spørgsmål:  Hvorfor har jeg ikke en indstilling for **Opsummer ikke**?

Svar:  Det felt, du har valgt, er sandsynligvis et beregnet mål eller avanceret mål, der er oprettet i Excel eller [Power BI Desktop](desktop-measures.md). Hvert beregnede mål har sin egen hard-coded formel. Du kan ikke ændre den aggregering, der bruger Power BI. F.eks, hvis det er en sum, kan den kun være en sum. Den **felter** vises på listen over *beregnede målinger* med lommeregnersymbolet.

Spørgsmål:  Mit felt **er** numerisk, så hvorfor kan jeg kun vælge **Antal** og **Distinkt antal**?

Svar 1:  Den sandsynlige forklaring er, at datasættets ejer har *ikke* klassificeret feltet som et tal. Hvis et datasæt har f.eks. en **år** feltet datasættets ejer kategorisere værdien, som tekst. Der er større sandsynlighed for, at Power BI, tælles den **år** felt (f.eks, antallet af personer født i 1974). Det er mindre sandsynligt, at Power BI bliver opsummeret eller Gennemsnitlig størrelse på den. Hvis du ejer, du kan åbne datasættet i Power BI Desktop og bruge den **udformning** fane for at ændre datatypen.

Svar 2: Hvis feltet har et lommeregnerikon, det betyder, at det er en *beregnet måling*. Hvert beregnede mål har sin egen hard-coded formel, som kan ændre kun ejeren af datasættet. Den beregning, der bruger Power BI kan være en simpel aggregering som f.eks. et gennemsnit eller en sum. Det kan også være noget mere kompliceret som en "procentdel af bidraget til forældrekategori" eller "løbende totalværdi siden årets begyndelse". Powerbi vil ikke opsummeret eller beregnet gennemsnit af resultaterne. I stedet for genberegne det blot (ved hjælp af den hard-coded formel) for hvert datapunkt.

Svar 3:  En anden mulighed er, at du har valgt at benytte feltet i en *bucket*, der kun tillader kategoriværdier.  Hvis dette er tilfældet, så har du kun adgang til antal og distinkt antal.

Svar 4:  Og en fjerde mulighed er, at du bruger feltet for en akse. Eksempelvis på en akse i et søjlediagram – her vises én søjle i Power BI for hver distinkte værdi – her vises slet ikke aggregerede feltværdier.

>[!NOTE]
>Undtagelsen for denne regel er punktdiagrammer, som *kræver* aggregerede værdier for X- og Y-akserne.

Spørgsmål:  Hvorfor kan jeg kan ikke aggregere tekstfelter til SSAS-datakilder (SQL Server Analysis Services)?

Svar:  Dynamiske forbindelser til flerdimensionelle SSAS-modeller tillader ikke en hvilken som helst aggregering på klientsiden, herunder først, sidst, gennemsnit, min., maks. og sum.

Spørgsmål:  Jeg har et punktdiagram, og jeg vil *ikke* have, at mit felt foretager sammenlægninger.  Hvordan?

Svar:  Føj feltet til din bucket af typen **Oplysninger** og ikke til dine buckets af typen X- eller Y-akser.

Spørgsmål:  Når jeg føjer et tekstfelt til en visualisering, så indstilles de fleste af dem automatisk til sum, men nogle indstilles automatisk til gennemsnit eller antal eller en anden sammenlægning.  Hvorfor er standardakkumuleringen ikke altid den samme?

Svar:  Datasætejere kan indstille standardopsummeringen for hvert felt. Hvis du er ejer af et datasæt, skal du ændre standardopsummeringen på den **udformning** fanen af Power BI Desktop.

Spørgsmål:  Jeg er datasætejer, og jeg vil gerne sikre, at et felt aldrig sammenlægges.

Svar:  På fanen **Uformning** i Power BI Desktop skal du angive **Datatype** til **Tekst**.

Spørgsmål:  Jeg kan ikke se **Opsummer ikke** som en indstilling på min rulleliste.

Svar:  Prøv at fjerne feltet og tilføje det igen.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)