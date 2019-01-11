---
title: Brug R-drevne brugerdefinerede visualiseringer i Power BI
description: Brug R-drevne brugerdefinerede visualiseringer i Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 07/27/2018
LocalizationGroup: Create reports
ms.openlocfilehash: 7bf7b5ae6fc68977d98660f69a02e38c6a8750d2
ms.sourcegitcommit: c09241803664643e1b2ba0c150e525e1262ca466
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/08/2019
ms.locfileid: "54072192"
---
# <a name="use-r-powered-custom-visuals-in-power-bi"></a>Brug R-drevne brugerdefinerede visualiseringer i Power BI

I **Power BI Desktop** og **Power BI-tjenesten** kan du bruge R-drevne brugerdefinerede visualiseringer uden at have kendskab til R og uden et R-script. Det giver dig mulighed for at udnytte den analytiske og visuelle kraft i R-visualiseringer og R-scripts uden at skulle lære R eller programmere.

Hvis du vil bruge R-drevne, brugerdefinerede visualiseringer, vælger og downloader du først den brugerdefinerede R-visualisering, som du ønsker at bruge, fra galleriet [ **AppSource** ](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1) med **brugerdefinerede visualiseringer** til Power BI.

![R-visualisering 1a](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_1a.png)

I de følgende afsnit beskrives det, hvordan du vælger, indlæser og bruger R-drevne visualiseringer i **Power BI Desktop**.

## <a name="use-r-custom-visuals"></a>Brug brugerdefinerede R-visualiseringer

Hvis du vil bruge brugerdefinerede R-drevne visualiseringer, skal du downloade hver enkelt visualisering fra biblioteket med **brugerdefinerede visualiseringer** og derefter bruge den pågældende visualisering som enhver anden type visualisering i **Power BI Desktop**. Der er to måder, hvorpå du kan få brugerdefinerede visualiseringer – du kan downloade dem fra webstedet **AppSource**, eller du kan søge i og få dem inde fra **Power BI Desktop**. 

### <a name="get-custom-visuals-from-appsource"></a>Hent brugerdefinerede visualiseringer fra AppSource

Her er den fremgangsmåde, du skal benytte for at gennemse og vælge visualiseringer på webstedet **AppSource**:

1. Gå til biblioteket med visualiseringer i Power BI, som du finder på [https://appsource.microsoft.com](https://appsource.microsoft.com/). Markér afkrydsningsfeltet *Power BI apps* under *Afgræns efter produkt*, og vælg derefter linket **Se alle**.

   ![R-visualisering 2a](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2a.png)

2. Vælg [Brugerdefinerede visualiseringer i Power BI](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1) på bibliotekssiden **Brugerdefinerede visualiseringer i Power BI** på listen over tilføjelsesprogrammer i venstre rude.

   ![R-visualisering 2b](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2b.png)

3. Vælg den **visualisering**, som du er interesseret i at bruge, fra galleriet. Derefter sendes du videre til en side, som beskriver visualiseringen. Tryk på knappen **Hent det nu** for at downloade.

   > [!NOTE]
    > For at kunne redigere i **Power BI Desktop** skal du have R installeret på din lokale computer. Men når brugere vil have vist en R-drevet visualisering i **Power BI-tjenesten**, behøver de ikke at have R installeret lokalt.

   ![R-visualisering 3a](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_3a.png)

   Du behøver ikke at installere R for at bruge R-drevne, brugerdefinerede visualiseringer i **Power BI-tjenesten**, men hvis du vil bruge R-drevne, brugerdefinerede visualiseringer i **Power BI Desktop**, *skal* du installere R på den lokale computer. Du kan downloade R fra følgende steder:

   * [CRAN](https://cran.r-project.org/)
   * [MRO](https://mran.microsoft.com/)

4. Når den pågældende visualisering er downloadet (hvilket svarer til at downloade enhver anden fil via din browser), skal du gå til **Power BI Desktop** og klikke på ellipsen (...) i ruden **Visualiseringer** og vælge **Importér fra fil**.

   ![R-visualisering 4a](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4a.png)
5. Du bliver advaret om at importere en brugerdefineret visualisering, som vist på følgende billede:

   ![R-visualisering 5](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_5.png)
6. Gå til den placering, hvor visualiseringsfilen blev gemt, og vælg derefter filen. Brugerdefinerede visualiseringer i **Power BI Desktop** har filtypenavnet .pbiviz.

   ![R-visualisering 6](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_6.png)
7. Når du går tilbage til Power BI Desktop, kan du se den nye visualiseringstype i ruden **Visualiseringer**.

   ![R-visualisering 7](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_7.png)
8. Når du importerer den nye visualisering (eller åbner en rapport, der indeholder en R-drevet brugerdefineret visualisering), installerer **Power BI Desktop** de påkrævede R-pakker.

   ![R-visualisering 8](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_8.png)

9. Herfra kan du føje data til visualiseringen på samme måde som med andre **Power BI Desktop**-visualiseringer. Når du er færdig, kan du se dine afsluttede visualiseringer på lærredet. I følgende visualisering blev den R-drevne visualisering **Prognose** brugt sammen med Forenede Nationers (FN) forudsigelser af fødselshyppighed (visualiseringen til venstre).

    ![R-visualisering 10](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_10.png)

    Som enhver anden **Power BI Desktop**-visualisering kan du udgive denne rapport med dens R-drevne visualisering i **Power BI-tjenesten** og dele den med andre.

    Besøg biblioteket ofte, da der tilføjes nye visualiseringer hele tiden.

### <a name="get-custom-visuals-from-within-power-bi-desktop"></a>Importér brugerdefinerede visualiseringer fra **Power BI Desktop**

1. Du kan også importere brugerdefinerede visualiseringer fra **Power BI Desktop**. I **Power BI Desktop** skal du klikke på ellipsen (...) i ruden **Visualiseringer** og vælge **Importér fra Marketplace**.

   ![R-visualisering 4a](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4a.png)

2. Når du gør det, åbnes dialogboksen **Brugerdefinerede visualiseringer i Power BI**, hvor du kan rulle gennem de brugerdefinerede visualiseringer, som er til rådighed, og vælge det, du kan lide. Du kan søge efter navn, vælge en kategori eller blot rulle gennem de tilgængelige visualiseringer. Når du er klar, skal du blot vælge **Tilføj** for at føje den brugerdefineredevisualisering til **Power BI Desktop**.

   ![R-visualisering 12](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_12.png)

## <a name="contribute-r-powered-custom-visuals"></a>Bidrag med R-drevne brugerdefinerede visualiseringer

Hvis du opretter dine egne R-visualiseringer til brug i dine rapporter, kan du dele dem globalt ved at bidrage med dine brugerdefinerede visualiseringer i **galleriet med brugerdefinerede visualiseringer**. Bidrag er oprettet via GitHub, og processen er beskrevet på følgende placering:

* [Bidrag til galleriet med R-drevne, brugerdefinerede visualiseringer](https://github.com/Microsoft/PowerBI-visuals#building-r-powered-custom-visual-corrplot)

## <a name="troubleshoot-r-powered-custom-visuals"></a>Fejlfinding i R-drevne brugerdefinerede visualiseringer

R-drevne brugerdefineredevisualiseringer har visse afhængigheder, der skal opfyldes, før visualiseringerne fungerer korrekt. Når R-drevne brugerdefinerede visualiseringer ikke kører eller indlæses korrekt, er problemet normalt et af følgende:

* Programmet R mangler
* Fejl i R-scriptet, som visualiseringen er baseret på
* R-pakker mangler eller er forældede

I følgende afsnit beskrives de fejlfindingstrin, som du kan gennemgå for at afhjælpe de problemer, der måtte opstå.

### <a name="missing-or-outdated-r-packages"></a>Manglende eller forældede R-pakker

Når du forsøger at installere en R-drevet visualisering, kan der opstå fejl, når der er manglende eller forældede R-pakker. Årsagen er normalt en af følgende:

* R-installationen er ikke kompatibel med R-pakken
* Firewallen, antivirussoftwaren eller proxyindstillingerne forhindrer R i at oprette forbindelse til internettet
* Internetforbindelsen er langsom, eller der er et problem med internetforbindelsen

Power BI-teamet arbejder aktivt på at mindske disse problemer, før de opstår hos dig, og den næste Power BI Desktop omfatter opdateringer, der har til formål at løse disse problemer. Indtil da kan du prøve en af de følgende løsninger for at afhjælpe problemerne:

1. Fjern den brugerdefinerede visualisering, og installér den derefter igen. Dette starter en ny installation af R-pakkerne.
2. Hvis installationen af R ikke er aktuel, skal du opgradere R-installationen og derefter fjerne/geninstallere den brugerdefinerede visualisering, som beskrevet under forrige trin.

   Understøttede R-versioner er angivet i beskrivelsen af hver R-drevne brugerdefinerede visualisering, som vist på følgende billede.

     ![R-visualisering 11](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_11.png)
    > [!NOTE]
    > Du kan beholde den oprindelige R-installation og kun knytte Power BI Desktop til den aktuelle version, som du installerer. Gå til **Fil > Indstillinger > Indstillinger > R scripting**.

3. Installer R-pakker manuelt vha. en R-konsol. Fremgangsmåden er følgende:

   a.  Download installationsscriptet for den R-drevne visualisering, og gem filen på et lokalt drev.

   b.  Fra R-konsollen skal du køre følgende:

       source(“C:/Users/david/Downloads/ScriptInstallPackagesForForecastWithWorkarounds.R”)

   Typiske standardinstallationsplaceringer er følgende:

       c:\Program Files\R\R-3.3.x\bin\x64\Rterm.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\x64\Rgui.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\R.exe (for CRAN-R)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\R.exe (for MRO)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\x64\Rgui.exe (for MRO)
       c:\Program Files\RStudio\bin\rstudio.exe (for RStudio)
4. Hvis de foregående trin ikke fungerer, kan du prøve følgende:

   a. Brug **R Studio**, og følg de trin, der er beskrevet i 3.b. ovenfor (kør scriptlinjen fra R-konsollen).

   b. Hvis det forrige trin ikke virker, kan du ændre **Værktøjer > Globale indstillinger > Pakker** i **R Studio**, markere afkrydsningsfeltet for **Brug Internet Explorer bibliotek/proxy for HTTP** og derefter gentage trin 3.b. fra trinnene ovenfor.

## <a name="next-steps"></a>De næste trin

Du kan finde yderligere oplysninger om R i Power BI i følgende artikler.

* [Galleri med brugerdefinerede, Power BI-visualiseringer](https://app.powerbi.com/visuals/)
* [Kørsel af R-scripts i Power BI Desktop](desktop-r-scripts.md)
* [Opret R-visualiseringer i Power BI Desktop](desktop-r-visuals.md)
* [Brug en ekstern R-IDE med Power BI](desktop-r-ide.md)
