---
title: Tilgængelighed i Power BI Desktop-rapporter
description: Funktioner og forslag til oprettelse af tilgængelighedsrapporter i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f07b5174d031c79f4d8f232c49836b54d95621f1
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256026"
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Tilgængelighed i Power BI Desktop-rapporter
Power BI indeholder funktioner, der gør det nemmere for personer med et handicap at bruge og interagere med Power BI-rapporter. Funktionerne omfatter muligheden for at bruge en rapport ved hjælp tastaturet eller en skærmlæser, bruge tabulatortasten til at sætte fokus på forskellige objekter på en side og bruge markører i visualiseringer.

![Brug forskellige mærker til kurve- og områdediagrammer til at forbedre tilgængelighed](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> Disse tilgængelighedsfunktioner er tilgængelige i versionen af **Power BI Desktop** fra juni 2017 og nyere versioner. Der er planlagt yderligere tilgængelighedsfunktioner for fremtidige versioner.
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>Brug en Power BI Desktop-rapport med et tastatur eller en skærmlæser
Fra og med versionen af **Power BI Desktop** fra september 2017 kan du trykke på tasten med spørgsmålstegnet (**?**) for at få vist et vindue, der beskriver de tastaturgenveje for tilgængelighed, som findes i **Power BI Desktop**.

![Tryk på tasten ? i Power BI Desktop for at få vist tastaturgenveje for tilgængelighed](media/desktop-accessibility/accessibility_03.png)

Med den udvidede tilgængelighed kan du bruge en Power BI-rapport med et tastatur eller en skærmlæser med følgende teknikker:

Du kan skifte fokus mellem rapportens sidefaner eller objekter på en given rapportside ved hjælp af **Ctrl + F6**.

* Når der er fokus på en *rapports sidefaner*, skal du bruge *tabulator*- eller *pile*tasten til at flytte fokus fra én rapportside til den næste. Titlen på rapportsiden, og om den er markeret i øjeblikket, læses højt af skærmlæseren. For at indlæse den rapportside, der i øjeblikket er i fokus, skal du bruge *Enter* eller *mellemrumstasten*.
* Når der er fokus på en indlæst *rapportside*, skal du bruge *tabulatortasten* til at skifte fokus til de enkelte objekter på siden, som inkluderer alle tekstfelter, billeder, figurer og diagrammer. Skærmlæseren læser objektets type, objektets titel, hvis den har en sådan, og en beskrivelse af objektet, hvis rapportforfatteren har angivet det. 

Hvis du, mens du navigere mellem visuelle elementer, vil interagere med dem yderligere, kan du trykke på **Alt+Skift+F10** for at flytte fokus til overskriften, der indeholder forskellige indstillinger, herunder sortering, eksport af de underliggende data for diagrammet og fokustilstand. 

![Tryk på Alt+Skift+F10 i Power BI Desktop for at flytte fokus til den visuelle header](media/desktop-accessibility/accessibility_08.png)

Du kan trykke på **Alt+Skift+F11** for at få vist en tilgængelighedsversion af vinduet *Vis data*. Med det kan du udforske data, der bruges i visualiseringen i en HTML-tabel, ved hjælp af de samme tastaturgenveje, du normalt anvender med din skærmlæser. 

![Tryk på Alt + Skift + F11 i Power BI Desktop for at få vist tilgængelighedsvinduet Se data for et visuelt element](media/desktop-accessibility/accessibility_04.png)

> [!NOTE]
> Funktionen "Vis data" er kun tilgængelig for skærmlæsere med brug af denne tastaturgenvej. Hvis du åbner Vis data via indstillingen i visualiseringens overskrift, vil det ikke være tilgængelig for skærmlæsere.

Fra og med udgivelsen af **Power BI Desktop** i juli 2018 har udsnit nu tilgængelighedsfunktioner indbygget. Når du vælger et udsnit, kan du bruge Ctrl+pil højre til at justere værdien af udsnittet for at skifte mellem de forskellige kontrolelementer i udsnittet. Når du trykker på Ctrl+pil højre første gang, vil fokus f.eks. være på viskelæderet, og hvis du trykker på mellemrumstasten, svarer det til at klikke på viskelæderknappen, hvilket sletter alle værdierne i udsnittet. 

Du kan flytte gennem kontrolelementerne i et udsnit ved at trykke på tabulatortasten. Hvis du trykker på tabulatortasten, når fokus er på viskelæderet, flyttes til rullelisten, og med endnu et tryk på tabulatortasten flyttes fokus til den første værdi i udsnittet (hvis der er flere værdier i udsnittet, f.eks. et interval). 

![Tryk på Ctrl+pil højre i Power BI Desktop for at tilpasse et element eller værdier i et udsnit, tryk på mellemrumstasten for at vælge elementet, og tilpas værdien.](media/desktop-accessibility/accessibility_07.png)

Disse tilgængelighedstilføjelser er oprettet for at give brugere mulighed for at bruge alle funktioner i Power BI-rapporter ved hjælp af en skærmlæser og tastaturnavigation.

## <a name="tips-for-creating-accessible-reports"></a>Tip til oprettelse af tilgængelighedsrapporter
Følgende tip kan hjælpe dig med at oprette **Power BI Desktop**-rapporter med større tilgængelighed.

* For de visuelle elementer for **linje**, **område** og **kombinationsfelt** samt for de visuelle elementer for **punktdiagram** og **boble** skal du slå mærkerne til og bruge en anden *mærkeform* for hver linje.
  
  * Slå *Mærker* til, vælg sektionen **Format** i ruden **Visualiseringer**, udvid sektionen **Former**, og rul derefter ned for at finde **Mærker**, og slå indstillingen *til*.
  * Vælg derefter navnet på de enkelte linjer (eller området, hvis du bruger et **område**diagram) på rullelisten i sektionen **Former**. Under rullelisten kan du derefter justere mange aspekter for det mærke, der bruges til den valgte linje, herunder form, farve og størrelse.
  
  ![Brug forskellige mærker til kurve- og områdediagrammer til at forbedre tilgængelighed](media/desktop-accessibility/accessibility_01.png)
  
  * Hvis du bruger en anden *mærkeform* for hver linje, kan brugere af rapporter nemmere adskille linjer (eller områder) fra hinanden.
* Som opfølgning til forrige punkt skal du ikke bruge farver til at angive oplysninger. Ud over at bruge figurer på linje- og punktdiagrammer behøver du ikke nøjes med betinget formatering for at få indsigt i tabeller og matrixer. 
* Vælg en bevidst sorteringsrækkefølge for hver visualisering i din rapport. Når brugere af skærmlæsere navigerer mellem de underliggende data i diagrammet, benytter den samme rækkefølge som visualiseringen.
* Vælg et *tema*, der har stor kontrast, og som kan bruges af farveblinde, fra temagalleriet, og importér det ved hjælp af [eksempelfunktionen **Temaer**](desktop-report-themes.md).
* For alle objekter i en rapport skal du angive en *alternativ tekst*. Hvis du gør det, sikrer du, at brugere af din rapport forstår, hvad du forsøger at fortælle med et visuelt element, selvom de ikke kan se det visuelle element, billedet, formen eller tekstfeltet. Du kan angive en *alternativ tekst* for et hvilket som helst objekt i en **Power BI Desktop**-rapport ved at vælge objektet (f.eks. en visual, en figur osv.), gå til ruden **Visualiseringer** og vælge **Format**, udvide **Generelt**, rulle til bunden og udfylde tekstfeltet **Alternativ tekst**.
  
  ![Alternativ tekst for et hvilket som helst objekt i en rapport kan tilføjes i Visualiseringer > Format > Generelt > feltet Alternativ tekst](media/desktop-accessibility/accessibility_02.png)
* Kontrollér, at der er tilstrækkelig kontrast mellem teksten og eventuelle baggrundsfarver i dine rapporter. Der er flere værktøjer (f.eks. [Colour Contrast Analyser](https://developer.paciellogroup.com/resources/contrastanalyser/)), som du kan bruge til at kontrollere farverne i din rapport. 
* Brug tekststørrelser og skrifttyper, der er nemme at læse. En lille tekststørrelse eller skrifttyper, der kan være vanskelige at læse, hjælper ikke i forbindelse med tilgængelighed.
* Medtag en titel, akseetiketter og datanavne i alle visuelle elementer.
* Brug titler, der giver mening, for alle rapportsider.
* Undgå dekorative figurer og billeder i din rapport, hvis det er muligt, da de er inkluderet i tabulatorrækkefølgen af rapporten. Hvis du er nødt til at indsætte dekorative objekter i din rapport, kan du opdatere objektets alternative tekst for at fortælle brugere af skærmlæsere, at objektet kun har et dekorativt formål.

## <a name="high-contrast-support-for-reports"></a>Understøttelse af stor kontrast i rapporter

Når du bruger stor kontrast i Windows, anvendes disse indstillinger og den valgte farvepalet også i rapporter i **Power BI Desktop**. 

![Indstillinger for stor kontrast](media/desktop-accessibility/accessibility_05.png)

**Power BI Desktop** registrerer automatisk, hvilket tema med stor kontrast der bruges i Windows, og indstillingerne anvendes i dine rapporter. Farverne med høj kontrast vil også følge rapporten, når den publiceres på Power BI-tjenesten eller andre steder.

![Indstillinger for stor kontrast](media/desktop-accessibility/accessibility_05b.png)

Power BI-tjenesten forsøger også at registrere de indstillinger for stor kontrast, der er valgt i Windows, men hvor effektiv og nøjagtig registreringen er, afhænger af den browser, er bruges med Power BI-tjenesten. Hvis du vil angive temaet manuelt i Power BI-tjenesten, kan du vælge **Vis > Farver med høj kontrast** og derefter vælge det tema, du vil bruge i rapporten.

![Indstillinger for stor kontrast i Power BI-tjenesten](media/desktop-accessibility/accessibility_06.png)

Når du er i **Power BI Desktop** vil du sikkert bemærke, at nogle områder som **Visualiseringer** og **Felter** ikke anvender farveskemaerne med stor kontrast i Windows.


## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
Der er et par kendte problemer og begrænsninger i forbindelse med tilgængelighedsfunktioner, hvilket er beskrevet på følgende liste:

* Når du bruger skærmlæsere med **Power BI Desktop**, får du den bedste oplevelse, hvis du åbner din foretrukne skærmlæser, før du åbner nogen filer i Power BI Desktop.
* Hvis du bruger Oplæser, vil der være nogle begrænsninger, når du navigerer omkring Vis data som en HTML-tabel.

## <a name="next-steps"></a>Næste trin
* [Brug rapporttemaer i Power BI Desktop (prøveversion)](desktop-report-themes.md)

