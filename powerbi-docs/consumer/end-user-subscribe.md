---
title: Meld dig selv til et abonnement på rapporter og dashboards
description: Få mere at vide om, hvordan du melder dig selv og kolleger til et abonnement på et snapshot af en rapport eller et dashboard, sendt via mail, i Power BI.
author: mihart
ms.author: mihart
manager: kvivek
ms.reviewer: cmfinlan
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 02/14/2019
LocalizationGroup: Common tasks
ms.openlocfilehash: 99501c6acc54188e2e87f0ae93354cac8116273c
ms.sourcegitcommit: e9c45d6d983e8cd4cb5af938f838968db35be0ee
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/05/2019
ms.locfileid: "57327935"
---
# <a name="subscribe-to-a-report-or-dashboard-in-power-bi-service"></a>Abonner på en rapport eller et dashboard i Power BI-tjenesten 
Det har aldrig været nemmere at holde dig opdateret om dine vigtigste dashboards og rapporter. Abonner på rapportsider og dashboards, der betyder mest for dig, og Power BI sender et snapshot til din indbakke. Fortæl Power BI, hvor ofte du vil modtage mails: dagligt, ugentligt eller efter dataopdatering. Du kan tilmed angive et bestemt tidspunkt for, hvornår Power BI sender mails, eller køre det nu.  

Det sprog, der er angivet under Power BI-indstillingerne, bruges til mail og snapshot (se [Understøttede sprog og lande/regioner til Power BI](../supported-languages-countries-regions.md)). Hvis der ikke er angivet et sprog, bruger Power BI det sprog, der stemmer overens med indstillingen for landestandard i din aktuelle browser. Hvis du vil se eller indstille dine sprogindstillinger, skal du vælge ![tandhjulsikonet](./media/end-user-subscribe/power-bi-settings-icon.png) > **Indstillinger > Generelt > Sprog**. 

![Rullelisten Sprog](./media/end-user-subscribe/power-bi-language.png)

Når du modtager mailen, indeholder den et link til at "gå til rapport eller dashboard". På mobile enheder med Power BI-apps installeret, startes appen (i modsætning til standardhandlingen med at åbne rapporten eller dashboardet på Power BI-webstedet), hvis du vælger dette link.


## <a name="requirements"></a>Krav
**Oprettelse af** et abonnement er en Power BI Pro-funktion.   

## <a name="subscribe-to-a-dashboard-or-a-report-page"></a>Abonner på et dashboard eller en rapportside
Uanset om du abonnerer på et dashboard eller en rapport, er processen den samme. Du bruger den samme knap til at abonnere på dashboards og rapporter i Power BI-tjenesten.
 
![vælg ikonet Abonner](./media/end-user-subscribe/power-bi-subscribe-orientation.png).

1. Åbn dashboardet eller rapporten.
2. Vælg **Abonner** på menulinjen øverst, eller vælg konvolutikonet ![ikonet Abonner](./media/end-user-subscribe/power-bi-icon-envelope.png).
   
   ![Ikonet Abonner](./media/end-user-subscribe/power-bi-subscribe-icon.png)

   ![Vinduet Abonner](./media/end-user-subscribe/power-bi-emails-new.png)
    
    Skærmen til venstre vises, når du er på et dashboard og vælger **Abonner**. Skærmen til højre vises, når du er på en rapportside og vælger **Abonner**. Hvis du vil abonnere på mere end én side i en rapport, skal du vælge **Tilføj et andet abonnement** og vælge en anden side. 

4. Brug den gule skyder til at slå abonnementet til og fra.  Abonnementet slettes ikke, når skyderen sættes til Fra. Hvis du vil slette abonnementet, skal du vælge ikonet for papirkurven.

4. Alternativt kan du tilføje mailoplysninger. 

5. Vælg en **Hyppighed** for dit abonnement.  Du kan vælge Dagligt, Ugentligt eller Efter dataopdatering (dagligt).  Hvis du kun vil modtage abonnementsmailen på bestemte dage, skal du vælge **Ugentligt** og vælge, hvilke dage du vil modtage den.  Hvis du f.eks. kun vil modtage abonnementsmailen på hverdage, skal du vælge **Ugentligt** som hyppighed og fjerne markeringen af felterne for lørdag og søndag.   

6. Planlæg det tidspunkt, som mailen skal sendes på, ved at vælge Dagligt eller Ugentligt som hyppighed, og angiv et **planlagt** **tidspunkt** for abonnementet.   

7. Planlæg start- og slutdato ved at angive datoer i datofelterne. Starttidspunktet for dit abonnement er som standard den dato, du opretter den, og slutdatoen vil være et år senere. Når et abonnement når en slutdato, ophører det, indtil du aktiveret det igen.  Du modtager en meddelelse, før den planlagte slutdato, hvor du bliver spurgt, om du vil forlænge det.     

8. Hvis du vil gennemse abonnementet og teste det, skal du vælge **Kør nu**.  Så sendes der en mail til dig med det samme. 

8. Hvis alt ser rigtigt ud, skal du vælge **Gem og luk** for at gemme abonnementet. Du modtager en mail og et snapshot af dashboardet eller rapporten iht. den plan, du har angivet. For alle abonnementer, hvor hyppigheden er angivet til **Efter dataopdatering**, sendes der kun en mail efter den første planlagte opdatering på den pågældende dag.
   
   ![mail snapshot af dashboard](media/end-user-subscribe/power-bi-subscribe-email.png)
   
    Opdatering af rapportsiden opdaterer ikke datasættet. Det er kun ejeren af datasættet, der kan opdatere et datasæt manuelt. Hvis du vil søge efter navnet på det eller de underliggende datasæt, skal du vælge **Få vist relaterede** på den øverste menulinje.
   
    ![Relaterede datasæt](./media/end-user-subscribe/power-bi-view-related-screen.png)


## <a name="manage-your-subscriptions"></a>Administrer dine abonnementer
Det er kun dig, som kan administrere dine abonnementer. Vælg **Abonner** igen, og vælg **Administrer alle abonnementer** i nederste venstre hjørne. Se skærmbilleder ovenfor. 

![se alle abonnementer under Mit arbejdsområde](./media/end-user-subscribe/power-bi-manage.png)

Et abonnement slutter, hvis Pro-licensen udløber, dashboardet eller rapporten slettes af ejeren, eller hvis den brugerkonto, der blev brugt til oprettelse af abonnementet, slettes.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Dashboards med mere end 25 fastgjorte felter eller 4 fastgjorte liverapportsider gengives muligvis ikke fuldstændigt i abonnementsmails, der sendes til brugerne. Det anbefales, at du reducerer fastgjorte felter til mindre end 25 og fastgjorte liverapporter til mindre end 4 for at sikre, at mailen gengives korrekt.  
* Hvis der er anvendt sikkerhed på rækkeniveau på nogen af felterne, bliver disse felter ikke vist for e-mailabonnementer på dashboard.  Hvis datasættet bruger RLS, vil du ikke kunne oprette et abonnement for mailabonnementer på rapporter.
* Rapportsideabonnementer er bundet til navnet på siden i rapporten. Hvis du abonnerer på en rapportside, og den bliver omdøbt, skal du genoprette dit abonnement
* Hvis du ikke kan bruge abonnementsfunktionen, skal du kontakte din systemadministrator. Din organisation kan have deaktiveret denne funktion pga. godkendelse eller af andre årsager.  
* Mailabonnementer understøtter ikke de fleste [brugerdefinerede visuelle elementer](../power-bi-custom-visuals.md).  Undtagelsen er de brugerdefinerede visualiseringer, der er blevet [certificeret](../power-bi-custom-visuals-certified.md).  
* Mailabonnementer understøtter ikke R-drevne brugerdefinerede visuals på nuværende tidspunkt.  
* Særligt for dashboardabonnementer understøttes nogle typer af felter endnu ikke.  Det omfatter: streamingfelter, videofelter, felter med brugerdefineret webindhold.     
* Abonnementer mislykkes muligvis på dashboards og rapporter med meget store billeder på grund af størrelsesbegrænsninger for mails.    
* Power BI afbryder automatisk midlertidigt opdatering af datasæt, der er knyttet til dashboards og rapporter, som ikke er blevet besøgt i mere end to måneder.  Men hvis du føjer et abonnement til et dashboard eller en rapport, standses det ikke midlertidigt, selvom det ikke besøges.    

## <a name="next-steps"></a>Næste trin

[Søg efter og sortér indhold](end-user-search-sort.md)
