---
title: Introduktion til datasæt på tværs af arbejdsområder (prøveversion)
description: Få mere at vide om, hvordan du deler et datasæt med brugere på tværs af organisationen. De kan derefter oprette rapporter baseret på dit datasæt i deres egne arbejdsområder.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/16/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: ace40fed472dc516cce5a761544cc5365566f3cd
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074114"
---
# <a name="intro-to-datasets-across-workspaces-preview"></a>Introduktion til datasæt på tværs af arbejdsområder (prøveversion)

Business intelligence er en aktivitet baseret på samarbejde. Det er vigtigt at oprette standardiserede datasæt, der fungerer som fælles udgangspunkt. Derefter er registrering og genbrug af disse standardiserede datasæt helt centralt. Når eksperter inden for datamodellering i din organisation opretter og deler optimerede datasæt, kan oprettere af rapporter bruge disse datasæt som udgangspunkt for at oprette præcise rapporter. Din organisation har derefter ensartede data, når der skal træffes beslutninger, samt en sund datakultur.

![Vælg et delt datasæt](media/service-datasets-across-workspaces/power-bi-select-shared-dataset.png)

I Power BI kan forfattere af datasæt styre, hvem der har adgang til deres data, ved hjælp af [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets). Forfatterne af datasæt kan også *certificere* eller *fremhæve* datasæt, så andre kan finde dem. På denne måde ved forfattere af rapporter, hvilke datasæt der er i høj kvalitet og officielle, og de kan bruge disse datasæt, uanset hvor de er forfattere i Power BI. Lejeradministratorer har en ny lejerindstilling til at [styre brugen af datasæt på tværs af arbejdsområder](service-datasets-admin-across-workspaces.md).

## <a name="dataset-sharing-and-the-new-workspace-experience"></a>Deling af datasæt og den nye arbejdsområdeoplevelse

Oprettelse af rapporter baseret på datasæt i forskellige arbejdsområder og kopiering af rapporter til forskellige arbejdsområder er tæt forbundet med den [nye arbejdsområdeoplevelse](service-create-the-new-workspaces.md):

- Når du åbner datasætkataloget fra en ny arbejdsområdeoplevelse i tjenesten, viser datasætkataloget datasæt, der findes i Mit arbejdsområde og i andre nye arbejdsområdeoplevelser. 
- Når du åbner datasætkataloget fra et klassisk arbejdsområde, kan du kun se datasættene i det pågældende arbejdsområde, ikke datasættene i andre arbejdsområder.
- I Power BI Desktop kan du publicere Live Connect-rapporter i forskellige arbejdsområder, så længe deres datasæt befinder sig i arbejdsområder med den nye oplevelse.
- Når du kopierer rapporter på tværs af arbejdsområder, skal destinationsarbejdsområdet være et arbejdsområde med den nye oplevelse.

## <a name="discover-datasets-preview"></a>Opdag datasæt (prøveversion)

Når du opretter en rapport oven på et eksisterende datasæt, skal du som det første oprette forbindelse til datasættet enten i Power BI-tjenesten eller i Power BI Desktop. Læs om [registrering af datasæt fra forskellige arbejdsområder (prøveversion)](service-datasets-discover-across-workspaces.md)

## <a name="copy-a-report"></a>Kopiér en rapport

Når du finder en rapport, du vil bruge i et arbejdsområde eller en app, kan du lave en kopi af den og derefter redigere den, så det passer til dine behov. Du behøver ikke at oprette datamodellen. Den er allerede oprettet for dig. Og det er meget nemmere at redigere en eksisterende rapport end at starte forfra. Læs mere om [kopiering af rapporter](service-datasets-copy-reports.md).

## <a name="build-permission-for-datasets"></a>Tilladelsen Opret for datasæt

Hvis du er forfatteren af et datasæt, kan du med tilladelsestypen Opret bestemme, hvem i din organisation der kan oprette nyt indhold i dine datasæt. Personer med tilladelsen Opret kan også oprette nyt indhold i datasæt uden for Power BI, f.eks. Excel-ark via Analysér i Excel, XMLA og eksportér. Læs mere om [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets).

## <a name="promotion-and-certification"></a>Fremhævning og certificering

Hvis du opretter datasæt, som andre kan få glæde af, kan du gøre det nemmere for dem at finde det ved at [fremhæve dit datasæt](service-datasets-promote.md). Du kan også anmode om, at eksperter i din organisation [certificerer dit datasæt](service-datasets-certify.md).

## <a name="licensing"></a>Licensering

De specifikke funktioner og oplevelser, der er baseret på funktioner for delte datasæt, er givet i licens i henhold til deres eksisterende scenarier. Eksempel:

- Generelt kan alle registrere og oprette forbindelse til delte datasæt. Brugere uden en Pro-licens kan dog kun oprette forbindelse til datasæt, der er placeret i deres egen version af Mit arbejdsområde.
- Brugere uden en Pro-licens kan kun bruge rapporter og dashboards, der er baseret på et delt datasæt, hvis begge arbejdsområder (det med indholdet og det med datasættet) hostes i en Premium-kapacitet.
- I Power BI Desktop kan brugere uden en Pro-licens kun se datasæt fra deres egen version af Mit arbejdsområde.
- Det kræver en Pro-licens at kopiere rapporter mellem arbejdsområder.
- Hvis du vil kopiere rapporter fra en app, skal du have en Pro-licens, som er påkrævet for organisationsindholdspakker.
- Det kræver en Pro-licens at fremhæve og certificere datasæt.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

- Hvis du vil oprette en rapport oven på et datasæt i et andet arbejdsområde, kræver det, at den nye arbejdsområdeoplevelse er begge steder: Rapporten skal være i en ny arbejdsområdeoplevelse og datasættet skal være i en ny arbejdsområdeoplevelse.
- Lad os sige, at du opretter en rapport i arbejdsområde A, der er baseret på et datasæt i arbejdsområde B. Når du opretter en app til arbejdsområde A, kan du kun inkludere den pågældende rapport i appen til arbejdsområde A, hvis du også er medlem af arbejdsområde B.
- I et klassisk arbejdsområde viser datasæts registreringsoplevelse kun datasættene i det pågældende arbejdsområde.
- Hvis du vil føje en rapport baseret på et delt datasæt til en app, skal du være medlem af datasættets arbejdsområde. Dette er et kendt problem.
- "Publicer på internettet" er designet til ikke at virke for en rapport, der er baseret på et delt datasæt.
- Hvis to personer er medlem af et arbejdsområde, der åbner et delt datasæt, er det er muligt, at kun én af dem kan se det relaterede datasæt i arbejdsområdet. Det er kun personer, der som minimum har læseadgang til datasættet, som kan se det delte datasæt. 

## <a name="next-steps"></a>Næste trin

- [Fremhæv datasæt](service-datasets-promote.md)
- [Certificer datasæt](service-datasets-certify.md)
- [Styr brugen af datasæt på tværs af arbejdsområder](service-datasets-admin-across-workspaces.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
