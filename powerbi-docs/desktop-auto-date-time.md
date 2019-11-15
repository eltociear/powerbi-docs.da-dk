---
title: Automatisk dato/klokkeslæt i Power BI Desktop
description: Forstå funktionen til automatisk dato/klokkeslæt i Power BI Desktop.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/23/2019
ms.author: v-pemyer
ms.openlocfilehash: 7453854376923fbb55376182a8674e5f3d7d1b63
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878791"
---
# <a name="auto-datetime-in-power-bi-desktop"></a>Automatisk dato/klokkeslæt i Power BI Desktop

Denne artikel henvender sig til dataudviklere af importmodeller og sammensatte modeller i Power BI Desktop.

## <a name="background"></a>Baggrund

_Automatisk dato/klokkeslæt_ er en indstilling for dataindlæsning i Power BI Desktop. Formålet med denne indstilling er at understøtte praktisk time intelligence-rapportering, der er baseret på datokolonner, som er indlæst i en model. Det giver især forfattere af rapporter mulighed for at filtrere, gruppere og foretage detailudledning ved hjælp af kalenderens tidsperioder uden at kræve, at udvikleren eksplicit har udviklet dem. Kalenderens tidsperioder omfatter år, kvartaler, måneder og dage.

Når indstillingen er aktiveret, opretter Power BI Desktop en skjult tabel for automatisk dato/klokkeslæt for de enkelte datokolonner, forudsat at følgende forhold er til stede:

- Tabellens lagringstilstand er Import
- Kolonnens datatype er dato eller dato/klokkeslæt
- Kolonnen er ikke "mange"-siden i en modelrelation

## <a name="how-it-works"></a>Sådan fungerer det

Alle tabeller med automatisk dato/klokkeslæt er i realiteten en [beregnet tabel](desktop-calculated-tables.md), der genererer rækker med data ved hjælp af DAX-funktionen [CALENDAR](/dax/calendar-function-dax). De enkelte tabeller omfatter også seks beregnede kolonner: **Day**, **MonthNo**, **Month**, **QuarterNo**, **Quarter** og **Year**.

> [!NOTE]
> Kolonnenavnene og værdierne oversættes og formateres i henhold til [modelsproget](supported-languages-countries-regions.md#choose-the-language-for-the-model-in-power-bi-desktop).

Der oprettes også en relation mellem kolonnen **Dato** i tabellen med automatisk dato/klokkeslæt og kolonnen med modeldatoen.

Tabellen med automatisk dato/klokkeslæt indlæses med hele kalenderår, som omfatter alle datoværdier, der er gemt i kolonnen med modeldatoen. Hvis den tidligste værdi i en datokolonne f.eks. er 20. marts 2016, og den seneste værdi er 23. oktober 2019, indeholder tabellen 1.461 rækker. Det repræsenterer én række for hver dato i de fire kalenderår 2016 til 2019. Når modellen opdateres, opdateres alle tabeller med automatisk dato/klokkeslæt også for at sikre, at de altid indeholder datoer, der omfatter datokolonnernes værdier.

Hvis det var muligt at se rækkerne i en tabel med automatisk dato/klokkeslæt, ville de muligvis se sådan ud:

![Eksempel på, hvordan rækker i en tabel med automatisk dato/klokkeslæt kan se ud. Viser syv kolonner: Date, Day, MonthNo, Month, QuarterNo, Quarter og Year. Viser 10 rækker med data, der beskriver datoer fra den 1. januar 2019 til den 10. januar 2019.](media/desktop-auto-date-time/auto-date-time-hidden-table-example-rows.png)

> [!NOTE]
> Tabellerne med automatisk dato/klokkeslæt er skjult permanent, også for udviklere. De kan ikke ses i ruden **Felter** eller i diagramvisningen for modellen, og rækkerne kan ikke ses i datavisning. Desuden kan der ikke refereres direkte til tabellen og den tilhørende kolonne fra DAX-udtryk.

Tabellen definerer også et hierarki, der giver visuelle elementer med en detailudledningssti, der går fra niveauerne for år, kvartal, måned og dag.

Hvis det var muligt at se en tabel med automatisk dato/klokkeslæt i diagramvisning for modellen, ville den muligvis se sådan ud (relaterede kolonner er fremhævet):

![Eksempel på, hvordan en skjult tabel med automatisk dato/klokkeslæt kan se ud. Viser to tabeller: Tabellen Sales og LocalDateTime. Tabellerne er relateret på baggrund af kolonnen OrderDate i tabellen Sales og kolonnen Date i tabellen LocalDateTime. LocalDateTime definerer syv kolonner: Date, Day, Month, MonthNo, Quarter, QuarterNo, Year og et enkelt hierarki. Hierarkiet hedder Datohierarki og består af fire niveauer: Year, Quarter, Month og Day.](media/desktop-auto-date-time/auto-date-time-hidden-table-example-diagram.png)

## <a name="work-with-auto-datetime"></a>Arbejd med automatisk dato/klokkeslæt

Når der findes en tabel med automatisk dato/klokkeslæt for en datokolonne (og den pågældende kolonne er synlig), kan rapportens forfattere ikke se kolonnen som et felt i ruden **Felter**. De finder i stedet et objekt, der kan udvides, som har samme navn som datokolonnen. Du kan let finde den, da den er angivet med et kalenderikon. Når forfatterne af rapporten udvider kalenderobjektet, finder de et hierarki med navnet **Datohierarki**. Når hierarkiet er udvidet, finder de fire niveauer: **Year**, **Quarter**, **Month** og **Day**.

![Eksempel på ruden Felter, hvor tabellen Sales er udvidet og åben. Den indeholder et felt af typen OrderDate, der er angivet med kalenderikonet. Den er udvidet og åben og indeholder et hierarki med navnet Datohierarki. Det er også udvidet og indeholder fire niveauer: Year, Quarter, Month og Day.](media/desktop-auto-date-time/auto-date-time-fields-pane-example.png)

Det oprettede hierarki til automatisk dato/klokkeslæt kan bruges til at konfigurere en visualisering på præcis samme måde, som almindelige hierarkier kan bruges. Du kan enten konfigurere visualiseringer ved at bruge hele hierarkiet **Datohierarki** eller specifikke niveauer i hierarkiet.

Der er dog tilføjet én funktion, der ikke understøttes af almindelige hierarkier. Når hierarkiet for automatisk dato/klokkeslæt – eller et niveau fra hierarkiet – føjes til et visuelt element, kan rapportens forfatter skifte mellem at bruge hierarkiet eller datokolonnen. Denne fremgangsmåde giver mening for nogle visuelle elementer, når det eneste, du har brug for, er datokolonnen, ikke hierarkiet og dets niveauer. Du starter med at konfigurere feltet for det visuelle element (højreklik på feltet for det visuelle element, eller klik på pil ned), og brug derefter genvejsmenuen til at skifte mellem datokolonnen og datohierarkiet.

![Eksempel på konfiguration af et felt for et visuelt element til hierarkiet OrderDate. I genvejsmenuen Åbn vises to indstillinger, der gør det muligt at skifte mellem brugen af kolonnen OrderDate og datohierarkiet.](media/desktop-auto-date-time/auto-date-time-configure-visuals-fields.png)

Endelig kan modelberegninger, der skrives i DAX, direkte referere til en datokolonne eller indirekte til de skjulte tabelkolonner med automatisk dato/klokkeslæt.

En formel, der er skrevet i Power BI Desktop, kan referere til en datokolonne på normal vis. Der skal dog refereres til tabelkolonnerne med automatisk dato/klokkeslæt ved hjælp af en særlig udvidet syntaks. Du starter med først at referere til datokolonnen, som dernæst skal efterfølges af et punktum (.). Via automatisk fuldførelse af formellinjen kan du derefter vælge en kolonne fra tabellen med automatisk dato/klokkeslæt.

![Eksempel på indtastning af et DAX-målingsudtryk i formellinjen. Indtil videre står der Date Count = COUNT(Sales[OrderDate] i formlen. og en liste med automatisk fuldførelse præsenterer alle syv kolonner fra den skjulte tabel med automatisk dato/klokkeslæt. Disse kolonner er: Date, Day, Month, MonthNo, Quarter, QuarterNo og Year.](media/desktop-auto-date-time/auto-date-time-dax-auto-complete.png)

I Power BI Desktop kan et gyldigt målingsudtryk være:

```dax
Date Count = COUNT(Sales[OrderDate].[Date])
```

> [!NOTE]
> Dette målingsudtryk er gyldigt i Power BI Desktop, men det er ikke den korrekte DAX-syntaks. Internt omdanner Power BI Desktop dit udtryk til at henvise til den sande (skjulte) tabelkolonne med automatisk dato/klokkeslæt.

## <a name="configure-auto-datetime-option"></a>Konfigurer indstillingen for automatisk dato/klokkeslæt

Automatisk dato/klokkeslæt kan konfigureres _globalt_ eller for den _aktuelle fil_. Indstillingen Global gælder for nye Power BI Desktop-filer, og den kan til enhver tid slås til eller fra. Hvis du har en ny installation af Power BI Desktop, er begge indstillinger som standard slået til.

Indstillingen Aktuel fil kan også når som helst slås til eller fra. Når indstillingen er slået til, oprettes der tabeller med automatisk dato/klokkeslæt. Når indstillingen er slået fra, fjernes alle tabeller med automatisk dato/klokkeslæt fra modellen.

> [!CAUTION]
> Vær forsigtig, når du slår indstillingen Aktuel fil fra, da det vil fjerne tabellerne med automatisk dato/klokkeslæt. Sørg for at løse eventuelle problemer med brudte rapportfiltre eller visuelle elementer, der er konfigureret til at bruge dem.

I Power BI Desktop skal du vælge _Filer > Indstillinger > Indstillinger_ og derefter enten vælge siden **Global** eller **Aktuel fil**. På begge sider findes indstillingen i sektionen **Time Intelligence**.

![Konfiguration af indstillinger i Power BI Desktop. Siden Dataindlæsning fra gruppen GLOBAL er valgt. Indstillingen Automatisk dato/klokkeslæt for nye filer er markeret i sektionen Time intelligence.](media/desktop-auto-date-time/auto-date-time-configure-global-options.png)

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om automatisk dato/klokkeslæt og relaterede emner i følgende ressourcer:

- [Angiv og brug datotabeller i Power BI Desktop](desktop-date-tables.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
