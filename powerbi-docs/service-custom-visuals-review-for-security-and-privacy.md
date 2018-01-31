---
title: Gennemse brugerdefinerede visualiseringer for sikkerhed og beskyttelse af personlige oplysninger
description: "Inden du aktiverer et brugerdefineret visuelt element, skal du gennemse dette visuelle element med henblik på sikkerhed og beskyttelse af personlige oplysninger for at sikre, at det passer til organisationens standarder."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: 15f8d9090736a62fdaa53aa3f19e7e0fff127337
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>Gennemse brugerdefinerede visualiseringer for sikkerhed og beskyttelse af personlige oplysninger
Inden du aktiverer et brugerdefineret visuelt element, skal du gennemse dette visuelle element med henblik på sikkerhed og beskyttelse af personlige oplysninger for at sikre, at det passer til organisationens standarder.

## <a name="enable-a-custom-visual"></a>Aktivér et brugerdefineret visuelt element
<a name="enable"></a>Et brugerdefineret visuelt element i rapporten er deaktiveret, indtil du vælger **Aktivér brugerdefinerede visuelle elementer** som vist nedenfor.  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>Overvejelser før du aktiverer et brugerdefineret visuelt element
<a name="considerations"></a>

> [!WARNING]
> Et brugerdefineret visuelt element kan indeholde kode med risici for sikkerhed eller beskyttelse af personlige oplysninger. Et brugerdefineret visuelt element i rapporten er derfor deaktiveret, indtil du vælge Aktivér brugerdefinerede visuelle elementer. Her er nogle overvejelser, når du skal beslutte, om et brugerdefineret visuelt element skal aktiveres:
> 
> 

1. Kontrollér, at du har tillid til forfatteren og kilden til de brugerdefinerede visuelle elementer, der er brugt i rapporten
2. Hvis du ikke er sikker på, hvad du skal gøre, kan du kontakte dit it-team for at få hjælp til at afgøre, om du bør aktivere brugerdefinerede visuelle elementer for rapporter, som du skal have vist.
3. Hvis nogen deler en rapport med dig, der indeholder et brugerdefineret visuelt element, skal du ikke føle dig forpligtet til at aktivere det pågældende element, heller ikke selvom det er en kollega, du arbejder tæt sammen med. Det er helt i orden at træde et skridt tilbage og overveje, om det er nødvendigt for den opgave, der skal udføres. Det er altid i orden at bede nogen om at sende dig en rapport uden brugerdefinerede visuelle elementer, hvis du ikke føler dig tryg ved det pågældende element.

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>Bedste fremgangsmåder for sikkerhed for it-fagfolk ved aktivering af et brugerdefineret visuelt element
<a name="security"></a>

> [!WARNING]
> Et brugerdefineret visuelt element kan indeholde kode med risici for sikkerhed eller beskyttelse af personlige oplysninger. Et brugerdefineret visuelt element i rapporten er derfor deaktiveret, indtil du vælge Aktivér brugerdefinerede visuelle elementer. Der er adskillige bedste fremgangsmåder, som du kan følge, når du vil evaluere et brugerdefineret visuelt element med henblik på sikkerhed og beskyttelse af personlige oplysninger.
> 
> 

1. Implementer en kontrolproces for brugerdefinerede visuelle elementer i organisationen. Kontrollerede, brugerdefinerede visuelle elementer kan deles med interne brugere via et internt websted, f.eks. et SharePoint-dokumentbibliotek eller et OneNote-dokument.
2. Vejled forretningsbrugere med hensyn til passende brug af brugerdefinerede visuelle elementer, og etabler en mailgruppe, som forretningsbrugere kan sende spørgsmål om sikkerhed og beskyttelse af personlige oplysninger til.
3. Evaluer JavaScript-koden i den brugerdefinerede visuelle pbiviz-fil.

**Sådan evalueres JavaScript-kode i et brugerdefineret visuelt element**

Et brugerdefineret visuelt element bruger JavaScript og kan derfor udgøre en risiko for sikkerhed eller for beskyttelse af personlige oplysninger. Hvis du modtager et brugerdefineret visuelt element eller en pbix-fil med et brugerdefineret visuelt element fra en ukendt kilde, kan du se nærmere på det pågældende JavaScript for at se, om det er sikkert.

Udtræk koden i den brugerdefinerede visualisering for at vurdere JavaScript-koden i et brugerdefineret visuelt element. Sådan udtrækker du koden:  

1. Gem .pbiviz-filen i en mappe.
2. Omdøb filen til en .zip-fil.
3. Udpak zip-filen i en lokal mappe.

## <a name="custom-visual-file-contents"></a>Filindhold i brugerdefineret visuelt element
Følgende er indholdet af en pbiviz-fil:

| **Fil** | **Beskrivelse** |
|:--- |:--- |
| ./package.json |En manifestfil, der angiver, hvilke filer der skal indlæses til det brugerdefinerede visuelle element. |
| ./resources |Indeholder typografiark (CSS), TypeScript og JavaScript, der bruges i det brugerdefinerede visuelle element. |
| ./resources/&lt;name&gt; |&lt;name&gt; er navnet på det brugerdefinerede visuelle element. |
| ./resources/&lt;name&gt;.css |Ressourcefilen css til det brugerdefinerede visuelle element. |
| ./resources/&lt;name&gt;.js |Den kode, der afvikles, når en bruger klikker på Aktivér brugerdefinerede visuelle elementer, eller når en bruger importerer et brugerdefineret visuelt element. Advarsel! JavaScript-kode kan medføre risici for sikkerhed eller beskyttelse af personlige oplysninger. |
| ./resources/&lt;name&gt;.ts |JavaScript-kildekoden i det visuelle element i TypeScript-format. Advarsel! JavaScript- eller TypeScript-kode kan medføre risici for sikkerhed eller beskyttelse af personlige oplysninger. |
| ./resources/&lt;name&gt;.png |Ikonet, som brugeren får vist for det visuelle element. |

Når du har udpakket pbiviz-filen, kan du evaluere koden. Her er nogle bedste fremgangsmåder og trusler, du skal se efter.

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>Bedste fremgangsmåder til evaluering af JavaScript- eller TypeScript-kode
**JavaScript**- eller **TypeScript**-kode kan medføre risici for sikkerhed eller beskyttelse af personlige oplysninger. Her er nogle bedste fremgangsmåder og trusler, du skal se efter.

### <a name="best-practices-to-evaluate-javascript-code"></a>Bedste fremgangsmåder til evaluering af JavaScript-kode
* Evaluer altid indholdet af .js filen. Det er den kode, der reelt kører. Det kan være, at indholdet af filen .ts ikke kompileres til den .js-fil, der er inkluderet i det brugerdefinerede visuelle element.
* Evaluer altid indholdet af .ts filen. Du kan indlæse .ts filen til **Udviklerværktøjer**, eksportere det visuelle element og sammenligne den .js-fil, der fås som resultat, i den nyoprettede .pbiviz-fil med den oprindelige .js-fil, der er indeholdt i det visuelle element
* Sørg for, at ikonet for det brugerdefinerede visuelle element ikke ligger for tæt op ad andre visuelle elementer, som brugeren kender.
* Evaluere altid det visuelle element med brug af en testkonto med minimumrettigheder, der ikke har adgang til følsomme oplysninger. Ideelt bør testkontoen være en lokal konto uden logonoplysninger til andre tjenester end Power BI.

### <a name="threats-to-look-for-in-javascript-code"></a>Trusler, du skal være på udkig efter i JavaScript-kode
* Kontrollér netværksaktiviteten, når det visuelle element bruges, og det gælder både i redigerings- og visningstilstand. Sørg for, at du er tilfreds med de anmodninger, der oprettes. Du bør ikke få vist anmodninger til ressourcer uden for Power BI-domænet, medmindre forfatteren til det visuelle element har meddelt dette på forhånd.
* Alle de data, du kan se forlade Power BI-domænet, bør stemme overens med dine forventninger til, hvad "normal" brug er. Hvis det visuelle element f.eks. implementerer en videoafspiller, der bruger en iFrame til at vise en video fra et andet websted, bør iFrame-anmodningerne være fulgt af oplysninger, der gør det muligt at gengive videoen korrekt. Men hvis du ser hele datasæt overført, kan du eventuelt undersøge, om der er anmodet om dette, og om det er noget, du ønsker.
* Kontrollér, om personidentficerbare oplysninger sendes eller gemmes af det brugerdefinerede visuelle element.
* Kontrollér, om det brugerdefinerede visuelle element prøver at få adgang til lokale computerressourcer, f.eks. skriveadgang til filer på disken eller adgang til cookies.
* Kontrollér, om det brugerdefinerede visuelle element indeholder noget, der ligner sløret kode eller kode uden et klart formål.
* Gem kopier af hvert visuelle element, du tidligere har gennemset.
* Hvis du gennemser en opdatering til et visuelt element, som du tidligere har gennemset, skal du sørge for at kontrollere, om der er ændringer. Vær altid lige så stringent med opdateringer, som du var, da du første gang fik det visuelle element til gennemsyn
* Hvis du finder noget mistænkelig eller uklart, skal du endelig kontakte os. Vi er her for at hjælpe.

## <a name="next-steps"></a>Næste trin
[Visualiseringer i Power BI](power-bi-report-visualizations.md)  
[Brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals.md)  
[Publicer brugerdefinerede visualiseringer i Office Store](developer/office-store.md)  
[Introduktion til udviklerværktøjer til brugerdefinerede visualiseringer](service-custom-visuals-getting-started-with-developer-tools.md)  
[Sådan certificeres et brugerdefineret visuelt element](power-bi-custom-visuals-certified.md)    
[Video: Opret brugerdefinerede visualiseringer til Power BI med Sachin Patney og Nico Cristache](https://www.youtube.com/watch?v=kULc2VbwjCc)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

