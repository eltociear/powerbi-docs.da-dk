---
title: Udarbejd skabelonprogrammer i Power BI (prøveversion)
description: Sådan opretter du skabelonprogrammer i Power BI, som du kan distribuere til Power BI-kunder.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: c08b7e60777b720aa4fc2489b02c212bdd3e7169
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249571"
---
# <a name="create-a-template-app-in-power-bi-preview"></a>Opret et skabelonprogram i Power BI (prøveversion)

Med de nye Power BI-*skabelonprogrammer* kan Power BI-partnere udarbejde programmer i Power BI med kun lidt eller ingen kode og udrulle dem til Power BI-kunder.  Denne artikel indeholder en trinvis vejledning til at oprette et Power BI-skabelonprogram. 

Hvis du kan oprette Power BI-rapporter og dashboards, kan du blive *udvikler af skabelonprogrammer*, som udarbejder og pakker analytisk indhold i et *program*. Du kan derefter udrulle dit program til andre Power BI-lejere via alle tilgængelige platforme, f.eks. AppSource, eller ved at bruge den i din egen webtjeneste. Som udvikler kan du oprette en beskyttet analysepakke, som du kan distribuere. 

Administratorer af Power BI-lejere styrer, hvem der kan oprette skabelonprogrammer i organisationen, og hvem der kan installere dem. Dem, der er godkendt, kan installere dit skabelonprogram og derefter redigere det og distribuere det til Power BI-brugerne i deres organisation.

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
 
    ![Opret programarbejdsområde](media/service-template-apps-create/power-bi-new-workspace.png)

3. Under **Opret et programarbejdsområde**, under **Se eksempel på forbedrede arbejdsområder** skal du vælge **Prøv nu**.

    ![Prøv nye arbejdsområder](media/service-template-apps-create/power-bi-try-now-new-workspace.png)

5. Angiv et navn, en beskrivelse (valgfrit) og et logobillede (valgfrit) for dit programarbejdsområde.

4. Vælg **Udvikl et skabelonprogram**.

    ![Udvikl et skabelonprogram](media/service-template-apps-create/power-bi-template-app-develop.png)

5. Vælg **Gem**.

## <a name="create-the-content-in-your-template-app"></a>Opret indhold i dit skabelonprogram

Som med et almindeligt Power BI-programarbejdsområde er dit næste skridt at oprette indholdet i arbejdsområdet.  I denne prøveversion af skabelonprogrammer understøtter vi kun op til én af hver type: ét datasæt, én rapport og ét dashboard.

- [Opret dit Power BI-indhold](power-bi-creator-landing.md) i dit programarbejdsområde.

Hvis du bruger parametre i Power-forespørgsel, skal du kontrollere, at de har veldefinerede typer (f.eks. Text). Typerne Any og Binary understøttes ikke. 

[Tip til udarbejdelse af skabelonprogrammer i Power BI (prøveversion)](service-template-apps-tips.md) indeholder forslag, der er værd at overveje, når du opretter rapporter og dashboards til dit skabelonprogram.

## <a name="create-the-test-template-app"></a>Opret testskabelonprogrammet

Nu, hvor du har indhold i dit arbejdsområde, er du klar til at pakke det i et skabelonprogram. Det første trin er at oprette et testskabelonprogram, som kun er tilgængeligt i din organisation på din lejer.

1. Vælg **Opret program** i arbejdsområdet for skabelonprogrammet. 

    ![Opret program](media/service-template-apps-create/power-bi-create-app.png)
 
    Her udfylder du yderligere parametre i fire kategorier for dit skabelonprogram. 

    **Branding**

    - Appnavn 
    - Beskrivelse
    - Programlogo (valgfrit)
    - Programfarve 

    **Indhold** 

    - Programlandingsside (valgfrit): Angiv en rapport eller et dashboard som landingsside for dit program.  
    
    **Kontrolelement** 

    Styr flere begrænsninger eller restriktioner, som brugerne af dit program vil have, for indholdet af dit program. Du kan bruge dette kontrolelement til at beskytte visse immaterielle rettigheder, som dit program kan indeholde.

    **Adgang**

    - I testfasen kan du bestemme, hvem i din organisation der kan installere og teste dit program.

    Bare rolig, du kan altid vende tilbage og ændre disse indstillinger senere.  

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

Lad os gennemgå faserne.

1. Vælg **Udgivelsesadministration** i arbejdsområdet for skabelonprogrammet.

    ![Ikon for Udgivelsesadministration](media/service-template-apps-create/power-bi-release-management-icon.png)

2. Vælg **Opret program**. 

    Hvis du oprettede testprogrammet under trinnet **Opret testskabelonprogrammet** ovenfor, er den gule prik ud for **Test** allerede udfyldt, og du behøver ikke at vælge **Opret program** her. Hvis du vælger den, vender du tilbage til processen til oprettelse af skabelonprogrammer.
 
3. Vælg **Få link**.

    ![Opret program, få link](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)
 
9. Du tester oplevelsen af programinstallationen ved at kopiere linket i meddelelsesvinduet og indsætte det i et nyt browservindue. 

    Herfra følger du den samme fremgangsmåde som dine kunder. Se [Installér og distribuer skabelonprogrammer i din organisation](service-template-apps-install-distribute.md) for at se deres version.
 
10. Vælg **Installér** i dialogboksen.

    Når installationen er fuldført, får du vist en meddelelse om, at det nye program er klar. 
 
11. Vælg **Gå til program**.
 
12. Under **Kom i gang med dit nye program** kan du se programmet, som dine kunder vil se det. 

    ![Kom i gang med dit program](media/service-template-apps-create/power-bi-template-app-get-started.png)

13. Vælg **Udforsk program** for at bekræfte testprogrammet sammen med eksempeldataene.

1. Hvis du vil foretage ændringer, skal du vende tilbage til programmet i det oprindelige arbejdsområde. Opdater testprogrammet, indtil du er tilfreds.

9. Når du er klar til at hæve dit program til præproduktion med henblik på yderligere test uden for din lejer, skal du gå tilbage til ruden **Udgivelsesadministration** og vælge **Hæv program** ud for **Test**.
 
    ![Hæv programmet til præproduktion](media/service-template-apps-create/power-bi-template-app-promote.png)

11. Vælg **Hæv** for at bekræfte dit valg. 

12. Kopiér denne nye URL-adresse for at dele den uden for din lejer med henblik på test. Dette link er også det, du sender for at begynde processen med at distribuere dit program på AppSource.

12. Når programmet er klar til produktion eller deling via AppSource, skal du gå tilbage til ruden **Udgivelsesadministration** og vælge **Hæv program** ud for **Præproduktion**.
 
11. Vælg **Hæv** for at bekræfte dit valg. 

    Programmet er nu i produktion og klar til distribution.

    ![Program i produktion](media/service-template-apps-create/power-bi-template-app-production.png)

Hvis du vil gøre dit program tilgængeligt for tusindvis af Power BI-brugere i hele verden, opfordrer vi dig til at sende det til AppSource. Du kan se yderligere oplysninger under [Power BI-programtilbud](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer). 

## <a name="update-your-app"></a>Opret dit program

Nu, hvor programmet er i produktion, kan du starte forfra i testfasen uden at afbryde programmet i produktion. 

1. I ruden **Udgivelsesadministration** skal du vælge **Opret program**.

1. Gå tilbage gennem oprettelsesprocessen for programmet. 
2. Når du har angivet **Branding**, **Indhold**, **Kontrolelement** og **Adgang**, skal du igen vælge **Opret program**.
3. Vælg **Luk**, og gå tilbage til **Udgivelsesadministration**. 

    Du kan nu se, at du har to versioner: Versionen i produktion samt en ny version i test. 

    ![To versioner af et skabelonprogram](media/service-template-apps-create/power-bi-template-app-2-versions.png)

## <a name="next-steps"></a>Næste trin

Se, hvordan dine kunder kan interagere med dit skabelonprogram under [Installér, tilpas og distribuer skabelonprogrammer i din organisation](service-template-apps-install-distribute.md).

Du kan se yderligere oplysninger om, hvordan du distribuerer dit program under [Power BI-programtilbud](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).





