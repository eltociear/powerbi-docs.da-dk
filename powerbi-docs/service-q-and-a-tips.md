---
title: "Tip og tricks til at stille spørgsmål med Spørgsmål og svar i Power BI"
description: "Tip og tricks til at stille spørgsmål med Spørgsmål og svar i Power BI"
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
ms.date: 01/18/2018
ms.author: jastru
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: bdf1f161e0a95bda5b37d9c43a3bdcc6bde1066a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Tip til at stille spørgsmål med Spørgsmål og svar i Power BI
## <a name="words-and-terminology-that-qa-recognizes"></a>Ord og terminologi, som Spørgsmål og svar genkender
Denne liste over nøgleord er ikke udtømmende.  Den bedste måde at se, om Power BI genkender et nøgleord, er ved at prøve at indtaste det i spørgsmålsfeltet.  Hvis ordet eller udtrykket er nedtonet, genkender Power BI det ikke eller kan ikke genkende det i den aktuelle kontekst.

Listen nedenfor bruger nutid, men alle tider genkendes i de fleste tilfælde. For eksempel omfatter "er" var, vil være, have, har, havde, vil have, har fået, gøre, gør, gjorde.  Og "sortér" omfatter sorteret og sortering.  Desuden genkender Power BI og medtager entals- og flertalsformer af et ord. Power BI genkender f.eks. "måned" og "måneder".

> [!NOTE]
> Spørgsmål og svar er også tilgængelig i [Microsoft Power BI-appen til iOS på iPads, iPhones og iPod Touch-enheder](mobile-apps-ios-qna.md).
> 
> 

Hvis du ejer et datasæt, kan du tilføje vendinger og synonymer for at forbedre resultaterne af spørgsmål og svar for dine kunder.

**Aggregeringer**: total, sum, beløb, tal, mængde, antal, gennemsnit, mest, mindst, færrest, størst, højest, maksimum, max, lavest, minimum, min

**Artikler**: en, et, den, det

**Tom og boolesk**: blank, tom, null, indledes med "ikke" eller "ikke-", tom streng, tom tekst, sand, falsk

**Sammenligninger**: vs., versus, sammenlignet med, sammenlignes med

**Bindeord**: og, eller, hver af, med, versus, &, og, men, hverken, sammen med, ud over

**Sammentrækninger**: Spørgsmål og svar genkender næsten alle sammentrækninger, prøv selv.  Her er nogle eksempler på engelsk: didn’t, haven’t, he’d, he’s, isn’t, it’s, she’ll, they’d, weren’t, where’ll, who’s, won’t, wouldn’t.

**Datoer**: Power BI genkender de fleste datobegreber (dag, uge, måned, år, kvartal, årti osv.) og datoer, der er skrevet i mange forskellige formater (se nedenfor). Power BI genkender også følgende nøgleord: MånedNavn, dage 1-31, årti.

Eksempler: 3. januar 1995, jan 03 1995, 3 jan 1995, den 3. januar 1995, 1995 januar, 1995-01, 01/1995, navne på måneder.

**Relative datoer**: i dag, lige nu, aktuelt klokkeslæt, i går, i morgen, dags dato, næste, den kommende, sidst, tidligere, siden, før nu, tidligere end, efter, senere end, fra, på, fra nu, efter nu, i fremtiden, fortid, forrige, inden for, over, N dage siden, N dage fra nu, næste, en gang, to gange.

Eksempel: antallet af ordrer i løbet af de sidste 6 dage.

**Lighed (interval)**: i, er lig med, =, efter, er større end, i, mellem, før

Eksempler: Ordreår er før 2012? Pris lig med mellem 10 og 20? Er Johns alder større end 40? Samlet salg i 200-300?

**Lighed (værdi)**: er, lig med, i, af, for, inden for, er i, er på

Eksempler: Hvilke produkter er grønne? Ordredato lig med 2012. Er Johns alder 40? Samlet salg, der ikke er lig med 200? Ordredato den 1/1/2016. 10 i pris? Grøn som farve? 10 i pris?

**Navne**: Hvis en kolonne i datasættet indeholder udtrykket "navn" (f.eks. Medarbejdernavn), forstår Spørgsmål og svar, at værdierne i den pågældende kolonne er navne, og du kan stille spørgsmål som "hvilke medarbejdere hedder peter".

**Stedord**: han, ham, hans, hun, sig selv, hende, hendes, den, det, de, deres, dem selv, dette, disse

**Forespørgselskommandoer**: sorteret, sorter efter, retning, grupper, grupper efter, efter, vis, få vist, giv mig, kun, blot, arranger, ranger, sammenlign, til, med, i forhold til, alfabetisk, stigende, faldende, rækkefølge

**Område**: større, mere, over, >, mindre, færre, under, <,  mindst, ikke mindre end, >=, højst, ikke mere end, <=, i, mellem, i området, fra, senere, tidligere, efter, på, ved, senere end, siden, starter med, starter fra, slutter med

**Tider**: am, pm, klokken, eftermiddag, midnat, time, minut, sekund, tt:mm:ss

Eksempler: 10 pm, 10:35 pm, 10:35:15 pm, klokken 10, eftermiddag, midnat, time, minut, sekund.

**Top N** (sortering, rangering): top, bund, højeste, laveste, første, sidste, næste, tidligste, nyeste, ældste, seneste

**Visuelle typer**: alle visuelle typer, der er indbygget i Power BI.  Hvis det er en indstilling i ruden med visuelle effekter, kan du medtage den i dit spørgsmål.  Undtagelsen herfra er [brugerdefinerede visuelle elementer](power-bi-custom-visuals.md), som du manuelt har føjet til ruden med visuelle effekter.

Eksempel: vis distrikter efter måned og samlet salg som søjlediagram

**Hv (relation, kvalificeret)**: hvornår, hvor, hvilken, hvem, hvor mange, hvor meget, hvor ofte, hvor mange gange, antal, tal, mængde, hvor længe, hvad

## <a name="qa-helps-you-phrase-the-question"></a>Spørgsmål og svar hjælper dig med at stille spørgsmålet
Spørgsmål og svar gør sit bedste for at sikre, at svaret præcist afspejler det spørgsmål, der er blevet stillet. Det sker på flere måder. For alle disse kan du acceptere handlingen fuldt ud, delvist eller slet ikke. Mens du skriver dit spørgsmål, gør Spørgsmål og svar følgende:

* fuldfører automatisk ord og spørgsmål. Der bruges forskellige strategier, herunder automatisk fuldførelse af ord, som genkendes, populære spørgsmål for de underliggende projektmapper og tidligere anvendte spørgsmål, der returnerede gyldige svar. Hvis der er mere end én indstilling til automatisk fuldførelse, vises de på en rulleliste.
* udfører stavekontrol.
* giver et eksempel på svaret i form af en visualisering. Visualiseringen opdateres, mens du skriver og redigerer spørgsmålet (den venter ikke på, at du trykker på Enter).
* foreslår automatisk tilsvarende termer fra det eller de underliggende datasæt, når du flytter markøren tilbage i spørgsmålsfeltet.
* viser spørgsmålet igen baseret på dataene i det eller de underliggende datasæt. Det er med til at sikre, at Spørgsmål og svar har forstået dit spørgsmål, da Spørgsmål og svar erstatter de ord, du brugte, med synonymer fra det eller de underliggende datasæt.
* nedtoner ord, som ikke genkendes.

## <a name="combine-results-from-more-than-one-dataset"></a>Kombiner resultater fra mere end ét datasæt
En af Power BI's stærkeste funktioner er muligheden for at kombinere data fra forskellige datasæt.  Så der er ingen grund til at begrænse dine spørgsmål til et enkelt datasæt – stil spørgsmål, der henter data fra mere end ét datasæt. Hvis mit dashboard indeholder felter fra Retail Analysis Sample og et datasæt for delstatspopulation, kan jeg f.eks. spørge *vis antal butikker efter delstatspopulation som søjlediagram faldende*.

## <a name="dont-stop-now"></a>Stop ikke her
Hold samtalen i gang, når Spørgsmål og svar har vist dine resultater! Brug de interaktive funktioner i visualiseringen og Spørgsmål og svar til at afdække mere indsigt.

## <a name="next-steps"></a>Næste trin
Tilbage til [Spørgsmål og svar i Power BI](power-bi-q-and-a.md)  

[Power BI – Grundlæggende begreber](service-basic-concepts.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

