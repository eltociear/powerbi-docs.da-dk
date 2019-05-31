---
title: Selv og andre Abonner rapporter og dashboards – Power BI
description: Lær, hvordan du abonnerer på dig selv og andre et snapshot af en Power BI-rapportside, dashboard eller sideinddelt rapport.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: maggies
LocalizationGroup: Common tasks
ms.openlocfilehash: a344e3cdd93fbd237387b61fb4735b41f22625e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65991122"
---
# <a name="subscribe-yourself-and-others-to-reports-and-dashboards-in-the-power-bi-service"></a>Meld dig selv og andre til abonnementer på rapporter og dashboards i Power BI-tjenesten

Du kan abonnere på dig selv og dine kollegaer til rapportsider, dashboards og sideinddelte rapporter, der betyder mest for dig. Powerbi sender en mail med et snapshot til din indbakke. Fortæl Power BI, hvor ofte du vil modtage mails: dagligt, ugentligt eller én gang om dagen efter den første dataopdatering.  Hvis du vælger dagligt eller ugentligt, kan du vælge tid vil du gerne have køre abonnementet.  Du kan i alt angive op til 24 forskellige abonnementer pr. dag for hver rapportside og hvert dashboard.

![mail snapshot af dashboard](media/service-report-subscribe/power-bi-dashboard-email-new.jpg) 

Du kan kun oprette abonnementer i Power BI-tjenesten. Du modtager en mail med et snapshot af rapportsiden eller dashboardet med et link til at åbne rapporten eller dashboardet. På mobilenheder med Power BI-apps installeret startes Power BI-appen i stedet for at åbne rapporten eller dashboardet på Power BI-webstedet, når dette link vælges.

## <a name="requirements"></a>Krav

- **Oprettelse af** et abonnement er en Power BI Pro-funktion.
- Du behøver ikke at have redigeringstilladelser til indholdet (dashboard eller rapport) for at oprette et abonnement til dig selv, men du skal have redigeringstilladerlser for at oprette et for andre. 
- Fra og med januar 2019 behøver du ikke længere at have opdatering af datasæt angivet for at køre et abonnement.  Den kører uafhængigt af eventuelle planlagte opdateringer, som du har angivet.  

## <a name="subscribe-to-a-dashboard-report-page-or-paginated-report"></a>Abonner på et dashboard, en rapportside eller en sideinddelt rapport

Uanset om du abonnerer på et dashboard, rapport eller sideinddelt rapport, processen er tilsvarende. Du bruger den samme knap til at abonnere på dashboards og rapporter i Power BI-tjenesten.

Abonnerer på sideinddelte rapporter er lidt anderledes. Se [dig selv og andre abonnerer en sideinddelt rapport i Power BI-tjenesten](paginated-reports-subscriptions.md) for at få oplysninger.
 
![vælg ikonet Abonner](media/service-report-subscribe/power-bi-subscribe-orientation.png).

1. Åbn dashboardet eller rapporten.
2. Vælg **Abonner** på menulinjen øverst, eller vælg konvolutikonet ![ikonet Abonner](media/service-report-subscribe/power-bi-icon-envelope.png).
   
   ![Ikonet Abonner](media/service-report-subscribe/power-bi-subscribe-icon.png)

3. Brug den gule skyder til at slå abonnementet til og fra.  Abonnementet slettes ikke, når skyderen sættes til **Fra**. Hvis du vil slette abonnementet, skal du vælge ikonet for papirkurven.

4. Din mailadresse er allerede angivet i feltet **Abonner**. Du kan også føje andre mailadresser til abonnementet, men kun på det samme domæne. Hvis rapporten eller dashboardet hostes i [Premium-kapacitet](service-premium-what-is.md), kan du oprette abonnement for andre mailadresser og gruppealiasser. Hvis rapporten eller dashboardet ikke hostes i Premium-kapacitet, kan du oprette abonnement for andre, men de skal også have Power BI Pro-licenser. Se flere oplysninger under [Overvejelser og fejlfinding](#considerations-and-troubleshooting) herunder. 

5. Udfyld mailoplysningerne **Emne** og **Meddelelse**. 

5. Vælg en **Hyppighed** for dit abonnement: **Dagligt**, **Ugentligt** eller **Efter dataopdatering (dagligt)** .  Hvis du kun vil modtage abonnementsmailen på bestemte dage, skal du vælge **Ugentligt** og vælge, hvilke dage du vil modtage den.  Hvis du f.eks. kun vil modtage abonnementsmailen på hverdage, skal du vælge **Ugentligt** og fjerne markeringen af felterne for **lørdag** og **søndag**.  

6. Hvis du vælger **Dagligt** eller **Ugentligt**, kan du også vælge et **Planlagt tidspunkt** for abonnementet.  Du kører den hver hele time eller 15, 30 eller 45 minutter over.  Vælg morgen (AM) eller eftermiddag/aften (PM). Du kan også angive tidszonen.

7. Startdatoen for dit abonnement er som standard den dato, du har oprettet det. Du har mulighed for at vælge en slutdato. Hvis du ikke angiver en slutdato, er den automatisk ét år efter startdatoen. Du kan ændre den til en hvilken som helst dato i fremtiden (op til år 9999) når som helst, før abonnementet slutter. Når et abonnement når en slutdato, ophører det, indtil du aktiveret det igen. Du modtager en meddelelse, før den planlagte slutdato, hvor du bliver spurgt, om du vil forlænge det.    

    På skærmbilledet nedenfor kan du se, at du rent faktisk abonnerer på en *rapportside*, når du abonnerer på en rapport.  Hvis du vil abonnere på mere end én side i en rapport, skal du vælge **Tilføj et andet abonnement** og vælge en anden side. 
      
   ![Ruden Abonner](media/service-report-subscribe/power-bi-subscribe-pane.png)  

7. Vælg **Gem og luk**. Dem, der abonnerer, modtager en mail og et snapshot af dashboardet eller rapportsiden med den hyppighed og det tidspunkt, du har valgt. Du kan i alt oprette op til 24 abonnementer pr. rapport eller dashboard, og du kan angive entydige modtagere, tidspunkter og hyppigheder for hvert abonnement.  For alle abonnementer, der er angivet til **Efter dataopdatering** for dashboardet eller rapporten, sendes der stadig kun en mail efter den første planlagte opdatering.   
      
   > [!TIP]
   > Vil du sende mailen fra et abonnement med det samme eller on-demand når som helst? Vælg **Kør nu** for abonnementerne for det dashboard eller den rapport, du vil sende. Du får vist en meddelelse om, at en mail er på vej til alle med det pågældende abonnement.  Du kan gøre dette så ofte, som du ønsker. Det tæller ikke i forhold til grænsen på 24 planlagte abonnementskørsler pr. dag pr. rapport eller dashboard. De udløser ikke en opdatering af data i det underliggende datasæt. 
   > 
   > 
   
## <a name="email-languages"></a>Mailsprog

Det sprog, der er angivet under Power BI-indstillingerne, bruges til mail og snapshot (se [Understøttede sprog og lande/områder for Power BI](supported-languages-countries-regions.md)). Hvis der ikke er angivet et sprog, bruger Power BI det sprog, der stemmer overens med indstillingen for landestandard i din aktuelle browser. Hvis du vil se eller indstille dine sprogindstillinger, skal du vælge ![tandhjulsikonet](media/service-report-subscribe/power-bi-settings-icon.png) > **Indstillinger > Generelt > Sprog**. 

![Rullelisten Sprog](media/service-report-subscribe/power-bi-language.png)

## <a name="manage-your-subscriptions"></a>Administrer dine abonnementer
Det er kun den person, der har oprettet abonnementet, der kan administrere det.  Der er to stier til skærmen, hvor du kan administrere dine abonnementer.  Den første er at vælge **Administrer alle abonnementer** i dialogboksen **Abonner på mails** (se skærmbilledet under trin 4 herover). Den anden er at vælge tandhjulsikonet ![tandhjulsikon](media/service-report-subscribe/power-bi-settings-icon.png) i Power BI på den øverste menulinje og at vælge **Indstillinger**.

![vælg Indstillinger](media/service-report-subscribe/power-bi-subscribe-settings.png)

De abonnementer, der vises, afhænger af, hvilket arbejdsområde der er aktivt i øjeblikket.  Hvis du vil se alle dine abonnementer på én gang for alle arbejdsområder, skal du sørge for, at **Mit arbejdsområde** er aktivt. Du kan få hjælp til arbejdsområder i [Arbejdsområder i Power BI](service-create-workspaces.md).

![se alle abonnementer under Mit arbejdsområde](media/service-report-subscribe/power-bi-subscriptions.png)

Et abonnement slutter, hvis Pro-licensen udløber, hvis ejeren sletter dashboardet eller rapporten, eller hvis den brugerkonto, der blev brugt til at oprette abonnementet, slettes.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding

* Dashboards med mere end 25 fastgjorte felter eller 4 fastgjorte liverapportsider gengives muligvis ikke fuldstændigt i abonnementsmails, der sendes til brugerne.  Abonnementer på dashboards over disse antallet af felter, der ikke er blokeret. De er dog betragtes som ikke understøttes, hvis du støder på problemer. Overvej at ændre dem for at falder inden for en understøttede område i overensstemmelse hermed.
* Når du konfigurerer din e-mail-abonnementer, Vær opmærksom på er der en forsinkelse mellem, når abonnementet jobbet starter og det nøjagtige tidspunkt e-mailen er sendt.  For at minimere forsinkelsen mellem to, ved at konfigurere et andet tidspunkt for din planlagt opdatering af data end når din e-mail-abonnement er planlagt til at køre.
* For mailabonnementer på dashboardet, hvis alle felter har rækkeniveau (RLS) anvendes, vises disse felter ikke.  
* For mailabonnementer rapport, hvis datasættet bruger sikkerhed på Rækkeniveau, kan du oprette et abonnement til dig selv. Du kan ikke abonnere på andre til en rapport med sikkerhed på rækkeniveau (RLS) anvendes.
* Rapportsideabonnementer er bundet til navnet på siden i rapporten. Hvis du abonnerer på en rapportside og omdøber den, skal du genoprette dit abonnement.
* Din organisation kan konfigurere bestemte indstillinger i Azure Active Directory, som begrænser muligheden for at bruge mailabonnementer i Power BI.  Disse begrænsninger omfatter, men er ikke begrænset til, multifaktorgodkendelse eller IP-intervalbegrænsning, når ressourcer tilgås.
* Mailabonnementer for rapporter/dashboards, der bruger datasæt med direkte forbindelser, understøttes i øjeblikket ikke, når du abonnerer på brugere ud over dig selv.
* Mailabonnementer understøtter ikke de fleste [brugerdefinerede visualiseringer](power-bi-custom-visuals.md).  Den eneste undtagelse er de brugerdefinerede visuelle elementer, der er blevet [certificeret](power-bi-custom-visuals-certified.md).  
* Mailabonnementer understøtter ikke R-drevne brugerdefinerede visualiseringer på nuværende tidspunkt.  
* Mailabonnementer sendes med rapportens tilstande for standardfilter og -udsnit. Hvis du ændrer standardværdierne, efter du har oprettet abonnementet, vises de ikke i mailen.    
* For dashboardabonnementer specifikt understøttes visse typer felter endnu ikke.  Det omfatter: streamingfelter, videofelter, felter med brugerdefineret webindhold.     
* Hvis du deler et dashboard med en kollega uden for din lejer, kan du ikke også oprette et abonnement for den pågældende kollega. Så hvis du er aaron@xyz.com, kan du dele med anyone@ABC.com, men du kan endnu ikke oprette abonnement for anyone@ABC.com, og vedkommende kan ikke abonnere på delt indhold.      
* Power BI afbryder automatisk midlertidigt opdatering af datasæt, der er knyttet til dashboards og rapporter, som ikke er blevet besøgt i mere end to måneder.  Men hvis du føjer et abonnement til et dashboard eller en rapport, afbrydes det ikke midlertidigt, selvom det ikke besøges.    
* Hvis du ikke modtager abonnementsmailene, skal du kontrollere, at din brugers hovednavn (UPN) kan modtage mails. [Power BI-teamet arbejder på at slække på dette krav](https://community.powerbi.com/t5/Issues/No-Mail-from-Cloud-Service/idc-p/205918#M10163), så hold dig opdateret. 
* Hvis dit dashboard eller din rapport er i Premium-kapacitet, kan du bruge mailaliasser for grupper til abonnementer i stedet for at oprette abonnementer for kollegaer én mailadresse ad gangen. Aliasserne er baseret på det aktuelle Active Directory. 

## <a name="next-steps"></a>Næste trin

- [Selv og andre Abonner en sideinddelt rapport i Power BI-tjenesten](paginated-reports-subscriptions.md)
- Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)    
- [Læs blogindlægget](https://powerbi.microsoft.com/blog/introducing-dashboard-email-subscriptions-a-360-degree-view-of-your-business-in-your-inbox-every-day/)
