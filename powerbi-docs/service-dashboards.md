---
title: Introduktion til dashboards for Power BI-designere
description: Et dashboard er en vigtig funktion i Power BI-tjenesten. Det er en enkelt side, der ofte kaldes et lærred, som fortæller en historie via visualiseringer.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 709518924fbb9d83201eb5c070b7a3e93838ec79
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/27/2018
ms.locfileid: "52331936"
---
# <a name="intro-to-dashboards-for-power-bi-designers"></a>Introduktion til dashboards for Power BI-designere

Et ***dashboard*** i Power BI er en enkelt side, der ofte kaldes et lærred, som fortæller en historie via visualiseringer. Da det er begrænset til én side, indeholder et dashboard, der er godt designet, kun de vigtigste elementer fra historien. Læsere kan få vist relaterede rapporter med detaljerne.

![dashboard](media/service-dashboards/power-bi-dashboard2.png)

Et dashboard er en funktion i Power BI-tjenesten. De er ikke tilgængelige i Power BI Desktop. Du kan ikke oprette dashboards på mobilenheder, men du kan [få vist og dele](mobile-apps-view-dashboard.md) dem der.

## <a name="dashboard-basics"></a>Grundlæggende om dashboards 

De visualiseringer, du kan se på dashboardet, kaldes *felter*. Du *fastgør* felter til et dashboard via rapporter. Hvis du ikke har arbejdet med Power BI før, kan du få et godt overblik ved at læse [Power BI – Grundlæggende begreber](service-basic-concepts.md).

> [!IMPORTANT]
> Du skal have en [Power BI Pro](service-free-vs-pro.md)-licens for at oprette dashboards.

Visualiseringerne på et dashboard stammer fra rapporter, og alle rapporter er baseret på et datasæt. Du kan f.eks. se et dashboard som en måde at få adgang til de underliggende rapporter og datasæt på. Når du vælger en visualisering, bliver du ført til den pågældende rapport (og det pågældende datasæt), som er brugt til oprettelsen af visualiseringen.

![diagram, der viser relationer mellem dashboards, rapporter, datasæt](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Fordele ved dashboards
Dashboards er en fantastisk måde at holde øje med din virksomhed på og hurtigt få et overblik over de vigtigste data. Visualiseringer på et dashboard kan stamme fra ét underliggende datasæt eller mange og fra én underliggende rapport eller mange. Et dashboard kombinerer data fra det lokale miljø og cloudmiljøet, hvilket giver dig en samlet visning, uanset hvor dataene er gemt.

Et dashboard er ikke kun et flot billede. Det er yderst interaktivt, og felterne opdateres, når de underliggende data ændres.

## <a name="dashboards-versus-reports"></a>Dashboards sammenlignet med rapporter
[Rapporter](service-reports.md) og dashboards virker ens, da de begge er lærreder fyldt med visualiseringer. Men der er store forskelle på dem.

| **Egenskab** | **Dashboards** | **Rapporter** |
| --- | --- | --- |
| Sider |Én side |Én eller flere sider |
| Datakilder |Én eller flere rapporter og et eller flere datasæt pr. dashboard |Et enkelt datasæt pr. rapport |
| Tilgængelig i Power BI Desktop |Nej |Ja, ***oprettere*** kan bygge og få vist rapporter i Desktop |
| Abonner |Der kan abonneres på et dashboard |Der kan abonneres på rapportsider |
| Filtrering |Der kan ikke filtreres eller laves udsnit |Der er mange forskellige måder at filtrere, fremhæve og lave udsnit på |
| Fremhævet |Ét dashboard kan angives som dit "udvalgte" dashboard |Der kan ikke oprettes en udvalgt rapport |
| Favorit | Dashboards kan markeres som *favoritter* | Rapporter kan markeres som *favoritter*
| Angivelse af beskeder |Tilgængelig for dashboardfelter i visse tilfælde |Ikke tilgængelig via rapporter |
| Forespørgsler på et naturligt sprog |Tilgængelig via dashboard |Ikke tilgængelig via rapporter |
| Kan underliggende datasættabeller og felter ses? |Nej. Data kan eksporteres, men tabeller og felter på selve dashboardet kan ikke ses. |Ja. Datasættabeller, felter og værdier kan ses. |
| Tilpasning |Nej |I Læsevisning kan du publicere, integrere, filtrere, eksportere, downloade som .pbix, få vist relateret indhold, generere QR-koder og analysere i Excel m.m.  |

## <a name="next-steps"></a>Næste trin
* Bliv fortrolig med dashboards ved at se præsentationen af et af vores [eksempler på et dashboard](sample-tutorial-connect-to-the-samples.md).
* Få mere at vide om [dashboardfelter](service-dashboard-tiles.md).
* Vil du holde øje med et enkelt dashboardfelt og modtage en mail, når den når en bestemt grænse? [Opret beskeder for felterne](service-set-data-alerts.md).
* Få mere at vide om, hvordan du bruger [Spørgsmål og svar i Power BI](power-bi-tutorial-q-and-a.md) til at stille et spørgsmål om dine data og få svar i form af en visualisering.
