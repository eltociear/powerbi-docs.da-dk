---
title: Publicer på internettet fra Power BI
description: Med Power BI Publicer på internettet kan du nemt integrere interaktive Power BI-visualiseringer online, f.eks. i blogindlæg, på websteder, via mails eller sociale medier på enhver enhed.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/16/2019
LocalizationGroup: Share your work
ms.openlocfilehash: 1b5dfc0b05595e96c9a297a5be3700e71cdbe229
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051573"
---
# <a name="publish-to-web-from-power-bi"></a>Publicer på internettet fra Power BI

Med Power BI'S **Publicer på internettet** indstilling, kan du nemt integrere interaktive Power BI-visualiseringer online, f.eks. som i blogindlæg, websteder, via mails eller sociale medier, fra en hvilken som helst enhed. Du kan også nemt redigere, opdatere eller fjerne deling af dine publicerede visualiseringer.

> [!WARNING]
> Når du bruger **Publicer på internettet**, alle på internettet kan få vist din publicerede rapport eller det visuelle element. Dette kræver ingen godkendelse og omfatter visning af detaljeniveau dine samlede rapporter. Inden du publicerer en rapport, Sørg for, at det er ok at dele dataene og visualiseringerne offentligt. Publicer ikke fortrolige eller beskyttede oplysninger. Hvis du er i tvivl, kan du kontrollere din organisations politikker inden publiceringen.

>[!Note]
>Hvis du vil integrere dit indhold på en sikker måde på en intern portal eller et websted, skal du bruge indstillingen [Integrer](service-embed-secure.md) eller [Integrer i SharePoint Online](service-embed-report-spo.md). Dette sikrer, at alle tilladelser og datasikkerhed håndhæves, når brugerne får vist dine interne data.

## <a name="how-to-use-publish-to-web"></a>Sådan bruger du Publicer på internettet

**Publicer på internettet** er tilgængelig for rapporter i din personlige arbejdsområder eller gruppearbejdsområder kan du redigere.  Det er ikke tilgængelige for rapporter, der er delt med dig, eller dem, der afhænger af sikkerhed på rækkeniveau til at sikre data. Se de [ **begrænsninger** ](#limitations) afsnittet nedenfor for at få en komplet liste over tilfælde hvor **Publicer på internettet** understøttes ikke. Gennemse den **advarsel** tidligere i denne artikel, før du bruger **Publicer på internettet**.

Følgende *korte video* viser, hvordan denne funktion fungerer. Prøv det selv i nedenstående trin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>

I fremgangsmåden nedenfor beskrives det, hvordan du bruger **Publicer på internettet**.

1. Åbn en rapport i arbejdsområdet, som du kan redigere og vælge **fil > Publicer på internettet**.

   ![PtW1](media/service-publish-to-web/publish_to_web1.png)

2. Gennemse dialogboksen indhold og vælg **Opret integreringskode**.

   ![PtW2](media/service-publish-to-web/publish_to_web2_ga.png)

3. Gennemse advarslen, som vist her, og Bekræft, at dataene er i orden at integrere i et offentligt websted. Hvis det er tilfældet, skal du vælge **Publicer**.

   ![PtW3](media/service-publish-to-web/publish_to_web3_ga.png)

4. Der vises en dialogboks med et link. Du kan sende dette link i en mail, integrere den i f.eks en iFrame-koden eller Indsæt den direkte på en webside eller blog.

   ![PtW4](media/service-publish-to-web/publish_to_web4.png)

5. Hvis du tidligere har oprettet en integreringskode for en rapport, og du vælger **Publicer på internettet**, kan du ikke se Dialogerne i trin 2-4. I stedet den **integreringskode** dialogboksen vises:

   ![PtW5](media/service-publish-to-web/publish_to_web5.png)

   Du kan kun oprette én integreringskode til hver enkelt rapport.


## <a name="tips-and-tricks-for-view-modes"></a>Tip og gode råd til visningstilstande

Når du integrerer indhold i et blogindlæg, skal det typisk passe inden for en bestemt skærmstørrelse.  Du kan tilpasse højden og bredden i iFrame-koden efter behov. Men du skal sikre, at din rapport passer inden for det angivne iFrame-område, så du skal også angive en passende visningstilstand, når du redigerer rapporten.

Følgende tabel indeholder vejledning om visningstilstanden, og hvordan den vises, når den er integreret.

| Visningstilstand | Sådan ser den ud, når den er integreret |
| --- | --- |
| ![PtW6b](media/service-publish-to-web/publish_to_web6b.png) |**Tilpas til siden** vil respekterer din rapport sidehøjde og bredde. Hvis du indstiller siden til 'Dynamiske' forhold som f.eks. 16:9 eller 4:3, skaleres dit indhold for at passe inden for iFrame. Når den er integreret i en iFrame, ved hjælp af **Tilpas til siden** kan resultere i **letterboxing**, hvor en grå baggrund vises i iFrame-områder efter at indholdet er skaleret til at passe inden for iFrame. Angiv din iFrame højde og bredde hensigtsmæssigt for at minimere letterboxing. |
| ![PtW6d](media/service-publish-to-web/publish_to_web6d.png) |**Faktisk størrelse** sikrer, at rapporten bevarer sin størrelse som indstillet på rapportsiden. Dette kan medføre rullepaneler i din iFrame. Angiv iFrame højden og bredden for at undgå rullepaneler. |
| ![PtW6c](media/service-publish-to-web/publish_to_web6c.png) |**Tilpas til bredde** sikrer, at indholdet passer inden for den iFrame vandrette område. En kant vises stadig, men indholdet skaleres til at bruge alle tilgængelig vandret plads. |

## <a name="tips-and-tricks-for-iframe-height-and-width"></a>Tip og tricks til højde og bredde på iFrame

A **Publicer på internettet** integrerede kode ser ud som følgende:

![PtW7](media/service-publish-to-web/publish_to_web7.png)
 
Du kan redigere bredden og højden manuelt for at sikre, at det er præcis, som du ønsker den til at passe på den side, hvor du integrerer den.

For at opnå passe mere perfekt, kan du prøve at føje 56 pixel til højde for den iFrame passer til den aktuelle størrelse af den nederste linje. Hvis rapportsiden bruger den dynamiske størrelse, indeholder tabellen herunder nogle størrelser, du kan bruge til at opnå en tilpasning uden letterboxing.

| Forhold | Størrelse | Dimension (bredde x højde) |
| --- | --- | --- |
| 16:9 |Lille |640 x 416 px |
| 16:9 |Mellem |800 x 506 px |
| 16:9 |Stor |960 x 596 px |
| 4:3 |Lille |640 x 536 px |
| 4:3 |Mellem |800 x 656 px |
| 4:3 |Stor |960 x 776 px |

## <a name="manage-embed-codes"></a>Administrer integreringskoder

Når du opretter en **Publicer på internettet** integreringskode, du kan administrere din koder fra den **indstillinger** menuen i Power BI. Administration af integreringskoder giver mulighed for at fjerne destinationens visuelle element eller rapport for en kode (ubrugelig integreringskoden), eller hente integreringskoden.

1. Du administrerer dine integreringskoder for **Publicer på internettet** ved at åbne tandhjulet **Indstillinger** og vælge **Håndter indlejringskoder**.

   ![PtW8](media/service-publish-to-web/publish_to_web8.png)

2. Dine integreringskoder, vises.

   ![PtW9](media/service-publish-to-web/publish_to_web9.png)

3. Du kan enten hente eller slette en integreringskode. Hvis du sletter det deaktiverer links til rapporten eller Visualiseringen.

   ![PtW10](media/service-publish-to-web/publish_to_web10.png)

4. Hvis du vælger **slette**, du bliver bedt om en bekræftelse.

   ![PtW11](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Opdateringer af rapporter og data

Når du har oprettet din **Publicer på internettet** integreringskoden og del den, rapporten er blevet opdateret med ændringerne, du foretager, og der er linket til koden aktivt med det samme, og alle, der åbner linket kan se den. Efter denne indledende handling, kan opdateringer af rapporter eller visuelle elementer dog tage ca. én time, før de bliver synlig for dine brugere. Hvis dine opdateringer skal være tilgængelige med det samme, kan du slette integreringskoden og oprette en ny. Hvis du vil vide mere, kan du se de [ **Sådan fungerer det** ](#howitworks) afsnit senere i denne artikel. 

## <a name="data-refresh"></a>Opdatering af data

Dataopdateringer afspejles automatisk i din integrerede rapport eller det visuelle element. Det kan tage ca. 1 time, før opdaterede data kan ses fra integreringskoder. Hvis du vil deaktivere automatisk opdatering, kan du vælge **opdateres ikke** i tidsplanen for det datasæt, der bruger rapporten.  

## <a name="custom-visuals"></a>Brugerdefinerede visualiseringer

Brugerdefinerede visuelle elementer, der understøttes i **Publicer på internettet**. Når du bruger **Publicer på internettet**, brugere, som du deler dit publicerede visuelle element behøver ikke at aktivere brugerdefinerede visuelle elementer til at få vist rapporten.

## <a name="limitations"></a>Begrænsninger

**Publicer på internettet** understøttes for langt de fleste data datakilder og rapporter i Power BI-tjenesten, men følgende **ikke understøttes i øjeblikket eller tilgængelige** med **Publicer på internettet** :

- Rapporter med sikkerhed på rækkeniveau.
- Rapporter, der bruger en vilkårlig Live Connection-datakilde, herunder Analysis Services Tabular, der hostes i det lokale miljø, Analysis Service Multidimensional og Azure Analysis Services.
- Rapporter, der er delt med dig direkte eller via en organisationsindholdspakke.
- Rapporter i en gruppe, hvor du ikke er redigeringsmedlem.
- Visuelle "R"-elementer understøttes ikke i øjeblikket i **Publicer på internettet** rapporter.
- Eksport af Data fra visualiseringer i en rapport, der er publiceret på internettet.
- ArcGIS Maps for Power BI-visualiseringer.
- Rapporter, der indeholder rapportniveau DAX-målinger.
- Enkelt-logon-forespørgsel datamodeller.
- [Fortrolige eller beskyttede oplysninger](#publish-to-web-from-power-bi).
- Muligheden for automatisk godkendelse, der er tilgængelig med indstillingen **Integrer** fungerer ikke sammen med Power BI JavaScript API. Til Power BI JavaScript API kan du bruge den strategi til integreringen, at [brugeren ejer dataene](developer/embed-sample-for-your-organization.md). Få mere at vide om, [brugeren ejer dataene](developer/embed-sample-for-your-organization.md).

## <a name="tenant-setting"></a>Lejerindstillinger

Power BI-administratorer kan aktivere eller deaktivere den **Publicer på internettet** funktion. De kan desuden begrænse adgang til bestemte grupper, som kan påvirke din mulighed for at oprette en integreringskode.

|Udvalgt |Aktiveret for hele organisationen |Deaktiveret for hele organisationen |Specifikke sikkerhedsgrupper   |
|---------|---------|---------|---------|
|**Publicer på internettet** under rapportens **fil** menuen|Aktiveret for alle|Ikke synligt for alle|Kun synligt for godkendte brugere eller grupper.|
|**Håndter integreringskoder** under **Indstillinger**|Aktiveret for alle|Aktiveret for alle|Aktiveret for alle.<br><br>Indstillingen * **Slet** er kun synlig for godkendte brugere eller grupper.<br>* **Hent koder** er aktiveret for alle.|
|**Integrer koder** i administrationsportalen|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret|Status vises som **Deaktiveret**|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret<br><br>Hvis en bruger ikke er godkendt baseret på lejeren indstilling, vises status som **krænket**.|
|Eksisterende publicerede rapporter|Alle aktiveret|Alle deaktiveret|Rapporter fortsætter med at gengive for alle.|

## <a name="understanding-the-embed-code-status-column"></a>Om kolonnen med status for integreringskoder

Den **Håndter indlejringskoder** -siden omfatter en statuskolonne. Som standard integreringskoder er **aktive**, men du kan også være en af de statusser, der er anført nedenfor.

| Status | Beskrivelse |
| --- | --- |
| **Aktiv** |Rapporten er tilgængelig, og internetbrugere kan få vist og interagere med den. |
| **Blokeret** |Rapportens indhold overtræder den [Power BI servicebetingelser](https://powerbi.microsoft.com/terms-of-service). Microsoft har blokeret for den. Hvis du mener, at indholdet blev blokeret ved en fejl, kan du kontakte support. |
| **Understøttes ikke** |Rapportens datasæt bruger sikkerhed på rækkeniveau, eller en anden konfiguration, der ikke understøttes. Se de [ **begrænsninger** ](#limitations) afsnit en fuldstændig liste. |
| **Krænket** |Integreringskoden er uden for den definerede lejerpolitik. Dette sker typisk, når en integreringskode blev oprettet og derefter den **Publicer på internettet** lejeren indstilling blev ændret for at udelade den bruger, der ejer integreringskoden. Hvis lejerindstillingen er deaktiveret, eller brugeren er ikke længere tilladt at oprette integreringskoder, eksisterende integrerede koder Vis en **krænket** status. |

## <a name="how-to-report-a-concern-with-publish-to-web-content"></a>Sådan rapporterer du et problem med indhold via Publicer på internettet

At rapportere et problem, der er relateret til **Publicer på internettet** indhold, der er integreret i et websted eller en blog, skal du bruge den **Flag** på den nederste linje, som vist på følgende billede. Du bliver bedt om at sende en mail til Microsoft forklarer dit spørgsmål. Microsoft vil evaluere det indhold, der er baseret på Power BI servicebetingelser og foretage de nødvendige handlinger.

Hvis du vil rapportere et problem, skal du vælge den **flag** ikon i den nederste linje i den **Publicer på internettet** rapport, du kan se.

![PtW12](media/service-publish-to-web/publish_to_web12_ga.png)

## <a name="licensing-and-pricing"></a>Licenser og priser

Du skal være Microsoft Power BI-bruger for at anvende **Publicer på internettet**. Din rapport seere behøver ikke at være Power BI-brugere.

<a name="howitworks"></a>
## <a name="how-it-works-technical-details"></a>Sådan fungerer det (tekniske detaljer)

Når du opretter en integrerede kode ved hjælp af **Publicer på internettet**, gøres rapporten synlig for brugere på internettet. Det er offentligt tilgængelige, så du kan forvente, at brugerne nemt dele rapporten via sociale medier på et senere tidspunkt. Når brugere får vist rapporten, enten ved at åbne den direkte offentlige URL-adresse eller se den integreret på en webside eller blog, cachelagrer Power BI rapportdefinitionen og resultaterne af de forespørgsler, der kræves for at få vist rapporten. Dette sikrer, at tusindvis af samtidige brugere kan få vist rapporten uden at påvirke ydeevnen.

Cachelageret er langvarigt, så hvis du opdaterer rapportdefinitionen (f.eks, hvis du ændrer dens visningstilstand) eller opdaterer rapportdataene, kan det tage ca. én time, før ændringerne afspejles i versionen af dine brugere få vist rapporten. Det anbefales derfor, at du planlægger dit arbejde på forhånd og først opretter integreringskoden for **Publicer på internettet**, når du er tilfreds med indstillingerne.

## <a name="next-steps"></a>Næste trin

- [Webdel til rapporten SharePoint Online](service-embed-report-spo.md) 

- [Integrer en rapport på en sikker portal eller et websted](service-embed-secure.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
