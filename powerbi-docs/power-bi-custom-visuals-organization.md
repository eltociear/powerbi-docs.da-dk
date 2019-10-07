---
title: Visualiseringer til virksomheder i Power BI
description: Brug, administrer og opret visualiseringer til virksomheder i Power BI
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/11/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: b10a856a98c892b32e873bd01105c52777d2b413
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/04/2019
ms.locfileid: "71946175"
---
# <a name="organizational-visuals-in-power-bi"></a>Visualiseringer til virksomheder i Power BI

Du kan bruge Power BI-visualiseringer i Power BI til at oprette en unik type visualiseringer, der er skræddersyet til dig. Power BI-visualiseringer oprettes af udviklere, og de oprettes ofte, når mængden af visualiseringer, der er inkluderet i Power BI, ikke opfylder deres behov.

I nogle organisationer er Power BI-visualiseringer endnu vigtigere. De kan være nødvendige for at gengive bestemte data eller bestemt indsigt, der er unikke for organisationen, de kan have særlige datakrav, eller de kan fremhæve private forretningsmetoder. Sådanne organisationer har brug for at udvikle Power BI-visualiseringer, dele dem i hele organisationen og sikre, at de bliver vedligeholdt korrekt. Med Power BI-visualiseringer kan organisationer gøre lige præcis det.

På følgende billede vises processen for, hvordan Power BI-visualiseringer til organisationen i Power BI kommer fra administratoren, fortsætter via udvikling og vedligeholdelse og ender hos dataanalytikeren.

![Custom visual pic](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Visualiseringer til virksomheder udrulles og administreres af Power BI-administratoren via Administrationsportalen. Når visualiseringerne er udrullet i organisationens lager, kan brugerne nemt finde dem og importere Power BI-visualiseringer til organisationer i deres rapporter direkte fra Power BI Desktop.

I følgende artikel kan du få mere at vide om, hvordan du bruger Power BI-visualiseringer til organisationer i de rapporter, du har oprettet: [Få mere at vide om import af visualiseringer til virksomheder i dine rapporter](power-bi-custom-visuals.md).

## <a name="administer-organizational-power-bi-visuals"></a>Administrer Power BI-visualisering til organisationer

I følgende artikel kan du få mere at vide om, hvordan du administrerer, udruller og håndterer Power BI-visualiseringer til organisationer i din organisation: [Få mere at vide om udrulning og administration af Power BI-visualiseringer til organisationer](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> En brugerdefineret visualisering kan indeholde kode, der kan udgøre en risiko for sikkerheden eller beskyttelse af personlige oplysninger. Sørg for, at du har tillid til forfatteren af og kilden til en brugerdefineret visualisering, før du udruller den i virksomhedens lager.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Der er adskillige overvejelser og begrænsninger, som du skal være opmærksom på.

Administrator:

* Ældre Power BI-visualiseringer (f.eks. Power BI-visualiseringer, som ikke er bygget oven på de nye versionerede API'er) understøttes ikke

* Hvis en brugerdefineret visualisering slettes fra lageret, gengives alle eksisterende rapporter, som bruger den slettede visualisering, ikke. Du kan ikke fortryde en sletning fra lageret. Brug funktionen "Deaktiver" til at deaktivere en brugerdefineret visualisering midlertidigt.

Slutbruger:

* Power BI-visualiseringer er private visualiseringer, der er importeret fra organisationens lager. På samme måde som andre private visuals kan de ikke [eksporteres til PowerPoint](https://docs.microsoft.com/power-bi/consumer/end-user-powerpoint) eller vises i mails, der modtages, når en bruger [abonnerer på rapportsider](https://docs.microsoft.com/power-bi/consumer/end-user-subscribe). Det er kun [certificerede Power BI-visualiseringer](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified), der er importeret direkte fra markedspladsen, som understøtter disse funktioner.

* Visio-visualiseringen, PowerApps-visualiseringen, Mapbox-visualiseringen og GlobeMap-visualiseringen fra AppSource-markedspladsen gengives ikke, hvis de udrulles via organisationens lager.

## <a name="troubleshoot"></a>Fejlfind

Du kan finde oplysninger om fejlfinding under [Fejlfinding af dine Power BI-visualiseringer](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger og få svar på spørgsmål under [Ofte stillede spørgsmål om Power BI-visualiseringer](power-bi-custom-visuals-faq.md#organizational-visuals).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).
