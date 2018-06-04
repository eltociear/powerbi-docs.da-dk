---
title: Introduktion til Power BI-tjenesten
description: Introduktion til Power BI-tjenesten
author: adamw
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: d66653ebe9232cb6da2f3c53b01e791ca9966db9
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34310124"
---
# <a name="get-started-with-power-bi-service-apppowerbicom"></a>Kom i gang med Power BI-tjenesten (app.powerbi.com)
Dette selvstudium hjælper dig med at komme i gang med ***Power BI-tjenesten***. Hvis du vil have et overblik over, hvordan Power BI-tjenesten passer sammen med de andre Power BI-tilbud, anbefaler vi kraftigt, at du starter med at læse [Hvad er Power BI](guided-learning/gettingstarted.yml?tutorial-step=1).

![kunst, der viser relationen mellem Desktop, tjeneste, mobil](media/service-get-started/power-bi-components.png)

Power BI-tjenesten har en gratis version og en Pro-version. Uanset hvilken version du bruger, skal du åbne en browser og skrive app.powerbi.com for at åbne Power BI-tjenesten, *hvis du allerede har en konto*. Hvis du er ny bruger, anbefaler vi, at du starter på www.powerbi.com i stedet. Herfra kan du få mere at vide om Power BI, inden du logger på tjenesten.  Når du er klar til at prøve det, kan du vælge linket, hvor du kan **tilmelde dig gratis**, der vises i øverste højre hjørne. Hvis din administrator allerede har aktiveret Power BI for dig, skal du ikke bruge knappen til gratis tilmelding, men i stedet gå direkte til app.powerbi.com. 

![Log på, eller tilmeld dig gratis](media/service-get-started/power-bi-sign-up.png)

Hvis du ønsker hjælp til Power BI Desktop, kan du se [Kom i gang med Desktop](desktop-getting-started.md). Hvis du ønsker hjælp til Power BI – Mobil, kan du se [Power BI-mobilapps til mobilenheder](mobile-apps-for-mobile-devices.md).

> [!TIP]
> Foretrækker du i stedet et gratis kursus i dit eget tempo? [Deltag i vores kursus om analyse og visualisering af data på EdX](http://aka.ms/edxpbi).

Besøg vores [afspilningsliste på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). En god video at starte med er Introduktion til Power BI-tjenesten:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Med Microsoft Power BI kan du holde dig ajour med de oplysninger, der er vigtige for dig.  Med Power BI-tjenesten hjælper ***dashboards*** dig med at holde styr på din virksomhed.  Dine dashboards viser ***felter***, som du kan klikke på for at åbne ***rapporter***, der skal udforskes yderligere.  Opret forbindelse til flere ***datasæt*** for at samle alle relevante data på ét sted. Har brug for hjælp til at forstå de komponenter, der udgør Power BI?  Se [Power BI – Grundlæggende begreber](service-basic-concepts.md).

Hvis du har vigtige data i Excel- eller CSV-filer, kan du oprette et Power BI-dashboard for at holde dig opdateret, uanset hvor du er, og dele indsigt med andre.  Har du et abonnement på en SaaS-app som for eksempel Salesforce?  Kom godt i gang ved at oprette forbindelse til Salesforce og automatisk oprette et dashboard ud fra disse data, eller [tjek alle de andre SaaS-apps](service-get-data.md), du kan oprette forbindelse til. Hvis du er en del af en organisation, kan du se, om der er publiceret [apps](service-create-distribute-apps.md) til dig.

Læs om alle de andre måder at [hente data til Power BI](service-get-data.md) på.

## <a name="step-1-get-data"></a>Trin 1: Hent data
Her er et eksempel på at hente data fra en CSV-fil. Har du lyst til at deltage i dette selvstudium? [Download denne CSV-eksempelfil](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Log på Power BI](http://www.powerbi.com/). Har du ikke en konto? Helt i orden, du kan tilmelde dig gratis.
2. Power BI åbnes i browseren. Vælg **Hent data** nederst på venstre navigationslinje.
   
   ![hent data](media/service-get-started/getdata3.png)
3. Vælg **Filer**. 
   
   ![hent filer](media/service-get-started/gs1.png)
4. Gå til filen på din computer, og vælg **Åbn**. Hvis filen er gemt i OneDrive for Business, skal du vælge denne mulighed. Hvis du har gemt den lokalt, skal du vælge **Lokal fil**. 
   
   ![Hent data > Skærmbilledet Filer](media/service-get-started/gs2.png)
5. Til dette selvstudium vælger vi **Importér** for at tilføje Excel-filen som et datasæt, som vi derefter kan bruge til at oprette rapporter og dashboards. Hvis du vælger **Overfør**, uploades hele Excel-projektmappen til Power BI, hvor du kan åbne og redigere den i Excel online.
   
   ![vælg Importér](media/service-get-started/power-bi-import.png)
6. Vælg **Vis datasæt**, når dit datasæt er klar, for at åbne det i rapporteditoren. 

    ![Dialogboksen Dit datasæt er parat](media/service-get-started/power-bi-gs.png)

    Da vi endnu ikke har oprettet nogen visualiseringer, er rapportcanvasset tomt.

    ![tomt rapportlærred](media/service-get-started/power-bi-report-editor.png)

6. Kig nærmere på den øverste menulinje, og læg mærke til, at der er en indstilling for **Læsevisning**. Eftersom du har mulighed for at vælge Læsevisning, betyder det, at du i øjeblikket er i **Redigeringsvisning**. 

    ![Indstillingen Læsevisning](media/service-get-started/power-bi-editing-view.png)

    Når du er Redigeringsvisning, kan du oprette og redigere dine egne rapporter, fordi du er *ejer* af rapporten altså en *opretter*. Når du deler din rapport med kollegaer, kan de kun interagere med rapporten i Læsevisning, da de er *forbrugere*. Få mere at vide om [Læsevisning og Redigeringsvisning](service-reading-view-and-editing-view.md).
    
    En glimrende måde at blive fortrolig med rapporteditoren på er at [få en introduktion](service-the-report-editor-take-a-tour.md)
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>Trin 2: Begynd at udforske dit datasæt
Nu hvor du har forbindelse til data, kan du begynde at udforske.  Vi har fundet noget spændende, så du kan oprette et dashboard for at overvåge det og se, hvordan det ændres over tid. Lad os se, hvordan det fungerer.
    
1. I rapporteditoren bruger vi ruden **Felter** i højre side for at oprette en visualisering.  Markér afkrydsningsfeltet ud for **Gross Sales** og **Date**.
   
   ![Listen Felter](media/service-get-started/fields.png)

2. Power BI analyserer dataene og opretter en visualisering.  Hvis du har valgt **Date** først, får du vist en tabel.  Hvis du har valgt **Gross Sales** først, får du vist et diagram. Skift til en anden måde at vise dine data på. Lad os se disse data som et kurvediagram. Vælg ikonet for kurvediagram (også kendt som en skabelon) i **ruden Visualiseringer**.
   
   ![rapporteditor med valgt ikon](media/service-get-started/gettingstart5new.png)

3. Det ser interessant ud, så lad os *fastgøre* det til et dashboard. Peg på visualiseringen med musen, og vælg **ikonet med tegnestiften**.  Når du fastgør denne visualisering, gemmes den på dashboardet og holdes opdateret, så du kan spore den seneste værdi på et øjeblik.
   
   ![tegnestiftikon](media/service-get-started/pinnew.png)

5. Da det er en ny rapport, skal du gemme den, før du kan fastgøre en visualisering på et dashboard. Giv din rapport et navn (f.eks. *Salg over tid*), og vælg **Gem og fortsæt**. 
   
   ![Dialogboksen Gem rapport](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
6. Lad os fastgøre kurvediagrammet til et nyt dashboard, og give det navnet "Økonomisk eksempel til selvstudium". 
   
   ![navngiv rapporten](media/service-get-started/power-bi-pin.png)
   
 1. Vælg **Fastgør**.
   
    En meddelelse om fuldførelse (næsten helt oppe i højre hjørne) giver dig besked om, at visualiseringen er blevet føjet til dit dashboard som et felt.
   
    ![Fastgjort til dashboarddialogboks](media/service-get-started/power-bi-pin-success.png)

8. Vælg **Gå til dashboard** for at se kurvediagrammet fastgjort som et felt til dit helt nye dashboard. Gør dit dashboard endnu bedre ved at tilføje flere visualiseringsfelter og [omdøbe, ændre størrelsen på, sammenkæde og flytte felter](service-dashboard-edit-tile.md).
   
   ![dashboard med fastgjort visualisering](media/service-get-started/power-bi-new-dashboard.png)
   
   Vælg det nye felt på dashboardet for til enhver tid at vende tilbage til rapporten. Power BI vender tilbage til rapporteditoren i Læsevisning. Hvis du vil skifte tilbage til Redigeringsvisning, skal du vælge **Rediger rapport** på den øverste menulinje. Når du er i Redigeringsvisning, kan du fortsætte med at udforske og fastgøre felter. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Trin 3: Fortsæt med at udforske via Spørgsmål og svar (forespørgsel på naturligt sprog)
1. Hvis du vil foretage en hurtig udforskning af dine data, kan du prøve at stille et spørgsmål i feltet Spørgsmål og svar. Feltet Spørgsmål og svar er placeret øverst i dit dashboard (**stil et spørgsmål om dataene**) og i den øverste menulinje i din rapport (**stil et spørgsmål**). Prøv for eksempel at skrive "hvilket segment havde den største omsætning".
   
   ![Spørgsmål og svar om lærred](media/service-get-started/powerbi-qna.png)

2. Spørgsmål og svar søger efter svar og præsenterer dem i form af en visualisering. Vælg fastgørelsesikonet ![tegnestiftikon](media/service-get-started/pbi_pinicon.png) for også at vise denne visualisering på dit dashboard.
3. Fastgør visualiseringen på dashboardet "Økonomisk eksempel til selvstudium".
   
    ![Dialogboksen Fastgør til dashboard](media/service-get-started/power-bi-pin2.png)

4. Vend tilbage til dit dashboard, hvor du kan se det nye felt.

   ![dashboard med fastgjort diagram](media/service-get-started/power-bi-final-dashboard.png)

## <a name="next-steps"></a>Næste trin
Er du klar til at prøve mere?  Her er nogle fantastiske måder at udforske Power BI på.

* [Opret forbindelse til et andet datasæt](service-get-data.md).
* [Del dit dashboard](service-share-dashboards.md) med dine kollegaer.
* Læs [tip til design af dashboards](service-dashboards-design-tips.md).
* Få vist dine dashboards med en [Power BI-app på en mobilenhed](mobile-apps-for-mobile-devices.md)

Er du ikke helt klar til at springe i med samlede ben? Start med disse emner, der er udarbejdet til at gøre dig komfortabel med Power BI.

* [Få mere at vide om, hvordan rapporter, datasæt, dashboards og felter passer sammen](service-basic-concepts.md)
* Gå til vores websted med [automatiseret læring til Power BI](guided-learning/index.md), og prøv et par (meget korte) kurser
* Se nogle [Power BI-videoer](videos.md)
* [Se, hvilke eksempler vi har, som du kan bruge](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Hold dig ajour med Power BI
* Følg [@MSPowerBI på Twitter](https://twitter.com/mspowerbi)
* Abonner på vores [YouTube-videokanal](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg)
* Se vores [webinarer med introduktion til Power BI](webinars.md) efter behov
* Er du usikker på, hvor du kan finde hjælp? Se vores side [10 tip til at få hjælp](service-tips-for-finding-help.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

