---
title: Opret forbindelse til datasæt i Power BI-tjenesten fra Power BI Desktop
description: Brug et almindeligt datasæt til flere Power BI Desktop-rapporter i flere arbejdsområder, og administrer rapportlevetiden
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 8b68f6ee5e475c1b53f914c84372a0875fe87b5d
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839115"
---
# <a name="connect-to-datasets-in-the-power-bi-service-from-power-bi-desktop"></a>Opret forbindelse til datasæt i Power BI-tjenesten fra Power BI Desktop
Du kan oprette en direkte forbindelse til et delt datasæt i Power Bi-tjenesten og oprette mange forskellige rapporter fra det samme datasæt. Det betyder, at du kan oprette en perfekt datamodel i Power BI Desktop og publicere den i Power BI-tjenesten. Derefter kan du og andre oprette flere forskellige rapporter (i separate .pbix-filer) ud fra den samme almindelige datamodel og gemme dem i forskellige arbejdsområder. Denne funktion kaldes **Direkte forbindelse til Power BI-tjeneste**.

![Hent data fra Power BI-tjenesten](media/desktop-report-lifecycle-datasets/report-lifecycle_01.png)

Der er mange forskellige fordele ved denne funktion, herunder bedste fremgangsmåder, som vi vil komme ind på i denne artikel. Der er også et par overvejelser og begrænsninger, så sørg for, at du læser disse. Du kan finde dem til sidst i artiklen.

## <a name="using-a-power-bi-service-live-connection-for-report-lifecycle-management"></a>Brug af en direkte forbindelse til Power BI-tjenesten til administration af rapportlevetid
En udfordring med Power BIs popularitet er det stadig større antal rapporter, dashboards og deres underliggende data. Her er hvorfor: Det er nemt at oprette overbevisende rapporter i **Power BI Desktop** for derefter at dele ([udgive](desktop-upload-desktop-files.md)) disse rapporter i **Power BI-tjenesten** og oprette gode dashboards fra disse datasæt. Da så mange personer gør det og ofte ved hjælp af de samme (eller næste de same) datasæt, er det en udfordring at vide, hvilken rapport, der er baseret på hvilket datasæt, og hvor hvert nyt datasæt er. Funktionen **Direkte forbindelse til Power BI-tjeneste** tager hånd om denne udfordring og gør det nemmere og mere ensartet at oprette, dele og udvide fælles datasætrapporter og dashboards.

### <a name="create-a-dataset-everyone-can-use-then-share-it"></a>Opret et datasæt, alle kan bruge, og del det derefter
Lad os antage, at Anna (en virksomhedsanalytiker) er på dit team, og hun er rigtig god til at oprette gode datamodeller (ofte kaldet datasæt). Med Annas ekspertise kan hun oprette et datasæt og en rapport, og derefter dele rapporten i **Power BI-tjenesten**.

![Publicer til Power BI-tjenesten](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

Alle er vilde med hendes rapport og datasæt, og det er her, problemerne begynder – alle på hendes team forsøger at oprette *deres egen version* af datasættet og derefter dele deres egne rapporter med teamet. Lige pludselig er der mange forskellige rapporter (fra forskellige datasæt) på dit teams arbejdsområde i **Power BI-tjenesten**. Hvilket var det seneste? Var datasættene de samme, eller kun næsten? Hvor var forskellene? Med funktionen **Direkte forbindelse til Power BI-tjeneste** kan alt dette ændres til det bedre. I næste afsnit kigger vi på, hvordan andre kan bruge Annas publicerede datasæt til deres egne rapporter og i deres egne arbejdsområder samt give alle mulighed for at bruge det samme solide, afprøvede og publicerede datasæt til at udarbejde deres unikke rapporter.

### <a name="connect-to-a-power-bi-service-dataset-using-a-live-connection"></a>Opret forbindelse til et Power BI-datasæt ved brug af en direkte forbindelse
Når Anna har oprettet sin rapport (og oprettet datasættet, som den er baseret på), udgiver hun den til **Power BI-tjenesten**, og den vises på hendes teams arbejdsområde i Power BI-tjenesten. Hvis hun gemmer den i et *arbejdsområde med den nye oplevelse*, kan hun derefter angive tilladelsen Opret for at gøre den tilgængelig for alle, der kommer og går i hendes arbejdsområde, så de kan se den og bruge den.

Hvis du vil vide mere om arbejdsområder med den nye oplevelse, skal du se [programarbejdsområder](service-new-workspaces.md).

Andre medlemmer af Annas arbejdsområde, der kommer og går, kan nu etablere en direkte forbindelse til hendes delte datamodel (ved hjælp af funktionen **Direkte forbindelse til Power BI-tjeneste**) og oprette deres egne unikke rapporter fra *hendes oprindelige datasæt* i *deres egne arbejdsområder med den nye oplevelse*.

På følgende billede kan du se, hvordan Anna opretter en **Power Bi Desktop**-rapport og udgiver den (inklusive dens datamodel) til **Power BI-tjenesten**. Andre kan derefter oprette forbindelse til hendes datamodel ved hjælp af **Direkte forbindelse til Power BI-tjenesten** og oprette deres egne unikke rapporter i deres egne arbejdsområder på baggrund af hendes datasæt.

![Flere rapporter baseret på det samme datasæt](media/desktop-report-lifecycle-datasets/report-lifecycle_03.png)

> [!NOTE]
> Hvis du gemmer dit datasæt i et [klassisk delt arbejdsområde](service-create-workspaces.md), er det kun medlemmer af det arbejdsområde, der kan udarbejde rapporter på baggrund af dit datasæt. Hvis du vil oprette en direkte forbindelse til en Power BI-tjeneste, skal det datasæt, som du opretter forbindelse til, være på et delt arbejdsområde, som du er medlem af.
> 
> 

## <a name="step-by-step-for-using-the-power-bi-service-live-connection"></a>Trinvis vejledning til at bruge Direkte forbindelse til Power BI-tjeneste
Nu, hvor vi ved, hvor nyttig **Direkte forbindelse til Power BI-tjenesten** er, og hvordan du kan bruge funktionen som bedste praksis til at administrere rapportlevetiden, er det tid til at gennemgå trinnene, der får os fra Annas fantastiske rapport (og datasæt) til et delt datasæt, som andre i hendes Power BI-team kan bruge.

### <a name="publish-a-power-bi-report-and-dataset"></a>Udgiv en Power BI-rapport og et Power BI-datasæt
Det første trin til at administrere rapportlevetiden ved brug af en **Direkte forbindelse til Power BI-tjeneste** er at have en rapport (og et datasæt), som teammedlemmerne vil bruge. Så Anna skal først **udgive** sin rapport fra **Power BI Desktop**. Det gør hun ved at vælge **Udgiv** på båndet **Hjem** i Power BI Desktop.

![Publicer en rapport](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

Hvis hun ikke er logget på sin Power BI-tjenestekonto, bliver hun bedt om at gøre det.

![Log på Power BI Desktop](media/desktop-report-lifecycle-datasets/report-lifecycle_04.png)

Hun kan derfra vælge destinationen i arbejdsområdet, hvor rapporten og datasættet skal udgives til. Husk på, at hvis hun gemmer det i et arbejdsområde med den nye oplevelse, så har alle med tilladelsen Opret adgang til det pågældende datasæt. Tilladelsen Opret er angivet i Power BI-tjenesten, når du har publiceret. Hvis hun gemmer det i et klassisk arbejdsområde, er det kun medlemmer, som har adgang til arbejdsområdet, hvor en rapport er publiceret, der kan tilgå datasættet ved hjælp af en **direkte forbindelse til Power BI-tjenesten**.

![Publicer til Power BI-tjenesten](media/desktop-report-lifecycle-datasets/report-lifecycle_05.png)

Udgivelsesprocessen begynder, og **Power BI Desktop** viser statussen.

![Publicering i gang](media/desktop-report-lifecycle-datasets/report-lifecycle_06.png)

Når den er færdig, viser **Power BI Desktop** dig, at udgivelsen er udført og giver dig et par links, så du selv kan komme til selve rapporten i **Power BI-tjenesten** og et link til at få **Hurtig indsigt** i rapporten.

![Vellykket publicering](media/desktop-report-lifecycle-datasets/report-lifecycle_07.png)

Nu, hvor din rapport med tilhørende datasæt befinder sig i Power BI-tjenesten, kan du også *hæve* det for at bekræfte dets kvalitet og pålidelighed. Du kan tilmed anmode om, at det bliver *certificeret* af en central myndighed i din Power BI-lejer. Med begge disse godkendelser vil dit datasæt blive vist på listen over emner, når folk søger efter datasæt. Hvis du er interesseret, kan du læse mere om processen med at [hæve dit datasæt](service-datasets-promote.md). 

Det sidste trin er at angive *tilladelsen Opret* for det datasæt, som rapporten er baseret på. Tilladelsen Opret bestemmer, hvem der kan se og bruge dit datasæt. Du kan konfigurere den i selve arbejdsområdet, eller når du deler et program fra arbejdsområdet. Få mere at vide om angivelse af [tilladelsen Opret](service-datasets-build-permissions.md#build-permissions-for-shared-datasets).

Lad os nu se, hvordan andre teammedlemmer, der har adgang til arbejdsområdet, hvor rapporten (og datasættet) blev udgivet, kan oprette forbindelse til datasættet og lave deres egne rapporter.

### <a name="establish-a-power-bi-service-live-connection-to-the-published-dataset"></a>Opret en direkte forbindelse til en Power BI-tjeneste til det udgivne datasæt
Vælg **Hent data** på båndet **Hjem** i **Power BI Desktop**, vælg **Power BI** i ruden til venstre, og vælg derefter **Power BI-datasæt** for at etablere en forbindelse til den publicerede rapport og oprette din egen rapport på baggrund af det publicerede datasæt.

Hvis du ikke allerede er logget på Power BI, bliver du bedt om at gøre det. Når du er logget på, får du vist et vindue, der viser, hvilke arbejdsområder du er medlem af, og du kan vælge, hvilket arbejdsområde der indeholder datasættet, som du vil oprette en **Direkte forbindelse til Power Bi-tjeneste** til.

Datasættene på listen er alle de delte datasæt, du har tilladelsen Opret til, i et hvilket som helst arbejdsområde. Du kan søge efter et bestemt datasæt og se dets navn, ejer og arbejdsområdet, hvor det befinder sig, samt hvornår det senest blev opdateret. Øverst på listen kan du også se de *godkendte* datasæt, uanset om de er certificerede eller hævede. 

![Liste over tilgængelige datasæt](media/desktop-report-lifecycle-datasets/desktop-select-shared-dataset.png)

Når du vælger **Indlæs** fra vinduet, opretter du en direkte forbindelse til det valgte datasæt, hvilket betyder, at de data, du ser (felterne og deres værdier), indlæses i **Power Bi Desktop** i realtid.

![Felter i datasættet i ruden Felter](media/desktop-report-lifecycle-datasets/report-lifecycle_10.png)

Nu kan du (og andre) oprette og dele brugerdefinerede rapporter fra det samme datasæt. Det er en god måde til at have en kyndig person, som opretter et veludformet datasæt (lige som Anna gør) og tillader mange teammedlemmer at bruge det delte datasæt til at oprette deres egne rapporter.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser
Når du bruger **Direkte forbindelse til Power BI-tjeneste**, er der et par begrænsninger og overvejelser, du skal huske.

* Det er kun brugere med tilladelsen Opret for et datasæt, der kan oprette forbindelse til et publiceret datasæt ved hjælp af **direkte forbindelse til Power BI-tjenesten**. 
* Gratis brugere kan kun se datasæt i deres Mit arbejdsområde og i Premium-baserede arbejdsområder.
* Da det er en direkte forbindelse, er venstrenavigation og modeller deaktiveret, ligesom funktionsmåden når der er oprettet forbindelse til **SQL Server Analysis Services**.
* Da det er en direkte forbindelse er RLS (sikkerhed på række- og rolleniveau), OneDrive for Business og andre lignende forbindelsesfunktionsmåder tvunget, ligesom de er det, når der er oprettet forbindelse til **SQL Server Analysis Services**.
* Hvis ejeren ændrer den originale delte .pbix-fil, overskrives datasættet og rapporten, der er delt i **Power BI tjenesten**. Rapporter baseret på dette datasæt overskrives ikke, men alle ændringer af datasættet afspejles i rapporten.
* Medlemmer af et arbejdsområde kan ikke erstatte den oprindeligt delte rapport. Forsøg på at gøre dette resulterer i en advarsel, der beder dig om at omdøbe filen og udgive den.
* Hvis du sletter det delte datasæt i **Power BI-tjenesten**, så vil andre rapporter, der er baseret på dette datasæt ikke længere fungere korrekt eller vise deres visualiseringer.
* Hvad angår indholdspakker skal du først oprette en kopi af en indholdspakke, inden den bruges som basis for at dele en .pbix-rapport eller et .pbix-datasæt til **Power BI-tjenesten**.
* Hvad angår indholdspakker fra *Min organisation* kan du, når de er kopieret, ikke erstatte rapporten, der er oprettet på tjenesten, og/eller en rapport, der er oprettet som en del af kopiering af en indholdspakke med en direkte forbindelse. Forsøg på at gøre dette resulterer i en advarsel, der beder dig om at omdøbe filen og udgive den. I denne situation kan du kun erstatte udgivne rapporter, der er direkte forbundne.
* Sletning af et delt datasæt i **Power BI-tjenesten** betyder, at ingen længere kan få adgang til det datasæt fra **Power BI Desktop**.

