---
title: Retningslinjer for Power BI-visualiseringer
description: Få mere at vide om, hvordan du kan publicere din brugerdefinerede visualisering i AppSource, så andre kan finde, købe og bruge den.
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 03/10/2019
ms.openlocfilehash: 02ce5146a154583d784de8030a0b0ec84740fcb3
ms.sourcegitcommit: 8fda7843a9f0e8193ced4a7a0e5c2dc5386059a6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/18/2019
ms.locfileid: "58175461"
---
# <a name="guidelines-for-power-bi-visuals"></a>Retningslinjer for Power BI-visualiseringer

## <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Retningslinjer for Power BI-visualiseringer med ekstra køb

Indtil for nylig accepterede Marketplace (AppSource) kun gratis Power BI-visualiseringer. Denne politik er blevet ændret (december 2018), så du nu også kan indsende visualiseringer til AppSource, som har prismærket "Yderligere køb kan være påkrævet". 

Visualiseringer med "Yderligere køb kan være påkrævet" er ligesom tilføjelsesprogrammer med apptilkøb i Office Store. Udviklere kan også indsende disse visualiseringer til certificering, efter AppSource-teamet har godkendt dem, og de har kontrolleret, at de overholder certificeringskravene. Du kan finde flere oplysninger om kravene i [Certificerede brugerdefinerede visualiseringer](../power-bi-custom-visuals-certified.md).

> [!NOTE]
> En visualisering kan kun certificeres, hvis den ikke har adgang til eksterne tjenester eller ressourcer.

>[!IMPORTANT]  
> Hvis du opdaterer din visualisering fra gratis til "Yderligere køb kan være påkrævet", skal brugerne modtage det samme niveau af gratis funktionalitet som før opdateringen. Du kan tilføje valgfrie avancerede betalte funktioner udover de eksisterende gratis funktioner. Vi anbefaler, at du indsender visualiseringer med apptilkøb sammen med de avancerede funktioner som nye visualiseringer i stedet for at opdatere de eksisterende gratis.


## <a name="what-changed-in-the-submission-process"></a>Hvad er blevet ændret i indsendelsesprocessen?

Udviklere uploader deres IAP-visualiseringer til AppSource via Seller Dashboard, på samme måde som de har gjort det med gratis visualiseringer. Udviklere bør skrive følgende i noterne på Seller Dashboard for at angive, at den indsendte visualisering har funktioner med apptilkøb: "Visualisering med apptilkøb". Udviklere skal også levere en licensnøgle eller token, så valideringsteamet kan validere IAP-funktionerne. Efter visualiseringen er blevet valideret og godkendt, angives "Yderligere køb kan være påkrævet" under prismulighederne for visualiseringen med apptilkøb i AppSource.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Hvad er en Power BI-visualisering med IAP-funktioner?

En visualisering med apptilkøb er en **gratis** visualisering, der tilbyder **gratis funktioner**. Den indeholder også nogle avancerede funktioner, som man muligvis skal betale for, før de kan anvendes. I beskrivelsen af visualiseringen skal udviklerne give brugerne besked om, hvilke funktioner der kræver yderligere køb, før de kan anvendes. I øjeblikket leverer Microsoft ikke oprindelige API'er til understøttelse af apptilkøb og tilføjelsesprogrammer.

Udviklere kan bruge et hvilket som helst betalingssystem fra tredjepart til disse køb. Du kan finde flere oplysninger i [vores politik for Store](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads).

> [!NOTE]
> Vandmærker er ikke tilladt i de gratis funktioner eller gratis visualiseringer. Vandmærker må kun bruges på de betalte funktioner, der bruges uden en gyldig licens. Vi anbefaler at vise et pop op-vindue med alle de licensrelaterede oplysninger, hvis de avancerede betalte funktioner bruges uden en gyldig licens.  

## <a name="logo-guidelines"></a>Retningslinjer for logo

I dette afsnit beskrives specifikationerne for tilføjelse af logoer og logotyper i visualiseringer.

> [!IMPORTANT]
> Logoer er kun tilladt i **redigeringstilstand**. Logoer **må ikke** vises i visningstilstand.

![Definitioner](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![Husk følgende](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![Undgå følgende](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![Størrelse og format](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![Margener og størrelse](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![Redigeringstilstand](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Bedste praksis

### <a name="visual-landing-page"></a>Landingsside for visualisering

Brug landingssiden til at tydeliggøre over for brugerne, hvordan de kan bruge din visualisering, og hvor de kan købe licensen. Undlad at inkludere videoer, der udløses automatisk. Tilføj kun materiale, der hjælper med at forbedre brugeroplevelsen, f.eks. oplysninger eller links til oplysninger om licenskøb, og hvordan funktioner for apptilkøb bruges.

### <a name="license-key-and-token"></a>Licensnøgle og -token

Af hensyn til brugerne skal du tilføje en licensnøgle eller tokenrelaterede felter øverst i formateringsruden.

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger om visualiseringer under [Ofte stillede spørgsmål om visualiseringer med yderligere køb](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Næste trin

Du kan få mere at vide om, hvordan du kan publicere din brugerdefinerede visualisering i [AppSource](office-store.md), så andre kan finde og bruge den.
