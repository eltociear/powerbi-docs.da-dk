---
title: Spørgsmål og svar til Power BI-forbrugere
description: Oversigtsemne i dokumentationen om forespørgsler i naturligt sprog i Spørgsmål og svar i Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/01/2019
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 35ff71d5956c1c48c304324c121f79addf04cb56
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625121"
---
# <a name="qa-for-power-bi-consumers"></a>Spørgsmål og svar til Power BI-**forbrugere**
## <a name="what-is-qa"></a>Hvad er Spørgsmål og svar?
Den hurtigste måde at få svar ud af dine data på er nogle gange at stille et spørgsmål på et naturligt sprog. For eksempel "Hvad var den samlede omsætning sidste år".

Brug Spørgsmål og svar til at udforske dine data ved hjælp af intuitive funktioner på et naturligt sprog, og få svar i form af diagrammer og grafer. Spørgsmål og svar adskiller sig fra en søgemaskine – Spørgsmål og svar giver kun resultater om dataene i Power BI.

**Power BI Q&A** understøtter kun besvarelse af forespørgsler på et naturligt sprog på engelsk. Der findes en prøveversion til spansk, som kan være aktiveret af Power BI-administratoren.

**Spørgsmål og svar til Power BI** er tilgængelig med en Pro- eller Premium-licens. 
>

![træstruktur oprettet med Spørgsmål og svar](media/end-user-q-and-a/power-bi-qna.png)

At stille spørgsmålet er kun begyndelsen.  Nyd det, mens du suser gennem dine data og tilpasser eller udvider dit spørgsmål, opdager pålidelige nye oplysninger, fokuserer på detaljer og zoomer ud for at få et større overblik. Du bliver henrykt over de nye indblik og opdagelser, du gør.

Oplevelsen er virkelig interaktiv ... og hurtig! Med lager i hukommelsen som drivkraft får du næsten øjeblikkeligt svar.

## <a name="where-can-i-use-qa"></a>Hvor kan jeg bruge Spørgsmål og svar?
Du kan finde spørgsmål og svar om dashboards og rapporter i Power BI-tjenesten, og nederst på dashboardet i Power BI mobile. Medmindre designeren har givet dig redigeringstilladelser, kan du bruge Spørgsmål og svar til at udforske data, men ikke gemme visualiseringer, der er oprettet ved hjælp af Spørgsmål og svar.

![spørgsmålsfelt](media/end-user-q-and-a/powerbi-qna.png)

## <a name="how-does-qa-know-how-to-answer-questions"></a>Hvordan ved Spørgsmål og svar, hvordan der skal svares på spørgsmål?
Spørgsmål og svar søger efter svar i alle de datasæt, der er knyttet til dashboardet. Hvis der er et felt for et datasæt på dashboardet, så søger Spørgsmål og svar i dette datasæt for at få svar. 

## <a name="how-do-i-start"></a>Hvordan starter jeg?
Først skal du blive bekendt med indholdet. Se nærmere på visualiseringerne på dashboardet og i rapporten. Få en fornemmelse af typen og rækken af data, der er tilgængelig for dig. Vend derefter tilbage dashboardet, og placer markøren i spørgsmålsfeltet. Dette åbner skærmen Spørgsmål og svar.

![skærmen Spørgsmål og svar](media/end-user-q-and-a/power-bi-qna-screen.png) 

* Hvis visualiseringernes aksemærkater og værdier omfatter "salg", "konto", "måned" og "muligheder", kan du med sikkerhed stille spørgsmål som: "Hvilken *konto* har den højeste *mulighed*, eller vis *salg* efter måned som et liggende søjlediagram."

* Hvis du har data om et websteds ydeevne i Google Analytics, kan du spørge Spørgsmål og svar om, hvor meget tid der er brugt på en webside, antallet af entydige besøg på siden og brugerengagement. Eller hvis du forespørger på demografiske data, kan du stille spørgsmål om alder og indkomst i husholdningen efter placering.

Nederst på skærmen kan du se andre nyttige elementer. For hvert datasæt viser Spørgsmål og svar nøgleord, og nogle gange kan du tilmed se eksempler eller forslag til spørgsmål. Vælg et af dem for at føje det til spørgsmålsfeltet. 

Spørgsmål og svar kan også hjælpe dig med at stille spørgsmål ved hjælp af prompter, automatisk fuldførelse og visuelle tips. 

![video](media/end-user-q-and-a/qa.gif) 


### <a name="which-visualization-does-qa-use"></a>Hvilken visualisering bruger Spørgsmål og svar?
Spørgsmål og svar vælger den bedste visualisering baseret på de data, der bliver vist. Nogle gange er data i det eller de underliggende datasæt defineret som en bestemt type eller kategori, og det hjælper Spørgsmål og svar med at vide, hvordan de skal vises. Hvis data f.eks. er defineret som en datotype, er det mere sandsynligt, at de vises som et kurvediagram. For data, der er kategoriseret som en by, er det mere sandsynligt, at de vises som et kort.

Du kan også fortælle Spørgsmål og svar, hvilken visualisering der skal bruges, ved at føje den til dit spørgsmål. Men husk, at det ikke altid er muligt for Spørgsmål og svar at vise dataene i den ønskede visualiseringstype. Spørgsmål og svar viser en prompt med en liste over visualiseringstyper, du kan arbejde med.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
**Spørgsmål:** Jeg kan ikke se Spørgsmål og svar på dette dashboard.    
**Svar 1:** Hvis du ikke kan se et spørgsmålsfelt, skal du starte med at kontrollere dine indstillinger. Det gør du ved at vælge tandhjulsikonet i øverste højre hjørne af Power BI-værktøjslinjen.   
![tandhjulsikon](media/end-user-q-and-a/power-bi-settings.png)

Vælg derefter **Indstillinger** > **Dashboards**. Kontrollér, at der er en markering ud for **Vis søgefeltet for Spørgsmål og svar på dette dashboard**.    
![Indstillinger for Spørgsmål og svar på dashboard](media/end-user-q-and-a/power-bi-turn-on.png)  


**Svar 2:** Nogle gange slår *designeren* af dashboardet eller administratoren Spørgsmål og svar fra. Spørg dem, om det er okay at slå det til igen.   

**Spørgsmål:** Jeg får ikke de resultater, jeg gerne vil se, når jeg skriver et spørgsmål.    
**Svar**: Tal med *designeren* af dashboardet. Der er mange ting, som designeren kan gøre for at forbedre Spørgsmål og svar. Designeren kan f.eks. omdøbe kolonner i datasættet, så der bruges begreber, som er nemme at forstå (`CustomerFirstName` i stedet for `CustFN`). Da designeren kender datasættet virkelig godt, kan designeren også komme med nyttige spørgsmål og føje dem til lærredet for Spørgsmål og svar.

![udvalgt spørgsmål fremhævet](media/end-user-q-and-a/power-bi-featured-q.png)

## <a name="next-steps"></a>Næste trin

