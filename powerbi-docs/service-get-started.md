---
title: Kom i gang med Power BI-tjenesten
description: Kom i gang med Power BI-onlinetjenesten (app.powerbi.com)
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 007819ead82f558efa8179a49dfba9454558dfbb
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2019
ms.locfileid: "68995185"
---
# <a name="tutorial-get-started-with-the-power-bi-service-apppowerbicom"></a>Selvstudium: Kom i gang med Power BI-tjenesten (app.powerbi.com)
Dette selvstudium hjælper dig med at komme i gang med *Power BI-tjenesten*. Hvis du vil have en forståelse af, hvordan Power BI-tjenesten passer sammen med de andre Power BI-tilbud, anbefaler vi, at du starter med at læse [Hvad er Power BI](power-bi-overview.md).

![Relation mellem Power BI Desktop, tjenesten, mobil](media/service-get-started/power-bi-components.png)

I dette selvstudium udfører du følgende trin:

> [!div class="checklist"]
> * Find indhold om at komme i gang med Power BI-tjenesten.
> * Log på din Power BI-onlinekonto, eller opret én, hvis du endnu ikke har en.
> * Åbn Power BI-tjenesten.
> * Hent nogle data, og åbn dem i rapportvisning.
> * Brug disse data til at oprette visualiseringer, og gem dem som en rapport.
> * Opret et dashboard ved at fastgøre felter fra rapporten.
> * Føj en anden visualisering til dit dashboard ved hjælp af værktøjet Spørgsmål og svar i naturligt sprog.
> * Fjern ressourcer ved at slette datasættet, rapporten og dashboardet.

## <a name="sign-up-for-the-power-bi-service"></a>Tilmeld dig Power BI-tjenesten
Hvis du ikke har en Power BI-konto, [kan du tilmelde dig en gratis prøveversion af Power BI Pro](https://app.powerbi.com/signupredirect?pbi_source=web), før du begynder.

Når du har fået en konto, skal du angive *app.powerbi.com* i din browser for at åbne Power BI-tjenesten. 

Hvis du har brug for hjælp til Power BI Desktop, kan du se [Kom i gang med Power BI Desktop](desktop-getting-started.md). Hvis du ønsker hjælp til Power BI – Mobil, kan du se [Power BI-mobilapps til mobilenheder](consumer/mobile/mobile-apps-for-mobile-devices.md).

> [!TIP]
> Foretrækker du i stedet et gratis kursus i dit eget tempo? [Deltag i vores kursus om analyse og visualisering af data på EdX](http://aka.ms/edxpbi).

Besøg vores [afspilningsliste på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). Videoen *Introduktion til Power BI-tjenesten* er god at starte med:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 

## <a name="what-is-the-power-bi-service"></a>Hvad er Power BI-tjenesten?
Microsoft Power BI-tjenesten kaldes nogle gange også Power BI online eller app.powerbi.com. Power BI hjælper dig med at holde dig ajour med de oplysninger, der er vigtige for dig. Med Power BI-tjenesten hjælper *dashboards* dig med at holde styr på din virksomhed. Der vises *felter* på dine dashboards, som du kan vælge for at åbne *rapporter*, der skal udforskes yderligere. Opret forbindelse til flere *datasæt* for at samle alle relevante data på ét sted. Har du brug for hjælp til at forstå de komponenter, der udgør Power BI? Se [Grundlæggende begreber for designere i Power BI-tjenesten](service-basic-concepts.md).

Hvis du har vigtige data i Excel- eller CSV-filer, kan du oprette et Power BI-dashboard for at holde dig opdateret, uanset hvor du er, og dele indsigt med andre.  Har du et abonnement på en SaaS-app som for eksempel Salesforce?  Kom godt i gang ved at oprette forbindelse til Salesforce og automatisk oprette et dashboard ud fra disse data, eller [tjek alle de andre SaaS-apps](service-get-data.md), du kan oprette forbindelse til. Hvis du er en del af en organisation, kan du se, om der er publiceret [apps](service-create-distribute-apps.md) til dig.

Læs om alle de andre måder at [hente data til Power BI](service-get-data.md) på.

## <a name="step-1-get-data"></a>Trin 1: Hent data
Her er et eksempel på at hente data fra en CSV-fil. Har du lyst til at deltage i dette selvstudium? [Download CSV-filen Økonomisk eksempel](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Log på Power BI](http://www.powerbi.com/). Har du ikke en konto? Helt i orden, du kan tilmelde dig og få en gratis prøveversion.
2. Power BI åbnes i browseren. Vælg **Hent data** nederst på venstre navigationslinje.

    Siden **Hent data** åbnes.   

3. Under sektionen **Opret nyt indhold** skal du vælge **Filer**. 
   
   ![Hent filer](media/service-get-started/gs1.png)
4.  Vælg **Lokal fil**.
   
     ![Hent data > Skærmbilledet Filer](media/service-get-started/gs2.png)

5. Gå til filen på din computer, og vælg **Åbn**.

5. Til dette selvstudium vælger vi **Importér** for at tilføje Excel-filen som et datasæt, som vi derefter kan bruge til at oprette rapporter og dashboards. Hvis du vælger **Upload**, uploades hele Excel-projektmappen til Power BI, hvor du kan åbne og redigere den i Excel online.
   
   ![Vælg Importér](media/service-get-started/power-bi-import.png)
6. Vælg **Vis datasæt**, når dit datasæt er klar, for at åbne det i rapporteditoren. 

    ![Dialogboksen Dit datasæt er parat](media/service-get-started/power-bi-gs.png)

    Da vi endnu ikke har oprettet nogen visualiseringer, er rapportlærredet tomt.

    ![Tomt rapportlærred](media/service-get-started/power-bi-report-editor.png)

7. Bemærk, at der er en indstilling for **Læsevisning** på den øverste navigationslinje. Når denne indstilling er aktiv, betyder det, at du i øjeblikket er i Redigeringsvisning. 

    ![Indstillingen Læsevisning](media/service-get-started/power-bi-editing-view.png)

    Når du er Redigeringsvisning, kan du oprette og redigere dine rapporter, fordi du er *ejer* af rapporten. Det vil sige, at du er *forfatteren*. Når du deler din rapport med kolleger, kan de kun interagere med rapporten i Læsevisning, da de er *forbrugere*. Få mere at vide om [Læsevisning og Redigeringsvisning](consumer/end-user-reading-view.md).
    
    En god måde at blive fortrolig med rapporteditoren på er ved at [få en introduktion](service-the-report-editor-take-a-tour.md).
 

## <a name="step-2-start-exploring-your-dataset"></a>Trin 2: Begynd at udforske dit datasæt
Nu hvor du har forbindelse til data, kan du begynde at udforske.  Vi har fundet noget spændende, så du kan oprette et dashboard for at overvåge det og se, hvordan det ændres over tid. Lad os se, hvordan det fungerer.
    
1. I rapporteditoren bruger vi ruden **Felter** i højre side for at oprette en visualisering. Markér afkrydsningsfelterne for **Bruttoomsætning** og **Dato**.
   
   ![Listen Felter](media/service-get-started/fields.png)

    Power BI analyserer dataene og opretter en visualisering. Hvis du valgte **Dato** først, får du vist en tabel. Hvis du valgte **Bruttoomsætning** først, får du vist et diagram. 

2. Skift til en anden måde at vise dine data på. Lad os se disse data som et kurvediagram. Vælg ikonet for kurvediagrammet i ruden **Visualiseringer**.
   
   ![Rapporteditor med kurvediagram valgt](media/service-get-started/gettingstart5new.png)

3. Dette diagram ser interessant ud, så lad os *fastgøre* det til et dashboard. Hold over visualiseringen, og vælg ikonet med tegnestiften. Når du fastgør denne visualisering, gemmes den på dashboardet og holdes opdateret, så du kan spore den seneste værdi på et øjeblik.
   
   ![Ikon med tegnestift](media/service-get-started/pinnew.png)

4. Da denne rapport er ny, bliver du bedt om at gemme den, før du kan fastgøre en visualisering på et dashboard. Navngiv din rapport (f.eks. *Salg over tid*), og vælg **Gem og fortsæt**. 
   
   ![Dialogboksen Gem rapport](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
5. Fastgør kurvediagrammet til et nyt dashboard, og navngiv det *Økonomisk eksempel til selvstudium*. 
   
   ![Navngiv rapporten](media/service-get-started/power-bi-pin.png)
   
6. Vælg **Fastgør**.
   
    En meddelelse om fuldførelse (i nærheden af øverste højre hjørne) giver dig besked om, at visualiseringen blev føjet til dit dashboard som et felt.
   
    ![Fastgjort til dashboarddialogboks](media/service-get-started/power-bi-pin-success.png)

7. Vælg **Gå til dashboard** for at se det kurvediagram, du har fastgjort til dit nye dashboard som et felt. Gør dit dashboard endnu bedre ved at tilføje flere visualiseringsfelter og [omdøbe, ændre størrelsen på, sammenkæde og flytte felter](service-dashboard-edit-tile.md).
   
   ![Dashboard med fastgjort visualisering](media/service-get-started/power-bi-new-dashboard.png)
   
8. Vælg det nye felt på dashboardet for at vende tilbage til rapporten. Power BI vender tilbage til rapporteditoren i Læsevisning. Hvis du vil skifte tilbage til Redigeringsvisning, skal du vælge **Rediger rapport** på den øverste navigationslinje. Når du er i Redigeringsvisning, kan du fortsætte med at udforske og fastgøre felter. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Trin 3:  Fortsæt med at udforske via Spørgsmål og svar (forespørgsel på naturligt sprog)
1. Hvis du vil foretage en hurtig udforskning af dine data, kan du stille et spørgsmål i feltet Spørgsmål og svar. Feltet Spørgsmål og svar er placeret øverst på dit dashboard (**Stil et spørgsmål om dataene**) og på den øverste navigationslinje i din rapport (**Stil et spørgsmål**). Prøv f.eks. at skrive *hvilket segment havde den største omsætning* i feltet Spørgsmål og svar.
   
   ![Spørgsmål og svar om lærred](media/service-get-started/powerbi-qna.png)

2. Spørgsmål og svar søger efter svar og præsenterer dem i form af en visualisering. Vælg ikonet med tegnestiften ![Ikon med tegnestift](media/service-get-started/pbi_pinicon.png) for at vise denne visualisering på dit dashboard.
3. Fastgør visualiseringen på dashboardet **Økonomisk eksempel til selvstudium**.
   
    ![Dialogboksen Fastgør til dashboard](media/service-get-started/power-bi-pin2.png)

4. Vend tilbage til dit dashboard, hvor du kan se det nye felt.

   ![Dashboard med fastgjort diagram](media/service-get-started/power-bi-final-dashboard.png)

## <a name="clean-up-resources"></a>Fjern ressourcer
Nu, hvor du har gennemført selvstudiet, kan du slette datasættet, rapporten og dashboardet. 

1. Vælg **My Workspace** på navigationslinjen til venstre.
2. Vælg fanen **Datasæt**, og find det datasæt, du har importeret i dette selvstudium.  
3. Vælg ellipsen (...) > **Slet**.

    ![Slet datasættet](media/service-get-started/power-bi-delete.jpg)

    Når du sletter datasættet, sletter du også rapporten og dashboardet i Power BI. 


## <a name="next-steps"></a>Næste trin

> [!div class="nextstepaction"]
> [Opret forbindelse til de onlinetjenester, du bruger med Power BI](service-connect-to-services.md)

