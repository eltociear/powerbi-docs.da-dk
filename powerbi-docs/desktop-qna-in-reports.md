---
title: Brug af Spørgsmål og svar i Power BI Desktop
description: Du kan nu bruge et naturligt sprog til forespørgsler i Power BI Desktop ved hjælp af Spørgsmål og svar
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/05/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: a34de25af7febf63b34d7608ff7ef40e8b653fc4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61284818"
---
# <a name="use-qa-in-power-bi-desktop-for-natural-language-queries"></a>Brug Spørgsmål og svar i Power BI Desktop til forespørgsler på et naturligt sprog
Det er effektivt, når du bruger almindelige udtryk og naturligt sprog til dataforespørgsler. Endnu mere effektiv er det, når dataene svarer dig, hvilket Spørgsmål og svar i **Power BI Desktop** gør muligt for dig.

For at aktivere Spørgsmål og svar med henblik på at kunne fortolke den store samling af spørgsmål, som funktionen er i stand til at svare på, så skal Spørgsmål og svar opstille forudsætninger for modellen. Hvis strukturen i din model ikke opfylder en eller flere af disse forudsætninger, så er du nødt til at justere din model. De pågældende justeringer for Spørgsmål og svar er de samme bedste praksis-optimeringer for enhver model i Power BI, uanset om du bruger Spørgsmål og svar. 

> [!NOTE]
> Spørgsmål og svar er kun tilgængelig, når du arbejder med en model, der indeholder **importeret** data eller direkte forbindelser til SSAS. DirectQuery-modeller understøttes ikke.
>
> Spørgsmål og svar kræver følgende C runtime-opdatering, hvis du bruger en ældre version af Windows end Windows 10. Du kan prøve at installere vigtige opdateringer fra Windows Update eller installere den påkrævede komponent manuelt fra Microsoft (KB2999226). [https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)
>
>

I afsnittene nedenfor beskriver vi, hvordan du justerer din model, så den fungerer godt med Spørgsmål og svar i Power BI.

## <a name="add-missing-relationships"></a>Tilføj manglende relationer

Hvis der mangler relationer mellem tabeller i modellen, kan hverken Power BI-rapporter eller Spørgsmål og svar fortolke, hvordan disse tabeller skal forbindes, hvis du benytter forespørgsler med dem. Relationerne er hjørnestenen i en god model. Eksempelvis kan du ikke bede om "det samlede salg for kunder i Seattle", hvis relationen mellem tabellen *ordrer* og tabellen *kunder* mangler. Følgende billeder viser eksempler på en model, der skal forbedres, og en model, der er klar til Spørgsmål og svar.

**Skal forbedres**

![relationer, der skal forbedres mht. Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_01.png)

**Klar til Spørgsmål og svar**

![relationer, der virker mht. Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_02.png)


## <a name="rename-tables-and-columns"></a>Omdøb tabeller og kolonner

Valget af tabeller og kolonner er vigtigt for Spørgsmål og svar. Lad os f.eks. sige, at du har en tabel med navnet *Kundeoversigt*, som indeholder en liste over dine kunder. Du skal stille spørgsmål som "Angiv kundeoversigterne i Chicago på en liste" i stedet for "Angiv kunderne i Chicago på en liste". 

Selvom Spørgsmål og svar kan benytte basal orddeling og registrering af flertalsformer, så forudsætter Spørgsmål og svar, at dine tabel- og kolonnenavne præcist afspejler deres indhold.

Tænk over et andet eksempel. Forestil dig, at du har en tabel med navnet *Antallet af medarbejdere*, som indeholder for- og efternavne samt medarbejdernumre. Du har en anden tabel med navnet *Medarbejdere*, som indeholder medarbejdernumre, jobnumre og startdatoer. Personer, der er bekendt med modellen, vil sandsynligvis forstå denne struktur. Andre, som stiller spørgsmålet "Tæl medarbejdere", vil få vist antallet af rækker fra tabellen "Medarbejdere". Dette resultat er sandsynligvis ikke det, de havde tænkt sig, da det er en optælling af hvert eneste job, medarbejderne nogensinde har haft. Det vil være meget bedre at omdøbe disse tabeller, så de afspejler det, de indeholder, nøjagtigt.

**Skal forbedres**

![tabelnavne, der skal forbedres mht. Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_03.png)

**Klar til Spørgsmål og svar**

![tabelnavne, der virker mht. Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_04.png)

## <a name="fix-incorrect-data-types"></a>Ret forkerte datatyper

Importerede data kan have forkerte datatyper. Særligt kolonner med *dato* og *tal*, der importeres som *strenge*, vil ikke fortolkes som datoer og tal af Spørgsmål og svar. Sørg for at vælge den korrekte datatype i din Power BI-model.

![vælg den korrekte datatype for at sikre, at den er tilgængelig for Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_05.png)

## <a name="mark-year-and-identifier-columns-as-dont-summarize"></a>Angiv år- og id-kolonner som Opsummer ikke

Power BI aggregerer numeriske kolonner aggressivt som standard, så forespørgsler som "samlede salg pr. år" somme tider kan resultere i et samlet tal for salg sammen med et samlet tal for år. Hvis du har specifikke kolonner, hvor du ikke vil benytte denne funktionsmåde i Power BI, så skal du indstille egenskaben **Opsummer efter** på kolonnen til **Opsummer ikke**. Vær opmærksom på kolonnerne **år**, **måned**, **dag** og **id**, idet disse kolonner hyppigst er problematiske. Andre kolonner, der ikke er praktiske at opsummere, f.eks. *alder*, kan også drage fordel af, at **Opsummer efter** indstilles til **Opsummer ikke** eller til **Gennemsnit**. Du kan finde denne indstilling under fanen **Udformning**.

![Opsummer ikke kolonner som f.eks. år, måned, dato for Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_06.png)

## <a name="choose-a-data-category-for-each-date-and-geography-column"></a>Vælg en datakategori for hver dato- og geografikolonne

**Datakategori** giver yderligere semantisk viden om indholdet af en kolonne, der ligger ud over dens datatype. En heltalskolonne kan f.eks. være markeret som et postnummer, en strengkolonne kan være markeret som en by, et land, et område osv. Disse oplysninger bruges af Spørgsmål og svar på to vigtige måder: Til valg af visualisering og til sprogforskelle.

For det første bruger Spørgsmål og svar **Datakategori**-oplysninger til at hjælpe med at foretage valg af, hvilken type visuel visning, der skal bruges. Funktionen genkender for eksempel, at kolonner med **Datakategorierne** dato eller klokkeslæt typisk er et godt valg til den vandrette akse i et kurvediagram eller afspilningsaksen i et boblediagram. Og den forudsætter, at resultater med kolonner med geografiske **Datakategorier** kan se flotte ud på et kort.

For det andet kan Spørgsmål og svar give nogle kvalificerede gæt med hensyn til, hvordan brugere sandsynligvis taler om dato- og geografi-kolonner, for at hjælpe funktionen med at forstå visse typer af spørgsmål. For eksempel "hvornår" i "Hvornår blev John Smith ansat?" vil næsten med sikkerhed blive knyttet til en datokolonne, og "Brown" i "Antal kunder i Brown" er sandsynligvis en by og ikke en hårfarve.


![Vælg Datakategorier hensigtsmæssigt for Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_07.png)

## <a name="choose-a-sort-by-column-for-relevant-columns"></a>Vælg en "Sortér efter kolonne" for de relevante kolonner

Egenskaben **Sortér efter kolonne** tillader sortering efter én kolonne for automatisk at sortere efter en anden kolonne i stedet. Når du f.eks. benytter forespørgslen "sortér kunder efter skjortestørrelse", vil du sandsynligvis have, at din kolonne med Skjortestørrelser sorterer efter det underliggende størrelsesnummer (XS, S, M, L, XL) i stedet for alfabetisk (L, M, S, XL, XS).

![Vælg "Sortér efter kolonne" korrekt i forhold til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_08.png)

## <a name="normalize-your-model"></a>Normaliser din model

Bare rolig, vi foreslår ikke, at du skal redefinere hele din model. Visse strukturer er dog så svære, at Spørgsmål og svar ikke kan håndtere dem særligt godt. Hvis du udfører noget grundlæggende normalisering af strukturen af din model, øges Power BI-rapporternes brugbarhed væsentligt, hvilket også gælder Spørgsmål og svar-resultaternes nøjagtighed.

Følg denne generelle regel: Hver unikke "ting", som brugeren taler om, bør være repræsenteret af nøjagtigt ét modelobjekt (tabel eller kolonne). Så hvis dine brugere taler om kunder, bør der være ét *kunde*-objekt. Og hvis dine brugere taler om salg, bør der være ét *salg*-objekt. Det lyder enkelt, ikke? Det kan det også være, afhængigt af hvilken formatering dataene, du starter med, har. Der er rig mulighed for dataformatering i **Forespørgselseditoren**, hvis du får brug for det, mens mange af de mere enkle transformationer kan udføres ved blot at bruge beregninger i Power BI-modellen.

De følgende sektioner indeholder nogle gængse transformationer, som du kan få brug for at udføre.

### <a name="create-new-tables-for-multi-column-entities"></a>Opret nye tabeller for flerkolonneenheder

Hvis du har flere kolonner, der fungerer som en enkelt særskilt enhed i en større tabel, skal disse kolonner opdeles i deres egen tabel. Lad os f.eks. sige, at du har kolonnerne Navn på kontakt, Titel på kontakt og Telefonnummer i tabellen *Firmaer*. Et bedre design vil være at have en særskilt tabel med *Kontakter*, som indeholder Navn, Titel og Telefonnummer samt et link tilbage til tabellen *Firmaer*. Det gør det væsentligt lettere at stille spørgsmål om kontakter uafhængigt af spørgsmål om firmaer, som de fungerer som kontakt for, og det forbedrer fleksibiliteten af visningen.

**Skal forbedres**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_09.png)

**Klar til Spørgsmål og svar**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_10.png)

### <a name="pivot-to-eliminate-property-bags"></a>Pivotér for at eliminere egenskabsbeholdere

Hvis du har egenskabsbeholdere i modellen, skal de omstruktureres for at få en enkelt kolonne for hver egenskab. Egenskabsbeholdere kan være praktiske til administrering af et stort antal egenskaber, men har en række indlejrede begrænsninger, som hverken Power BI-rapporter eller Spørgsmål og svar er designet til at kunne omgå.

Lad os f.eks. antage, at vi har tabellen *Kundedemografi* med kolonnerne Kunde-id, Egenskab og Værdi, hvor hver række repræsenterer en særskilt egenskab hos kunden (f.eks. alder, civilstand, by osv.). Ved at overbelaste betydningen af kolonnen Værdi baseret på indholdet i kolonnen Egenskab bliver det umuligt for Spørgsmål og svar at fortolke de fleste forespørgsler, der refererer til den. En simpel forespørgsel som f.eks. "vis alderen for en kunde" vil muligvis fungere, siden den kan fortolkes som "vis kunderne og kundedemografier, hvor egenskaben er alder". Dog understøtter strukturen i modellen ikke lidt mere komplekse forespørgsler, som f.eks. "gennemsnitlig alder for kunder i Chicago." Mens brugere, som direkte udvikler Power BI-rapporter, somme tider kan finde smarte måder at hente de ønskede data på, så fungerer Spørgsmål og svar kun, når hver kolonne kun har én enkelt betydning.

**Skal forbedres**

![brug ikke egenskabsbeholdere i modeller til spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_11.png)

**Klar til Spørgsmål og svar**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_12.png)

### <a name="union-to-eliminate-partitioning"></a>Benyt samling for at fjerne partitionering

Hvis du har partitioneret dine data på tværs af flere tabeller, eller du har pivoteret værdier på tværs af flere kolonner, bliver det svært eller umuligt for brugerne at benytte visse almindelige handlinger. Overvej først en typisk tabelpartitionering: en tabel med *Salg 2000-2010* og en tabel med *Salg 2011-2020*. Hvis alle dine vigtige rapporter er begrænset til et specifikt årti, så kan du nok lade det være på denne måde for Power BI-rapporter. Dog vil fleksibiliteten i Spørgsmål og svar føre til, at brugerne forventer svar på forespørgsler som f.eks. "samlet salg pr. år." Hvis denne forespørgsel skal fungere, skal du samle dataene i en enkelt Power BI-modeltabel.

Overvej desuden en typisk pivoteret værdikolonne: en tabel over en *Bogturné*, der indeholder kolonnerne Forfatter, Bog, By 1, By 2 og By 3. Denne struktur gør, at selv simple forespørgsler som f.eks. "antal bøger efter by", ikke kan fortolkes korrekt. Hvis denne forespørgsel skal fungere, skal du oprette en separat tabel med navnet *BogturnéByer*, som samler værdierne for by i en enkelt kolonne.

**Skal forbedres**

![brug ikke egenskabsbeholdere i modeller til spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_13.png)

**Klar til Spørgsmål og svar**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_14.png)

### <a name="split-formatted-columns"></a>Opdel formaterede kolonner

Hvis kilden, hvorfra du importerer dine data, indeholder formaterede kolonner, vil Power BI-rapporter (og Spørgsmål og svar) ikke række ind i kolonnen for at opdele dens indhold. Hvis du f.eks. har en kolonne med **Fuld adresse**, der indeholder adresse, by og land, bør du opdele den i kolonnerne Adresse, By og Land, så brugerne kan oprette forespørgsler til dem hver for sig.

**Skal forbedres**

![brug ikke enkeltkolonner for flere dataelementer til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_15.png)

**Klar til Spørgsmål og svar**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_16.png)

Hvis du på samme måde har en "fulde navn"-kolonne for en person, så bør du tilføje kolonnerne **Fornavn** og **Efternavn** i det tilfælde, at nogen vil oprette forespørgsler ved hjælp af delvise navne. 


### <a name="create-new-tables-for-multi-value-columns"></a>Opret nye tabeller for flerværdikolonner

En lignende situation forekommer, hvis kilden, hvorfra du importerer dataene, indeholder flerværdikolonner, så rækker Power BI-rapporter (og Spørgsmål og svar) ikke ind i kolonnen for at opdele dens indhold. Så hvis du f.eks. har en Komponist-kolonne, der indeholder navnene på flere komponister til en sang, bør du opdele den i flere rækker i en særskilt tabel over *Komponister*.

**Skal forbedres**

![brug ikke flerværdikolonner til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_17.png)

**Klar til Spørgsmål og svar**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_18.png)

### <a name="denormalize-to-eliminate-inactive-relationships"></a>Benyt denormalisering for at fjerne inaktive relationer

Den eneste undtagelse for reglen "normalisering er bedre" opstår, når der er flere stier til og fra én tabel til en anden. Lad os f.eks. sige, at du har en tabel med *Flyafgange* med kolonnerne KildeById og DestinationsById, som hver især er relateret til tabellen *Byer*. En én af disse skal relationer markeres som inaktiv. Idet Spørgsmål og svar kun kan bruge aktive relationer, kan du ikke stille spørgsmål om enten kilde eller destination, afhængigt af hvilken kolonne du vælger. Hvis du i stedet benytter denormalisering af kolonnerne med bynavn i tabellen *Flyafgange*, kan du stille spørgsmål som: "Angiv flyafgange i morgen med Seattle som kildeby og San Francisco som destinationsby på en liste".

**Skal forbedres**

![kun én vej for hver tabel til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_19.png)

**Klar til Spørgsmål og svar**

![brug flere tabeller til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_20.png)

### <a name="add-synonyms-to-tables-and-columns"></a>Føj synonymer til tabeller og kolonner

Dette trin gælder specielt for Spørgsmål og svar (og ikke for Power BI-rapporter generelt). Brugere har ofte en række ord, som de bruger til at henvise til det samme, som f.eks. samlet salg, nettosalg, samlet nettosalg. Power BI-modellen giver mulighed for, at disse synonymer kan føjes til tabeller og kolonner inden for modellen. 

Dette trin kan være vigtigt. Selv med helt enkle tabel- og kolonnenavne så benytter brugere af Spørgsmål og svar sig af forespørgsler med nogle ord, der lige falder dem ind, og vælger ikke ordene på en foruddefineret liste over kolonner. Jo mere fornuftige synonymer, du kan tilføje, jo bedre er brugernes oplevelse med din rapport. Hvis du vil tilføje synonymer, skal du vælge knappen Synonymer på båndet i visningen **Relationer**, som vist på følgende billede.

![Føj synonymer til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_21.png)

Feltet **Synonymer** vises i højre side af **Power BI Desktop**, hvor du kan tilføje dine synonymer, som vist på følgende billede.

![Føj synonymer til Spørgsmål og svar](media/desktop-qna-in-reports/desktop-qna_22.png)

 Vær forsigtig, når du tilføjer synonymer, for hvis du tilføjer det samme synonym til flere end én kolonne eller tabel, så vil det medføre flertydighed. Spørgsmål og svar anvender kontekst, hvor det er muligt at vælge mellem flertydige synonymer, men ikke alle forespørgsler har tilstrækkelig kontekst. Når en bruger f.eks. benytter forespørgslen "tæl kunderne", og du har tre ting med synonymet "kunde" i din model, så får vedkommende nok ikke det ønskede svar. I disse tilfælde skal du sørge for, at det primære synonym er entydigt, for det er det, der bruges i tilpasningen. Det kan gøre brugeren opmærksom på flertydigheden (f.eks. en tilpasning af "vis antallet af arkiverede kundejournaler") og give vedkommende et praj om, at forespørgslen måske bør ændres.


## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om de funktioner, der findes i Power BI Desktop, i følgende artikler:

* [Brug detaljeadgang i Power BI Desktop](desktop-drillthrough.md)
* [Vis et dashboardfelt eller en rapport i fokustilstand](consumer/end-user-focus.md)

