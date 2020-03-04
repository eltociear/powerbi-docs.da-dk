---
title: Publicer på internettet fra Power BI
description: Med Power BI Publicer på internettet kan du nemt integrere interaktive Power BI-visualiseringer online, f.eks. i blogindlæg, på websteder, via mails eller sociale medier på enhver enhed.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/25/2020
LocalizationGroup: Share your work
ms.openlocfilehash: 34754f413cd6bb8e520ff8d7f2c9d4a28da73ef5
ms.sourcegitcommit: 032a77f2367ca937f45e7e751997d7b7d0e89ee2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609937"
---
# <a name="publish-to-web-from-power-bi"></a>Publicer på internettet fra Power BI

Med Power BI-indstillingen **Publicer på internettet** kan du nemt integrere interaktive Power BI-visualiseringer online, f.eks. i blogindlæg, på websteder, via mails eller sociale medier, fra en hvilken som helst enhed. Du kan også nemt redigere, opdatere eller stoppe deling af dine publicerede visualiseringer.

> [!WARNING]
> Når du bruger **Publicer på internettet**, kan alle på internettet se den rapport eller det visuelle element, som du har publiceret. Dette kræver ingen godkendelse og omfatter visning af data på detaljeniveau, der er aggregeret i dine rapporter. Inden du publicerer en rapport, skal du sikre dig, at du har ret til at dele dataene og visualiseringerne offentligt. Publicer ikke fortrolige eller beskyttede oplysninger. Hvis du er i tvivl, kan du kontrollere din organisations politikker inden publiceringen.

>[!Note]
>Hvis du vil integrere dit indhold på en sikker måde på en intern portal eller et websted, skal du bruge indstillingen [Integrer](service-embed-secure.md) eller [Integrer i SharePoint Online](service-embed-report-spo.md). Dette sikrer, at alle tilladelser og datasikkerhed håndhæves, når brugerne får vist dine interne data.

## <a name="how-to-use-publish-to-web"></a>Sådan bruger du Publicer på internettet

**Publicer på internettet** er tilgængelig for rapporter, som du kan redigere i dine personlige arbejdsområder eller gruppearbejdsområder.  Indstillingen er ikke tilgængelig for rapporter, der er delt med dig, eller dem, der bruger sikkerhed på rækkeniveau til at beskytte data. Se afsnittet [**Begrænsninger**](#limitations) herunder for at få vist en fuldstændig liste over situationer, hvor **Publicer på internettet** ikke understøttes. Gennemgå **advarslen** tidligere i denne artikel, før du bruger **Publicer på internettet**.

I følgende korte video kan du se, hvordan denne funktion virker. Prøv det derefter selv i nedenstående trin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>

I fremgangsmåden nedenfor beskrives det, hvordan du bruger **Publicer på internettet**.

1. Åbn en rapport i arbejdsområdet, som du kan redigere, og vælg **Filer > Publicer på internettet**.

   ![PtW1](media/service-publish-to-web/publish_to_web1.png)
   
2. Kontakt din [Power BI-administrator](service-admin-role.md), hvis vedkommende ikke har givet dig tilladelse til at oprette integreringskoder

   ![PtW1](media/service-publish-to-web/publish_to_web_admin_prompt.png)
   
   Hvis du har brug for hjælp til at finde den person, der kan aktivere Publicer på internettet i din organisation, skal du [se disse tip](#how-to-find-your-power-bi-administrator).

3. Gennemse dialogboksens indhold, og vælg **Opret integreringskode**.

   ![PtW2](media/service-publish-to-web/publish_to_web2_ga.png)

4. Gennemgå advarslen, som vises her, og bekræft, at det er i orden at integrere dataene på et offentligt websted. Vælg **Publicer**, hvis det er tilfældet.

   ![PtW3](media/service-publish-to-web/publish_to_web3_ga.png)

5. Der vises en dialogboks med et link. Du kan sende dette link i en mail, integrere det i kode, f.eks. en iFrame-kode, eller indsætte det direkte på en webside eller i en blog.

   ![PtW4](media/service-publish-to-web/publish_to_web4.png)

6. Hvis du tidligere har oprettet en integreringskode for en rapport, og du vælger **Publicer på internettet**, kan du ikke se dialogboksene i trin 2-4. I stedet vises dialogboksen **Integreringskode**:

   ![PtW5](media/service-publish-to-web/publish_to_web5.png)

   Du kan kun oprette én integreringskode til hver enkelt rapport.


## <a name="tips-and-tricks-for-view-modes"></a>Tip og tricks til visningstilstande

Når du integrerer indhold i et blogindlæg, skal det typisk passe inden for en bestemt skærmstørrelse.  Du kan tilpasse højden og bredden i iFrame-koden efter behov. Men du skal sikre, at din rapport passer inden for det angivne iFrame-område, så du skal også angive en passende visningstilstand, når du redigerer rapporten.

Følgende tabel indeholder vejledning om visningstilstanden, og hvordan den vises, når den er integreret.

| Visningstilstand | Sådan ser den ud, når den er integreret |
| --- | --- |
| ![PtW6b](media/service-publish-to-web/publish_to_web6b.png) |**Tilpas til siden** beskytter sidehøjden og -bredden i din rapport. Hvis du indstiller siden til *dynamiske* forhold, f.eks. 16:9 eller 4:3, skaleres indholdet, så det passer inden for iFrame-koden. Ved integration i en iFrame kan brug af **Tilpas til siden** resultere i *letterboxing*, hvor en grå baggrund vises i iFrame-områder, efter at indholdet er skaleret til at passe inden for iFrame. Du minimerer letterboxing ved at angive passende højde og bredde for din iFrame. |
| ![PtW6d](media/service-publish-to-web/publish_to_web6d.png) |**Faktisk størrelse** sikrer, at rapporten bevarer sin størrelse som angivet på rapportsiden. Dette kan medføre, at der vises rullepaneler i din iFrame. Angiv højden og bredden på iFrame for at undgå rullepaneler. |
| ![PtW6c](media/service-publish-to-web/publish_to_web6c.png) |**Tilpas til bredde** sikrer, at indholdet fylder det vandrette område i din iFrame. Der vises stadig en kant, men indholdet skaleres til at bruge al tilgængelig vandret plads. |

## <a name="tips-and-tricks-for-iframe-height-and-width"></a>Tip og tricks til højde og bredde på iFrame

En integreringskode for **Publicer på internettet** ser ud som vist i følgende eksempel:

![PtW7](media/service-publish-to-web/publish_to_web7.png)
 
Du kan redigere bredden og højden manuelt for at sikre, at den er præcis, som du vil have den, så den passer på den side, du integrerer den på.

For at opnå en mere perfekt pasform kan du prøve at føje 56 pixel til højden på din iFrame for at imødekomme den aktuelle størrelse af den nederste linje. Hvis rapportsiden bruger den dynamiske størrelse, indeholder tabellen herunder nogle størrelser, du kan bruge til at opnå en tilpasning uden letterboxing.

| Forhold | Størrelse | Dimension (bredde x højde) |
| --- | --- | --- |
| 16:9 |Lille |640 x 416 px |
| 16:9 |Mellem |800 x 506 px |
| 16:9 |Stor |960 x 596 px |
| 4:3 |Lille |640 x 536 px |
| 4:3 |Mellem |800 x 656 px |
| 4:3 |Stor |960 x 776 px |

## <a name="manage-embed-codes"></a>Administrer integreringskoder

Når du har oprettet en integreringskode for **Publicer på internettet**, kan du administrere dine koder fra menuen **Indstillinger** i Power BI. Administration af integreringskoder gør det muligt at fjerne destinationens visuelle element eller rapport for en kode (hvilket gør integreringskoden ubrugelig) eller at hente integreringskoden.

1. Du administrerer dine integreringskoder for **Publicer på internettet** ved at åbne tandhjulet **Indstillinger** og vælge **Håndter indlejringskoder**.

   ![PtW8](media/service-publish-to-web/publish_to_web8.png)

2. Dine integreringskoder vises.

   ![PtW9](media/service-publish-to-web/publish_to_web9.png)

3. Du kan enten hente eller slette en integreringskode. Hvis du sletter den, deaktiveres links til rapporten eller det visuelle element.

   ![PtW10](media/service-publish-to-web/publish_to_web10.png)

4. Hvis du vælger **Slet**, bliver du bedt om en bekræftelse.

   ![PtW11](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Opdateringer af rapporter og data

Når du har oprettet din integreringskode for **Publicer på internettet** og deler den, opdateres rapporten med de ændringer, du foretager, og linket til integreringskoden bliver straks aktivt. Alle, der åbner linket, kan se den. Men efter denne indledende handling kan det dog vare to til tre timer, før opdateringer af rapporter eller visualiseringer bliver synlige for dine brugere. Se afsnittet [**Sådan fungerer det**](#howitworks) senere i denne artikel, hvis du vil vide mere. 

## <a name="data-refresh"></a>Opdatering af data

Dataopdateringer afspejles automatisk i din integrerede rapport eller det visuelle element. Det kan tage ca. én time, før opdaterede data kan ses fra integreringskoder. Du kan deaktivere automatisk opdatering ved at vælge **Opdater ikke** i tidsplanen for det datasæt, der bruges af rapporten.  

## <a name="custom-visuals"></a>Brugerdefinerede visualiseringer

Brugerdefinerede visuelle elementer, der understøttes i **Publicer på internettet**. Når du bruger **Publicer på internettet**, behøver brugere, som du deler dit publicerede visuelle element med, ikke at aktivere brugerdefinerede visuelle elementer for at få vist rapporten.

## <a name="limitations"></a>Begrænsninger

**Publicer på internettet** understøttes for langt de fleste datakilder og rapporter i Power BI-tjenesten, men følgende understøttes i øjeblikket ikke eller er ikke tilgængelige med **Publicer på internettet**:

- Rapporter med sikkerhed på rækkeniveau.
- Rapporter, der bruger en vilkårlig Live Connection-datakilde, herunder Analysis Services Tabular, der hostes i det lokale miljø, Analysis Service Multidimensional og Azure Analysis Services.
- Rapporter, der er delt med dig direkte eller via en organisationsindholdspakke.
- Rapporter i en gruppe, hvor du ikke er redigeringsmedlem.
- Visuelle "R"-elementer understøttes i øjeblikket ikke i **Publicer på internettet**-rapporter.
- Eksport af data fra visualiseringer i en rapport, som er publiceret på internettet.
- ArcGIS Maps til Power BI-visualiseringer.
- Rapporter med DAX-målinger på rapportniveau.
- Forespørgselsmodeller for enkeltlogon til data.
- Fortrolige eller beskyttede oplysninger.
- [Delte og certificerede datasæt](service-datasets-share.md).
- Muligheden for automatisk godkendelse, der er tilgængelig med indstillingen **Integrer** fungerer ikke sammen med Power BI JavaScript API. Til Power BI JavaScript API kan du bruge den strategi til integreringen, at [brugeren ejer dataene](developer/embed-sample-for-your-organization.md).

## <a name="tenant-setting"></a>Lejerindstillinger

Indstillingen **Publicer på internettet** giver mulighed for at angive, hvilke brugere der kan oprette integreringskoder.

![Indstillingen Publicer på internettet](media/service-admin-portal/powerbi-admin-publish-to-web-setting.png)

Du bliver bedt om at kontakte en Power BI-administrator for at oprette en integreringskode, når indstillingen **Vælg, hvordan integreringskoder fungerer** er angivet til **Tillad kun eksisterende integreringskoder**, og indstillingen **Publicer på internettet** er angivet til **Aktiveret**.

![Publicer på internettet-prompt](media/service-publish-to-web/publish_to_web_admin_prompt.png)

Power BI-administratorer kan aktivere eller deaktivere funktionen **Publicer på internettet**. De kan desuden begrænse adgang til bestemte grupper, hvilket kan påvirke din mulighed for at oprette en integreringskode. Du kan se forskellige indstillinger i brugergrænsefladen afhængigt af indstillingen **Publicer på internettet**.

|Funktion |Aktiveret for hele organisationen |Deaktiveret for hele organisationen |Specifikke sikkerhedsgrupper   |
|---------|---------|---------|---------|
|**Publicer på internettet** i menuen **Filer** for rapporten|Aktiveret for alle|Ikke synligt for alle|Kun synligt for godkendte brugere eller grupper.|
|**Håndter integreringskoder** under **Indstillinger**|Aktiveret for alle|Aktiveret for alle|Aktiveret for alle.<br><br>Indstillingen * **Slet** er kun synlig for godkendte brugere eller grupper.<br>* **Hent koder** er aktiveret for alle.|
|**Integrer koder** i administrationsportalen|Status afspejler en af følgende tilstande:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret|Status vises som **Deaktiveret**|Status afspejler en af følgende tilstande:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret<br><br>Hvis en bruger ikke er godkendt baseret på lejeren indstilling, vises status som **krænket**.|
|Eksisterende publicerede rapporter|Alle aktiveret|Alle deaktiveret|Rapporter fortsætter med at gengive for alle.|

## <a name="understanding-the-embed-code-status-column"></a>Om kolonnen med status for integreringskoder

>[!Note]
>Du bør regelmæssigt gennemgå de integreringskoder, du har publiceret, og fjerne alle dem, der ikke længere skal være offentligt tilgængelige. 

Siden **Administrer integreringskoder** indeholder en statuskolonne. Som standard er integreringskoder **aktive**, men de kan også have en af de statusser, der er anført nedenfor.

| Status | Beskrivelse |
| --- | --- |
| **Aktiv** |Rapporten er tilgængelig, og internetbrugere kan få vist og interagere med den. |
| **Blokeret** |Indholdet af rapporten er i strid med [Power BI Servicebetingelser](https://powerbi.microsoft.com/terms-of-service). Microsoft har blokeret for det. Hvis du mener, at indholdet blev blokeret ved en fejl, kan du kontakte support. |
| **Understøttes ikke** |Rapportens datasæt bruger sikkerhed på rækkeniveau, eller en anden konfiguration, der ikke understøttes. Se afsnittet [**Begrænsninger**](#limitations) for at få vist en fuldstændig liste. |
| **Krænket** |Integreringskoden er ikke omfattet af den definerede lejerpolitik. Dette sker typisk, når en integreringskode blev oprettet, og lejerindstillingen **Publicer på internettet** blev ændret for at udelade den bruger, der ejer integreringskoden. Hvis lejerindstillingen er deaktiveret, eller brugeren ikke længere har tilladelse til at oprette integreringskoder, vises status for eksisterende integreringskoder som **Krænket**. |

## <a name="how-to-report-a-concern-with-publish-to-web-content"></a>Sådan rapporterer du et problem med indhold via Publicer på internettet

Hvis du vil rapportere et problem, der er relateret til indhold i **Publicer på internettet**, som er integreret på et websted eller i en blog, skal du bruge **flagikonet** på nederste linje, som vist på følgende billede. Du bliver bedt om at sende en mail til Microsoft med en beskrivelse af problemet. Microsoft evaluerer indholdet baseret på Power BI Servicebetingelser og træffer de nødvendige foranstaltninger.

Hvis du vil rapportere et problem, skal du vælge **flagikonet** på nederste linje i den **Publicer på internettet**-rapport, som vises.

![PtW12](media/service-publish-to-web/publish_to_web12_ga.png)

## <a name="licensing-and-pricing"></a>Licenser og priser

Du skal være Microsoft Power BI-bruger for at anvende **Publicer på internettet**. Seerne af din rapport behøver ikke at være Power BI-brugere.

<a name="howitworks"></a>
## <a name="how-it-works-technical-details"></a>Sådan fungerer det (tekniske detaljer)

Når du opretter en integreringskode ved hjælp af **Publicer på internettet**, bliver rapporten synlig for brugere på internettet. Den er offentligt tilgængelig, så du kan forvente, at brugerne nemt kan dele rapporten via sociale medier på et senere tidspunkt. Når brugere får vist rapporten, enten ved at åbne den direkte offentlige URL-adresse eller se den integreret på en webside eller blog, cachelagrer Power BI rapportdefinitionen og resultaterne af de forespørgsler, der kræves for at få vist rapporten. Dette sikrer, at tusindvis af samtidige brugere kan se rapporten, uden at det påvirker ydeevnen.

Cachen har en lang levetid, så hvis du opdaterer rapportdefinitionen (f.eks. hvis du ændrer dens visningstilstand) eller opdaterer rapportdataene, kan det tage cirka en time, før ændringerne afspejles i den version af rapporten, der ses af brugerne. Det anbefales derfor, at du planlægger dit arbejde på forhånd og først opretter integreringskoden for **Publicer på internettet**, når du er tilfreds med indstillingerne.

## <a name="how-to-find-your-power-bi-administrator"></a>Sådan finder du din Power BI-administrator

Hvis du vil ændre [lejerindstillingerne for Publicer på internettet](#tenant-setting), skal du arbejde sammen med din organisations [Power BI-administrator](service-admin-role.md).

Mindre organisationer eller enkeltpersoner, der har tilmeldt sig Power BI, har muligvis endnu ikke en Power BI-administrator. Du skal følge vores [proces for overtagelse af lejeradministrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover). Når du har en Power BI-administrator, kan vedkommende aktivere oprettelse af integreringskoder for dig.

Etablerede organisationer har normalt allerede en Power BI-administrator. Personer med en af følgende roller kan fungere som Power BI-administrator:

- Office 365-administratorer
- Azure Active Directory-administratorer
- Brugere med rollen Power BI-tjenesteadministrator i Azure Active Directory

Du skal [finde en af disse personer](https://docs.microsoft.com/office365/admin/admin-overview/admin-overview#who-has-admin-permissions-in-my-business) i din organisation, så kan de opdatere indstillingen.


## <a name="next-steps"></a>Næste trin

- [Webdel til rapporten SharePoint Online](service-embed-report-spo.md) 

- [Integrer en rapport på en sikker portal eller et websted](service-embed-secure.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
