---
title: Yderligere køb kan være påkrævet – retningslinjer for Power BI-visualiseringer
description: Få mere at vide om, hvordan du kan publicere din brugerdefinerede visualisering i AppSource, så andre kan finde, købe og bruge den.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 097095cda1e0ffea4f43059351f22638c502e8b4
ms.sourcegitcommit: a2f274cfb392fe3b1b466a39ec7eaf58a7c5ce00
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/19/2019
ms.locfileid: "56408063"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Retningslinjer for Power BI-visualiseringer med ekstra køb

Indtil for nylig accepterede **Marketplace (AppSource)** kun gratis Power BI-visualiseringer. Denne politik ændres, så visualiseringer med prismærket "Yderligere køb kan være påkrævet" også kan sendes til **AppSource**. Yderligere køb kan være påkrævet. Visualiseringer svarer til tilføjelsesprogrammer som apptilkøb i Office Store. Udviklere kan også sende disse visualiseringer til certificering, når **AppSource**-teamet har godkendt dem, og når det er sikret, at de overholder certificeringskravene, som beskrevet i [artiklen om certificerede brugerdefinerede visualiseringer](../power-bi-custom-visuals-certified.md).

> [!Note]
> En visualisering kan kun certificeres, hvis den ikke har adgang til eksterne tjenester eller ressourcer.

> [!Note]
> Alle gratis visualiseringer bør bevare de samme gratis funktioner, som blev tilbudt tidligere. Du kan føje valgfrie avancerede betalte funktioner til de gamle gratis funktioner. Vi anbefaler, at du sender IAP-visualiseringer sammen med de avancerede funktioner som nye visualiseringer i stedet for at opdatere de gratis gamle.


## <a name="whats-changing-in-the-submission-process"></a>Hvad ændres i indsendelsesprocessen?

Udviklere uploader deres IAP-visualiseringer til AppSource via Seller Dashboard, på samme måde som de har gjort det med gratis visualiseringer. Hvis udviklere vil angive, at den indsendte visualisering har IAP-funktioner, skal de skrive følgende i noterne på Seller Dashboard: "Visualisering med apptilkøb". Udviklere skal også levere en licensnøgle eller token, så valideringsteamet kan validere IAP-funktionerne. Når visualiseringen er valideret og godkendt, angives "Yderligere køb kan være påkrævet" under prismulighederne for IAP-visualiseringen i AppSource.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Hvad er en Power BI-visualisering med IAP-funktioner?

En IAP-visualisering er en gratis visualisering, og den indeholder gratis funktioner, men har også yderligere funktioner, der kan anvendes mod ekstrabetaling. I beskrivelsen af visualiseringen skal udviklerne give brugerne besked om, hvilke funktioner der kræver yderligere køb, før de kan anvendes. I øjeblikket leverer Microsoft ikke oprindelige API'er til understøttelse af apptilkøb og tilføjelsesprogrammer. Udviklere kan bruge alle betalingssystemer fra tredjepart til disse køb. Se i vores [politik](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) for Store.

## <a name="logo-guidelines"></a>Retningslinjer for logo

I dette afsnit beskrives specifikationerne for tilføjelse af logoer og logotyper i visualiseringer.

> [!NOTE]
> Logoer er kun tilladt i redigeringstilstand. Logoer kan ikke vises i visningstilstand.

![definitioner](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![ting-der-skal-beholdes](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![ting-der-skal](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![størrelse-og-format ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![margener-og](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![redingeringstilstand](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Bedste praksis

### <a name="visual-landing-page"></a>Landingsside for visualisering

Brug landingssiden til at tydeliggøre over for brugerne, hvordan de kan bruge din visualisering, og hvor de kan købe licensen. Undlad at inkludere videoer, der udløses automatisk. Tilføj kun materiale, der hjælper med at forbedre brugeroplevelsen, f.eks. oplysninger eller links til oplysninger om licenskøb og brugen af IAP-funktioner.

### <a name="license-key-and-token"></a>Licensnøgle og -token

Af hensyn til brugerne skal du tilføje en licensnøgle eller tokenrelaterede felter øverst i formateringsruden, så de er lettere at finde for brugerne.

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger og få svar på spørgsmål under [Ofte stillede spørgsmål om visualiseringer med yderligere køb](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Næste trin

Du kan få mere at vide om, hvordan du kan publicere din brugerdefinerede visualisering i [AppSource](office-store.md), så andre kan finde og bruge den.
