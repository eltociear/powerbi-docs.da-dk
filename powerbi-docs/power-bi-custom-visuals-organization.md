---
title: Brugerdefinerede visualiseringer til virksomheder i Power BI
description: Brug, administrer og opret brugerdefinerede visualiseringer til virksomheder i Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/11/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 6622625f27f62d9d8ffc35ecfddf4550f2a7e16e
ms.sourcegitcommit: c09241803664643e1b2ba0c150e525e1262ca466
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/08/2019
ms.locfileid: "54072146"
---
# <a name="organizational-custom-visuals-in-power-bi"></a>Brugerdefinerede visualiseringer til virksomheder i Power BI

Du kan bruge brugerdefinerede visualiseringer i Power BI til at oprette unikke visualiseringer, der er skræddersyet til dig. Brugerdefinerede visualiseringer oprettes ofte af udviklere, og de oprettes ofte, når mængden af visualiseringer, der er inkluderet i Power BI, ikke opfylder deres behov.

I nogle virksomheder er brugerdefinerede visualiseringer endnu vigtigere: De kan være nødvendige for at gengive bestemte data eller indsigter, der er unikke for virksomheden; de kan have særlige datakrav; eller de kan fremhæve private forretningsmetoder. Sådanne virksomheder har brug for at udvikle brugerdefinerede visualiseringer, dele dem i hele virksomheden og sikre, at de bliver vedligeholdt korrekt. Med brugerdefinerede visualiseringer i Power BI kan virksomheder gøre lige præcis det.

På følgende billede vises processen for, hvordan de brugerdefinerede visualiseringer til virksomheden i Power BI kommer fra administratoren, fortsætter via udvikling og vedligeholdelse og ender hos dataanalytikeren.

![Billede af brugerdefineret visualisering](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Visualiseringer til virksomheder udrulles og administreres af Power BI-administratoren via Administrationsportalen. Når visualiseringerne er udrullet i virksomhedens lager, kan brugerne nemt finde dem og importere de brugerdefinerede visualiseringer til virksomheder i deres rapporter direkte fra Power BI Desktop.

I følgende artikel kan du få mere at vide om, hvordan du bruger brugerdefinerede visualiseringer til virksomheder i de rapporter, du har oprettet: [Få mere at vide om import af visualiseringer til virksomheder i dine rapporter](power-bi-custom-visuals.md).

## <a name="administer-organizational-custom-visuals"></a>Administrer brugerdefinerede visualiseringer til virksomheder

I følgende artikel kan du få mere at vide om, hvordan du administrerer, udruller og håndterer brugerdefinerede visualiseringer til virksomheder i din organisation: [Få mere at vide om udrulning og administration af brugerdefinerede visualiseringer til virksomheder](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> En brugerdefineret visualisering kan indeholde kode, der kan udgøre en risiko for sikkerheden eller beskyttelse af personlige oplysninger. Sørg for, at du har tillid til forfatteren af og kilden til en brugerdefineret visualisering, før du udruller den i virksomhedens lager.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Der er adskillige overvejelser og begrænsninger, som du skal være opmærksom på.

Administrator:

* Ældre brugerdefinerede visualiseringer (f.eks. brugerdefinerede visualiseringer, som ikke er bygget oven på de nye versionerede API'er) understøttes ikke

* Hvis en brugerdefineret visualisering slettes fra lageret, gengives alle eksisterende rapporter, som bruger den slettede visualisering, ikke. Du kan ikke fortryde en sletning fra lageret. Brug funktionen "Deaktiver" til at deaktivere en brugerdefineret visualisering midlertidigt.

Slutbruger:

* Brugerdefinerede visualiseringer er private visualiseringer, der er importeret fra virksomhedens lager. På samme måde som andre private visualiseringer kan de ikke [eksporteres til PowerPoint](https://docs.microsoft.com/power-bi/consumer/end-user-powerpoint) eller vises i mails, der modtages, når en bruger [abonnerer på rapportsider](https://docs.microsoft.com/power-bi/consumer/end-user-subscribe). Det er kun [certificerede brugerdefinerede visualiseringer](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified), der er importeret direkte fra markedspladsen, som understøtter disse funktioner.

* Visio-visualiseringen, PowerApps-visualiseringen, Mapbox-visualiseringen og GlobeMap-visualiseringen fra AppSource-markedspladsen gengives ikke, hvis de udrulles via organisationens lager.

## <a name="troubleshoot"></a>Fejlfind

Du kan finde oplysninger om fejlfinding under [Fejlfinding af dine brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger og få svar på spørgsmål under [Ofte stillede spørgsmål om brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).
