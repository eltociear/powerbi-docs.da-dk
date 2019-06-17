---
title: Brug datasæt på tværs af arbejdsområder (prøveversion) – Power BI
description: Få mere at vide om, hvordan du kan dele et datasæt med brugere på tværs af organisationen. De kan derefter oprette rapporter, der er baseret på dit datasæt, i deres egne arbejdsområder.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: a5e4b41b36dfbf6cca14a348268b96eaad21b00e
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461850"
---
# <a name="use-datasets-across-workspaces-preview"></a>Brug datasæt på tværs af arbejdsområder (prøveversion)

Business intelligence er en aktivitet baseret på samarbejde. Det er vigtigt at oprette standardiserede datasæt, der fungerer som fælles udgangspunkt. Registrering og genbrug af disse standardiserede datasæt er nøglen. Når eksperter inden for datamodellering i din organisation opretter og deler optimerede datasæt, kan oprettere af rapporter bruge disse datasæt som udgangspunkt for at oprette præcise rapporter. Din organisation har derefter ensartede data, når der skal træffes beslutninger, samt en sund datakultur.

Power BI gør det nemt for oprettere af datasæt at certificere eller fremhæve datasæt, så andre kan finde dem. Derefter kan rapportforfattere finde officielle datasæt i god kvalitet, som de kan bruge, uanset hvor de er i Power BI. Ejere af datasæt kan bevare kontrollen over, hvem der har adgang til deres data, ved hjælp af [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets). Lejeradministratorer har en ny lejerindstilling til at [styre brugen af datasæt på tværs af arbejdsområder](service-datasets-admin-across-workspaces.md).

## <a name="dataset-sharing-and-the-new-workspace-experience"></a>Deling af datasæt og den nye arbejdsområdeoplevelse

Oprettelse af rapporter baseret på datasæt i forskellige arbejdsområder og kopiering af rapporter til forskellige arbejdsområder er tæt forbundet med den [nye arbejdsområdeoplevelse](service-create-the-new-workspaces.md):

- Når du åbner datasætkataloget fra en ny arbejdsområdeoplevelse i tjenesten, viser datasætkataloget datasæt, der findes i Mit arbejdsområde og i den nye arbejdsområdeoplevelse. 
- Når du åbner datasætkataloget fra et klassisk arbejdsområde, kan du kun se datasættene i det pågældende arbejdsområde, ikke datasættene i andre arbejdsområder.
- I Desktop kan du publicere Live Connect-rapporter til forskellige arbejdsområder, så længe deres datasæt er i arbejdsområder med den nye oplevelse.
- Når du kopierer rapporter på tværs af arbejdsområder, skal destinationsarbejdsområdet være et arbejdsområde med den nye oplevelse.

## <a name="build-permission-for-datasets"></a>Tilladelsen Opret for datasæt

Med tilladelsestypen Opret kan du give andre i din organisation tilladelse til at oprette nyt indhold, f.eks. rapporter, dashboards og fastgjorte felter fra spørgsmål og svar, i et eksisterende datasæt. De kan også oprette nyt indhold i datasæt uden for Power BI, f.eks. Excel-ark via Analysér i Excel, XMLA og eksport. Læs mere om [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets).

## <a name="discover-datasets-preview"></a>Opdag datasæt (prøveversion)

Når du opretter en rapport oven på et eksisterende datasæt, skal du som det første oprette forbindelse til datasættet enten i Power-tjenesten eller i Power BI Desktop. Læs om [registrering af datasæt fra forskellige arbejdsområder (prøveversion)](service-datasets-discover-across-workspaces.md)

## <a name="copy-a-report"></a>Kopiér en rapport

Når du finder en rapport, du vil bruge i et arbejdsområde eller en app, kan du lave en kopi af den og derefter redigere den, så det passer til dine behov. Du behøver ikke at oprette datamodellen. Den er allerede oprettet for dig. Og det er meget nemmere at redigere en eksisterende rapport end at starte forfra. Læs mere om [kopiering af rapporter](service-datasets-copy-reports.md).

## <a name="promotion-and-certification"></a>Fremhævning og certificering

Hvis du opretter datasæt, opretter du et, som andre kan få glæde af, og du kan gøre det nemmere for dem at finde den ved at [fremhæve dit datasæt](service-datasets-promote.md). Du kan også anmode om, at eksperter i din organisation [certificerer dit datasæt](service-datasets-certify.md).

## <a name="licensing"></a>Licensering

De specifikke funktioner og oplevelser, der er baseret på funktioner for delte datasæt, er givet i licens i henhold til deres eksisterende scenarier.  Eksempel:

- Generelt kan alle registrere og oprette forbindelse til delte datasæt. Brugere uden en Pro-licens kan dog kun oprette forbindelse til datasæt, der er placeret i deres egen personlige version af Mit arbejdsområde eller i Premium-arbejdsområder.
- Hvis du vil fremhæve og certificere datasæt uden for personlige arbejdsområder, skal du have en Pro-licens, da du skal have en Pro-licens for at være medlem af et apparbejdsområde.
- Hvis du vil kopiere rapporter mellem arbejdsområder, skal du også her have en Pro-licens, da du skal have en Pro-licens for at være medlem af et apparbejdsområde.
- Hvis du vil kopiere rapporter fra en app, skal du have en Pro-licens, som er påkrævet for organisationsindholdspakker.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

- Hvis du vil oprette en rapport oven på et datasæt i et andet arbejdsområde, kræver det, at den nye arbejdsområdeoplevelse er begge steder: Rapporten skal være i en ny arbejdsområdeoplevelse og datasættet skal være i en ny arbejdsområdeoplevelse.
- I et klassisk arbejdsområde viser datasæts registreringsoplevelse kun datasættene i det pågældende arbejdsområde.
- Du kan oprette rapporter i apparbejdsområder, der er baseret på datasæt i et andet arbejdsområde. Men du kan ikke oprette en app for et arbejdsområde, der indeholder disse datasæt.
- Free-brugere i Desktop kan kun se datasæt fra Mit arbejdsområde og fra Premium-baserede arbejdsområder.
- Hvis du vil føje en rapport baseret på et delt datasæt til en app, skal du være medlem af datasættets arbejdsområde. Dette er et kendt problem.
- "Publicer på internettet" virker ikke for en rapport, der er baseret på et delt datasæt. Dette er tilsigtet.
- Hvis to personer er medlem af et arbejdsområde, der åbner et delt datasæt, er det er muligt, at kun én af dem kan se det relaterede datasæt i arbejdsområdet. Det er kun personer, der som minimum har læseadgang til datasættet, som kan se det delte datasæt. 

## <a name="next-steps"></a>Næste trin

- [Fremhæv datasæt](service-datasets-promote.md)
- [Certificer datasæt](service-datasets-certify.md)
- [Styr brugen af datasæt på tværs af arbejdsområder](service-datasets-admin-across-workspaces.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
