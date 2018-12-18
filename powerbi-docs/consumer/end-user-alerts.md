---
title: 'Selvstudium: Indstil databeskeder i Power BI-tjenesten'
description: I dette selvstudium får du mere at vide om, hvordan du angiver beskeder, så du får besked, når dataene i dine dashboards ændres ud over de grænser, du har angivet i Microsoft Power BI-tjenesten.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: JbL2-HJ8clE
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: tutorial
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 0d614b6028fa4d7e11ac5bf82e05d44a95e4f234
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280851"
---
# <a name="tutorial-set-data-alerts-in-power-bi-service"></a>Selvstudium: Indstil databeskeder i Power BI-tjenesten
Angiv beskeder, så du får besked, når dataene på dine dashboards ændres ud over de grænser, du har angivet. 

Du kan angive beskeder for felter, hvis du har en Power BI Pro-licens, eller hvis et dashboard er blevet delt med dig fra en [Premium-kapacitet](../service-premium.md). Der kan kun angives beskeder på felter, der er fastgjort via rapportvisualiseringer, og kun på målere, KPI'er og kort. Beskeder kan angives på visualiseringer, der oprettes ud fra streamingdatasæt, der er fastgjort på et dashboard via en rapport, men de kan ikke angives på streamingfelter, der er oprettet direkte på dashboardet ved hjælp af **Tilføj felt** > **Brugerdefinerede streamingdata**. 

Det er kun dig, der kan se de angivne beskeder, selvom du deler dashboardet. Databeskeder er fuldt synkroniseret på tværs af platforme. Angiv og få vist databeskeder [i Power BI-mobilapps](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) og i Power BI-tjenesten. 

![felter](../media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Datadrevne beskeder indeholder oplysninger om dine data. Hvis du få vist dine data i Power BI på en mobilenhed, og enheden bliver stjålet, anbefaler vi, at du bruger Power BI-tjenesten til at slå alle datadrevne regler for beskeder fra.
> 

Denne artikel omhandler følgende:
> [!div class="checklist"]
> * Hvem kan indstille beskeder
> * Hvilke visuals understøtter beskeder
> * Hvem kan indstille beskeder
> * Virker beskeder i Power BI Desktop og Mobil
> * Hvordan opretter jeg en besked
> * Hvor modtager jeg mine beskeder

Hvis du ikke er tilmeldt Power BI, kan du [tilmelde dig en gratis prøveversion](https://app.powerbi.com/signupredirect?pbi_source=web), før du begynder.

## <a name="set-data-alerts-in-power-bi-service"></a>Indstil databeskeder i Power BI-tjenesten
Se, hvordan Amanda føjer nogle beskeder til felterne på sit dashboard. Følg derefter den trinvise vejledning under videoen for at prøve det selv.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

I dette eksempel bruges et kortfelt fra [Retail Analysis-eksempel](http://go.microsoft.com/fwlink/?LinkId=529778)dashboardet.

1. Vælg ellipsen i en dashboardmåler, et KPI eller et kortfelt.
   
   ![Feltet Butikker i alt](media/end-user-alerts/powerbi-card.png)
2. Vælg klokkeikonet ![beskedikon](media/end-user-alerts/power-bi-bell-icon.png) eller **Administrer beskeder** for at tilføje en eller flere beskeder for **Butikker i alt**.
   
1. I ruden **Administrer beskeder** skal du vælge **+ Tilføj påmindelsesregel**.  Kontrollér, at skyderen er angivet til **Til**, og giv beskeden en titel. Titler hjælper dig med let at genkende dine beskeder.
   
   ![Vinduet Administrer beskeder](media/end-user-alerts/powerbi-alert-title.png)
4. Rul ned, og angiv oplysninger om beskederne.  I dette eksempel opretter vi en besked, som skal sendes til os én gang om dagen, hvis antallet af samlede butikker går over 100. Beskederne vises i vores meddelelsescenter. Vi får også Power BI til at sende os en mail.
   
   ![Vinduet Administrer beskeder, angiv grænseværdi](media/end-user-alerts/power-bi-set-alert-details.png)
5. Vælg **Gem og luk**.

## <a name="receiving-alerts"></a>Modtag beskeder
Når de sporede data når en af de angivne tærskelværdier, sker der flere ting. Først tjekker Power BI, om der er gået mere end én time eller mere end et døgn (afhænger af den valgte indstilling), siden den seneste besked blev sendt. Du får en besked, så længe dataene har overskredet grænsen.

Derefter sendes en besked til meddelelsescenteret og evt. en mail via Power BI. Hver enkelt besked indeholder et direkte link til dine data. Vælg linket for at se det relevante felt.  

1. Hvis du har indstillet beskeden til at sende en mail til dig, modtager du mail i din indbakke.
   
   ![Mail med vigtig besked](media/end-user-alerts/powerbi-alerts-email.png)
2. Power BI føjer en meddelelse til dit **meddelelsescenter** og føjer et ny beskedikon til det relevante felt.
   
   ![Meddelelsesikon i Power BI-tjeneste](media/end-user-alerts/powerbi-alert-notifications.png)
3. Åbn dit meddelelsescenter for at få vist oplysningerne for beskeder.
   
    ![læs beskeden](media/end-user-alerts/powerbi-alert-notification.png)
   
   > [!NOTE]
   > Beskeder fungerer kun i forbindelse med opdaterede data. Når data opdateres, kontrolleres det via Power BI, om der er angivet en besked for disse data. Hvis dataene har nået grænsen for en besked, udløses der en besked.
   > 
   > 

## <a name="managing-alerts"></a>Administration af beskeder
Der er mange måder at administrere dine beskeder på: Fra selve dashboardfeltet, fra menuen Indstillinger for Power BI og på et individuelt felt i [Power BI-mobilappen på iPhone](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) eller i [Power BI-mobilappen til Windows 10](mobile/mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Fra selve feltet
1. Hvis du vil ændre eller fjerne en besked fra et felt, skal du genåbne vinduet **Administrer beskeder** ved at vælge klokkeikonet for ![Beskedikon](media/end-user-alerts/power-bi-bell-icon.png). Alle de beskeder, du har angivet for dette felt, vises.
   
    ![Vinduet Administrer beskeder](media/end-user-alerts/powerbi-see-alerts.png).
2. Hvis du vil redigere en besked, skal du vælge pilen til venstre for beskednavnet.
   
    ![pil ud for Beskednavn](media/end-user-alerts/powerbi-see-alerts-arrow.png).
3. Hvis du vil slette en besked, skal du vælge skraldespanden til højre for beskednavnet.
   
      ![Skraldespandsikonet er valgt](media/end-user-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>I menuen Indstillinger for Power BI
1. Vælg tandhjulsikonet på menulinjen i Power BI.
   
    ![tandhjulsikon](media/end-user-alerts/powerbi-gear-icon.png).
2. Under **Indstillinger** skal du vælge **Beskeder**.
   
    ![Fanen Beskeder i vinduet Indstillinger](media/end-user-alerts/powerbi-alert-settings.png)
3. Her kan du slå beskeder til og fra, åbne vinduet **Administrer beskeder** for at ændre eller slette beskeden.

## <a name="tips-and-troubleshooting"></a>Tip og fejlfinding
* Beskeder understøttes ikke i øjeblikket for Bing-felter eller kortfelter med målinger for dato/klokkeslæt.
* Beskeder fungerer kun i forbindelse med numeriske datatyper.
* Beskeder fungerer kun i forbindelse med opdaterede data. De fungerer ikke med statistiske data.
* Beskeder fungerer kun i forbindelse med streamingdatasæt, hvis du opretter en rapportvisualisering for KPI/kort/måler og derefter fastgør visualiseringen til dashboardet.

## <a name="clean-up-resources"></a>Fjern ressourcer
Fremgangsmåden til sletning af beskeder er beskrevet ovenfor. Vælg tandhjulsikonet på menulinjen i Power BI. Vælg **Beskeder** under **Indstillinger**, og slet beskeden.

> [!div class="nextstepaction"]
> [Angiv databeskeder på din mobilenhed](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


