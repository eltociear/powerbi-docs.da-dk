---
title: Tips til udformning af et fantastisk Power BI-dashboard
description: Tips til udformning af et fantastisk Power BI-dashboard
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/22/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: a113cf75ae238b19cdc54b03ffc049bdcdfb8368
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54281798"
---
# <a name="tips-for-designing-a-great-power-bi-dashboard"></a>Tips til udformning af et fantastisk Power BI-dashboard
Nu, hvor du har oprettet et dashboard og tilføjet nogle felter, kan du overveje, hvordan du ikke bare gør dit dashboard flot, men også funktionelt. Generelt betyder det, at man sørger for, at den vigtigste information er tydelig, og at udseendet er rent og ryddeligt.

Her er nogle få tips.

> [!TIP]
> Mange af designprincipperne for rapporter gælder også for dashboards.  Læs vores hvidbog [Best design practices for reports and visuals](visuals/power-bi-visualization-best-practices.md).
>
>

## <a name="watch-the-dashboard-makeover-webinarhttpsinfomicrosoftcomco-powerbi-wbnr-fy16-05may-12-dashboard-makeover-registrationhtml"></a>Se [webinaret Dashboard Makeover](https://info.microsoft.com/CO-PowerBI-WBNR-FY16-05May-12-Dashboard-Makeover-Registration.html)
Se Marc Reguera, der er ekspert i Microsoft Principal Program Manager- og Power BI-dashboard, [udføre makeovers af dashboards](https://info.microsoft.com/CO-PowerBI-WBNR-FY16-05May-12-Dashboard-Makeover-Registration.html).

## <a name="consider-your-audience"></a>Tænk over din målgruppe
Hvad er de vigtigste målepunkter, der kan hjælpe dem med at træffe beslutninger? Hvordan vil dashboardet blive brugt? Hvilke indlærte eller kulturelle forudsætninger kan påvirke designvalg? Hvilke oplysninger skal modtageren bruge for at få succes?

Husk, at et dashboard er en oversigt – et samlet sted, hvor du kan se dataenes aktuelle tilstand. Dashboardet er baseret på underliggende rapporter og datasæt, og de kan indeholde mange detaljer. Dine læsere kan analysere rapporterne fra dit dashboard. Derfor skal du ikke lægge detaljerne på dashboardet, med mindre det er det, dine læsere skal overvåge.

Hvor skal dashboardet vises? Hvis det skal vises på en større skærm, kan du lægge mere indhold på det. Hvis læserne skal se det på deres tablets, vil færre felter være mere læsevenlige.

## <a name="tell-a-story-and-keep-it-to-one-screen"></a>Fortæl en historie, og sørg for, at den kun fylder et skærmbillede
Eftersom dashboards er beregnet til at vise vigtige oplysninger i overblik, er det bedst, at alle felterne er på samme skærmbillede. Kan du undgå rullepaneler på dit dashboard?

Er dashboardet for rodet?  Fjern alle uvigtige oplysninger, og behold kun dem, der let kan læses og forstås.

## <a name="make-use-of-full-screen-mode"></a>Brug fuldskærmstilstand
Vis dit dashboard i [fuld skærm](consumer/end-user-focus.md) uden forstyrrelser.

## <a name="make-the-most-important-information-biggest"></a>Gør de vigtigste oplysninger størst
Hvis tekst og visualiseringer på dit dashboard alle har samme størrelse, kan læserne have vanskeligt ved at fokusere på, hvad der er vigtigst. For eksempel er kortvisualiseringer en god måde at fremhæve et vigtigt tal på:  
![Kortvisualisering](media/service-dashboards-design-tips/pbi_card.png)

Men husk at angive kontekst.  

Læs om [oprettelse af et felt med blot et tal](visuals/power-bi-visualization-card.md).

## <a name="put-the-most-important-information-in-the-upper-corner"></a>Placer de vigtigste oplysninger i øverste hjørne
De fleste læser oppefra og ned, så sæt det højeste detaljeniveau øverst, og vis flere detaljer, efterhånden som du bevæger dig i den retning, modtagerne læser (venstre mod højre, højre mod venstre).

## <a name="use-the-right-visualization-for-the-data-and-format-it-for-easy-reading"></a>Brug den rigtige visualisering til dataene, og formatér den, så den er letlæselig
Undgå at variere visualiseringerne bare for variationens skyld.  Visualiseringer skal give et overblik og være enkle at "læse" og forstå.  En enkel grafisk visualisering er nok til visse data og visualiseringer. Men andre data kan kræve en mere kompleks visualisering - brug titler og etiketter og andre brugerdefinerede hjælpemidler til at hjælpe læseren.  

* [Vælg relevante datavisualiseringer](https://www.youtube.com/watch?v=-tdkUYrzrio). Vær forsigtig med at bruge diagrammer, der forvrænger virkeligheden, medføre udgangspunkt, dvs. 3D-diagrammer. Vær opmærksom på, at det er vanskeligt for den menneskelige hjerne at fortolke cirkulære former. Cirkeldiagrammer, kransediagrammer, målere og andre cirkulære diagramtyper kan se flotte ud, men de er ikke den bedste metode til visualisering af data.
* Vær konsekvent med diagramskalaer på akser, sortering af diagramdimensioner og også de farver, som bruges til dimensionsværdier i diagrammer.
* Sørg for, at kode kvantitative data pænt. Brug ikke mere end tre eller fire tal ved visning af tal. Vis måleenheder for et eller to tal til venstre for decimalkommaet og skala for tusindtals- eller millionseparatorer, dvs. 3,4 millioner og ikke 3.400.000.
* Bland ikke præcisions- og tidsniveauer. Sørg for, at tidsrammerne forstås korrekt.  Undgå at have et diagram, der har sidste måned ud for filtrerede diagrammer fra en bestemt måned i året.
* Bland ikke store og små målinger på samme skala, som f.eks. på en linje eller et liggende søjlediagram.  F.eks. kan én måling være i millioner og en anden måling i tusinder.  Med sådan en stor skalainddeling vil det være vanskeligt at se forskellene i den måling, som er i tusinder.  Hvis du er nødt til at blande, skal du vælge en visualisering, som tillader brug af en akse mere.
* Lav ikke dine diagrammer rodede med datanavne, der ikke er nødvendige. Værdierne i liggende søjlediagrammer forstås normalt uden at vise det faktiske tal.
* Vær opmærksom på, hvordan [diagrammer sorteres](consumer/end-user-change-sort.md).  Hvis du vil fremhæve det højeste eller laveste tal, skal du sortere efter målingen.  Hvis du ønsker, at modtagerne hurtigt skal kunne finde en bestemt kategori blandt mange andre kategorier, skal du sortere efter aksen.  
* Cirkeldiagrammer er bedst, hvis de har mindre end otte kategorier. Eftersom du ikke kan sammenligne værdier ved siden af hinanden, er det vanskeligere at sammenligne værdier i et cirkeldiagram end i liggende søjlediagrammer og stående søjlediagrammer. Cirkeldiagrammer kan være gode til visning af dele i forhold til helheder i stedet for at sammenligne delene. Og målerdiagrammer er gode til visning af den aktuelle status i forbindelse med et mål.

Se [Visualiseringstyper i Power BI](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md) for at få en mere visualiseringsspecifik vejledning.  

## <a name="learning-more-about-best-practice-dashboard-design"></a>Få mere at vide om den bedste fremgangsmåde i forbindelse med dashboard-design
For at kunne mestre kunsten at lave et godt dashboard-design bør du overveje at lære de grundlæggende designprincipper for visuel perception, og hvordan du tydeligt kommunikerer handlingsrettet information i kontekst. Heldigvis findes der allerede et bredt udvalg af ressourcer til rådighed bl.a. rundt omkring i vores blogs. Nogle få af vores foretrukne bøger er bl.a.:

* *Information Dashboard Design* af Stephen Few  
* *Show Me the Numbers* af Stephen Few  
* *Now You See It* af Stephen Few  
* *Envisioning Information* af Edward Tufte  
* *Advanced Presentations* by Design af Andrew Abela   

## <a name="next-steps"></a>Næste trin
[Opret et dashboard fra en rapport](service-dashboard-create.md)  
[Power BI – Grundlæggende begreber](consumer/end-user-basic-concepts.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
