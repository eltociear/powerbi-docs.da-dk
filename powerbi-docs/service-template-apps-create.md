---
title: Udarbejd skabelonprogrammer i Power BI (prøveversion)
description: Sådan opretter du skabelonprogrammer i Power BI, som du kan distribuere til Power BI-kunder.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/22/2019
ms.author: maggies
ms.openlocfilehash: 653050fbe5c860ef1902a4700c3a70a8af2f7092
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514976"
---
# <a name="create-a-template-app-in-power-bi-preview"></a>Opret et skabelonprogram i Power BI (prøveversion)

Med de nye Power BI-*skabelonprogrammer* kan Power BI-partnere udarbejde programmer i Power BI med kun lidt eller ingen kode og udrulle dem til Power BI-kunder.  Denne artikel indeholder en trinvis vejledning til at oprette et Power BI-skabelonprogram.

Hvis du kan oprette Power BI-rapporter og dashboards, du kan blive en *skabelon generator* og builds og pakker analytiske indhold i en *app*. Du kan installere din app til andre Power BI-lejere via alle tilgængelige platforme, f.eks AppSource, eller ved at bruge det i dit eget webtjeneste. Som en builder har du mulighed for at oprette en beskyttet analytics-pakke til distribution.

Administratorer af Power BI-lejere styrer, hvem der kan oprette skabelonprogrammer i organisationen, og hvem der kan installere dem. Disse brugere, der er godkendt kan installere din skabelonapp, og derefter redigere den og distribuere den til Power BI brugerne i deres organisation.

## <a name="prerequisites"></a>Forudsætninger

Her er kravene til at udarbejde et skabelonprogram:  

- En [Power BI Pro-licens](service-self-service-signup-for-power-bi.md)
- En [installation af Power BI Desktop](desktop-get-the-desktop.md) (valgfrit)
- Kendskab til de [grundlæggende begreber i Power BI](service-basic-concepts.md)
- Tilladelser til at oprette et skabelonprogram. Du kan finde flere oplysninger på Power BI[-administrationsportal, indstillingen Skabelonprogram](service-admin-portal.md#template-apps-settings-preview).

## <a name="enable-app-developer-mode"></a>Aktivér programudviklertilstand

Hvis du vil oprette et skabelonprogram, som du kan distribuere til andre Power BI-lejere, skal du være i Programudviklertilstand. Ellers opretter du blot et program til Power BI-brugerne i din egen organisation.

1. Åbn Power BI-tjenesten i en browser.
2. Gå til **Indstillinger** > **Generelt** > **Udvikler** > **Aktivér udviklingstilstand af skabelonrogram**.

    ![Aktivér skabelonprogrammer](media/service-template-apps-create/power-bi-dev-template-app.png)

    Hvis du ikke kan se denne indstilling, skal du kontakte din Power BI-administrator, som skal give dig [tilladelse til at udvikle skabelonprogrammer](service-admin-portal.md#template-apps-settings-preview) på administrationsportalen.

3. Vælg **Anvend**.

## <a name="create-the-template-app-workspace"></a>Opret arbejdsområdet for skabelonprogrammet

Hvis du vil oprette et skabelonprogram, som du kan distribuere til andre Power BI-lejere, skal du oprette det i et af de nye programarbejdsområder.

1. Vælg **Arbejdsområder** > **Opret programarbejdsområde** i Power BI-tjenesten.

    ![Opret apparbejdsområde](media/service-template-apps-create/power-bi-new-workspace.png)

2. Under **Opret et programarbejdsområde**, under **Se eksempel på forbedrede arbejdsområder** skal du vælge **Prøv nu**.

    ![Prøv nye arbejdsområder](media/service-template-apps-create/power-bi-try-now-new-workspace.png)

3. Angiv et navn, en beskrivelse (valgfrit) og et logobillede (valgfrit) for dit programarbejdsområde.

4. Vælg **Udvikl et skabelonprogram**.

    ![Udvikl et skabelonprogram](media/service-template-apps-create/power-bi-template-app-develop.png)

5. Vælg **Gem**.
>[!NOTE]
>Du skal have tilladelse fra din Power BI-administrator for at markedsføre skabelon apps.

## <a name="create-the-content-in-your-template-app"></a>Opret indhold i dit skabelonprogram

Som med et almindeligt Power BI-programarbejdsområde er dit næste skridt at oprette indholdet i arbejdsområdet.  I denne prøveversion af skabelonprogrammer understøtter vi kun op til én af hver type: ét datasæt, én rapport og ét dashboard.

- [Opret dit Power BI-indhold](power-bi-creator-landing.md) i dit programarbejdsområde.

Hvis du bruger parametre i Power-forespørgsel, skal du kontrollere, at de har veldefinerede typer (f.eks. Text). Typerne Any og Binary understøttes ikke.

[Tip til udarbejdelse af skabelonprogrammer i Power BI (prøveversion)](service-template-apps-tips.md) indeholder forslag, der er værd at overveje, når du opretter rapporter og dashboards til dit skabelonprogram.

## <a name="create-the-test-template-app"></a>Opret testskabelonprogrammet

Nu, hvor du har indhold i dit arbejdsområde, er du klar til at pakke det i et skabelonprogram. Det første trin er at oprette et testskabelonprogram, som kun er tilgængeligt i din organisation på din lejer.

1. Vælg **Opret program** i arbejdsområdet for skabelonprogrammet.

    ![Opret app](media/service-template-apps-create/power-bi-create-app.png)

    Her, udfylde du bygning af yderligere indstillinger til din skabelonapp i fem kategorier:

    **Branding**

    ![Branding](media/service-template-apps-create/power-bi-create-branding.png)
    - Appnavn
    - Beskrivelse
    - Supportwebsted (link vises under app-oplysninger efter fordeling af skabelonapp som org app)
    - App-logo (45K filstørrelser, 1:1 højde-bredde-forhold, .png .jpg .jpeg formater)
    - Temafarve for App

    **Indhold**

    **App-landingsside:** Definer en rapport eller et dashboard for at være landingssiden af din app, skal du bruge en landingsside, der giver den rette indtryk:

    ![Indhold](media/service-template-apps-create/power-bi-create-content.png)

    **Kontrolelement**

    Angiv grænser og begrænsninger, som dit programbrugere har med indholdet af dit program. Du kan bruge dette kontrolelement til at beskytte immaterielle rettigheder i din app.

    ![Kontrolelementet](media/service-template-apps-create/power-bi-create-control.png)

    >[!NOTE]
    >Eksport til .pbix-format er altid blokeret for brugere, der installerer appen.

    **Parametre**

    Brug denne kategori til at administrere parameteren funktionsmåde, når der oprettes forbindelse til datakilder. Få mere at vide om [oprette forespørgselsparametre](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/).

    ![Parametre](media/service-template-apps-create/power-bi-create-parameters.png)
    - **Værdien**: Parameteren standardværdi.
    - **Påkrævet**: bruges til at kræve, at indtaste en brugerspecifikke parameter under installationen.
    - **Lås**: Låsning forhindrer installationsprogrammet opdaterer en parameter.
    - **Statisk**: Aktivér i tilfælde af appen indeholder *kun* eksempel på data. Når du vælger **statisk**, installationsguiden ikke beder brugerne om at oprette forbindelse til en datakilde.

    **Få adgang til** i testfasen beslutte, hvilke andre i virksomheden kan installere og teste din app. Bare rolig, du kan altid vende tilbage og ændre disse indstillinger senere (indstilling påvirker ikke adgang til appen distribuerede skabelon).

2. Vælg **Opret program**.

    Du får vist en meddelelse om, at testprogrammet er klar med et link til at kopiere og dele med testerne af dit program.

    ![Testprogrammet er klar](media/service-template-apps-create/power-bi-template-app-test-ready.png)

    Du har også udført det første trin i processen for udgivelsesadministration, der er som følger.

## <a name="manage-the-template-app-release"></a>Administrer udgivelsen af skabelonprogrammet

Før du udgiver dette skabelonprogram offentligt, skal du sikre, at det er klar. Power BI indeholder ruden Udgivelsesadministration, hvor du kan følge og undersøge den fulde sti til udgivelse af programmet. Du kan også udløse overgangen fra fase til fase. De almindelige faser er:

- Opret et testprogram: kun til test i organisationen.
- Hæv testpakken til præproduktionsfasen: test uden for organisationen.
- Hæv præproduktionspakken til produktion: produktionsversion.
- Slet en pakke, eller start forfra fra den forrige fase.

URL-adressen ændres ikke, når du flytter mellem version faser. Kampagnetilbud påvirker ikke den URL-adresse til sig selv.

Lad os gå gennem faserne:

1. Vælg **Udgivelsesadministration** i arbejdsområdet for skabelonprogrammet.

    ![Ikon for Udgivelsesadministration](media/service-template-apps-create/power-bi-release-management-icon.png)

2. Vælg **Opret program**.

    Hvis du oprettede testprogrammet under trinnet **Opret testskabelonprogrammet** ovenfor, er den gule prik ud for **Test** allerede udfyldt, og du behøver ikke at vælge **Opret program** her. Hvis du vælger den, vender du tilbage til processen til oprettelse af skabelonprogrammer.

3. Vælg **Få link**.

    ![Opret program, få link](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)

4. Du tester oplevelsen af programinstallationen ved at kopiere linket i meddelelsesvinduet og indsætte det i et nyt browservindue.

    Herfra følger du den samme fremgangsmåde som dine kunder. Se [Installér og distribuer skabelonprogrammer i din organisation](service-template-apps-install-distribute.md) for at se deres version.

5. Vælg **Installér** i dialogboksen.

    Når installationen er fuldført, får du vist en meddelelse om, at det nye program er klar.

6. Vælg **Gå til program**.
7. Under **Kom i gang med dit nye program** kan du se programmet, som dine kunder vil se det.

    ![Kom i gang med dit program](media/service-template-apps-create/power-bi-template-app-get-started.png)
8. Vælg **Udforsk program** for at bekræfte testprogrammet sammen med eksempeldataene.
9. Hvis du vil foretage ændringer, skal du vende tilbage til programmet i det oprindelige arbejdsområde. Opdater testprogrammet, indtil du er tilfreds.
10. Når du er klar til at markedsføre din app til præ-produktions til yderligere test uden for din lejer, gå tilbage til den **Release Management** rude, og vælg **Hæv app**. 

    ![Hæv programmet til præproduktion](media/service-template-apps-create/power-bi-template-app-promote.png)

    >[!NOTE]
    > Når appen er forfremmet bliver offentligt tilgængelige uden for din organisation.

11. Vælg **Hæv** for at bekræfte dit valg.
12. Kopiér denne nye URL-adresse for at dele den uden for din lejer med henblik på test. Dette link er også et du indsender, for at starte processen med at distribuere din app på AppSource ved at oprette en [nye Cloudpartnerportal tilbud](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-publish-offer). Send kun præ-produktions-links til Cloud Partner-portalen. Kun, når appen er blevet godkendt, og du får besked, den er publiceret i AppSource, og derefter kan du forfremme denne pakke til produktion i Power BI.
13. Når programmet er klar til produktion eller deling via AppSource, skal du gå tilbage til ruden **Udgivelsesadministration** og vælge **Hæv program** ud for **Præproduktion**.
14. Vælg **Hæv** for at bekræfte dit valg.

    Programmet er nu i produktion og klar til distribution.

    ![Program i produktion](media/service-template-apps-create/power-bi-template-app-production.png)

Hvis du vil gøre dit program tilgængeligt for tusindvis af Power BI-brugere i hele verden, opfordrer vi dig til at sende det til AppSource. Du kan se yderligere oplysninger under [Power BI-programtilbud](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).

## <a name="update-your-app"></a>Opret dit program

Nu, hvor programmet er i produktion, kan du starte forfra i testfasen uden at afbryde programmet i produktion.

1. I ruden **Udgivelsesadministration** skal du vælge **Opret program**.
2. Gå tilbage gennem oprettelsesprocessen for programmet.
3. Når du har angivet **Branding**, **Indhold**, **Kontrolelement** og **Adgang**, skal du igen vælge **Opret program**.
4. Vælg **Luk**, og gå tilbage til **Udgivelsesadministration**.

   Du kan nu se, at du har to versioner: Versionen i produktion samt en ny version i test.

    ![To versioner af et skabelonprogram](media/service-template-apps-create/power-bi-template-app-2-versions.png)

5. Når du er klar til at markedsføre din app til præ-produktions til yderligere test uden for din lejer, skal du gå tilbage til ruden Release Management, og vælg **Hæv app** ud for **Testing**.
6. Link til dit er nu live og sende den igen til Cloud Partner Portal ved at følge trinnene i [Power BI-App tilbud opdatering](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-update-existing-offer).

>[!NOTE]
>Markedsfør din app til produktion fase, når din app er godkendt af Cloud Partner-portalen, og du har udgivet den.

## <a name="next-steps"></a>Næste trin

Se, hvordan dine kunder kan interagere med dit skabelonprogram under [Installér, tilpas og distribuer skabelonprogrammer i din organisation](service-template-apps-install-distribute.md).

Du kan se yderligere oplysninger om, hvordan du distribuerer dit program under [Power BI-programtilbud](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).
