---
title: Hvad er et Power BI-dashboard?
description: Et dashboard er en vigtig funktion i Power BI-tjenesten.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 7db5bf514b567cbcaf9dddc5d48006762237a622
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/10/2018
ms.locfileid: "48909124"
---
# <a name="dashboards-in-power-bi-service"></a>Dashboards i Power BI-tjenesten

Et Power BI-***dashboard*** er en enkelt side, der ofte kaldes et canvas, hvor der bruges visualiseringer til at fortælle en historie. Da det er begrænset til én side, indeholder et dashboard, der er godt designet, kun de vigtigste elementer fra historien.

![dashboard](media/end-user-dashboards/power-bi-dashboard2.png)

De visualiseringer, du kan se på dashboardet, kaldes *felter* og er *fastgjort* til dashboardet fra rapporter. Hvis du ikke har arbejdet med Power BI før, kan du få et godt overblik ved at læse [Power BI – Grundlæggende begreber](end-user-basic-concepts.md).

> [!NOTE]
> Dashboards er en funktion i Power BI-tjenesten og er ikke tilgængelig i Power BI Desktop. Der kan ikke oprettes dashboards på mobilenheder, men du kan [få dem vist og dele dem](/mobile/mobile-apps-view-dashboard.md).
> 
> 

Visualiseringerne på et dashboard stammer fra rapporter, og hver rapport er baseret på et datasæt. Du kan faktisk opfatte et dashboard som en måde at få adgang til underliggende rapporter og datasæt på. Når du vælger en visualisering, bliver du ført til den rapport (og det datasæt), der blev brugt til at oprette den.

![diagram, der viser relationer mellem dashboards, rapporter, datasæt](media/end-user-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Fordele ved dashboards
Dashboards er en fantastisk måde at holde øje med din virksomhed, søge efter svar og se dine vigtigste data i korte træk på. Visualiseringer på et dashboard kan stamme fra ét underliggende datasæt eller mange og fra én underliggende rapport eller mange. Et dashboard kombinerer data i det lokale miljø og cloudmiljøet, hvilket giver dig en samlet visning, uanset hvor dataene er gemt.

Et dashboard er ikke kun et flot billede. Det er yderst interaktivt og kan i vidt omfang tilpasses, og felterne opdateres, når de underliggende data ændres.

## <a name="dashboards-versus-reports"></a>Dashboards sammenlignet med rapporter
Rapporter forveksles ofte med dashboards, da de også er lærreder med visualiseringer. Men der er nogle store forskelle.

| **Egenskab** | **Dashboards** | **Rapporter** |
| --- | --- | --- |
| Sider |Én side |Én eller flere sider |
| Datakilder |Én eller flere rapporter og et eller flere datasæt pr. dashboard |Et enkelt datasæt pr. rapport |
| Tilgængelig i Power BI Desktop |Nej |Ja, der kan oprettes og vises rapporter i Desktop |
| Fastgørelse |Eksisterende visualiseringer (felter) kan kun fastgøres fra det aktuelle dashboard til dine andre dashboards |Visualiseringer kan fastgøres (som felter) til et hvilket som helst af dine dashboards. Hele rapportsider kan fastgøres til et hvilket som helst af dine dashboards. |
| Abonnement |Der kan ikke abonneres på et dashboard |Der kan abonneres på rapportsider |
| Filtrering |Der kan ikke filtreres eller laves udsnit |Der er mange forskellige måder at filtrere, fremhæve og lave udsnit på |
| Angivelse af beskeder |Der kan oprettes beskeder, som sendes via mail, når visse betingelser er opfyldt |Nej |
| Udvalgt |Ét dashboard kan angives som dit "udvalgte" dashboard |Der kan ikke oprettes en udvalgt rapport |
| Forespørgsler på et naturligt sprog |Tilgængelig via dashboard |Ikke tilgængelig via rapporter |
| Kan visualiseringstypen ændres? |Nej. Faktisk opdateres en fastgjort visualisering på dashboardet ikke, hvis en rapportejer ændrer visualiseringstypen i rapporten |Ja |
| Kan underliggende datasættabeller og felter ses? |Nej. Data kan eksporteres, men tabeller og felter på selve dashboardet kan ikke ses. |Ja. Datasættabeller, felter og værdier kan ses. |
| Oprettelse af visualiseringer |Begrænset til tilføjelse af knapper til dashboardet ved hjælp af "Tilføj felt" |Mange forskellige typer visualiseringer kan oprettes, brugerdefinerede visualiseringer kan tilføjes, visualiseringer kan redigeres m.m. ved hjælp af Redigeringstilladelser |
| Tilpasning |Der kan foretages handlinger for visualiseringerne (felterne), f.eks. flytte og arrangere, tilpasse størrelsen, tilføje links, omdøbe, slette og få vist hele skærmen. Men selve dataene og visualiseringerne er skrivebeskyttede. |I Læsevisning kan du publicere, integrere, filtrere, eksportere, downloade som .pbix, få vist relateret indhold, generere QR-koder og analysere i Excel m.m.  I Redigeringsvisning kan du foretage alle de ovennævnte handlinger og meget mere. |

## <a name="dashboard-creators-and-dashboard-consumers"></a>Dashboardforfattere og dashboardbrugere
Afhængigt af din rolle kan du være en person, der opretter dashboards til egen brug eller til at dele med kolleger. Du vil måske lære, hvordan du opretter og deler dashboards. Eller du kan være en person, der modtager dashboards fra andre. Du vil måske lære, hvordan du forstår og interagerer med dashboardet.

Her er nogle emner opdelt efter rolle, som kan hjælpe dig med at komme i gang.

Power BI Pro er påkrævet både for at dele et dashboard og få vist et delt dashboard.

### <a name="if-you-will-be-receiving-and-consuming-dashboards"></a>Hvis du skal modtage og bruge dashboards
* Bliv fortrolig med dashboards ved at se præsentationen af et af vores [eksempler på et dashboard](../sample-tutorial-connect-to-the-samples.md).
* Få mere at vide om [dashboardfelter](end-user-tiles.md), og hvad der sker, når du vælger et.
* Vil du holde øje med et enkelt dashboardfelt og modtage en mail, når den når en bestemt grænse? [Opret beskeder for felterne](end-user-alerts.md).
* Stil spørgsmål om dit dashboard. Få mere at vide om, hvordan du bruger [Spørgsmål og svar i Power BI](end-user-q-and-a.md) til at stille et spørgsmål om dine data og få svar i form af en visualisering.

> [!TIP]
> Hvis du ikke kunne finde det, du ledte efter her, kan du bruge indholdsfortegnelsen til venstre.
> 

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](../power-bi-overview.md)  
[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)  