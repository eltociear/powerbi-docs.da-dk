---
title: Brugerdefinerede visualiseringer i Power BI
description: Brugerdefinerede visualiseringer i Power BI
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 3fd2f3e47c9b6dd2144ed5a66d45e65a00c5b92e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051248"
---
# <a name="custom-visuals-in-power-bi"></a>Brugerdefinerede visualiseringer i Power BI

Når du opretter eller redigerer en Power BI-rapport, kan du bruge mange forskellige typer visualiseringer. Ikonerne for disse visualiseringer vises i den **visualiseringer** rude. Disse visualiseringer kommer færdigpakkede, når du downloader [Power BI Desktop](https://powerbi.microsoft.com/desktop/) eller åbne den [Power BI-tjenesten](https://app.powerbi.com).

![visualiseringer](media/power-bi-custom-visuals/power-bi-visualizations.png)

Men du ikke er begrænset til dette sæt visualiseringer. Hvis du vælger ellipsen (...) i bunden, en anden kilde af rapportvisualiseringer bliver tilgængelig –*brugerdefinerede visualiseringer*.

Udviklere oprette brugerdefinerede visuelle elementer ved hjælp af SDK'ET til brugerdefinerede visualiseringer. Disse visualiseringer virksomhedsbrugere kan se sine data på en måde, som passer bedst til deres forretning. Forfattere kan derefter importere de brugerdefinerede visualiseringsfiler til deres rapporter og bruge dem efter de ville alle andre visualiseringer i Power BI. Brugerdefinerede visualiseringer er førsteklasses borgerne i Power BI og kan filtreres, fremhæves, redigerede, delt og osv.

Brugerdefinerede visuelle elementer er installeret på tre måder:

* Brugerdefinerede visualiseringsfiler
* Visualiseringer til organisationen
* Visualiseringer på markedspladser

## <a name="custom-visual-files"></a>Brugerdefinerede visualiseringsfiler

Brugerdefinerede visualiseringer er pakker, der indeholder kode til at gengive fodres data. Alle kan oprette en brugerdefineret visualisering og pakke den som en enkelt `.pbiviz` -fil, som derefter kan importeres til en Power BI-rapport.

> [!WARNING]
> En brugerdefineret visualisering kan indeholde kode med sikkerhed eller beskyttelse af personlige oplysninger risici. Kontrollér, at du har tillid til forfatteren og kilden for brugerdefinerede visuelle før du importerer den til din rapport.

## <a name="organizational-visuals"></a>Visualiseringer til organisationen

Power BI-administratorer Godkend og udrulle brugerdefinerede visualiseringer i deres organisation, som forfattere kan nemt finde, opdatere og bruge. Administratorer kan nemt administrere (f.eks, opdatere version, deaktivere/aktivere) disse visualiseringer.

 [Læs mere om visualiseringer](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Visualiseringer på markedspladser

Medlemmer af community'et og Microsoft har bidraget deres brugerdefinerede visualiseringer til offentlig fordel og udgivet dem på den [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) marketplace. Du kan hente disse visualiseringer føje dem til Power BI-rapporter. Microsoft har testet og godkendt disse brugerdefinerede visualiseringer for funktionalitet og kvalitet.

Hvad er [AppSource](developer/office-store.md)? Det er det sted, hvor du kan finde apps, tilføjelsesprogrammer og udvidelser til din Microsoft-software. [AppSource](https://appsource.microsoft.com/) forbinder millioner af brugere af produkter som Office 365, Azure, Dynamics 365, Cortana og Power BI med løsninger, der hjælper dem med at arbejde mere effektivt, indsigt, og elegant måde end før.

### <a name="certified-visuals"></a>Certificerede visualiseringer

Certificerede Powerbi-visualiseringer er markedspladser, der har bestået yderligere strenge kvalitet tests og understøttes i yderligere scenarier, f.eks [mailabonnementer](https://docs.microsoft.com/power-bi/service-report-subscribe), og [Eksportér til PowerPoint](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
Hvis du vil have vist en liste over certificerede brugerdefinerede visualiseringer eller indsende dine egne, skal du se under [Certificerede brugerdefinerede visualiseringer](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified).

Er du webudvikler og interesseret i at oprette dine egne visualiseringer og føje dem til AppSource? Se [udvikle en brugerdefineret visualisering i Power BI](developer/custom-visual-develop-tutorial.md) og Lær, hvordan du [Publicer brugerdefinerede visuals til AppSource](https://docs.microsoft.com/power-bi/developer/office-store).

### <a name="import-a-custom-visual-from-a-file"></a>Importér en brugerdefineret visualisering fra en fil

1. Vælg ellipsen i bunden af den **visualiseringer** rude.

    ![visualiseringer2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Vælg **Importér fra fil** på rullelisten.

    ![importér fra fil](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Menuen Åbn fil, skal du vælge den `.pbiviz` fil, du vil importere, og vælg derefter **åben**. Ikon for den brugerdefinerede visualisering tilføjes nederst i din **visualiseringer** ruden og er nu tilgængelig til brug i din rapport.

    ![Importeret fra cv](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Importér visualiseringer til organisationen

1. Vælg ellipsen i bunden af den **visualiseringer** rude.

    ![Visualisering org 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Vælg **Importér fra markedsplads** på rullelisten.

    ![Visualisering org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Vælg **MIN ORGANISATION** i øverste fanemenu.

    ![Visualisering org 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. Rul gennem listen for at finde den visualisering, du vil importere.

    ![Visualisering org 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Vælg **Tilføj** til at importere den brugerdefinerede visualisering. Dets ikon, der føjes til bunden af din **visualiseringer** ruden og er nu tilgængelig til brug i din rapport.

    ![Visualisering org 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Download eller importér brugerdefinerede visualiseringer fra Microsoft AppSource

Har du to valgmuligheder for Download og import af brugerdefinerede visualiseringer: fra Power BI og fra den [AppSource-webstedet](https://appsource.microsoft.com/).

### <a name="import-custom-visuals-from-within-power-bi"></a>Importér brugerdefinerede visualiseringer fra Power BI

1. Vælg ellipsen i bunden af den **visualiseringer** rude.

    ![visualiseringer 2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Vælg **Importér fra markedsplads** på rullelisten.

    ![Visualisering org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Rul gennem listen for at finde den visualisering, du vil importere.

    ![importér visualisering](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Du kan få mere at vide om en af visualiseringerne, hvis du fremhæver og vælger den.

    ![Markér](media/power-bi-custom-visuals/power-bi-select.png)

5. På siden med oplysninger kan du se skærmbilleder, videoer, en detaljeret beskrivelse med mere.

    ![Synoptic](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. Rul ned til bunden for at se anmeldelser.

    ![Anmeldelser](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Vælg **Tilføj** til at importere den brugerdefinerede visualisering. Dets ikon, der føjes til bunden af din **visualiseringer** ruden og er nu tilgængelig til brug i din rapport.

    ![visualisering er importeret](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Download og importér brugerdefinerede visualiseringer fra Microsoft AppSource

1. Start med [Microsoft AppSource](https://appsource.microsoft.com), og vælg fanen for **Apps**.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Gå til [siden med appresultater](https://appsource.microsoft.com/marketplace/apps), hvor du kan få vist de mest populære apps i hver kategori, herunder *Power BI-apps*. Vi er på udkig efter brugerdefinerede visualiseringer, så lad os vælge **Power BI-visualiseringer** fra venstre navigationsrude listen for at begrænse resultaterne.

    ![AppSource-visualiseringer](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource viser et felt for hver brugerdefinerede visualisering.  Hvert felt har et brugerdefineret visual snapshot med en kort beskrivelse og et downloadlink. Vælg feltet for at få vist flere detaljer.

    ![Valgt brugerdefineret visualisering](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. På siden med oplysninger kan du se skærmbilleder, videoer, en detaljeret beskrivelse med mere. Vælg **Hent det nu** til at downloade den brugerdefinerede visualisering og derefter acceptere vilkårene for anvendelse.

    ![Hent AppSource](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Vælg linket for at downloade den brugerdefinerede visualisering.

    ![Download](media/power-bi-custom-visuals/powerbi-custom-download.png)

    Downloadsiden indeholder også instruktioner om, hvordan du importerer den brugerdefinerede visualisering til Power BI Desktop og Power BI-tjenesten.

    Du kan også downloade et eksempel på en rapport, der indeholder den brugerdefinerede visual og viser dets egenskaber.

    ![Eksempel](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Gem den `.pbiviz` filen, og Åbn derefter Power BI.

7. Import af `.pbiviz` filen til din rapport. Se afsnittet [Importér en brugerdefineret visualisering fra en fil](#import-a-custom-visual-from-a-file) ovenfor.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* En brugerdefineret visualisering føjes til en bestemt rapport, når den importeres. Hvis du vil bruge visualiseringen i en anden rapport, skal du også importere den i denne rapport. Når du gemmer en rapport med en brugerdefineret visualisering vha. indstillingen **Gem som**, gemmes der en kopi af den brugerdefinerede visualisering sammen med den nye rapport.

* Hvis du ikke ser en **visualiseringer** rude, der betyder, at du ikke har en rapport, redigere tilladelser.  Du kan kun tilføje brugerdefinerede visualiseringer til rapporter, som du kan redigere, og ikke til rapporter, der er blevet delt med dig.

## <a name="troubleshoot"></a>Fejlfind

Du kan foretage fejlfinding, se [fejlfinding i forbindelse med dine egne brugerdefinerede visuals i Power BI](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger og få svar på spørgsmål under [Ofte stillede spørgsmål om brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals).

## <a name="next-steps"></a>Næste trin

* [Visualiseringer i Power BI-rapporter](visuals/power-bi-report-visualizations.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).
