---
title: Ofte stillede spørgsmål om brugerdefinerede visualiseringer i Power BI
description: Gennemse en liste med ofte stillede spørgsmål og svar om brugerdefinerede visualiseringer i Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: c17f9b9841335420db67abb62c92603bf804f275
ms.sourcegitcommit: 13fdc8d62960f20c6d9ca1ab292f98992b47083b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/18/2018
ms.locfileid: "53553898"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Ofte stillede spørgsmål om brugerdefinerede visualiseringer i Power BI

## <a name="organizational-custom-visuals"></a>Brugerdefinerede visualiseringer til virksomheden

### <a name="how-can-the-admin-manage-the-organizational-custom-visuals"></a>Hvordan kan administratoren administrere de brugerdefinerede visualiseringer til virksomheden?

Under fanen "Brugerdefinerede visualiseringer til virksomheder" på administrationsportalen kan administratoren se og [administrere alle de brugerdefinerede visualiseringer til virksomheden](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): tilføje, deaktivere, aktivere og slette.
Der er ikke længere grund til at dele disse visualiseringer via mail eller en delt mappe. Når visualiseringerne er udrullet i virksomhedens lager, kan brugerne nemt finde dem og importere de brugerdefinerede visualiseringer til virksomheden i deres rapporter direkte fra Power BI Desktop eller Power BI-tjenesten. Du kan finde de brugerdefinerede visualiseringer til virksomheden i det indbyggede lager (på skrivebordet og i tjenesten) under fanen *MIN ORGANISATION*. Når administratoren overfører en ny version af en brugerdefineret visualisering til virksomheden, får alle i organisationen den samme opdaterede version. Forfattere af rapporter behøver ikke at slette visualiseringen i deres rapporter for at få den nye version af disse visualiseringer, da alle rapporter, der bruger disse visualiseringer, opdateres automatisk. Opdateringsmekanismen svarer til visualiseringer på markedspladser.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Hvis en administrator uploader en brugerdefineret visualisering fra den offentlige markedsplads til virksomhedslageret, opdateres den så automatisk, når en leverandør opdaterer visualiseringen på den offentlige markedsplads?

Nej, der sker ingen automatisk opdatering fra den offentlige markedsplads.
Det er administratorens ansvar at opdatere versionen af de brugerdefinerede visualiseringer til virksomheden.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Er det muligt at deaktivere virksomhedslageret?

Nej, brugere får altid vist fanen "MIN ORGANIZATION" fra Power BI-skrivebordet og -tjenesten. Administratoren kan deaktivere eller slette alle brugerdefinerede visualiseringer til virksomheden fra administrationsportalen, hvilket medfører, at virksomhedslageret bliver tomt.
  
### <a name="if-the-administrator-disables-custom-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-custom-visuals"></a>Hvis administratoren deaktiverer brugerdefinerede visualiseringer fra administrationsportalen (lejerindstillinger), har brugerne så stadig adgang til de brugerdefinerede visualiseringer til virksomheden?

Ja, hvis administratoren deaktiverer de brugerdefinerede visualiseringer fra administrationsportalen, har det ingen indflydelse på virksomhedslageret. Nogle organisationer deaktiverer brugerdefinerede visualiseringer og aktiverer kun håndplukkede visualiseringer, der er importeret og overført af Power BI-administratoren til virksomhedslageret. Deaktivering af brugerdefinerede visualiseringer fra administrationsportalen gennemtvinges ikke i Power BI Desktop. Desktop-brugere kan stadig tilføje og bruge brugerdefinerede visualiseringer fra den offentlige markedsplads i deres rapporter. Men de offentlige brugerdefinerede visualiseringer stopper med at gengive, når de publiceres på Power BI-tjenesten, og der udstedes en passende fejl. Når du bruger Power BI-tjenesten, kan du ikke importere brugerdefinerede visualiseringer fra den offentlige markedsplads. Det er kun visualiseringer fra virksomhedslageret, der kan importeres, fordi indstillingen for de brugerdefinerede visualiseringer på administrationsportalen gennemtvinges i Power BI-tjenesten.

### <a name="why-does-the-organizational-store-and-organizational-custom-visuals-make-a-great-enterprise-solution"></a>Hvorfor er virksomhedslageret og brugerdefinerede visualiseringer til virksomheden en fantastisk virksomhedsløsning?

* Alle får den samme version af visualiseringer, der styres af Power BI-administratoren. Når administratoren opdaterer versionen af visualiseringer på administrationsportalen, får alle brugere i virksomheden automatisk den opdaterede version.

* Der er ikke længere grund til at dele visualiseringsfiler via mail eller delte mapper! Ét sted, som er synligt for alle medlemmer, der er logget på.

* Sikkerhed og understøttelse – nye versioner af brugerdefinerede visualiseringer til virksomheden opdateres automatisk i alle rapporter på samme måde som visualiseringer på markedspladsen.

* Brugere i organisationen, der anvender de brugerdefinerede visualiseringer til virksomheden, skal være logget på for at se og bruge de brugerdefinerede visualiseringer til virksomheden, hvilket er en sikkerhedsfaktor for organisationen.

* Administratorer kan styre, hvilke brugerdefinerede visualiseringer der skal være tilgængelige i organisationen.

* Administratorer kan aktivere/deaktivere visualiseringer til test fra administrationsportalen. Bedre håndhævelse af sikkerhed, da disse visualiseringer kun bliver tilladt for medlemmer af organisationen.

## <a name="certified-custom-visuals"></a>Certificerede brugerdefinerede visualiseringer

### <a name="what-are-certified-custom-visuals"></a>Hvad er certificerede brugerdefinerede visualiseringer?

Certificerede brugerdefinerede visualiseringer er visualiseringer på [markedspladsen](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals), der opfylder visse [angivne](power-bi-custom-visuals-certified.md) kodekrav og test udført af Power BI-teamet.  De udførte test er udviklet for at kontrollere, at visualiseringen ikke har adgang til eksterne tjenester eller ressourcer. Microsoft er dog ikke forfatteren af brugerdefinerede visualiseringer fra tredjepart. Vi råder kunderne til at kontakte forfatteren direkte for at kontrollere funktionaliteten af sådanne visualiseringer.

## <a name="visuals-with-additional-purchases"></a>Visualiseringer med ekstra køb

### <a name="what-is-a-visual-with-additional-purchases"></a>Hvad er en visualisering med ekstra køb?

En visualisering med ekstra køb svarer til tilføjelsesprogrammet apptilkøb (IAP) på markedspladsen. Disse tilføjelsesprogrammer har prismærket  **Yderligere køb kan være påkrævet**.

Brugerdefinerede visualiseringer med IAP er gratis brugerdefinerede visualiseringer, der kan downloades. Brugerne betaler ikke noget for at downloade disse brugerdefinerede visualiseringer fra markedspladsen. Visualiseringer med IAP tilbyder valgfri apptilkøb for avancerede funktioner.  

### <a name="whats-the-benefit-to-developers"></a>Hvad er fordelen for udviklere?

Brugerdefinerede visualiseringer med IAP i AppSource vil være synlige for de mange dagligt besøgende, hvilket resulterer i værdifuld trafik og øget opmærksomhed om dine brugerdefinerede visualiseringer med IAP, og for dig som udvikleren.

Hvis du indtil for nylig administrerede disse visualiseringer via dit websted, kan du nu sende dem til AppSource. Hvilket øger niveauet af registrering og synlighed for visualiseringerne med IAP i Power BI-community'et.

Visualiseringer i AppSource nyder godt af en kanal til direkte feedback fra de kunder, der bruger de brugerdefinerede visualiseringer med IAP, via systemet til anmeldelser og klassifikation i lageret.  

Når visualiseringen med IAP er blevet godkendt af AppSource-valideringsteamet, kan du også indsende disse visualiseringer til certificering. Det er en valgfri proces.  

Når en brugerdefineret visualisering er blevet certificeret, kan de brugerdefinerede visualiseringer med IAP eksporteres til PowerPoint og vises i de mails, som modtages, når en bruger abonnerer på rapportsider. Så i dag kan brugerdefinerede visualiseringer med IAP også certificeres og understøtte et ekstra funktionssæt, når visualiseringer med IAP indsendes til markedspladsen.  

### <a name="do-iap-visuals-need-to-be-certified"></a>Skal visualiseringer med IAP certificeres?

Certificeringsprocessen er valgfri. Det er op til udvikleren at beslutte, om vedkommendes brugerdefinerede visualisering med IAP skal certificeres eller ej på samme måde som med gratis visualiseringer.

### <a name="what-is-changing-in-the-submission-process"></a>Hvad ændres i indsendelsesprocessen?

Indsendelsesprocessen for brugerdefinerede visualiseringer med IAP til markedspladsen er den samme proces som for gratis visualiseringer. Det sker via Seller Dashboard.  Den eneste ændring i processen for indsendelse er, at udviklere skal angive følgende i udviklernoterne på Seller Dashboard: "Visualisering med apptilkøb". Du skal om nødvendigt også angive en licensnøgle/et licenstoken for at validere de betalte/avancerede funktioner.  

Der vil ikke være nogen ny indstilling på Seller Dashboard: *gratis med apptilkøb*. Du skal indsende dine visualiseringer med IAP som *gratis*.

Derudover kan du give brugerne besked om, hvad de kan forvente, ved at angive under den lange beskrivelse af dit lager, hvilke funktioner der er gratis, og hvilke funktioner der kræver ekstra køb for at fungere.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>Hvad skal jeg gøre, før jeg indsender min brugerdefinerede visualisering med IAP?

Hvis du arbejder på en brugerdefineret visualisering med IAP, eller du allerede har en, skal du kontrollere, at den opfylder retningslinjerne.  

Hvis du har et logo i den brugerdefinerede visualisering, skal du sørge for, at det opfylder retningslinjerne for logo (farve, placering, størrelse og udløsning af handling).

I retningslinjerne kan du også finde noter med bedste praksis.  

### <a name="can-i-get-my-iap-custom-visual-certified"></a>Kan jeg få min brugerdefinerede visualisering med IAP certificeret?

Ja, på samme måde som med gratis visualiseringer.  Når din brugerdefinerede visualisering med IAP er godkendt af AppSource-teamet, kan du indsende visualiseringen til certificeringsprocessen.

For at få visualiseringen certificeret skal den overholde kravene til certificering. Visualiseringen kan f.eks. ikke få adgang til eksterne tjenester til validering af licenser.

Husk, at certificering er en valgfri proces. Det er op til dig at beslutte, om du vil have din visualisering med IAP certificeret.

## <a name="additional-questions"></a>Yderligere spørgsmål

### <a name="how-to-get-support"></a>Hvordan får jeg support?

Du er meget velkommen til at kontakte supportteamet til brugerdefinerede visualiseringer: *pbicvsupport@microsoft.com* , hvis du har spørgsmål, kommentarer eller problemer.  

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger under [Fejlfinding af dine brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-troubleshoot.md).
