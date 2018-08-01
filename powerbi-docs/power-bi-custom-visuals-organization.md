---
title: Brug af brugerdefinerede visualiseringer til virksomheder i Power BI
description: Brug, administrer og opret brugerdefinerede visualiseringer til virksomheder i Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: bc4dcc26ac2007e482b396139d572018c8a3acd3
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/31/2018
ms.locfileid: "34291897"
---
# <a name="using-organization-custom-visuals-in-power-bi"></a>Brug af brugerdefinerede visualiseringer til virksomheder i Power BI

Du kan bruge brugerdefinerede visualiseringer i Power BI til at oprette unikke visualiseringer, som er skræddersyet til dig eller de dataindsigter, du forsøger at gengive. Denne type brugerdefineret visualisering oprettes ofte af udviklere, og de oprettes ofte, når mængden af visualiseringer, der er inkluderet i Power BI, ikke opfylder deres behov. 

I nogle virksomheder er brugerdefinerede visualiseringer endnu vigtigere: De kan være nødvendige for at gengive bestemte data eller indsigter, der er unikke for virksomheden; de kan have særlige datakrav; eller de kan fremhæve private forretningsmetoder. Sådanne virksomheder har brug for at udvikle brugerdefinerede visualiseringer, dele dem i hele virksomheden og sikre, at de bliver vedligeholdt korrekt. Med brugerdefinerede visualiseringer i Power BI kan virksomheder gøre lige præcis det.

På følgende billede vises processen for, hvordan den brugerdefinerede visualisering til virksomheder i Power BI kommer fra administratoren, fortsætter via udvikling og vedligeholdelse og ender hos dataanalytikeren.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Visualiseringer til virksomheder udrulles og administreres af Power BI-administratoren via Administrationsportalen. Når visualiseringerne er udrullet i virksomhedens lager, kan brugerne nemt finde dem og importere de brugerdefinerede visualiseringer til virksomheder i deres rapporter direkte fra Power BI Desktop.

## <a name="using-organizational-custom-visuals"></a>Brug af brugerdefinerede visualiseringer til virksomheder

Du kan få mere at vide om, hvordan du bruger brugerdefinerede visualiseringer til virksomheder i de rapporter, du har oprettet, i følgende artikel: [Få mere at vide om, hvordan du importerer visualiseringer til virksomheder i dine rapporter](power-bi-custom-visuals.md).
 
## <a name="administering-organizational-custom-visuals"></a>Administration af brugerdefinerede visualiseringer til virksomheder

Du kan få mere at vide om, hvordan du administrerer og udruller brugerdefinerede visualiseringer til virksomheder i din virksomhed i følgende artikel: [Få mere at vide om udrulning og administration af brugerdefinerede visualiseringer til virksomheder](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> En brugerdefineret visualisering kan indeholde kode, der kan udgøre en risiko for sikkerheden eller beskyttelse af personlige oplysninger. Sørg for, at du har tillid til forfatteren af og kilden til en brugerdefineret visualisering, før du udruller den i virksomhedens lager. 
> 

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
 
Der er adskillige overvejelser og begrænsninger, som du skal være opmærksom på.
 
Administrator:

* Ældre brugerdefinerede visualiseringer (f.eks. brugerdefinerede visualiseringer, som ikke er bygget oven på de nye versionerede API'er) understøttes ikke.

* Hvis en brugerdefineret visualisering slettes fra lageret, gengives alle eksisterende rapporter, som bruger den slettede visualisering, ikke. Du kan ikke fortryde en sletning. Brug funktionen "Deaktiver" til at deaktivere en brugerdefineret visualisering midlertidigt.
 
Slutbruger:

* Arbejdsområdesamling i Power BI understøttes ikke for visualiseringer til virksomheder.

* Visio-visualiseringen, PowerApps-visualiseringen og GlobeMap-visualiseringen fra AppSource-markedspladsen gengives ikke, hvis de udrulles via virksomhedens lager.
