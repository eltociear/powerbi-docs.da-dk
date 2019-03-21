---
title: Ofte stillede spørgsmål om brugerdefinerede Power BI-visuals
description: Gennemse en liste med ofte stillede spørgsmål og svar om brugerdefinerede Power BI-visuals
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: 9c5d2665f012881f951a186c3ec8c9fd94031a28
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/18/2019
ms.locfileid: "57980352"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Ofte stillede spørgsmål om brugerdefinerede Power BI-visuals

## <a name="organizational-custom-visuals"></a>Brugerdefinerede visuals til virksomheden

### <a name="how-can-the-admin-manage-the-organizational-custom-visuals"></a>Hvordan kan administratoren administrere de brugerdefinerede visualiseringer til virksomheden?

I Administrationsportal under fanen "Brugerdefinerede visuals til virksomheden" kan administratoren se og [administrere alle organisationsmæssige brugerdefinerede visualiseringer i virksomheden](service-admin-portal.md#organizational-visuals): tilføje, deaktivere, aktivere og slette.
Der er ikke længere grund til at dele disse visualiseringer via mail eller en delt mappe. Når visualiseringerne er udrullet i virksomhedens lager, kan brugerne nemt finde dem og importere de brugerdefinerede visualiseringer til virksomheden i deres rapporter direkte fra Power BI Desktop eller Power BI-tjenesten. Du kan finde de brugerdefinerede visualiseringer til virksomheden i det indbyggede lager (på skrivebordet og i tjenesten) under fanen *MIN ORGANISATION*. Når administratoren overfører en ny version af en brugerdefineret visual til virksomheden, får alle i organisationen den samme opdaterede version. Forfattere af rapporter behøver ikke at slette visualiseringen i deres rapporter for at få den nye version af disse visualiseringer, da alle rapporter, der bruger disse visualiseringer, opdateres automatisk. Opdateringsmekanismen svarer til visuals på markedspladser.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Hvis en administrator uploader en brugerdefineret visualisering fra den offentlige markedsplads til virksomhedslageret, opdateres den så automatisk, når en leverandør opdaterer visualiseringen på den offentlige markedsplads?

Nej, der sker ingen automatisk opdatering fra den offentlige markedsplads.
Det er administratorens ansvar at opdatere versionen af de brugerdefinerede visualiseringer til virksomheden.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Er det muligt at deaktivere virksomhedslageret?

Nej, brugere får altid vist fanen "MIN ORGANIZATION" fra Power BI-skrivebordet og -tjenesten. Administratoren kan deaktivere eller slette alle brugerdefinerede visuals til virksomheden fra administrationsportalen, hvilket medfører, at virksomhedslageret bliver tomt.
  
### <a name="if-the-administrator-disables-custom-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-custom-visuals"></a>Hvis administratoren deaktiverer brugerdefinerede visualiseringer fra administrationsportalen (lejerindstillinger), har brugerne så stadig adgang til de brugerdefinerede visualiseringer til virksomheden?

Ja, hvis administratoren deaktiverer de brugerdefinerede visuals fra administrationsportalen, har det ingen indflydelse på virksomhedslageret. Nogle organisationer deaktiverer brugerdefinerede visuals og aktiverer kun håndplukkede visuals, der er importeret og overført af Power BI-administratoren til virksomhedslageret. Deaktivering af brugerdefinerede visualiseringer fra administrationsportalen gennemtvinges ikke i Power BI Desktop. Desktop-brugere kan stadig tilføje og bruge brugerdefinerede visualiseringer fra den offentlige markedsplads i deres rapporter. Men de offentlige brugerdefinerede visuals stopper med at gengive, når de publiceres på Power BI-tjenesten, og der udstedes en passende fejl. Når du bruger Power BI-tjenesten, kan du ikke importere brugerdefinerede visualiseringer fra den offentlige markedsplads. Det er kun visuals fra virksomhedslageret, der kan importeres, fordi indstillingen for de brugerdefinerede visuals i administrationsportalen gennemtvinges i Power BI-tjenesten.

### <a name="why-does-the-organizational-store-and-organizational-custom-visuals-make-a-great-enterprise-solution"></a>Hvorfor er virksomhedslageret og brugerdefinerede visualiseringer til virksomheden en fantastisk virksomhedsløsning?

* Alle får den samme version af visuals, der styres af Power BI-administratoren. Når administratoren opdaterer versionen af visuals på administrationsportalen, får alle brugere i virksomheden automatisk den opdaterede version.

* Der er ikke længere grund til at dele visualfiler via mail eller delte mapper! Ét sted, som er synligt for alle medlemmer, der er logget på.

* Sikkerhed og understøttelse – nye versioner af brugerdefinerede visuals til virksomheden opdateres automatisk i alle rapporter på samme måde som visuals på markedspladsen.

* Brugere i organisationen, der anvender de brugerdefinerede visuals til virksomheden, skal være logget på for at se og bruge de brugerdefinerede visuals til virksomheden, hvilket er en sikkerhedsfaktor for organisationen.

* Administratorer kan styre, hvilke brugerdefinerede visuals der skal være tilgængelige i organisationen.

* Administratorer kan aktivere/deaktivere visuals til test fra administrationsportalen. Bedre håndhævelse af sikkerhed, da disse visuals kun bliver tilladt for medlemmer af organisationen.

## <a name="certified-custom-visuals"></a>Certificerede brugerdefinerede visuals

### <a name="what-are-certified-custom-visuals"></a>Hvad er certificerede brugerdefinerede visualiseringer?

Certificerede brugerdefinerede visualiseringer er visualiseringer på [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals), der opfylder visse [angivne](power-bi-custom-visuals-certified.md) kodekrav og test udført af Power BI-teamet.  De udførte test er udviklet til at kontrollere, at visualiseringen ikke har adgang til eksterne tjenester eller ressourcer. Microsoft er dog ikke forfatter af brugerdefinerede visualiseringer fra tredjepart, og vi råder kunderne til at kontakte forfatteren direkte for at bekræfte funktionaliteten af sådanne visualiseringer.

### <a name="what-tests-are-done-during-the-certification-process"></a>Hvilke test udføres under certificeringsprocessen?

Test under certificeringsprocessen omfatter, men er ikke begrænset til: Kodegennemgang, analyse af statisk kode, datalækage, datafuzzytest, indtrængningstest, test af adgang til XSS, ondsindet datainjektion, inputvalidering og funktionstest.
 
### <a name="do-you-certify-visuals-every-submission"></a>Certificerer I visualiseringer ved hver indsendelse?

Ja. Hver gang en ny version af en certificeret visualisering sendes til Marketplace, undergår versionsopdateringen af visualiseringen de samme certificeringskontroller.

Bemærkning til udviklere! Hvis du sender en versionsopdatering af en certificeret visualisering, behøver du ikke at sende en separat mail ligesom ved [anmodningen om førstegangscertificering.](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified#process-for-submitting-a-custom-visual-for-certification) Certificering af versionsopdateringen sker automatisk, og evt. overtrædelser, som medfører en afvisning, sendes i en mail med en forklaring om, hvad der skal rettes. 

### <a name="is-it-possible-that-a-certified-visual-stops-being-certified-with-a-new-update"></a>Kan det ske, at en certificeret visualisering holder op med at være certificeret i forbindelse med en ny opdatering?

Nej, det kan ikke ske. Certificeringen af en certificeret visualisering kan ikke fjernes i forbindelse med en ny opdatering. Opdateringen afvises.
 
### <a name="do-i-need-to-share-my-code-in-public-repository-if-i-am-submitting-to-the-certification-process"></a>Skal jeg dele min kode på et offentligt lager, hvis jeg indsender til certificering?

Nej, du behøver ikke at dele din kode offentligt. Du skal dog give os læserettigheder til at kontrollere visualiseringskoden. F.eks. private lagre i GitHub.
 
### <a name="do-we-have-to-publishhttpsdocsmicrosoftcompower-bideveloperoffice-store-the-visual-in-the-marketplacehttpsappsourcemicrosoftcommarketplaceappspage1productpower-bi-visuals-to-certify-it"></a>Skal vi [publicere](https://docs.microsoft.com/power-bi/developer/office-store) visualiseringen på [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) for at få den certificeret?

Ja. Det er et obligatorisk krav til certificering at publicere visualiseringen på Marketplace først.
Hvis du vil certificere en brugerdefineret visualisering, skal den være på vores servere. Vi kan ikke certificere private visualiseringer.
 
### <a name="how-long-does-it-take-to-certify-my-visual"></a>Hvor lang tid tager det at certificere min visualisering?

Det kan tage op til to uger for en opdateret version. Det kan tage op til tre uger for en ny indsendelse (førstegangscertificering). 

### <a name="does-the-certification-process-ensure-that-no-data-leakage-occurs"></a>Sikrer certificeringsprocessen, at der ikke opstår datalækage?

De udførte test er udviklet til at kontrollere, at visualiseringen ikke har adgang til eksterne tjenester eller ressourcer. Microsoft er dog ikke forfatter af brugerdefinerede visualiseringer fra tredjepart, og vi råder kunderne til at kontakte forfatteren direkte for at bekræfte funktionaliteten af sådanne visualiseringer.
 
### <a name="are-uncertified-custom-visuals-safe-to-use"></a>Er det sikkert at anvende brugerdefinerede visualiseringer, der ikke er certificerede?

Brugerdefinerede visualiseringer, der ikke er certificerede, er ikke nødvendigvis ensbetydende med usikre visualiseringer.
Nogle visualiseringer er ikke certificeret, fordi de ikke er i overensstemmelse med et eller flere af [certificeringskravene](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Det kan f.eks. være i forbindelse med oprettelse af forbindelse til en ekstern tjeneste, som f.eks. kortvisualiseringer eller visualiseringer, der anvender kommercielle biblioteker.
 
## <a name="visuals-with-additional-purchases"></a>Visualiseringer med ekstra køb

### <a name="what-is-a-visual-with-additional-purchases"></a>Hvad er en visualisering med ekstra køb?

En visualisering med ekstra køb svarer til tilføjelsesprogrammet apptilkøb (IAP) på markedspladsen. Disse tilføjelsesprogrammer har prismærket **Yderligere køb kan være påkrævet**.

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
> [!Note]
> Alle gratis visualiseringer bør bevare de samme gratis funktioner, som blev tilbudt tidligere. Du kan føje valgfrie avancerede betalte funktioner til de gamle gratis funktioner. Vi anbefaler, at du sender IAP-visualiseringer sammen med de avancerede funktioner som nye visualiseringer i stedet for at opdatere de gratis gamle.

### <a name="can-i-get-my-iap-custom-visual-certified"></a>Kan jeg få min brugerdefinerede visualisering med IAP certificeret?

Ja, på samme måde som med gratis visualiseringer.  Når din brugerdefinerede visualisering med IAP er godkendt af AppSource-teamet, kan du indsende visualiseringen til certificeringsprocessen.

For at få visualiseringen certificeret skal den overholde kravene til certificering. Visualiseringen kan f.eks. ikke få adgang til eksterne tjenester til validering af licenser.

Husk, at certificering er en valgfri proces. Det er op til dig at beslutte, om du vil have din visualisering med IAP certificeret.

## <a name="additional-questions"></a>Yderligere spørgsmål

### <a name="how-to-get-support"></a>Hvordan får jeg support?

Du er meget velkommen til at kontakte supportteamet til brugerdefinerede visualiseringer: *pbicvsupport@microsoft.com* , hvis du har spørgsmål, kommentarer eller problemer.  

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger under [Fejlfinding af dine brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-troubleshoot.md).
