---
title: Spørgsmål og svar til Power BI-forbrugere
description: Oversigtsemne i dokumentationen om forespørgsler i naturligt sprog i Spørgsmål og svar i Power BI.
author: mihart
ms.reviewer: mohammad ali
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/22/2019
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 051803b3d9708289f37271afc02b7802fb52b50e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73862653"
---
# <a name="qa-for-power-bi-consumers"></a>Spørgsmål og svar til Power BI-**forbrugere**

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

## <a name="what-is-qa"></a>Hvad er Spørgsmål og svar?
Den hurtigste måde at få svar ud af dine data på er nogle gange at stille et spørgsmål på et naturligt sprog. For eksempel "Hvad var den samlede omsætning sidste år".

Brug Spørgsmål og svar til at udforske dine data ved hjælp af intuitive funktioner på et naturligt sprog, og få svar i form af diagrammer og grafer. Spørgsmål og svar adskiller sig fra en søgemaskine – Spørgsmål og svar giver kun resultater om dataene i Power BI.

## <a name="which-visualization-does-qa-use"></a>Hvilken visualisering bruger Spørgsmål og svar?
Spørgsmål og svar vælger den bedste visualisering baseret på de data, der bliver vist. Nogle gange er data i det eller de underliggende datasæt defineret som en bestemt type eller kategori, og det hjælper Spørgsmål og svar med at vide, hvordan de skal vises. Hvis data f.eks. er defineret som en datotype, er det mere sandsynligt, at de vises som et kurvediagram. For data, der er kategoriseret som en by, er det mere sandsynligt, at de vises som et kort.

Du kan også fortælle Spørgsmål og svar, hvilken visualisering der skal bruges, ved at føje den til dit spørgsmål. Men husk, at det ikke altid er muligt for Spørgsmål og svar at vise dataene i den ønskede visualiseringstype. Spørgsmål og svar viser en prompt med en liste over visualiseringstyper, du kan arbejde med.

## <a name="where-can-i-use-qa"></a>Hvor kan jeg bruge Spørgsmål og svar?
Du finder Spørgsmål og svar på dashboards i Power BI-tjenesten og nederst på dashboardet i Power BI Mobil. Medmindre designeren har givet dig redigeringstilladelser, kan du bruge Spørgsmål og svar til at udforske data, men ikke gemme visualiseringer, der er oprettet ved hjælp af Spørgsmål og svar.

![spørgsmålsfelt](media/end-user-q-and-a/powerbi-qna.png)

Du finder også Spørgsmål og svar i rapporter, hvis *designeren* af rapporten har tilføjet en [visualisering til Spørgsmål og svar](../visuals/power-bi-visualization-q-and-a.md).   

![Visualisering til Spørgsmål og svar](media/end-user-q-and-a/power-bi-q-and-a-default.png)

## <a name="qa-on-dashboards"></a>Spørgsmål og svar på dashboards

**Spørgsmål og svar til Power BI** er tilgængelig med en Pro- eller Premium-licens.  [Spørgsmål og svar i Power BI-mobilapps](mobile/mobile-apps-ios-qna.md) og [Spørgsmål og svar med Power BI Embedded](../developer/qanda.md) behandles i særskilte artikler. På nuværende tidspunkt understøtter **Spørgsmål og svar i Power BI** kun besvarelse af spørgsmål på et naturligt sprog på engelsk, men der findes en prøveversion til spansk, som kan aktiveres af Power BI-administratoren.


![træstruktur oprettet med Spørgsmål og svar](media/end-user-q-and-a/power-bi-treemap.png)

At stille spørgsmålet er kun begyndelsen.  Nyd det, mens du suser gennem dine data og tilpasser eller udvider dit spørgsmål, opdager pålidelige nye oplysninger, fokuserer på detaljer og zoomer ud for at få et større overblik. Du bliver henrykt over de nye indblik og opdagelser, du gør.

Oplevelsen er virkelig interaktiv ... og hurtig! Med lager i hukommelsen som drivkraft får du næsten øjeblikkeligt svar.


## <a name="use-qa-on-a-dashboard-in-the-power-bi-service"></a>Brug Spørgsmål og svar på et dashboard i Power BI-tjenesten
I Power BI-tjenesten (app.powerbi.com) indeholder et dashboard felter, der er fastgjort fra et eller flere datasæt, så du kan stille spørgsmål om alle dataene, der er indeholdt i alle disse datasæt. Hvis du vil se, hvilke rapporter og datasæt der blev brugt til at oprette dashboardet, skal du vælge **Få vist relaterede** på rullelisten **Flere handlinger**.

![få vist relaterede på menulinjen](media/end-user-q-and-a/power-bi-q-and-a-view-related.png)

## <a name="how-do-i-start"></a>Hvordan starter jeg?
Først skal du blive bekendt med indholdet. Se nærmere på visualiseringerne på dashboardet og i rapporten. Få en fornemmelse af typen og rækken af data, der er tilgængelig for dig. 

Eksempel:

* Hvis en visualiserings aksemærkater og værdier omfatter "salg", "konto", "måned" og "muligheder", kan du med sikkerhed stille spørgsmål som: "Hvilken *konto* har den højeste *mulighed*, eller vis *salg* efter måned som et liggende søjlediagram."

* Hvis du har data om et websteds ydeevne i Google Analytics, kan du spørge Spørgsmål og svar om, hvor meget tid der er brugt på en webside, antallet af entydige besøg på siden og brugerengagement. Eller hvis du forespørger på demografiske data, kan du stille spørgsmål om alder og indkomst i husholdningen efter placering.

Når du er fortrolig med dataene, kan du vende tilbage til dashboardet og placere markøren i spørgsmålsfeltet. Dette åbner skærmen Spørgsmål og svar.

![skærmen Spørgsmål og svar](media/end-user-q-and-a/power-bi-screen.png) 

Selv inden du begynder at skrive, viser Spørgsmål og svar en ny skærm med forslag som hjælp til at udforme dit spørgsmål. Du får vist udtryk og spørgsmål, der indeholder navnene på tabellerne i de underliggende datasæt, og du kan muligvis tilmed se *udvalgte* spørgsmål, der er oprettet af ejeren af datasættet.

Du kan vælge et af dem for at føje dem til feltet med spørgsmål og derefter tilpasse dem, så de finder et bestemt svar. 

Spørgsmål og svar kan også hjælpe dig med at stille spørgsmål ved hjælp af prompter, automatisk fuldførelse og tip til visualiseringer. 

<!-- ![video](../visuals/media/end-user-q-and-a/qna4.gif) -->


## <a name="the-qa-visual"></a>Visualiseringen til Spørgsmål og svar

Visualiseringen til Spørgsmål og svar giver dig mulighed for at stille spørgsmål på et naturligt sprog og få svar i form af en visualisering. Visualiseringen til Spørgsmål og svar fungerer som en hvilken som helst anden visualisering. Den kan krydsfiltreres/-fremhæves, og den understøtter også bogmærker og kommentarer. 

Du kan identificere en visualisering til Spørgsmål og svar på spørgsmålsfeltet øverst. Det er her, du angiver eller skriver spørgsmål ved hjælp af et naturligt sprog. Visualiseringen til Spørgsmål og svar kan bruges igen og igen til at stille spørgsmål om dine data. Når du forlader rapporten, nulstilles visualiseringen til Spørgsmål og svar til standardindstillingen. 

![Skærmbillede af standardvisualiseringen til Spørgsmål og svar](media/end-user-q-and-a/power-bi-q-and-a-default.png)


## <a name="use-the-qa-visual"></a>Brug visualiseringen til Spørgsmål og svar
Hvis du vil bruge visualiseringen til Spørgsmål og svar, skal du enten vælge et af de foreslåede spørgsmål eller skrive dit eget spørgsmål på et naturligt sprog. 

### <a name="create-a-qa-visual-by-using-a-suggested-question"></a>Opret en visualisering til Spørgsmål og svar ved hjælp af et foreslået spørgsmål

Her har vi valgt **de mest populære geo-stater efter samlet antal enheder**. Power BI gør sit bedste for at vælge den visualiseringstype, der skal bruges. I dette tilfælde er det et kort.

![Kort som visualisering til Spørgsmål og svar](media/end-user-q-and-a/power-bi-q-and-a-suggested.png)

Men du kan fortælle Power BI, hvilken visualiseringstype du vil bruge, ved at føje den til din forespørgsel på et naturligt sprog. Vær opmærksom på, at det ikke er alle visualiseringstyper, der vil fungere eller give mening for dine data. Disse data ville f.eks. ikke resultere i et meningsfyldt punktdiagram. Men de fungerer som et kartogram.

![Visualiseringen til Spørgsmål og svar som et kartogram](media/end-user-q-and-a/power-bi-filled-map.png)

### <a name="create-a-qa-visual-by-typing-a-natural-language-query"></a>Opret en visualisering til Spørgsmål og svar ved at skrive en forespørgsel på et naturligt sprog


Hvis du er usikker på, hvilken type spørgsmål du skal stille, eller hvilken terminologi du skal bruge, skal du udvide **Vis alle forslag** eller gennemse de andre visualiseringer i rapporten. På den måde bliver du bekendt med begreberne og indholdet i datasættet.

1. Skriv dit spørgsmål i feltet til Spørgsmål og svar ved hjælp af et naturligt sprog. I takt med at du skriver dit spørgsmål, hjælper Power BI dig med autofuldførelse, forslag og feedback.

    - Der bruges en rød understregning til ord, som Power BI ikke genkender. Når det er muligt, hjælper Power BI dig med at definere disse ord. Hvis du kan se den korrekte definition, skal du vælge den på rullelisten.  

        ![Begreb med rød understregning i spørgsmålsfeltet i Spørgsmål og svar](media/end-user-q-and-a/power-bi-q-and-a-red.png)

    - Hvis ingen af definitionerne er korrekte, kan du prøve et andet begreb eller vælge ordet med den røde understregning for at bede ejeren af rapporten om at tilføje ordet.

        ![Skriv et spørgsmål i spørgsmålsfeltet i Spørgsmål og svar](media/end-user-q-and-a/power-bi-q-and-a-owner.png)

    - I takt med at du skriver mere af spørgsmålet, giver Power BI dig besked, hvis spørgsmålet ikke er forstået, og forsøger at hjælpe. I eksemplet nedenfor spørger Power BI dig "Mente du..." og foreslår en anden måde at formulere spørgsmålet på ved hjælp af terminologi fra dit datasæt. 

        ![Visualisering til Spørgsmål og svar med foreslåede rettelser](media/end-user-q-and-a/power-bi-q-and-a-did-you-mean.png)

2. Når du har valgt rettelsen fra Power BI, vises resultaterne som et kurvediagram. 

    ![Visualisering til Spørgsmål og svar med resultater som et kurvediagram](media/end-user-q-and-a/power-bi-q-and-a-line.png)


3. Du kan dog ændre kurvediagrammet til en anden visualiseringstype.  

    ![Visualisering til Spørgsmål og svar med "som et søjlediagram" føjet til spørgsmålet](media/end-user-q-and-a/power-bi-q-and-a-specify-type.png)



## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

**Spørgsmål:** Jeg kan ikke se Spørgsmål og svar på dette dashboard.    
**Svar 1:** Hvis du ikke kan se et spørgsmålsfelt, skal du starte med at kontrollere dine indstillinger. Det gør du ved at vælge tandhjulsikonet i øverste højre hjørne af Power BI-værktøjslinjen.   
![tandhjulsikon](media/end-user-q-and-a/power-bi-settings.png)

Vælg derefter **Indstillinger** > **Dashboards**. Kontrollér, at der er en markering ud for **Vis søgefeltet for Spørgsmål og svar på dette dashboard**.    
![Indstillinger for Spørgsmål og svar på dashboard](media/end-user-q-and-a/power-bi-turn-on.png)  


**Svar 2:** Nogle gange har du ikke adgang til indstillingerne. Hvis *designeren* af dashboardet eller din administrator har slået Spørgsmål og svar fra, kan du spørge vedkommende, om det er OK at slå det til igen.   

**Spørgsmål:** Jeg får ikke de resultater, jeg gerne vil se, når jeg skriver et spørgsmål.    
**Svar**: Vælg muligheden for at kontakte ejeren af rapporten eller dashboardet. Du kan gøre dette direkte fra siden Dashboard til Spørgsmål og svar eller visualisering til Spørgsmål og svar. Du kan også slå ejeren op i Power BI-headeren.  Der er mange ting, som designeren kan gøre for at forbedre Spørgsmål og svar. Designeren kan f.eks. omdøbe kolonner i datasættet, så der bruges begreber, som er nemme at forstå (`CustomerFirstName` i stedet for `CustFN`). Da designeren kender datasættet virkelig godt, kan vedkommende også komme med nyttige spørgsmål og føje dem til foreslåede spørgsmål i Spørgsmål og svar.

![Vis kontaktoplysninger](media/end-user-q-and-a/power-bi-q-and-a-contact.png)

## <a name="next-steps"></a>Næste trin
Du kan få mere at vide om, hvordan en visualisering til Spørgsmål og svar oprettes og administreres af *designeren* af rapporten, i [Visualiseringstype til Spørgsmål og svar](../visuals/power-bi-visualization-q-and-a.md).
