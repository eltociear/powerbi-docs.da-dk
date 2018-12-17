---
title: Abonner på rapporter og dashboards i Power BI-tjenesten
description: Få mere at vide om, hvordan du selv og andre abonnerer på et snapshot af en rapport og et dashboard i Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 635e16a6c7deaf6d2bdb3617d29625e8fda005d2
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280208"
---
# <a name="subscribe-to-a-report-or-dashboard-in-power-bi-service"></a>Abonner på en rapport eller et dashboard i Power BI-tjenesten 
Det har aldrig været nemmere at holde dig opdateret om dine vigtigste dashboards og rapporter. Abonner på rapportsider og dashboards, der betyder mest for dig, og Power BI sender et snapshot til din indbakke. Fortæl Power BI, hvor ofte du gerne vil modtage mails: fra en gang om dagen til en gang om ugen. 

Det sprog, der er angivet under Power BI-indstillingerne, bruges til mail og snapshot (se [Understøttede sprog og lande/regioner til Power BI](../supported-languages-countries-regions.md)). Hvis der ikke er angivet et sprog, bruger Power BI det sprog, der stemmer overens med indstillingen for landestandard i din aktuelle browser. Hvis du vil se eller indstille dine sprogindstillinger, skal du vælge ![tandhjulsikonet](./media/end-user-subscribe/power-bi-settings-icon.png) > **Indstillinger > Generelt > Sprog**. 

![Rullelisten Sprog](./media/end-user-subscribe/power-bi-language.png)

Når du modtager mailen, indeholder den et link til "gå til rapport eller dashboard". På mobile enheder med Power BI-apps installeret, startes appen (i modsætning til standardhandlingen med at åbne rapporten eller dashboardet på Power BI-webstedet), hvis du vælger dette link.


## <a name="requirements"></a>Krav
- **Oprettelse af** et abonnement er en Power BI Pro-funktion. 
- Da abonnementsmails kun sendes, når et underliggende datasæt opdateres, kan du ikke abonnere på de datasæt, der ikke opdateres.

## <a name="subscribe-to-a-dashboard-or-a-report-page"></a>Abonner på et dashboard eller en rapportside
Uanset om du abonnerer på et dashboard eller en rapport, er processen stort set den samme. Du bruger den samme knap til at abonnere på dashboards og rapporter i Power BI-tjenesten.
 
![vælg ikonet Abonner](./media/end-user-subscribe/power-bi-subscribe-orientation.png).

1. Åbn dashboardet eller rapporten.
2. Vælg **Abonner** på den øverste menulinje, eller vælg konvolutikonet ![ikonet Abonner](./media/end-user-subscribe/power-bi-icon-envelope.png).
   
   ![Ikonet Abonner](./media/end-user-subscribe/power-bi-subscribe-icon.png)

3. Brug den gule skyder til at slå abonnementet til og fra.  Abonnementet slettes ikke, når skyderen sættes til Fra. Hvis du vil slette abonnementet, skal du vælge ikonet for papirkurven.

4. Alternativt kan du tilføje mailoplysninger. 

    I skærmbilledet nedenfor kan du se, at når du abonnerer på en rapport, abonnerer du rent faktisk på en *rapportside*.  Hvis du vil abonnere på mere end én side i en rapport, skal du vælge **Tilføj et andet abonnement** og vælge en anden side. 
      
   ![Vinduet Abonner](./media/end-user-subscribe/power-bi-emails.png)

5. Vælg **Gem og luk** for at gemme abonnementet. Du modtager en mail og et snapshot af dashboardet eller rapportsiden, hver gang nogle af de underliggende datasæt ændres. Hvis dashboardet eller rapporten opdateres mere end en gang om dagen, sendes mailen kun efter den første opdatering.  
   
   ![mail snapshot af dashboard](./media/end-user-subscribe/power-bi-dashboard-email-new.jpg)
   
Opdatering af rapportsiden opdaterer ikke datasættet. Det er kun ejeren af datasættet, der kan opdatere et datasæt manuelt. Hvis du vil søge efter navnet på det eller de underliggende datasæt, skal du vælge **Få vist relaterede** på den øverste menulinje.
   
![Relaterede datasæt](./media/end-user-subscribe/power-bi-view-related-screen.png)

## <a name="how-the-email-schedule-is-determined"></a>Sådan bestemmes mailtidsplanen
I nedenstående tabel beskrives, hvor ofte du modtager en mail. Det afhænger alt sammen af forbindelsesmetoden for det datasæt, som dashboardet eller rapporten er baseret på (DirectQuery, Direkte forbindelse, importeret til Power BI eller Excel-fil i OneDrive eller SharePoint Online), og af de tilgængelige og valgte abonnementsindstillinger (dagligt, ugentligt eller ingen).

|  | **DirectQuery** | **Live Connect** | **Planlagt opdatering (import)** | **Excel-fil i OneDrive/SharePoint Online** |
| --- | --- | --- | --- | --- |
| **Hvor ofte bliver rapporten/dashboardet opdateret?** |Hvert 15. min. |Power BI undersøger hvert 15. minut, og hvis datasættet er ændret, opdateres rapporten. |Brugeren vælger ingen, dagligt eller ugentligt. Dagligt kan være op til 8 gange om dagen. Ugentlig er faktisk en ugentlig tidsplan, som brugeren opretter og indstiller til opdatering så lidt som en gang om ugen og så ofte som dagligt. |Én gang i timen |
| **Hvor stor kontrol har brugeren over tidsplanen for mail ifm. abonnementet?** |Indstillinger er: dagligt eller ugentligt |Ingen indstillinger: Brugerne får tilsendt en mail, hvis rapporten opdateres, men ikke mere end én gang om dagen. |Hvis tidsplanen for opdatering er dagligt, er indstillinger dagligt og ugentligt.  Hvis tidsplanen for opdatering er ugentligt, kan der kun vælges ugentligt. |Ingen indstillinger: Brugeren får tilsendt en mail, når datasættet opdateres, men ikke mere end én gang om dagen. |

## <a name="manage-your-subscriptions"></a>Administrer dine abonnementer
Det er kun dig, som kan administrere dine abonnementer. Vælg **Abonner** igen, og vælg **Administrer alle abonnementer** (se skærmbilleder under trin 4 ovenfor). 

![se alle abonnementer under Mit arbejdsområde](./media/end-user-subscribe/power-bi-subscriptions.png)

Et abonnement slutter, hvis Pro-licensen udløber, dashboardet eller rapporten slettes af ejeren, eller hvis den brugerkonto, der blev brugt til oprettelse af abonnementet, slettes.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Hvis der er anvendt sikkerhed på rækkeniveau på nogen af felterne, bliver disse felter ikke vist for e-mailabonnementer på dashboard.  Hvis datasættet bruger RLS, vil du ikke kunne oprette et abonnement for mailabonnementer på rapporter.
* Rapportsideabonnementer er bundet til navnet på siden i rapporten. Hvis du abonnerer på en rapportside, og den bliver omdøbt, skal du genoprette dit abonnement
* Visse indstillinger for din organisation kan konfigureres i Azure Active Directory, hvilket kan begrænse muligheden for at bruge mailabonnementer i Power BI.  Dette omfatter, men er ikke begrænset til, multifaktorgodkendelse eller IP-intervalbegrænsning, når ressourcer tilgås.
* For mailabonnementer på datasæt med direkte forbindelse får du kun mails, når dataene ændres. Så hvis der finder en opdatering sted, men ingen dataændringer, sender Power BI dig ikke en mail.
* Mailabonnementer understøtter ikke de fleste [brugerdefinerede visuelle elementer](../power-bi-custom-visuals.md).  Den eneste undtagelse er de brugerdefinerede visuelle elementer, der er blevet [certificeret](../power-bi-custom-visuals-certified.md).  
* Mailabonnementer understøtter ikke R-drevne brugerdefinerede visuals på nuværende tidspunkt.  
* Hvis der er anvendt sikkerhed på rækkeniveau på nogen af dashboardfelterne, bliver disse felter ikke vist.
* Mailabonnementer sendes med rapportens tilstande for standardfilter og -udsnit. Hvis du ændrer standardværdierne, efter at du har oprettet abonnementet, vises de ikke i mailen.    
* Særligt for dashboardabonnementer understøttes nogle typer af felter endnu ikke.  Det omfatter: streamingfelter, videofelter, felter med brugerdefineret webindhold.     
* Abonnementer mislykkes muligvis på dashboards og rapporter med meget store billeder på grund af størrelsesbegrænsninger for mails.    
* Power BI afbryder automatisk opdatering på datasæt, der er knyttet til dashboards og rapporter, som ikke er blevet besøgt i mere end to måneder.  Men hvis du føjer et abonnement til et dashboard eller en rapport, standses det ikke midlertidigt, selvom det ikke besøges.    

## <a name="next-steps"></a>Næste trin
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)    
* [Læs blogindlægget](https://powerbi.microsoft.com/blog/introducing-dashboard-email-subscriptions-a-360-degree-view-of-your-business-in-your-inbox-every-day/)

